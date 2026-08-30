<h1 align="center">Knave FSM</h1>

<p align="center">
  <b>States are assets. The graph is a table. Nothing else knows about anything.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Unity-2021.3+-000000?style=for-the-badge&logo=unity" />
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white" />
  <img src="https://img.shields.io/badge/deps-none-2ea44f?style=for-the-badge" />
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" />
</p>

---

Most Unity FSMs rot the same way: `IdleState` checks input and calls `ChangeState(Walk)`. Six exits
later you're editing a file that has nothing to do with the feature you're adding.

Here a state only knows **how to run**. Every "what comes next" lives in one method:

```csharp
yield return new Transition<PlayerControllerMachine, ControllerStates>(
    "Walk → Sprint", ControllerStates.Walk, ControllerStates.Sprinting,
    ctx => ctx.InputData.running && ctx.InputData.InputVector.sqrMagnitude > 0.1f,
    priority: 2);
```

Read that method, you've read the character.

## What you get

- **Generic over context + tag:** states receive your concrete controller. No casts, no `GetComponent`.
- **ScriptableObject states:** authored as assets, instanced per machine. No shared mutable state.
- **Priorities:** dodge `4` beats sprint `2` beats walk `1` when both fire the same frame.
- **Cooldowns:** per transition, no timer field on the state.
- **Any-state edges:** `From: None` applies everywhere.
- **Zero per-frame allocation:** the table sorts once in its constructor; `Update` is an array walk.

## Three steps

```csharp
// 1. Tags. None must be first; it means "any state".
public enum ControllerStates { None, Idle, Walk, Sprinting, Dodge }

// 2. A state. Override only what you need.
[CreateAssetMenu(menuName = "Knave/States/Idle")]
public class IdleState : BaseState<PlayerControllerMachine, ControllerStates>
{
    public override ControllerStates Tag => ControllerStates.Idle;
    public override void EnterState() => Context.Animator.SetBool("isIdle", true);
}

// 3. The graph.
protected override IEnumerable<ITransition<PlayerControllerMachine, ControllerStates>>
    CreateTransitions()
{
    yield return new Transition<PlayerControllerMachine, ControllerStates>(
        "Any → Dodge", ControllerStates.None, ControllerStates.Dodge,
        ctx => ctx.InputData.ConsumeRoll(), priority: 4, cooldown: 0.6f);
}
```

Drop the state assets into `stateAssets`, pick `initialTag`, done.

Sharing an exit across states? Loop a group instead of copy-pasting:

```csharp
foreach (var from in PlayerStateGroups.DodgeFromStates)
    yield return new Transition<...>($"{from} → Dodge", from, ControllerStates.Dodge, ...);
```

## Layout

`Core/` · `StateSystem/` · `Transitions/` are the reusable engine, with no external deps.
`Machines/PlayerControllerMachine.cs` is a worked example (locomotion + aim + dodge) and does pull in
Animation Rigging.

## License

MIT
