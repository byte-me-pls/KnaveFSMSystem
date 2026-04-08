# 🔗 Konu 5: Kısmi İntegrasyon (Parçalı İntegrasyon)

> **Ne zaman kullanırız?** İki farklı türden fonksiyon **çarpılmış** haldeyse:
> `x · eˣ`,  `x · cosx`,  `x² · lnx`,  `lnx`,  `arctanx` gibi

---

## 🔑 FORMÜL

Türev çarpım kuralından türetilir:

```
d(u·v) = u·dv + v·du
∫d(u·v) = ∫u·dv + ∫v·du
u·v = ∫u·dv + ∫v·du

→ ∫u·dv = u·v − ∫v·du
```

> **Tek cümle:** `∫u dv = uv − ∫v du`

---

## 🧠 LAPTÜ KURALI — u'yu ne seçeceğiz?

Notunda da var: **L A P T Ü** sırasına göre u seç, geri kalan dv olur.

```
L → Logaritma   (lnx, log...)
A → Arcus       (arcsinx, arctanx...)
P → Polinom     (x, x², x³...)
T → Trigonometri (sinx, cosx...)
Ü → Üstel       (eˣ, aˣ...)
```

> **Kural:** Listede önce gelenini **u** yap, diğerini **dv** yap.

**Örnek seçimler:**
```
∫ x · eˣ dx     → u = x (P),    dv = eˣ dx (Ü)
∫ x² · lnx dx  → u = lnx (L),  dv = x² dx (P)
∫ x · cosx dx  → u = x (P),    dv = cosx dx (T)
∫ lnx dx       → u = lnx (L),  dv = 1 dx (P → 1 sayılır)
∫ arctanx dx   → u = arctanx (A), dv = 1 dx
```

---

## 📋 UYGULAMA ADIMLARI

```
1. u ve dv'yi belirle (LAPTÜ ile)
2. du'yu hesapla  (u'nun türevi · dx)
3. v'yi hesapla   (dv'nin integrali)
4. Formüle koy:  ∫u dv = u·v − ∫v·du
5. Kalan integrali hesapla
```

---

## ✏️ ÖRNEK 1: x · eˣ
```
∫ x · eˣ dx

u = x        dv = eˣ dx
du = dx       v = eˣ

= x · eˣ − ∫ eˣ dx
= x · eˣ − eˣ + C
= eˣ(x − 1) + C
```

---

## ✏️ ÖRNEK 2: x² · lnx
```
∫ x² · lnx dx

u = lnx       dv = x² dx
du = 1/x dx   v = x³/3

= x³/3 · lnx − ∫ x³/3 · 1/x dx
= x³/3 · lnx − ∫ x²/3 dx
= x³/3 · lnx − x³/9 + C
```

---

## ✏️ ÖRNEK 3: x · cosx
```
∫ x · cosx dx

u = x         dv = cosx dx
du = dx        v = sinx

= x · sinx − ∫ sinx dx
= x · sinx − (−cosx) + C
= x · sinx + cosx + C
```

---

## ✏️ ÖRNEK 4: lnx tek başına
```
∫ lnx dx

u = lnx       dv = 1 dx   (yani dv = dx)
du = 1/x dx   v = x

= x · lnx − ∫ x · 1/x dx
= x · lnx − ∫ 1 dx
= x · lnx − x + C
```

> **Trick:** lnx tek başına gelince **dv = dx** yazıyoruz.

---

## ✏️ ÖRNEK 5: arctanx tek başına
```
∫ arctanx dx

u = arctanx       dv = dx
du = 1/(1+x²) dx  v = x

= x · arctanx − ∫ x/(1+x²) dx
```

**Kalan integral için değişken değiştirme:**
```
u₂ = 1+x²
du₂ = 2x dx  →  du₂/2 = x dx

∫ x/(1+x²) dx = ∫ du₂/2 / u₂ = 1/2 · ln|1+x²|
```

**Sonuç:**
```
= x · arctanx − 1/2 · ln|1+x²| + C
```

---

## ✏️ ÖRNEK 6: x · sec²x
```
∫ x · sec²x dx

u = x          dv = sec²x dx
du = dx         v = tanx

= x · tanx − ∫ tanx dx
```

**∫ tanx dx hesabı:**
```
∫ sinx/cosx dx

u₂ = cosx
du₂ = −sinx dx  →  −du₂ = sinx dx

= ∫ −du₂/u₂ = −ln|u₂| = −ln|cosx|
```

**Sonuç:**
```
= x · tanx − (−ln|cosx|) + C
= x · tanx + ln|cosx| + C
```

---

## 🧠 TANI TABLOSU

| Gördüğün yapı | u seç | dv seç |
|---------------|-------|--------|
| x · eˣ | x | eˣ dx |
| x² · lnx | lnx | x² dx |
| x · sinx veya cosx | x | sinx/cosx dx |
| lnx (tek başına) | lnx | dx |
| arctanx (tek başına) | arctanx | dx |
| x · sec²x | x | sec²x dx |

---

## 📝 SINAV CHECKLIST

1. ☐ LAPTÜ'ye bak → **u** hangisi?
2. ☐ Geri kalanı **dv** yap
3. ☐ **du** = u'nun türevi
4. ☐ **v** = dv'nin integrali
5. ☐ `∫u dv = uv − ∫v du` formülüne koy
6. ☐ Kalan integrali hesapla (bazen değişken değiştirme gerekir)

---

## 🏋️ PRATİK

### Soru 1
**∫ x · e²ˣ dx**

### Soru 2
**∫ lnx / x² dx**

*(İpucu: u = lnx, dv = x⁻² dx)*

### Soru 3
**∫ x · sinx dx**

> Çözmeyi dene, takılırsan "çözümü göster" de! 🚀
