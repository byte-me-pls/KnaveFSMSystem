# 📝 ÇALIŞMA KAĞIDI
### Konular: Grafik Çizme · Ekstremum · Belirsiz İntegral · Kısmi İntegrasyon

> ⏱ Önce çöz, sonra çözümlere bak!

---

## 📌 BÖLÜM 1 — Fonksiyon Grafiği Çizme

**S1.**  `f(x) = x³ − 6x² + 9x`  fonksiyonu için aşağıdakileri bulunuz ve grafiğini çiziniz:

- a) **Eksen kesişim noktaları** → x=0 koy, f(x)=0 çöz
- b) **f'(x)'i bul** → kritik noktaları (f'=0) bul
- c) **Artan / Azalan aralıkları** → f' işaret tablosu
- d) **Yerel maksimum ve minimum** → f' işaret değişiminden belirle
- e) **f''(x)'i bul** → f''=0 dan dönüm noktasını bul
- f) **Konkav yukarı / aşağı aralıkları** → f'' işaret tablosu
- g) **Grafiği çiz** → tüm bilgileri kullanarak

---

## 📌 BÖLÜM 2 — Ekstremum Problemleri

**S6.**  Çevresi 80 cm olan bir dikdörtgenin alanı en fazla kaç cm²'dir?

&nbsp;

**S7.**  Bir kenarı duvara dayanan ve diğer üç kenarı 90 m tel ile çevrilen dikdörtgen arsanın alanı en fazla kaç m²'dir?

&nbsp;

**S8.**  `y = 8 − x²`  parabolü altında x ekseni üzerinde duran bir dikdörtgenin en büyük alanını bulunuz.

&nbsp;

**S9.**  Hacmi 32π cm³ olan bir silindirin yüzey alanı en az kaç cm² olur?
*(İpucu: V = πr²h = 32π → h = 32/r²)*

&nbsp;

**S10.**  Toplam yüzey alanı 54 cm² olan bir karenin hacmi en fazla kaç cm³ olur?
*(İpucu: 6a² = 54 → a = 3)*

---

## 📌 BÖLÜM 3 — Belirsiz İntegral

**S11.**  `∫ (4x³ − 6x² + 2x − 5) dx`

&nbsp;

**S12.**  `∫ √x / x²  dx`
*(İpucu: önce üsse çevir, sadeleştir)*

&nbsp;

**S13.**  `∫ (x² + 3) / x  dx`

&nbsp;

**S14.**  `∫ (3x² − 4x)⁵ · (6x − 4) dx`
*(Değişken değiştirme)*

&nbsp;

**S15.**  `∫ sinx · cos⁴x dx`
*(Değişken değiştirme)*

---

## 📌 BÖLÜM 5 — Kısmi İntegrasyon

**S16.**  `∫ x · e³ˣ dx`

&nbsp;

**S17.**  `∫ x³ · lnx dx`

&nbsp;

**S18.**  `∫ x · sin2x dx`

&nbsp;

**S19.**  `∫ ln(x²) dx`
*(İpucu: ln(x²) = 2lnx olarak yaz)*

&nbsp;

**S20.**  `∫ x² · eˣ dx`
*(İpucu: iki kez kısmi integrasyon gerekiyor!)*

---
---

# ✅ ÇÖZÜMLER

> Önce kendi çözümünü kontrol et!

---

### BÖLÜM 1 — Çözüm

**S1.**  `f(x) = x³ − 6x² + 9x`

**a) Eksen kesişimleri:**
```
x = 0  →  f(0) = 0       Y-ekseni: (0, 0)

f(x) = 0  →  x³ − 6x² + 9x = 0
           →  x(x² − 6x + 9) = 0
           →  x(x − 3)² = 0
           →  x = 0  veya  x = 3

X-ekseni: (0,0)  ve  (3,0)
```

**b) f'(x) ve kritik noktalar:**
```
f'(x) = 3x² − 12x + 9 = 3(x² − 4x + 3) = 3(x−1)(x−3)
f'(x) = 0  →  x = 1  ve  x = 3
```

**c) İşaret tablosu (f'):**
```
      |   x<1   |  x=1  |  1<x<3  |  x=3  |  x>3
──────|─────────|───────|─────────|───────|──────
f'(x) |    +    |   0   |    −    |   0   |   +
f(x)  |   ↗    |  max  |   ↘    |  min  |   ↗
```

**d) Yerel max/min:**
```
f(1) = 1 − 6 + 9 = 4   →  Yerel MAKSİMUM  nokta: (1, 4)
f(3) = 27 − 54 + 27 = 0 →  Yerel MİNİMUM   nokta: (3, 0)
```

**e) f''(x) ve dönüm noktası:**
```
f''(x) = 6x − 12 = 0  →  x = 2
f(2) = 8 − 24 + 18 = 2  →  Dönüm noktası: (2, 2)
```

**f) Konkavlık:**
```
x < 2  →  f''(x) < 0  →  Konkav AŞAĞI (∩)
x > 2  →  f''(x) > 0  →  Konkav YUKARI (∪)
```

**g) Grafik için özet:**
```
Geçtiği noktalar: (0,0)  (1,4)  (2,2)  (3,0)
Yerel maks: (1, 4)
Yerel min:  (3, 0)
Dönüm:      (2, 2)
x→+∞ → f→+∞,   x→-∞ → f→-∞
```


---

### BÖLÜM 2 — Çözümler

**S6.**
```
2x + 2y = 80  →  y = 40−x
A = x(40−x) = 40x − x²
A' = 40 − 2x = 0  →  x = 20, y = 20
A = 400 cm²
```

**S7.**
```
x + 2y = 90  →  x = 90−2y
A = xy = (90−2y)y = 90y − 2y²
A' = 90 − 4y = 0  →  y = 22.5,  x = 45
A = 45 · 22.5 = 1012.5 m²
```

**S8.**
```
Köşe (t, 8−t²)  →  genişlik 2t, yükseklik 8−t²
A = 2t(8−t²) = 16t − 2t³
A' = 16 − 6t² = 0  →  t² = 8/3  →  t = 2√(2/3)
A_max = 2t(8−t²) = 64√6/9 ≈ 17.4
```

**S9.**
```
SA = 2πr² + 2πrh = 2πr² + 2πr·(32/r²) = 2πr² + 64π/r
SA' = 4πr − 64π/r² = 0  →  r³ = 16  →  r = 2∛2
h = 32/r² = 4∛2
SA_min = 24π∛4 cm²
```

**S10.**
```
6a² = 54  →  a = 3
V = a³ = 27 cm³
```

---

### BÖLÜM 3 — Çözümler

**S11.**
```
= x⁴ − 2x³ + x² − 5x + C
```

**S12.**
```
√x / x² = x^(1/2) / x² = x^(1/2−2) = x^(-3/2)
∫ x^(-3/2) dx = x^(-1/2) / (-1/2) = −2/√x + C
```

**S13.**
```
(x²+3)/x = x + 3/x
∫(x + 3/x) dx = x²/2 + 3ln|x| + C
```

**S14.**
```
u = 3x²−4x,  du = (6x−4)dx
= ∫ u⁵ du = u⁶/6 + C = (3x²−4x)⁶/6 + C
```

**S15.**
```
u = cosx,  du = −sinx dx  →  −du = sinx dx
= ∫ u⁴ · (−du) = −u⁵/5 + C = −cos⁵x/5 + C
```

---

### BÖLÜM 5 — Çözümler

**S16.**
```
u = x,   dv = e³ˣ dx
du = dx,  v = e³ˣ/3

= x·e³ˣ/3 − ∫ e³ˣ/3 dx
= x·e³ˣ/3 − e³ˣ/9 + C
```

**S17.**
```
u = lnx,   dv = x³ dx
du = 1/x dx,  v = x⁴/4

= x⁴/4 · lnx − ∫ x⁴/4 · 1/x dx
= x⁴/4 · lnx − x⁴/16 + C
```

**S18.**
```
u = x,   dv = sin2x dx
du = dx,  v = −cos2x/2

= −x·cos2x/2 + ∫ cos2x/2 dx
= −x·cos2x/2 + sin2x/4 + C
```

**S19.**
```
∫ 2lnx dx = 2∫ lnx dx

u = lnx, dv = dx  →  v = x
= 2(x·lnx − x) + C = 2x·lnx − 2x + C
```

**S20.**
```
1. kısmi:
u = x²,  dv = eˣ dx  →  v = eˣ
= x²eˣ − ∫ 2x·eˣ dx

2. kısmi (∫ 2xeˣ dx için):
u = 2x,  dv = eˣ dx  →  v = eˣ
= 2xeˣ − ∫ 2eˣ dx = 2xeˣ − 2eˣ

Sonuç:
= x²eˣ − (2xeˣ − 2eˣ) + C
= eˣ(x² − 2x + 2) + C
```
