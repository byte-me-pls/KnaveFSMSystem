# Knave FSM System

A finite state machine for Unity where **states are ScriptableObject assets** and **transitions are
declared in code as a table**, not wired into each state.

The point of the split: a state never knows what comes after it. It only knows how to run. Every
"when does this end and what follows" decision lives in one readable method per machine, so you can
read the whole control flow of a character without opening ten files.

## Why this shape

Most hand-rolled Unity FSMs put transition logic inside the state itself — `IdleState` checks input
and calls `ChangeState(Walk)`. That works until a state has six exits, and then adding a seventh
means editing a file that has nothing to do with the new behaviour.

Here, `PlayerControllerMachine.CreateTransitions()` yields the entire graph:

```csharp
yield return new Transition<PlayerControllerMachine, ControllerStates>(
    "Walk → Sprint", ControllerStates.Walk, ControllerStates.Sprinting,
    ctx => ctx.InputData.running && ctx.InputData.InputVector.sqrMagnitude > 0.1f,
    priority: 2);
```

States stay reusable. The graph stays reviewable in one place.

## Features

- **Generic over context and tag.** `KnaveMachineController<TContext, TTag>` is constrained so the
  state receives your concrete controller type — no casting, no `GetComponent` in hot paths.
- **ScriptableObject states.** Authored as assets, `Instantiate`d per machine at `Awake` so two
  characters never share mutable state.
- **Priority-ordered transitions.** Higher priority wins when several conditions are true in the
  same frame. Dodge (4) beats sprint (2) beats walk (1).
- **Per-transition cooldowns.** `Time.time < lastUsedTime + Cooldown` blocks re-entry without a
  timer field on the state.
- **Global (any-state) transitions.** A transition whose `From` is `default(TTag)` — i.e. `None` —
  applies from every state.
- **Flat pre-sorted lookup.** `TransitionTable` builds `Dictionary<TTag, ITransition[]>` once in the
  constructor and sorts by priority there, so per-frame evaluation is an array walk with no LINQ and
  no allocation.
- **Full Unity lifecycle.** `Update`, `FixedUpdate`, `LateUpdate`, plus `OnAnimationFinished()` for
  driving transitions off animation events.

## Layout

```text
Core/
  Enums.cs                     ControllerStates, CombatStates
  KnaveMachineController.cs    generic MonoBehaviour base, state cache, ChangeState
StateSystem/
  Interfaces/IState.cs         lifecycle contract
  Interfaces/ITransition.cs    From / To / CanUse / MarkUsed
  Abstracts/BaseState.cs       ScriptableObject base with virtual no-op lifecycle
Transitions/
  Transition.cs                condition + priority + cooldown + blocked flag
  TransitionTable.cs           pre-sorted per-state and global lookup
Machines/
  PlayerControllerMachine.cs   worked example: locomotion + aim + dodge
  PlayerStateGroups.cs         reusable sets of states for fan-in/fan-out transitions
Debug/
  KnaveMachineDebugger.cs      inspector view of the live state
```

## Usage

**1. Define your tags.**

```csharp
public enum ControllerStates { None, Idle, Walk, Sprinting, Dodge, Fall }
```

`None` must be the default (first) member — the table treats `default(TTag)` as "any state".

**2. Write a state.**

```csharp
[CreateAssetMenu(menuName = "Knave/States/Idle")]
public class IdleState : BaseState<PlayerControllerMachine, ControllerStates>
{
    public override ControllerStates Tag => ControllerStates.Idle;

    public override void EnterState() => Context.Animator.SetBool("isIdle", true);
    public override void ExitState()  => Context.Animator.SetBool("isIdle", false);
}
```

Only override what you need — `BaseState` provides empty virtuals for the rest.

**3. Write the machine.**

```csharp
public class PlayerControllerMachine
    : KnaveMachineController<PlayerControllerMachine, ControllerStates>
{
    protected override IEnumerable<ITransition<PlayerControllerMachine, ControllerStates>>
        CreateTransitions()
    {
        yield return new Transition<PlayerControllerMachine, ControllerStates>(
            "Idle → Walk", ControllerStates.Idle, ControllerStates.Walk,
            ctx => ctx.InputData.InputVector.magnitude > 0.1f, priority: 1);

        // any state → Dodge, with a cooldown so it cannot chain
        yield return new Transition<PlayerControllerMachine, ControllerStates>(
            "Any → Dodge", ControllerStates.None, ControllerStates.Dodge,
            ctx => ctx.InputData.ConsumeRoll(), priority: 4, cooldown: 0.6f);
    }
}
```

**4. Wire it in the inspector.** Drop the state assets into `stateAssets` and pick `initialTag`.

### Fan-in and fan-out

When several states share an exit, loop over a group instead of repeating yourself:

```csharp
foreach (var from in PlayerStateGroups.DodgeFromStates)
    yield return new Transition<PlayerControllerMachine, ControllerStates>(
        $"{from} → Dodge", from, ControllerStates.Dodge,
        ctx => ctx.InputData.ConsumeRoll(), priority: 4);
```

## Notes

- States are instantiated per controller, so instance fields on a state are safe. Anything you want
  shared belongs on the context.
- `Transition.IsBlocked` lets you disable an edge at construction time — useful for gating an
  ability behind progression without deleting the transition.
- The included `PlayerControllerMachine` depends on Unity's Animation Rigging package
  (`MultiAimConstraint`) and a project-local `InputData`/`MovementData`. It is a reference
  implementation — the `Core`, `StateSystem` and `Transitions` folders are the reusable part and
  have no such dependency.

## Requirements

Unity 2021.3 or newer. No external packages for the core system.

## License

MIT — see [LICENSE](LICENSE).
