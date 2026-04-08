# 🎯 Konu 2: Ekstremum (Maksimum/Minimum) Problemleri

> **Sınav Notu:** Hocan bu konudan **1 soru** geleceğini söyledi. Soru bir gerçek hayat problemi olacak — kutu, çevre, alan gibi.

---

## 🔑 Genel Yöntem (Her Soruda Aynı!)

```
1. Ne maksimize/minimize etmek istiyoruz? → Buna f(x) de
2. Bir kısıt denklemi var (çevre, hacim, alan eşitliği gibi) → y'yi x cinsinden yaz
3. f(x)'i sadece x cinsinden yaz
4. f'(x) = 0 yap → kritik nokta bul
5. Cevabı hesapla
```

> **Tek cümle:** Problemi bir fonksiyona çevir, türevini sıfıra eşitle.

---

## ✏️ ÖRNEK 1: Dikdörtgen + Çevre Problemi

**Soru:** Çevresi 40 cm olan bir dikdörtgenin alanı en fazla kaç birimkaredir?

**Adım 1 — Değişkenleri belirle:**
```
Kenarlar: x ve y
Çevre: 2x + 2y = 40  →  x + y = 20  →  y = 20 − x
```

**Adım 2 — Alan fonksiyonunu kur:**
```
Alan = x · y = x · (20 − x) = 20x − x²

Bunu f(x) diyoruz:  f(x) = 20x − x²
```

**Adım 3 — Türev al, sıfıra eşitle:**
```
f'(x) = 20 − 2x = 0
2x = 20
x = 10  →  y = 20 − 10 = 10
```

**Adım 4 — Cevabı hesapla:**
```
Alan = 10 · 10 = 100 birimkare
```

> **Sonuç:** En büyük alan, **kare** olduğunda elde edilir! (x = y = 10)

![Örnek 1 - Dikdörtgen Alanı](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/eks1_dortgen.png)

---

## ✏️ ÖRNEK 2: Tel ile Çevre Problemi

**Soru:** Arsanın üç tarafı tel ile çevrilecektir. 180 metre tel kullanıldığına göre arsanın alanı en fazla kaç metrekaredir?

```
      x        x
   ┌──────────────┐
   │              │  ← Bir kenar açık (duvar var)
   └──────────────┘
          y
```

**Adım 1 — Kısıt denklemi:**
```
Üç taraf: y + 2x = 180  →  y = 180 − 2x
```

**Adım 2 — Alan fonksiyonu:**
```
Alan = x · y = x · (180 − 2x) = 180x − 2x²

f(x) = 180x − 2x²
```

**Adım 3 — Türev = 0:**
```
f'(x) = 180 − 4x = 0
4x = 180
x = 45  →  y = 180 − 90 = 90
```

**Adım 4 — Cevap:**
```
Alan = 45 · 90 = 4050 m²
```

![Örnek 2 - Tel Çevre](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/eks2_tel.png)

---

## ✏️ ÖRNEK 3: Parabolün Altındaki Dikdörtgen

**Soru:** y = 27 − x² parabolü altındaki dikdörtgenin alanı en fazla kaç birimkaredir?

```
        ↑ y
        |    ╭────────╮  ← parabolün üst kısmı
        |    │ ██████ │
        │──t─┤ ██████ ├──→ x
        |    │ ██████ │
```

**Mantık:** Dikdörtgenin bir köşesi paraboldeki **(t, 27 − t²)** noktasında.
- Genişlik = 2t (simetrik)
- Yükseklik = 27 − t²

**Alan fonksiyonu:**
```
Alan = 2t · (27 − t²) = 54t − 2t³

f(t) = 54t − 2t³
```

**Türev = 0:**
```
f'(t) = 54 − 6t² = 0
6t² = 54
t² = 9  →  t = 3
```

**Cevap:**
```
Alan = 6 · (27 − 9) = 6 · 18 = 108 birimkare
```

![Örnek 3 - Parabol Dikdörtgen](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/eks3_parabol.png)

---

## ✏️ ÖRNEK 4: Paraboldeki Nokta — Koordinat Toplamı

**Soru:** y = x² − 9x + 5 parabolü üzerindeki bir noktanın koordinatları toplamı en az kaç olabilir?

**Mantık:** Paraboldeki nokta **(t, t² − 9t + 5)** şeklinde.

```
Toplam = t + (t² − 9t + 5) = t² − 8t + 5

f(t) = t² − 8t + 5
```

**Türev = 0:**
```
f'(t) = 2t − 8 = 0
t = 4
```

**Cevap:**
```
Toplam = 16 − 32 + 5 = −11  (minimum değer)
```

![Örnek 4 - Koordinat Toplamı](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/eks4_koordinat.png)

---

## ✏️ ÖRNEK 5: Kağıt Kenar Boşlukları Problemi

**Soru:** Bir kağıdın üst ve altından 0.5 cm, sağ ve soldan 1 cm boşluk bırakılarak yazı yazılabilecek alan 24 cm² olsun. Bu kağıdın alanı en az kaç cm²dir?

```
   ┌──────────────┐
   │  ┌────────┐  │  ← Yazı alanı: x · y = 24
   │  │  x·y   │  │
   │  └────────┘  │
   └──────────────┘
   Kağıt: (x+2)·(y+1)
```

**Kısıt:**
```
x · y = 24  →  y = 24/x
```

**Kağıt alanı fonksiyonu:**
```
f(x) = (x + 2)(y + 1)
     = (x + 2)(24/x + 1)

Her terimi ayrı ayrı çarp:
  x   · 24/x  =  24     (x'ler sadeleşir)
  x   · 1     =  x
  2   · 24/x  =  48/x
  2   · 1     =  2

Topla:
= 24 + x + 48/x + 2
= x + 48/x + 26
```

**Türev = 0:**
```
f'(x) = 3 − 48/x² = 0
3 = 48/x²
x² = 16  →  x = 4  →  y = 24/4 = 6
```

**Cevap:**
```
Kağıt alanı = (4+2)(6+1) = 6 · 9 = 54 cm²
```

---

## ✏️ ÖRNEK 6: Üçgen İçindeki Dikdörtgen

**Soru:** |AH| = 60 m, |BC| = 100 m olan bir üçgende içine çizilen dikdörtgenin alanı en fazla kaç m²dir?

```
       A
      /|\
     / | \
    /  |  \
   B───┼───C   |BC| = 100
       H       |AH| = 60
```

**Benzer üçgenler yardımıyla:**
```
(60 − y)/60 = x/100  →  300 − 5y = 3x  →  x = (300 − 5y)/3
```

**Alan fonksiyonu:**
```
Alan = x · y = [(300 − 5y)/3] · y = (300y − 5y²)/3

f(y) = (300y − 5y²)/3
```

**Türev = 0:**
```
f'(y) = (300 − 10y)/3 = 0
300 − 10y = 0
y = 30  →  x = (300 − 150)/3 = 50
```

**Cevap:**
```
Alan = 50 · 30 = 1500 m²
```

![Örnek 6 - Üçgen Dikdörtgen](C:/Users/meyzd/.gemini/antigravity/brain/4942ae85-8973-4c8a-8af4-f25a416817ab/graphs/eks6_ucgen.png)

---

## 🧠 SINAV STRATEJİSİ

| Soru tipi | Ne yaparsın? |
|-----------|-------------|
| Çevre verilmiş, en büyük alan | 2k.denklemden y'yi çek, f(x) = x·y |
| Alan verilmiş, en küçük çevre | Alan denkleminden y'yi çek, f(x) = 2x+2y |
| Paraboldeki nokta/alan | Noktayı (t, f(t)) koy, fonksiyon kur |
| Geometri (üçgen içi vb.) | Benzer üçgen / orantı ile ilişki kur |

---

## 📝 SINAV CHECKLIST

1. ☐ Neyi max/min yapmak istiyoruz? → **f(x)** belirle
2. ☐ Kısıt denklemi var mı? → **y'yi x cinsinden** yaz
3. ☐ f(x)'i sadece **tek değişkenle** yaz
4. ☐ f'(x) = 0 yap → **x'i** bul
5. ☐ **y'yi** hesapla (kısıt denklemine koy)
6. ☐ Sonucu (Alan / Hacim / Toplam) hesapla

---

## 🏋️ PRATİK

### Soru 1 (Kolay)
Çevresi 60 cm olan bir dikdörtgenin alanı en fazla kaç cm²dir?

### Soru 2 (Orta)
Bir arsanın iki tarafı duvar, iki tarafı tel ile çevrilecektir. 120 metre tel kullanıldığında alan en fazla kaç olur?

### Soru 3 (Sınav Tarzı)
y = 12 − x² parabolü altındaki dikdörtgenin en büyük alanı nedir?

> Çözmeyi dene, takılırsan "çözümü göster" de! 🚀
