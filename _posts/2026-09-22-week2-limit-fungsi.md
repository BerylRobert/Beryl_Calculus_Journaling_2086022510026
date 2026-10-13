---
title: "Week 2: Limit Fungsi"
date: 2026-09-22 09:00:00 +0800
categories: [Calculus, Journaling]
tags: [limit, limit-kiri-kanan, faktorisasi, merasionalkan]
math: true
---

## Pengantar

Minggu kedua membahas **Limit Fungsi**, konsep dasar kalkulus yang menjelaskan nilai yang didekati suatu fungsi ketika variabel mendekati titik tertentu, tanpa harus tepat berada di titik itu. Ditulis sebagai:

$$\lim_{x \to a} f(x) = L$$

Artinya, semakin $x$ mendekati $a$, nilai $f(x)$ semakin mendekati $L$.

## 1. Jenis-Jenis Limit

Ada empat jenis limit yang dipelajari minggu ini:

1. **Limit biasa** — substitusi langsung
2. **Limit kiri** ($x \to a^-$) — mendekati dari arah kiri (nilai lebih kecil)
3. **Limit kanan** ($x \to a^+$) — mendekati dari arah kanan (nilai lebih besar)
4. **Limit aljabar** — pakai faktorisasi atau merasionalkan, dipakai saat substitusi langsung menghasilkan bentuk tak tentu $\frac{0}{0}$

## 2. Limit Biasa (Substitusi Langsung)

Kalau fungsinya polinom atau kontinu, limit bisa langsung dihitung dengan substitusi nilai yang didekati ke fungsinya.

**Contoh:** $\lim\limits_{x \to 2} (3x^2 - 5x + 1)$

$$= 3(2)^2 - 5(2) + 1 = 12 - 10 + 1 = 3$$

## 3. Limit Kiri dan Limit Kanan

Dipakai untuk fungsi **potongan (piecewise)**, karena rumus fungsinya berbeda tergantung daerahnya.

**Contoh:** $f(x) = \begin{cases} x+2, & x<1 \\ 3x-1, & x \geq 1 \end{cases}$

- Limit kiri pakai rumus pertama (karena mendekati dari $x<1$): $\lim\limits_{x \to 1^-} f(x) = 1+2 = 3$
- Limit kanan pakai rumus kedua (karena mendekati dari $x \geq 1$): $\lim\limits_{x \to 1^+} f(x) = 3(1)-1 = 2$

Karena $3 \neq 2$, maka $\lim\limits_{x \to 1} f(x)$ **tidak ada**. Syarat limit ada: limit kiri harus sama dengan limit kanan.

## 4. Limit Aljabar dengan Faktorisasi

Dipakai saat substitusi langsung menghasilkan $\frac{0}{0}$ pada fungsi **polinom**.

**Rumus penting:**

$$a^2 - b^2 = (a-b)(a+b) \qquad a^3 - b^3 = (a-b)(a^2+ab+b^2)$$

**Contoh:** $\lim\limits_{x \to 3} \dfrac{x^2-9}{x-3}$

$$= \lim_{x \to 3} \frac{(x-3)(x+3)}{x-3} = \lim_{x \to 3} (x+3) = 6$$

## 5. Limit Aljabar dengan Merasionalkan

Dipakai saat substitusi langsung menghasilkan $\frac{0}{0}$ pada fungsi yang mengandung **akar**.

**Rumus sekawan:** $(\sqrt{A}-\sqrt{B})(\sqrt{A}+\sqrt{B}) = A - B$

**Contoh:** $\lim\limits_{x \to 4} \dfrac{\sqrt{x}-2}{x-4}$

$$= \frac{\sqrt{x}-2}{x-4} \times \frac{\sqrt{x}+2}{\sqrt{x}+2} = \frac{x-4}{(x-4)(\sqrt{x}+2)} = \frac{1}{\sqrt{x}+2}$$

Substitusi $x=4$: $\dfrac{1}{\sqrt{4}+2} = \dfrac{1}{4}$

## 6. Strategi Menentukan Metode

Panduan cepat memilih cara:

- Fungsi kontinu → substitusi langsung
- Fungsi potongan (piecewise) → limit kiri dan kanan
- Hasil substitusi $\frac{0}{0}$ pada polinom → faktorisasi
- Hasil substitusi $\frac{0}{0}$ pada bentuk akar → merasionalkan

## 7. Kesalahan yang Sering Terjadi

- Menganggap bentuk $\frac{0}{0}$ sama dengan nol (padahal ini bentuk tak tentu, harus disederhanakan dulu)
- Salah memilih rumus pada fungsi potongan (ketuker mana untuk limit kiri, mana untuk limit kanan)
- Lupa menyederhanakan setelah faktorisasi
- Hanya mengalikan sekawan pada pembilang saja, lupa penyebutnya juga harus dikali

## Contoh Soal dan Pembahasan

**Soal 1 (Limit Kiri-Kanan).** Diberikan $f(x) = \begin{cases} 2x, & x<3 \\ x+3, & x \geq 3 \end{cases}$. Tentukan apakah $\lim\limits_{x \to 3} f(x)$ ada.

*Pembahasan:* Hitung limit kiri dan kanan terpisah.

$$\lim_{x \to 3^-} f(x) = 2(3) = 6 \qquad \lim_{x \to 3^+} f(x) = 3+3 = 6$$

Karena keduanya sama (sama-sama 6), maka $\lim\limits_{x \to 3} f(x) = 6$, limitnya **ada**.

**Soal 2 (Faktorisasi).** Hitung $\lim\limits_{x \to 2} \dfrac{x^2-4}{x-2}$.

*Pembahasan:* Substitusi langsung menghasilkan $\frac{0}{0}$ (tak tentu), jadi harus difaktorkan dulu.

$$\frac{x^2-4}{x-2} = \frac{(x-2)(x+2)}{x-2} = x+2$$

Substitusi $x=2$: hasilnya $2+2 = 4$.

**Soal 3 (Merasionalkan).** Hitung $\lim\limits_{x \to 1} \dfrac{\sqrt{x+3}-2}{x-1}$.

*Pembahasan:* Ada akar dan hasil substitusi langsung $\frac{0}{0}$, jadi kalikan dengan sekawan $\sqrt{x+3}+2$.

$$\frac{\sqrt{x+3}-2}{x-1} \times \frac{\sqrt{x+3}+2}{\sqrt{x+3}+2} = \frac{(x+3)-4}{(x-1)(\sqrt{x+3}+2)} = \frac{x-1}{(x-1)(\sqrt{x+3}+2)} = \frac{1}{\sqrt{x+3}+2}$$

Substitusi $x=1$: $\dfrac{1}{\sqrt{4}+2} = \dfrac{1}{4}$.

## Quiz Week 2

### Limit Biasa

1. $\lim\limits_{x \to 2} (3x^2-5x+1)$ = . . .
   A. 1　B. 2　C. 3　D. 5　E. 7

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Fungsi polinom, langsung substitusi $x=2$: $3(4)-5(2)+1 = 12-10+1 = 3$.
   </details>

2. $\lim\limits_{x \to -1} (2x^3+x^2-4)$ = . . .
   A. −3　B. −5　C. −6　D. −7　E. 5

   <details><summary>Pembahasan</summary>
   Jawaban: B.<br>
   Substitusi $x=-1$: $2(-1)^3+(-1)^2-4 = -2+1-4 = -5$.
   </details>

3. $\lim\limits_{x \to 3} (x^3-2x^2+x-6)$ = . . .
   A. 8　B. 10　C. 11　D. 12　E. 15

   <details><summary>Pembahasan</summary>
   Catatan: ada kejanggalan pada soal ini.<br>
   Kalau dihitung persis sesuai fungsi yang tertulis: $27-18+3-6=6$, tapi angka ini tidak ada di pilihan manapun. Kemungkinan ada salah ketik pada soal aslinya. Kalau fungsinya $x^3-2x^2+x$ (tanpa "−6" di akhir), hasilnya $27-18+3=12$, cocok dengan opsi D. Sebaiknya dicek ulang ke sumber/dosen untuk memastikan fungsi yang benar.
   </details>

### Limit Kiri dan Kanan

4. Diberikan $f(x) = \begin{cases} x+2, & x<1 \\ 3x-1, & x \geq 1 \end{cases}$. Nilai $\lim\limits_{x \to 1^-} f(x)$ adalah . . .
   A. 1　B. 2　C. 3　D. 4　E. 5

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Karena mendekati dari kiri ($x<1$), pakai rumus pertama: $f(x)=x+2$. Substitusi $x=1$: $1+2=3$.
   </details>

5. Dengan fungsi pada soal 4, tentukan $\lim\limits_{x \to 1^+} f(x)$.
   A. 1　B. 2　C. 3　D. 4　E. 5

   <details><summary>Pembahasan</summary>
   Jawaban: B.<br>
   Karena mendekati dari kanan ($x \geq 1$), pakai rumus kedua: $f(x)=3x-1$. Substitusi $x=1$: $3(1)-1=2$.
   </details>

6. Diketahui $g(x) = \begin{cases} x^2, & x<2 \\ x+2, & x \geq 2 \end{cases}$. Limit kiri dan limit kanan saat $x \to 2$ berturut-turut adalah . . .
   A. (2,4)　B. (4,2)　C. (4,4)　D. (6,4)　E. (4,6)

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Limit kiri pakai $x^2$ (karena $x<2$): $2^2=4$. Limit kanan pakai $x+2$ (karena $x\geq2$): $2+2=4$. Keduanya sama, yaitu 4.
   </details>

7. Diberikan $p(x) = \begin{cases} x^2-1, & x<2 \\ 5-x, & x \geq 2 \end{cases}$. Pernyataan yang benar mengenai limit saat $x \to 2$ adalah . . .
   A. Limit kiri = 3, limit kanan = 3, limit ada　B. Limit kiri = 3, limit kanan = 4, limit tidak ada　C. Limit kiri = 4, limit kanan = 3, limit tidak ada　D. Limit kiri = 4, limit kanan = 4, limit ada　E. Limit kiri = 5, limit kanan = 3, limit tidak ada

   <details><summary>Pembahasan</summary>
   Jawaban: A.<br>
   Limit kiri pakai $x^2-1$: $2^2-1=3$. Limit kanan pakai $5-x$: $5-2=3$. Keduanya sama (3), jadi limitnya ada.
   </details>

### Limit Aljabar dengan Faktorisasi

8. $\lim\limits_{x \to 3} \dfrac{x^2-9}{x-3}$ = . . .
   A. 3　B. 5　C. 6　D. 8　E. 9

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Faktorkan: $\dfrac{(x-3)(x+3)}{x-3} = x+3$. Substitusi $x=3$: $3+3=6$.
   </details>

9. $\lim\limits_{x \to 2} \dfrac{x^2-4}{x-2}$ = . . .
   A. 2　B. 3　C. 4　D. 5　E. 6

   <details><summary>Pembahasan</summary>
   Jawaban: C (lihat pembahasan Soal 2 di atas).
   </details>

10. $\lim\limits_{x \to 1} \dfrac{x^3-1}{x-1}$ = . . .
    A. 1　B. 2　C. 3　D. 4　E. 5

    <details><summary>Pembahasan</summary>
    Jawaban: C.<br>
    Pakai identitas $a^3-b^3=(a-b)(a^2+ab+b^2)$: $x^3-1=(x-1)(x^2+x+1)$. Jadi $\dfrac{(x-1)(x^2+x+1)}{x-1}=x^2+x+1$. Substitusi $x=1$: $1+1+1=3$.
    </details>

11. $\lim\limits_{x \to -2} \dfrac{x^2+x-2}{x+2}$ = . . .
    A. −5　B. −4　C. −3　D. −2　E. −1

    <details><summary>Pembahasan</summary>
    Jawaban: C.<br>
    Faktorkan pembilang: $x^2+x-2=(x+2)(x-1)$. Jadi $\dfrac{(x+2)(x-1)}{x+2}=x-1$. Substitusi $x=-2$: $-2-1=-3$.
    </details>

12. $\lim\limits_{x \to 4} \dfrac{x^2-5x+4}{x-4}$ = . . .
    A. 1　B. 2　C. 3　D. 4　E. 5

    <details><summary>Pembahasan</summary>
    Jawaban: C.<br>
    Faktorkan pembilang: $x^2-5x+4=(x-1)(x-4)$. Jadi $\dfrac{(x-1)(x-4)}{x-4}=x-1$. Substitusi $x=4$: $4-1=3$.
    </details>

### Limit Aljabar dengan Merasionalkan

13. $\lim\limits_{x \to 4} \dfrac{\sqrt{x}-2}{x-4}$ = . . .
    A. $\frac{1}{8}$　B. $\frac{1}{6}$　C. $\frac{1}{4}$　D. $\frac{1}{2}$　E. 1

    <details><summary>Pembahasan</summary>
    Jawaban: C (lihat pembahasan Soal 3 di atas).
    </details>

14. $\lim\limits_{x \to 9} \dfrac{3-\sqrt{x}}{9-x}$ = . . .
    A. $\frac{1}{3}$　B. $\frac{1}{6}$　C. $\frac{1}{9}$　D. $\frac{1}{12}$　E. $\frac{1}{18}$

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    Kalikan sekawan $(3+\sqrt{x})$: $\dfrac{(3-\sqrt{x})(3+\sqrt{x})}{(9-x)(3+\sqrt{x})} = \dfrac{9-x}{(9-x)(3+\sqrt{x})} = \dfrac{1}{3+\sqrt{x}}$. Substitusi $x=9$: $\dfrac{1}{3+3}=\dfrac{1}{6}$.
    </details>

15. $\lim\limits_{x \to 1} \dfrac{\sqrt{2x+7}-3}{x-1}$ = . . .
    A. $\frac{1}{6}$　B. $\frac{1}{3}$　C. $\frac{1}{2}$　D. $\frac{2}{3}$　E. $\frac{1}{4}$

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    Kalikan sekawan $(\sqrt{2x+7}+3)$: pembilang menjadi $(2x+7)-9 = 2x-2 = 2(x-1)$. Jadi $\dfrac{2(x-1)}{(x-1)(\sqrt{2x+7}+3)} = \dfrac{2}{\sqrt{2x+7}+3}$. Substitusi $x=1$: $\dfrac{2}{\sqrt{9}+3} = \dfrac{2}{6} = \dfrac{1}{3}$.
    </details>

## Dokumentasi

Foto catatan di kelas membahas limit fungsi bersyarat (piecewise):

![Contoh soal limit fungsi bersyarat di papan tulis](/assets/img/week2_1.jpeg)

![Penyelesaian limit kiri dan limit kanan di papan tulis](/assets/img/week2_2.jpeg)

## Refleksi

Materi limit minggu ini terasa lebih sistematis dibanding fungsi di week 1, karena ada alur yang jelas: coba substitusi dulu, kalau hasilnya $\frac{0}{0}$ baru pilih antara faktorisasi (untuk polinom) atau merasionalkan (untuk bentuk akar). Bagian yang paling perlu latihan ekstra adalah limit kiri-kanan pada fungsi potongan, karena harus teliti memilih rumus yang mana sesuai arah pendekatannya, salah pilih rumus sedikit saja hasilnya langsung beda.

Bagian merasionalkan awalnya terasa membingungkan karena harus mengalikan dengan bentuk sekawan yang kelihatan "muncul dari mana", tapi setelah dicoba beberapa soal, polanya jadi lebih terasa: tujuannya selalu untuk menghilangkan akar di pembilang atau penyebut supaya bentuk $\frac{0}{0}$ bisa disederhanakan.

Target minggu depan: lebih hati-hati membaca soal, karena ada satu soal latihan (No. 3 kuis) yang hasilnya tidak cocok dengan pilihan jawaban. Perlu dibiasakan untuk mengecek ulang hasil substitusi sebelum yakin dengan jawaban, terutama kalau hasilnya tidak ada di pilihan.