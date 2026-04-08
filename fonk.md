# 📈 Konu 1: Verilen Fonksiyonun Grafiğini Çizme

> **Sınav Notu:** Hocan bu konudan tam bir grafik çizme sorusu soracak.

---

## 🎯 Grafik Çizme: 5 Adım

| Adım | Ne Yapılır? |
|------|-------------|
| 1 | Eksen kesişim noktalarını bul |
| 2 | f'(x) al, = 0 yap → artan/azalan aralıklar |
| 3 | Yerel max/min noktalarını belirle |
| 4 | f''(x) al, = 0 yap → konkav/konveks aralıklar |
| 5 | Dönüm noktalarını belirle, grafiği çiz |

---

## 🔧 Başlamadan: Lazım Olacak Türev Kuralları

```
xⁿ  →  n · xⁿ⁻¹       (üssü öne indir, üsten 1 çıkar)

Örnekler:
  x²  →  2x
  x³  →  3x²
  x⁴  →  4x³
  5x  →  5        (x¹ → 1·x⁰ = 1)
  7   →  0        (sabit sayının türevi 0)
```

---

## 📌 ADIM 1: Eksen Kesişim Noktaları

### Y-ekseni (x yerine 0 koy)
```
f(x) = x⁴ − 8x²
f(0) = 0 − 0 = 0  →  Y-ekseni kesişimi: (0, 0)
```

### X-ekseni (f(x) = 0 yap ve x'i bul)
```
x⁴ − 8x² = 0
```
Burada **ortak çarpana alma** yapıyoruz. Mantığı şu:

```
x⁴ = x² · x²    ve    8x² = x² · 8

İkisinde de x² var, onu dışarı çekiyoruz:

x²(x² − 8) = 0
```

Şimdi kural: **A · B = 0 ise, ya A=0 ya B=0**
```
x² = 0       →  x = 0
x² − 8 = 0   →  x² = 8  →  x = ±√8 = ±2√2
```

> **√8 neden 2√2?** → 8 = 4×2, √(4×2) = √4 · √2 = 2√2

X-ekseni kesişimleri: **(−2√2, 0),  (0, 0),  (2√2, 0)**

---

## 📌 ADIM 2-3: Birinci Türev → Artan/Azalan & Max/Min

### Kural:
| f'(x) | Fonksiyon |
|-------|-----------|
| **+ (pozitif)** | **Artan** ↗ |
| **− (negatif)** | **Azalan** ↘ |

### Max/Min nasıl anlarız?
| f' işareti nasıl değişiyor? | Sonuç |
|-----------------------------|-------|
| **+ → −** geçiş | **Yerel Maksimum** (tepe) |
| **− → +** geçiş | **Yerel Minimum** (çukur) |

---

### ✏️ Örnek: y = x⁴ − 8x²

**Türev al:**
```
y' = 4x³ − 16x
```

**Ortak çarpana al ve sıfıra eşitle:**
```
4x³ − 16x = 0

Her iki terimde 4x var, dışarı çek:
4x(x² − 4) = 0

x² − 4 = (x−2)(x+2)  ← fark çarpanları: a²−b² = (a−b)(a+b)

Yani: 4x(x−2)(x+2) = 0
→  x = 0,   x = 2,   x = −2
```

**İşaret tablosu** (her aralıktan bir sayı seç, f'(x)'e koy, + mı − mı bak):

| Aralık | (−∞, −2) | −2 | (−2, 0) | 0 | (0, 2) | 2 | (2, +∞) |
|--------|----------|-----|---------|---|--------|---|---------|
| f'(x)  | − | 0 | + | 0 | − | 0 | + |
| f      | ↘ | Min | ↗ | Max | ↘ | Min | ↗ |

> **İşaret nasıl bulunur?** Örneğin (−∞, −2) aralığında x = −3 dene:
> f'(−3) = 4(−3)³ − 16(−3) = −108 + 48 = −60 → **negatif**

**Noktaların y-değerlerini hesapla** (x'i orijinal fonksiyona koy):
```
f(−2) = (−2)⁴ − 8(−2)² = 16 − 32 = −16  →  Min: (−2, −16)
f(0)  = 0                                  →  Max: (0, 0)
f(2)  = 16 − 32 = −16                      →  Min: (2, −16)
```

---

## 📌 ADIM 4-5: İkinci Türev → Konkav/Konveks & Dönüm Noktası

### Kural:
| f''(x) | Eğrinin şekli |
|--------|---------------|
| **+ (pozitif)** | **Konveks** ∪ (çanak gibi) |
| **− (negatif)** | **Konkav** ∩ (tepe gibi) |

> **Hatırlama:** Kon**V**eks → V harfi → ∪ şekli

### Dönüm noktası:
Eğrinin ∪ dan ∩ e (veya tam tersi) geçtiği yer. f''(x) = 0 **ve** işaret değişmeli.

> ⚠️ **Sonuç:**
- Her iki noktada da işaret değişimi var → **İki dönüm noktası** mevcut.

![y = x⁴ − 8x² grafiği](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/graf1_x4_8x2.png)

---

### ✏️ Örnek devam: y = x⁴ − 8x²

**İkinci türev al** (birinci türevin türevini al):
```
y'  = 4x³ − 16x
y'' = 12x² − 16
```

**Sıfıra eşitle:**
```
12x² − 16 = 0
12x² = 16
x² = 16/12 = 4/3
x = ±2/√3
```

**İşaret tablosu:**

| Aralık | (−∞, −2/√3) | −2/√3 | (−2/√3, 2/√3) | 2/√3 | (2/√3, +∞) |
|--------|-------------|-------|---------------|------|------------|
| f''    | + | 0 | − | 0 | + |
| Şekil  | ∪ Konveks | D.N. | ∩ Konkav | D.N. | ∪ Konveks |

İşaret değişiyor (+ → − → +) → **2 dönüm noktası** var ✓

---

## 🖊️ TAM ÇİZİM ÖRNEĞİ: f(x) = 3x − x³

> Notlarında "sınav sorusu benzeri" olarak işaretli!

**ADIM 1 — Eksen kesişimleri:**
```
Y-ekseni: f(0) = 0 → (0,0)
X-ekseni: 3x − x³ = 0  →  x(3 − x²) = 0
                              x = 0,  x² = 3,  x = ±√3
```

**ADIM 2-3 — Birinci türev:**
```
f'(x) = 3 − 3x²  = 3(1 − x²) = 0
→ x² = 1 → x = −1,  x = 1
```

| Aralık | (−∞, −1) | −1 | (−1, 1) | 1 | (1, +∞) |
|--------|----------|-----|---------|---|---------|
| f'     | − | 0 | + | 0 | − |
| f      | ↘ | Min | ↗ | Max | ↘ |

```
f(−1) = −3 + 1 = −2  →  Min: (−1, −2)
f(1)  = 3 − 1  = 2   →  Max: (1, 2)
```

**ADIM 4-5 — İkinci türev:**
```
f''(x) = −6x = 0  →  x = 0
```

| Aralık | (−∞, 0) | 0 | (0, +∞) |
|--------|---------|---|---------|
| f''    | + | 0 | − |
| Şekil  | ∪ | D.N. | ∩ |

Dönüm noktası: **(0, 0)**

Grafik **S şeklinde** bir eğri olacak (kübik fonksiyonların tipik şekli).

![f(x) = 3x − x³ grafiği](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/graf2_3x_x3.png)

---

## 🧩 DİĞER ÖRNEKLER (Notlarından)

### Örnek: f(x) = 1/(1+x²) — Rasyonel fonksiyon

**Eksen kesişimleri:**
```
Y-ekseni: f(0) = 1/(1+0) = 1 → (0, 1)
X-ekseni: 1/(1+x²) = 0 → pay hiçbir zaman 0 olmaz → X-eksenini KESMEZ
```

**1. Türev:** (bölüm türevi: (pay'·payda − pay·payda') / payda²)
```
f'(x) = −2x / (1+x²)² = 0
→ pay = 0 olmalı → −2x = 0 → x = 0
```

| Aralık | (−∞, 0) | 0 | (0, +∞) |
|--------|---------|---|---------|
| f'     | + | 0 | − |
| f      | ↗ | Max | ↘ |

Max: **(0, 1)**

**2. Türev:**
```
f''(x) = 2(3x²−1) / (1+x²)³ = 0
→ 3x² − 1 = 0 → x² = 1/3 → x = ±1/√3
```

| Aralık | (−∞, −1/√3) | −1/√3 | (−1/√3, 1/√3) | 1/√3 | (1/√3, +∞) |
|--------|-------------|-------|---------------|------|------------|
| f''    | + | 0 | − | 0 | + |
| Şekil  | ∪ | D.N. | ∩ | D.N. | ∪ |

2 dönüm noktası var. Grafik: tepesinde (0,1) olan çan eğrisi şeklinde.

![f(x) = 1/(1+x²) grafiği](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/graf3_rational.png)

---

### Örnek: f(x) = x³ − 3x² + 4x − 1 — Sadece dönüm noktası bulma

```
f'(x) = 3x² − 6x + 4
f''(x) = 6x − 6 = 0  →  x = 1
```

| Aralık | (−∞, 1) | 1 | (1, +∞) |
|--------|---------|---|---------|
| f''    | − | 0 | + |
| Şekil  | ∩ | D.N. | ∪ |

```
f(1) = 1 − 3 + 4 − 1 = 1  →  Dönüm Noktası: (1, 1)
```

---

## 🖊️ TAM ÇİZİM ÖRNEĞİ 2: f(x) = x³ − 3x²

**ADIM 1 — Eksen kesişimleri:**
```
Y-ekseni: f(0) = 0 → (0, 0)
X-ekseni: x³ − 3x² = 0  →  x²(x − 3) = 0
  x² = 0 → x = 0
  x − 3 = 0 → x = 3
```
X-ekseni kesişimleri: **(0, 0)** ve **(3, 0)**

---

**ADIM 2-3 — Birinci türev:**
```
f'(x) = 3x² − 6x = 3x(x − 2) = 0
→ x = 0,  x = 2
```

| Aralık | (−∞, 0) | 0 | (0, 2) | 2 | (2, +∞) |
|--------|---------|---|--------|---|---------|
| f'     | + | 0 | − | 0 | + |
| f      | ↗ | Max | ↘ | Min | ↗ |

```
f(0) = 0        →  Yerel Max: (0, 0)
f(2) = 8 − 12 = −4  →  Yerel Min: (2, −4)
```

> **İşaret kontrol:** (−∞,0) aralığından x = −1 dene:
> f'(−1) = 3(1) − 6(−1) = 3 + 6 = 9 → **pozitif** ↗

---

**ADIM 4-5 — İkinci türev:**
```
f''(x) = 6x − 6 = 0  →  x = 1
```

| Aralık | (−∞, 1) | 1 | (1, +∞) |
|--------|---------|---|---------|
| f''    | − | 0 | + |
| Şekil  | ∩ Konkav | D.N. | ∪ Konveks |

```
f(1) = 1 − 3 = −2  →  Dönüm Noktası: (1, −2)
```

![f(x) = x³ − 3x² grafiği](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/graf4_x3_3x2.png)

---

## ⚠️ TUZAK ÖRNEK: f(x) = x⁴

```
f''(x) = 12x² = 0  →  x = 0
```

| (−∞, 0) | 0 | (0, +∞) |
|---------|---|---------|
| + | 0 | + |

İşaret **değişmiyor** (hep +) → Dönüm noktası **YOK!**

---

## 📝 SINAV CHECKLIST

1. ☐ f(0) → Y kesişimi
2. ☐ f(x)=0 → X kesişimleri
3. ☐ f'(x) hesapla, = 0 yap → kritik noktalar
4. ☐ f' işaret tablosu → artan/azalan
5. ☐ Max/Min belirle, y-değerlerini hesapla
6. ☐ f''(x) hesapla, = 0 yap
7. ☐ f'' işaret tablosu → konveks/konkav
8. ☐ Dönüm noktası (işaret değişimi kontrol!)
9. ☐ Tüm noktaları koy, grafiği çiz

---

## 🏋️ PRATİK

### Soru 1 (Kolay)
**f(x) = x³ − 3x**

### Soru 2 (Orta)
**f(x) = x⁴ − 4x³**

### Soru 3 (Sınav Tarzı)
**f(x) = x³ − 6x² + 9x − 4**

> Çözmeyi dene, takılırsan "çözümü göster" de! 🚀
