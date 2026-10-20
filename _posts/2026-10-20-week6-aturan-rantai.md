---
title: "Week 6: Aturan Rantai (Chain Rule)"
date: 2026-10-06 09:00:00 +0800
categories: [Calculus, Journaling]
tags: [turunan, derivative, chain-rule, aturan-rantai]
math: true
---

## Pengantar

Minggu ini lanjut ke **Aturan Rantai (Chain Rule)**, salah satu aturan turunan paling penting karena dipakai hampir di semua fungsi "campuran" — fungsi yang di dalamnya ada fungsi lain, misalnya $(x^2+3)^4$. Sebelum masuk ke situ, materi juga mengulang beberapa aturan dasar turunan (jumlah/selisih, perkalian konstanta, perkalian, pembagian) yang jadi bekal sebelum aturan rantai.

## 1. Aturan Dasar Turunan (Ulasan Singkat)

| Fungsi | Turunan |
|---|---|
| $c$ (konstanta) | $0$ |
| $x$ | $1$ |
| $x^n$ | $nx^{n-1}$ |
| $cx^n$ | $cnx^{n-1}$ |

**Penjumlahan/pengurangan:** $\dfrac{d}{dx}[f(x)+g(x)] = f'(x)+g'(x)$

**Perkalian konstanta:** $\dfrac{d}{dx}[cf(x)] = c\cdot f'(x)$

**Aturan perkalian (product rule).** Jika $y=f(x)g(x)$, maka:

$$y' = f'g+fg'$$

Contoh: $y=(x^2+1)(3x+2)$. Misalkan $u=x^2+1$, $v=3x+2$, jadi $u'=2x$, $v'=3$.

$$y' = 2x(3x+2)+3(x^2+1) = 6x^2+4x+3x^2+3 = 9x^2+4x+3$$

**Aturan pembagian (quotient rule).** Jika $y=\dfrac{f(x)}{g(x)}$, maka:

$$y' = \frac{f'g-fg'}{g^2}$$

Contoh: $y=\dfrac{x^2+3}{x+1}$. Misalkan $f=x^2+3$, $g=x+1$, jadi $f'=2x$, $g'=1$.

$$y' = \frac{2x(x+1)-(x^2+3)}{(x+1)^2} = \frac{x^2+2x-3}{(x+1)^2}$$

## 2. Aturan Rantai: Mengapa Diperlukan?

Aturan rantai dipakai saat ada **fungsi di dalam fungsi lain** (fungsi komposisi), misalnya $(x^2+1)^5$. Di sini bagian dalamnya adalah $x^2+1$, dan bagian luarnya adalah $(\cdot)^5$. Keduanya tidak bisa langsung diturunkan pakai aturan pangkat biasa, karena bagian dalamnya bukan $x$ murni.

## 3. Rumus Aturan Rantai

Jika $y=f(g(x))$, maka:

$$y' = f'(g(x)) \cdot g'(x)$$

Secara sederhana: **turunan luar × turunan dalam**. Notasi Leibniz-nya, kalau $y=f(x)$ dan $x=g(t)$:

$$\frac{dy}{dt} = \frac{dy}{dx}\cdot\frac{dx}{dt}$$

**Langkah sistematis:**
1. Identifikasi fungsi luar.
2. Identifikasi fungsi dalam.
3. Turunkan fungsi luar (tetap pertahankan bagian dalam apa adanya).
4. Turunkan fungsi dalam.
5. Kalikan keduanya.

## 4. Contoh Penerapan

**Contoh 1.** $y=(x^2+3)^4$. Misalkan $u=x^2+3$ (dalam), sehingga $y=u^4$ (luar).

$$y' = 4u^3 \cdot u' = 4(x^2+3)^3 \cdot 2x = 8x(x^2+3)^3$$

**Contoh 2.** $y=(3x^2-5)^6$.

$$y' = 6(3x^2-5)^5 \cdot 6x = 36x(3x^2-5)^5$$

**Contoh 3.** $y=(2x^3+x)^8$.

$$y' = 8(2x^3+x)^7 \cdot (6x^2+1)$$

## 5. Aturan Rantai Bertingkat (Lebih dari 2 Lapisan)

Kadang fungsinya punya lebih dari dua lapisan. Contoh: $y=((x^2+1)^3+5)^2$, lapisannya:

1. luar: $(\cdot)^2$
2. tengah: $(\cdot)^3$
3. dalam: $x^2+1$

Turunannya dikalikan berurutan dari luar ke dalam:

$$y' = \underbrace{2((x^2+1)^3+5)}_{\text{turunan luar}} \cdot \underbrace{3(x^2+1)^2}_{\text{turunan tengah}} \cdot \underbrace{2x}_{\text{turunan dalam}} = 12x(x^2+1)^2\big((x^2+1)^3+5\big)$$

## 6. Kesalahan Umum

**Kesalahan 1:** $(x^2+1)^5$ langsung diturunkan jadi $5(x^2+1)^4$ saja — **lupa mengalikan turunan bagian dalam**. Jawaban yang benar: $5(x^2+1)^4 \cdot 2x = 10x(x^2+1)^4$.

**Kesalahan 2:** Pada $\dfrac{x^2+1}{x+2}$, pembilang dan penyebut diturunkan terpisah lalu dibagi begitu saja. Ini salah — harus pakai aturan pembagian, bukan diturunkan sendiri-sendiri.

## Contoh Soal dan Pembahasan

Dua contoh ini diambil langsung dari pembahasan di kelas (lihat juga foto di bagian Dokumentasi).

**Soal 1.** Tentukan turunan $f(x) = \big((x+3)^9-6\big)^{20}$.

*Pembahasan:* Ini aturan rantai bertingkat tiga (pangkat dalam pangkat dalam fungsi linear). Misalkan:

$$a = (x+3)^9-6, \qquad b = x+3$$

sehingga $f(x) = a^{20}$, dengan $a = b^9-6$, dan $b=x+3$.

Turunan tiap lapis:

$$\frac{da^{20}}{da} = 20a^{19}, \qquad \frac{d(b^9-6)}{db} = 9b^8, \qquad \frac{db}{dx}=1$$

Kalikan semuanya (dari luar ke dalam):

$$f'(x) = 20a^{19} \cdot 9b^8 \cdot 1 = 180\,a^{19}b^8 = 180\big((x+3)^9-6\big)^{19}(x+3)^8$$

**Soal 2.** Tentukan turunan $f(x) = (x+3)^9-(x+3)^{11}$.

*Pembahasan:* Misalkan $a=x+3$, sehingga $f(x) = a^9-a^{11}$. Pakai aturan rantai plus aturan penjumlahan/pengurangan:

$$\frac{df}{dx} = \frac{df}{da}\cdot\frac{da}{dx} = (9a^8-11a^{10})\cdot 1 = 9(x+3)^8-11(x+3)^{10}$$

**Soal 3 (kasus khusus komposisi).** Diketahui $g(x)=x+1$ dan $f(y)=y^{30}$. Tentukan turunan $h(x)=(f\circ g)(x)$.

*Pembahasan:* $h(x) = f(g(x)) = (x+1)^{30}$. Fungsi luarnya $y^{30}$ (turunannya $30y^{29}$) dan fungsi dalamnya $g(x)=x+1$ (turunannya $1$). Jadi:

$$h'(x) = 30(x+1)^{29}\cdot 1 = 30(x+1)^{29}$$

## Latihan Tambahan (dari Modul)

**1.** $5x^6$
<details><summary>Pembahasan</summary>
Aturan pangkat langsung: $5\cdot6x^5 = 30x^5$.
</details>

**2.** $4x^5-7x^2+3$
<details><summary>Pembahasan</summary>
Turunkan suku per suku: $20x^4-14x+0 = 20x^4-14x$.
</details>

**3.** $(x^2+2)(x+5)$
<details><summary>Pembahasan</summary>
Aturan perkalian: $u=x^2+2$ ($u'=2x$), $v=x+5$ ($v'=1$).

$$y' = 2x(x+5)+1(x^2+2) = 2x^2+10x+x^2+2 = 3x^2+10x+2$$
</details>

**4.** $\dfrac{x^2+4}{x+2}$
<details><summary>Pembahasan</summary>
Aturan pembagian: $f=x^2+4$ ($f'=2x$), $g=x+2$ ($g'=1$).

$$y' = \frac{2x(x+2)-(x^2+4)}{(x+2)^2} = \frac{x^2+4x-4}{(x+2)^2}$$
</details>

**5.** $(x^2+1)^5$
<details><summary>Pembahasan</summary>
Aturan rantai: $5(x^2+1)^4\cdot2x = 10x(x^2+1)^4$.
</details>

**6.** $(4x^3-1)^4$
<details><summary>Pembahasan</summary>
Aturan rantai: $4(4x^3-1)^3\cdot12x^2 = 48x^2(4x^3-1)^3$.
</details>

**7.** $(x^4+x)^3$
<details><summary>Pembahasan</summary>
Aturan rantai: $3(x^4+x)^2\cdot(4x^3+1)$.
</details>

**8.** $\big((x^2+1)^2+3\big)^4$
<details><summary>Pembahasan</summary>
Rantai bertingkat. Misal $u=(x^2+1)^2+3$, $u' = 2(x^2+1)\cdot2x = 4x(x^2+1)$.

$$y' = 4u^3\cdot u' = 4\cdot4x(x^2+1)\cdot\big((x^2+1)^2+3\big)^3 = 16x(x^2+1)\big((x^2+1)^2+3\big)^3$$
</details>

**9.** $(5x^2-4)^7$
<details><summary>Pembahasan</summary>
Aturan rantai: $7(5x^2-4)^6\cdot10x = 70x(5x^2-4)^6$.
</details>

**10.** $\left(\dfrac{x^2-1}{x+1}\right)^3$
<details><summary>Pembahasan</summary>
Cara cepat: $x^2-1=(x-1)(x+1)$, jadi $\dfrac{x^2-1}{x+1}=x-1$ (untuk $x\neq-1$), sehingga fungsinya sama dengan $(x-1)^3$ dan turunannya $3(x-1)^2$.

Cara lengkap (pembagian + rantai, tanpa penyederhanaan di awal) memberi hasil yang sama: misalkan $u=\dfrac{x^2-1}{x+1}$, dengan aturan pembagian $u' = \dfrac{2x(x+1)-(x^2-1)}{(x+1)^2} = \dfrac{x^2+2x+1}{(x+1)^2}=1$. Maka $y=u^3$, $y'=3u^2\cdot u' = 3\left(\dfrac{x^2-1}{x+1}\right)^2 = 3(x-1)^2$. Hasilnya sama.
</details>

**Tantangan.** $\big((2x^2+1)^3+4\big)^5$ — selesaikan tanpa memperluas bentuk aljabarnya.
<details><summary>Pembahasan</summary>
Misalkan $u=(2x^2+1)^3+4$. Turunan dalam: $u' = 3(2x^2+1)^2\cdot4x = 12x(2x^2+1)^2$.

$$y' = 5u^4\cdot u' = 5\cdot12x(2x^2+1)^2\cdot\big((2x^2+1)^3+4\big)^4 = 60x(2x^2+1)^2\big((2x^2+1)^3+4\big)^4$$
</details>

## Quiz Week 6

Latihan pilihan ganda dari dosen, semuanya seputar aturan rantai pada fungsi pangkat.

**1. Turunan pertama dari $f(x)=(x^2+3)^4$ adalah...**

A. $4x(x^2+3)^3$
B. $8x(x^2+3)^3$
C. $8(x^2+3)^4$
D. $4x(x^2+3)^4$
E. $2x(x^2+3)^3$

<details><summary>Pembahasan</summary>

Jawaban: **B**

Fungsi luar $(\cdot)^4$ diturunkan jadi $4(\cdot)^3$, lalu dikalikan turunan fungsi dalam $x^2+3$, yaitu $2x$. Hasilnya $4(x^2+3)^3 \cdot 2x = 8x(x^2+3)^3$. Opsi A adalah kesalahan umum: lupa mengalikan koefisien pangkat luar (4) dengan turunan dalam (2x) secara penuh — cuma sebagian faktornya yang kebawa.
</details>

**2. Jika $y=(3x^2-2x+1)^5$, maka $\dfrac{dy}{dx}$ adalah...**

A. $5(3x^2-2x+1)^4$
B. $(6x-2)(3x^2-2x+1)^4$
C. $5(6x-2)(3x^2-2x+1)^4$
D. $(15x-10)(3x^2-2x+1)^4$
E. $10(3x^2-2x+1)^4$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Turunan luar: $5(3x^2-2x+1)^4$. Turunan dalam: $6x-2$. Dikalikan: $5(6x-2)(3x^2-2x+1)^4$. Opsi A dan E salah karena tidak mengalikan turunan bagian dalam sama sekali (kesalahan umum #1 di modul). Opsi D terlihat mirip tapi $5(6x-2)=30x-10$, bukan $15x-10$.
</details>

**3. Diketahui $f(x)=(2x^3+x)^6$. Nilai $f'(x)$ adalah...**

A. $6(2x^3+x)^5$
B. $(6x^2+1)(2x^3+x)^5$
C. $6(6x^2+1)(2x^3+x)^5$
D. $(12x^2+1)(2x^3+x)^6$
E. $36x^2(2x^3+x)^5$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Turunan luar: $6(2x^3+x)^5$. Turunan dalam: $6x^2+1$. Hasil: $6(6x^2+1)(2x^3+x)^5$. Opsi A dan B sama-sama tidak lengkap mengalikan kedua turunan.
</details>

**4. Turunan dari fungsi $y=(x^3-2x^2+4)^4$ adalah...**

A. $4(x^3-2x^2+4)^3$
B. $(3x^2-4x)(x^3-2x^2+4)^3$
C. $4(3x^2-4x)(x^3-2x^2+4)^3$
D. $(12x^2-8x)(x^3-2x^2+4)^4$
E. $4(3x^2-2x)(x^3-2x^2+4)^3$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Turunan luar: $4(x^3-2x^2+4)^3$. Turunan dalam: $3x^2-4x$. Hasil: $4(3x^2-4x)(x^3-2x^2+4)^3$. Opsi E salah karena turunan dalamnya keliru ($3x^2-2x$, seharusnya koefisien $-4x$ bukan $-2x$ karena turunan $-2x^2$ adalah $-4x$).
</details>

**5. Jika $y=(2x^2+3x-1)^3$, maka turunan pertamanya adalah...**

A. $3(2x^2+3x-1)^2$
B. $(4x+3)(2x^2+3x-1)^2$
C. $3(4x+3)(2x^2+3x-1)^2$
D. $(12x+9)(2x^2+3x-1)^3$
E. $6(2x^2+3x-1)^2$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Turunan luar: $3(2x^2+3x-1)^2$. Turunan dalam: $4x+3$. Hasil: $3(4x+3)(2x^2+3x-1)^2$.
</details>

**6. Diketahui $y=\big((x^2+1)^2+3\big)^4$. Turunan pertama $y'$ adalah...**

A. $4\big((x^2+1)^2+3\big)^3$
B. $8x(x^2+1)\big((x^2+1)^2+3\big)^3$
C. $16x(x^2+1)\big((x^2+1)^2+3\big)^3$
D. $16x(x^2+1)^2\big((x^2+1)^2+3\big)^3$
E. $8x\big((x^2+1)^2+3\big)^4$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Ini rantai tiga lapis. Lapis luar: $4(\cdot)^3$. Lapis tengah ($(x^2+1)^2+3$, turunan terhadap $x^2+1$): $2(x^2+1)$. Lapis dalam ($x^2+1$): $2x$. Kalikan semua: $4\cdot2(x^2+1)\cdot2x = 16x(x^2+1)$, dikali $\big((x^2+1)^2+3\big)^3$. Opsi D sering dipilih karena salah menambah pangkat pada $(x^2+1)$ — padahal dari $2(x^2+1)\cdot2x$ hasilnya $4x(x^2+1)$ pangkat satu, bukan dua.
</details>

**7. Turunan dari $y=\big((2x^2+1)^3-4x\big)^5$ adalah...**

A. $5\big((2x^2+1)^3-4x\big)^4$
B. $\big(12x(2x^2+1)^2-4\big)\big((2x^2+1)^3-4x\big)^4$
C. $5\big(12x(2x^2+1)^2-4\big)\big((2x^2+1)^3-4x\big)^4$
D. $30x(2x^2+1)^2\big((2x^2+1)^3-4x\big)^5$
E. $5\big(6x(2x^2+1)^2-4\big)\big((2x^2+1)^3-4x\big)^4$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Turunan luar: $5(\cdot)^4$. Turunan dalam $(2x^2+1)^3-4x$ (perlu rantai lagi untuk suku pertamanya): $3(2x^2+1)^2\cdot4x - 4 = 12x(2x^2+1)^2-4$. Kalikan: $5\big(12x(2x^2+1)^2-4\big)\big((2x^2+1)^3-4x\big)^4$. Opsi E salah karena koefisien $12x$ keliru ditulis $6x$ (lupa mengalikan $3\times4x$ dengan benar).
</details>

**8. Jika $y=\big((x^3+2x)^2+1\big)^4$, maka $y'$ adalah...**

A. $4\big((x^3+2x)^2+1\big)^3$
B. $8(x^3+2x)\big((x^3+2x)^2+1\big)^3$
C. $8(3x^2+2)(x^3+2x)\big((x^3+2x)^2+1\big)^3$
D. $4(3x^2+2)(x^3+2x)\big((x^3+2x)^2+1\big)^3$
E. $8(3x^2+2)\big((x^3+2x)^2+1\big)^4$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Rantai tiga lapis lagi: lapis luar $4(\cdot)^3$, lapis tengah $2(x^3+2x)$, lapis dalam $3x^2+2$. Kalikan: $4\cdot2(x^3+2x)\cdot(3x^2+2) = 8(3x^2+2)(x^3+2x)$, dikali $\big((x^3+2x)^2+1\big)^3$.
</details>

**9. Turunan pertama dari $y=\big((3x^2-1)^4+2\big)^3$ adalah...**

A. $3\big((3x^2-1)^4+2\big)^2$
B. $24x(3x^2-1)^3\big((3x^2-1)^4+2\big)^2$
C. $72x(3x^2-1)^3\big((3x^2-1)^4+2\big)^2$
D. $72x(3x^2-1)^4\big((3x^2-1)^4+2\big)^3$
E. $36x(3x^2-1)^3\big((3x^2-1)^4+2\big)^2$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Lapis luar: $3(\cdot)^2$. Lapis tengah: $4(3x^2-1)^3$. Lapis dalam: $6x$. Kalikan semua: $3\cdot4(3x^2-1)^3\cdot6x = 72x(3x^2-1)^3$, dikali $\big((3x^2-1)^4+2\big)^2$. Opsi B salah karena koefisiennya kurang satu faktor ($3\times4\times6=72$, bukan $24$).
</details>

**10. Diketahui fungsi $f(x)=\big((x^2+1)^3-2x^2\big)^4$. Turunan pertama $f'(x)$ adalah...**

A. $4\big((x^2+1)^3-2x^2\big)^3$
B. $\big(6x(x^2+1)^2-4x\big)\big((x^2+1)^3-2x^2\big)^3$
C. $4\big(6x(x^2+1)^2-4x\big)\big((x^2+1)^3-2x^2\big)^3$
D. $24x(x^2+1)^2\big((x^2+1)^3-2x^2\big)^4$
E. $4\big(3x(x^2+1)^2-2x\big)\big((x^2+1)^3-2x^2\big)^3$

<details><summary>Pembahasan</summary>

Jawaban: **C**

Turunan luar: $4(\cdot)^3$. Turunan dalam $(x^2+1)^3-2x^2$ (butuh rantai lagi untuk suku pertama): $3(x^2+1)^2\cdot2x - 4x = 6x(x^2+1)^2-4x$. Kalikan: $4\big(6x(x^2+1)^2-4x\big)\big((x^2+1)^3-2x^2\big)^3$. Opsi E salah karena koefisien $6x$ tertulis $3x$ (lupa kalikan $3\times2x$ dengan benar).
</details>

## Dokumentasi

Foto catatan di kelas membahas penerapan aturan rantai, termasuk kasus bertingkat dan notasi Leibniz:

![Aturan rantai bertingkat untuk f(x)=((x+3)^9-6)^20](/assets/img/week6_1.jpeg)

![Notasi Leibniz dy/dt = dy/dx · dx/dt dan contoh f(x)=(x+3)^9-(x+3)^11](/assets/img/week6_2.jpeg)

## Refleksi

Materi aturan rantai minggu ini kerasa seperti "kunci" yang menyambungkan semua aturan turunan yang sudah dipelajari sebelumnya. Power rule, aturan perkalian, aturan pembagian, semuanya masih dipakai, cuma sekarang ditambah satu langkah lagi: mengenali kalau ada fungsi di dalam fungsi, lalu mengalikan turunan dari tiap lapisannya satu per satu.

Bagian yang paling bikin "klik" adalah waktu lihat contoh bertingkat tiga di papan tulis, $((x+3)^9-6)^{20}$. Awalnya keliatan rumit banget, tapi begitu dipecah jadi langkah: turunin luar dulu (tetap bawa isinya), baru turunin tengah, baru turunin yang paling dalam, terus dikalikan semua — jadi jauh lebih terstruktur dan nggak bikin bingung lagi.

Kesalahan umum yang paling sering kejadian (dan juga paling sering jadi jebakan di soal pilihan ganda) adalah lupa mengalikan turunan bagian dalam. Kelihatannya sepele, tapi kalau nggak hati-hati, hasilnya bisa salah total meskipun bagian luar sudah benar. Jadi pelajaran utamanya: selalu cek, "sudah dikalikan turunan dalamnya belum?"

Target minggu depan: lanjut eksplorasi turunan fungsi trigonometri dan eksponensial, karena kombinasi aturan rantai dengan fungsi-fungsi itu sepertinya bakal jadi langkah selanjutnya yang logis.
</content>