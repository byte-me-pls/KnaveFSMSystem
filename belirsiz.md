# ∫ Konu 3: Belirsiz İntegral

> **Sınav Notu:** Bu konudan 2 tarz soru gelecek: **Temel Kural** ve **Değişken Değiştirme**

---

## 🔑 İntegral Nedir?

Türevin tersi. Türevde üssü azaltıyorduk, integralde **üssü artırıyoruz**.

```
Türev:   x⁴  →  4x³
İntegral:  x³ dx  →  x⁴/4 + C
```

> **C nedir?** Türev alınca kaybolan sabit sayı. Her belirsiz integrale **+ C** yazılır.

---

## 📋 TEMEL KURALLAR (Ezber!)

| İfade | İntegrali |
|-------|-----------|
| xⁿ dx | xⁿ⁺¹ / (n+1) + C |
| 1/x dx | ln\|x\| + C |
| eˣ dx | eˣ + C |
| sinx dx | −cosx + C |
| cosx dx | sinx + C |
| 1/(1+x²) dx | arctan x + C |
| 1/√(1−x²) dx | arcsin x + C |

> **xⁿ kuralı tek cümle:** Üssü 1 artır, başa böl.
> `x³ → x⁴/4`,  `x⁻² → x⁻¹/(-1) = -1/x`

---

## 📌 BÖLÜM 1: TEMEL ÖRNEKLER

### Örnek 1: Kök ve kesri üsse çevir
```
∫ 1/∜x³ dx

Adım 1: ∜x³ = x³/⁴  →  1/x³/⁴ = x⁻³/⁴

Adım 2: Kural → üssü 1 artır, başa böl
  ∫ x⁻³/⁴ dx = x⁻³/⁴ ⁺ ¹ / (-3/4 + 1)
             = x¹/⁴ / (1/4)
             = 4x¹/⁴ + C
             = 4∜x + C
```

### Örnek 2: Kesirli kök
```
∫ √x / ∛x dx

Adım 1: Kökleri üsse çevir
  √x = x¹/²     (karekök = 1/2 kuvveti)
  ∛x = x¹/³     (küpkök  = 1/3 kuvveti)

Adım 2: Aynı tabanlı bölme → üsler çıkarılır  (xᵃ / xᵇ = xᵃ⁻ᵇ)
  x¹/² / x¹/³ = x¹/²⁻¹/³

  Üs hesabı (paydaları eşitle):
  1/2 − 1/3 = 3/6 − 2/6 = 1/6

  → x¹/⁶

Adım 3: İntegral al (üssü 1 artır, başa böl)
  ∫ x¹/⁶ dx = x⁷/⁶ / (7/6) = 6/7 · x⁷/⁶ + C
```

### Örnek 3: Toplam/Fark olan integrallar
```
∫ 2x³ dx = 2 · x⁴/4 + C = x⁴/2 + C

∫ (3x² + 4x − 5) dx = 3·x³/3 + 4·x²/2 − 5x + C
                     = x³ + 2x² − 5x + C
```

### Örnek 4: Trigonometrik + üstel + ln
```
∫ (2cosx − 5sinx − 4eˣ + 3/x) dx

= 2sinx + 5cosx − 4eˣ + 3ln|x| + C
```

> **Dikkat:** sinx'in integrali **−cosx** (eksi var!), cosx'in integrali **+sinx**

### Örnek 5: Bölme işlemiyle sadeleştir
```
∫ (x³ − 4x² + 3x − 2) / x  dx

Her terimi x'e böl:
= ∫ (x² − 4x + 3 − 2/x) dx
= x³/3 − 4·x²/2 + 3x − 2ln|x| + C
= x³/3 − 2x² + 3x − 2ln|x| + C
```

---

## 📌 C SABİTİNİ BULMA (Sınava Gelebilir!)

### Örnek: İntegral verilmiş, f(2) sor
```
∫f(x)dx = x³ − 2x² + 5x − 4 ise  f(2) = ?
```

**Mantık:** İntegral = F(x) ise, f(x) = F'(x) (türevini al!)

```
f(x) = (x³ − 2x² + 5x − 4)' = 3x² − 4x + 5

f(2) = 3·4 − 4·2 + 5 = 12 − 8 + 5 = 9
```

---

### Örnek: f'(x) ve başlangıç koşulu verilmiş
```
f'(x) = 4x − 3,  f(1) = 5  →  f(0) = ?
```

```
f(x) = ∫(4x − 3)dx = 2x² − 3x + C

f(1) = 2 − 3 + C = 5
        C = 6

f(0) = 0 − 0 + 6 = 6
```

---

### Örnek: İki kez integre (f'' verilmiş)
```
f''(x) = 2,  f'(1) = 5,  f(1) = 7  →  f(2) = ?
```

**1. adım:** f''(x) → f'(x)
```
f'(x) = ∫2 dx = 2x + C₁

f'(1) = 2 + C₁ = 5  →  C₁ = 3
f'(x) = 2x + 3
```

**2. adım:** f'(x) → f(x)
```
f(x) = ∫(2x + 3) dx = x² + 3x + C₂

f(1) = 1 + 3 + C₂ = 7  →  C₂ = 3
f(x) = x² + 3x + 3
```

**Cevap:**
```
f(2) = 4 + 6 + 3 = 13
```

---

## 📌 BÖLÜM 2: DEĞİŞKEN DEĞİŞTİRME (u-yerine koyma)

### Ne zaman kullanırız?
İntegral içinde **bir ifade ve onun türevi** aynı anda varsa.

### Yöntem:
```
1. Karmaşık ifadeye u de
2. du/dx'i hesapla → du = ... dx yaz
3. dx'i du cinsinden yaz  
4. Her şeyi u ile yaz → basit integral
5. İntegrali al → u'yu geri koy
```

---

### ✏️ Örnek 1 (Temel)
### ✏️ Örnek 1 (Temel)
```
∫ (x² − 5x)⁷ · (2x − 5) dx
```

**Ne görüyoruz?**
- İçeride karmaşık bir ifade var: `x² − 5x`
- Bu ifade 7. kuvvete alınmış
- Yanında `(2x − 5)` çarpılmış

**Neden u koyuyoruz?**
Çünkü `(x² − 5x)` nin türevi `2x − 5` dir.
Yani parantez içindeki ifade ve türevi **aynı anda** var → u-değiştirme anı!

---

**Adım 1: u'yu belirle**
```
u = x² − 5x
```
(Kuvvet içindeki karmaşık ifadeyi u yaptık)

**Adım 2: du'yu hesapla**
```
du/dx = 2x − 5
du = (2x − 5) dx
```
`(2x − 5) dx` ifadesi zaten soruda var → doğrudan `du` yazabiliriz ✓

**Adım 3: Yerine koy**
```
∫ (x² − 5x)⁷ · (2x − 5) dx
       ↓              ↓
∫     u⁷          ·  du
```

**Adım 4: Basit integrali al**
```
∫ u⁷ du = u⁸/8 + C
```
(Temel kural: üssü 1 artır, başa böl)

**Adım 5: u'yu geri x ile yaz**
```
= (x² − 5x)⁸/8 + C
```



---

### ✏️ Örnek 2 (Kesirli — ln çıkar)
```
∫ (3x² − 8x) / (x³ − 4x²) dx

u = x³ − 4x²
du = (3x² − 8x) dx  ✓ (pay tam oluyor!)

= ∫ du/u = ln|u| + C = ln|x³ − 4x²| + C
```

> **Pay = du ise → sonuç ln|u| + C**

---

### ✏️ Örnek 3 (Üstel fonksiyon)
```
∫ eˢⁱⁿˣ · cosx dx

u = sinx
du = cosx dx  ✓

= ∫ eᵘ du = eᵘ + C = eˢⁱⁿˣ + C
```

---

### ✏️ Örnek 4 (du'yu uydurma)
```
∫ (x² − 6x)⁸ · (x − 3) dx

u = x² − 6x
du = (2x − 6) dx = 2(x−3) dx
du/2 = (x−3) dx  ← bunu yerine koy

= ∫ u⁸ · du/2 = 1/2 · u⁹/9 + C = u⁹/18 + C = (x²−6x)⁹/18 + C
```

---

### ✏️ Örnek 5 (Kök içinde)
```
∫ 5x² / √(x³+2) dx

u = x³ + 2
du = 3x² dx  →  du/3 = x² dx

= ∫ 5 · (du/3) / √u = 5/3 ∫ u^(-1/2) du
= 5/3 · u^(1/2)/(1/2) + C
= 10/3 · √(x³+2) + C
```

---

### ✏️ Örnek 6 (√x içeren)
```
∫ (3√x − 2)⁵ / √x dx

u = 3√x − 2
du = 3 · 1/(2√x) dx  →  2/3 · du = 1/√x dx

= ∫ u⁵ · 2/3 du = 2/3 · u⁶/6 + C = u⁶/9 + C = (3√x−2)⁶/9 + C
```

---

### ✏️ Örnek 7 (ln içinde)
```
∫ (4lnx − 3)⁶ / 3x dx

u = 4lnx − 3
du = 4/x dx  →  du/4 = 1/x dx

= ∫ u⁶ · 1/3 · du/4 = 1/12 ∫ u⁶ du = u⁷/84 + C = (4lnx−3)⁷/84 + C
```

---

### ✏️ Örnek 8 (x içeride kalıyor)
```
∫ (x−2)¹⁰ · x dx

u = x − 2  →  x = u + 2
du = dx

= ∫ u¹⁰ · (u+2) du = ∫ (u¹¹ + 2u¹⁰) du
= u¹²/12 + 2u¹¹/11 + C
= (x−2)¹²/12 + 2(x−2)¹¹/11 + C
```

---

### ✏️ Örnek 9 (cotx — trigonometri)
```
∫ cotx dx = ∫ cosx/sinx dx

u = sinx
du = cosx dx

= ∫ du/u = ln|sinx| + C
```

---

### ✏️ Örnek 10 (1/(x−3) tipi)
```
∫ 1/(x−3) dx

u = x − 3
du = dx

= ∫ du/u = ln|x−3| + C
```

---

## 🧠 TANI TABLOSU — Ne görürsen ne yaparsın?

| Gördüğün yapı | Yöntem |
|---------------|--------|
| Polinom veya kök → direkt | Temel kural |
| (ifade)ⁿ · (ifadenin türevi) | u = içteki ifade |
| pay = paydasın türevi | u = payda → ln çıkar |
| e^(ifade) · (ifadenin türevi) | u = üs |
| İçinde √x veya lnx var | du'yu ayarla |

---

## 📝 SINAV CHECKLIST

1. ☐ Direkt alınabilir mi? → Temel kural uygula
2. ☐ u = ? seç (karmaşık iç ifade)
3. ☐ du'yu hesapla
4. ☐ du yeteri kadar uyuyor mu? → Gerekirse böl/çarp
5. ☐ Her şeyi u ile yaz
6. ☐ İntegrali al
7. ☐ u'yu geri x ile yaz
8. ☐ + C yazmayı unutma!

---

## 🏋️ PRATİK

### Soru 1 (Temel)
**∫ (5x⁴ − 3x² + 7) dx**

### Soru 2 (Temel — kök)
**∫ 1/x³ dx**

### Soru 3 (Değişken değiştirme)
**∫ (x³ + 1)⁴ · x² dx**

### Soru 4 (Değişken değiştirme)
**∫ sinx · cos⁵x dx**

> Çözmeyi dene, takılırsan "çözümü göster" de! 🚀
