---
title: "Week 3: Persiapan AFL 1 (Fungsi, Komposisi, Invers, dan Limit)"
date: 2026-09-29 09:00:00 +0800
categories: [Calculus, Journaling]
tags: [afl-1, komposisi-fungsi, invers-fungsi, limit]
math: true
---

## Pengantar

Minggu ini tidak ada materi baru. Dosen membagikan **kisi-kisi untuk AFL 1** (Assessment for Learning 1), yang mencakup seluruh materi dari week 1 dan week 2: fungsi, komposisi fungsi, invers fungsi, dan limit. Di kelas juga sempat dibahas dua contoh soal yang ternyata polanya sama persis dengan soal di kisi-kisi, jadi aku dokumentasikan sekalian sebagai bahan latihan.

## Cakupan Materi AFL 1

- Fungsi dan komposisi fungsi
- Domain fungsi komposisi
- Invers fungsi dan invers fungsi komposisi
- Limit fungsi aljabar
- Faktorisasi dalam penyelesaian limit
- Rasionalisasi dalam penyelesaian limit
- Limit fungsi bersyarat dan limit kiri-kanan

**Distribusi soal** (5 soal, masing-masing bobot 20%):

| No. | Materi |
|---|---|
| 1 | Komposisi Fungsi dan Domain |
| 2 | Invers Komposisi Fungsi |
| 3 | Invers Fungsi berdasarkan $g \circ f$ |
| 4 | Limit Faktorisasi dan Rasionalisasi |
| 5 | Limit Fungsi Bersyarat |

## Kompetensi yang Perlu Dikuasai

1. Menentukan hasil komposisi dua fungsi: $(f \circ g)(x) = f(g(x))$
2. Menentukan domain fungsi dengan memperhatikan: penyebut tidak boleh nol, bilangan dalam akar harus non-negatif, dan pembatasan domain akibat komposisi
3. Menentukan invers fungsi aljabar dengan memanipulasi $y = f(x)$
4. Memahami hubungan antara fungsi, komposisi, dan invers
5. Menentukan nilai invers dari fungsi komposisi
6. Menyelesaikan limit bentuk tak tentu dengan faktorisasi
7. Menyelesaikan limit bentuk akar dengan rasionalisasi
8. Menentukan limit kiri $\left(\lim\limits_{x \to a^-} f(x)\right)$ dan limit kanan $\left(\lim\limits_{x \to a^+} f(x)\right)$
9. Menentukan parameter pada fungsi bersyarat berdasarkan syarat limit kiri = limit kanan
10. Menentukan nilai parameter yang membuat limit fungsi ada pada titik tertentu

## Latihan Soal AFL 1 (Paket B)

### Soal 1: Komposisi Fungsi dan Domain

Diberikan $f(x) = \dfrac{x-4}{2x+1}$ dan $g(x) = \sqrt{3x+6}$. Jika $h(x) = (f \circ g)(x)$, tentukan domain $h(x)$.

<details><summary>Pembahasan</summary>

$$h(x) = f(g(x)) = \frac{g(x)-4}{2g(x)+1} = \frac{\sqrt{3x+6}-4}{2\sqrt{3x+6}+1}$$

Domain $h$ ditentukan oleh dua syarat:

1. **Syarat akar:** $3x+6 \geq 0 \implies x \geq -2$
2. **Syarat penyebut tidak nol:** $2\sqrt{3x+6}+1 \neq 0$

Untuk syarat kedua, perhatikan bahwa $\sqrt{3x+6} \geq 0$ selalu (akar kuadrat tidak pernah negatif). Akibatnya $2\sqrt{3x+6} \geq 0$, sehingga $2\sqrt{3x+6}+1 \geq 1$. Artinya penyebutnya **tidak pernah bisa nol**, berapa pun nilai $x$ yang valid. Syarat kedua otomatis terpenuhi, tidak perlu mengecualikan nilai $x$ tambahan.

**Jadi domain $h$ hanya ditentukan oleh syarat akar:**

$$D_h = \{x \mid x \in \mathbb{R},\ x \geq -2\} = [-2, \infty)$$

*Catatan:* kalau mencoba menyelesaikan $2\sqrt{3x+6}+1=0$ secara aljabar (dengan mengkuadratkan kedua ruas), akan muncul nilai $x = -\frac{23}{12}$. Tapi ini adalah **akar palsu (extraneous root)**: nilai itu muncul karena proses pengkuadratan menghilangkan informasi tanda, padahal persamaan aslinya ($\sqrt{3x+6} = -\frac{1}{2}$) sebenarnya mustahil, karena ruas kiri tidak pernah negatif. Jadi nilai itu tidak boleh ikut mengecualikan domain.
</details>

### Soal 2: Invers Komposisi Fungsi

Diberikan $f(x) = \dfrac{2x+5}{x-3}$, $x \neq 3$, dan $g(x) = 3x+1$. Jika $h(x) = (f \circ g)(x)$, tentukan nilai $h^{-1}(2)$.

<details><summary>Pembahasan</summary>

$$h(x) = f(g(x)) = \frac{2(3x+1)+5}{(3x+1)-3} = \frac{6x+7}{3x-2}$$

Untuk mencari $h^{-1}(2)$, cari $x$ yang membuat $h(x)=2$:

$$\frac{6x+7}{3x-2} = 2 \implies 6x+7 = 2(3x-2) = 6x-4 \implies 7 = -4$$

Ini kontradiksi (7 tidak sama dengan −4), artinya **tidak ada nilai $x$** yang menghasilkan $h(x)=2$. Dengan kata lain, 2 bukan bagian dari range $h$, jadi $h^{-1}(2)$ **tidak terdefinisi**.

Ini bisa dicek juga dengan mencari rumus $h^{-1}(x)$ secara umum terlebih dahulu: dari $y = \dfrac{6x+7}{3x-2}$, selesaikan $x$ dalam $y$, diperoleh $x = \dfrac{7+2y}{3y-6}$. Substitusi $y=2$: penyebutnya menjadi $3(2)-6=0$, jadi hasilnya $\dfrac{11}{0}$, pembagian dengan nol, tidak terdefinisi. Dua cara ini memberi kesimpulan yang sama.
</details>

### Soal 3: Menentukan Invers f(x) dari Komposisi

Diketahui $g(x) = \dfrac{2x-1}{x+2}$ dan $(g \circ f)(x) = \dfrac{x+5}{2x-1}$. Tentukan $f^{-1}(3)$.

<details><summary>Pembahasan</summary>

Misalkan $u = f(x)$. Karena $(g \circ f)(x) = g(f(x)) = g(u)$, maka:

$$\frac{2u-1}{u+2} = \frac{x+5}{2x-1}$$

Kalikan silang:

$$(2u-1)(2x-1) = (x+5)(u+2)$$

$$4ux - 2u - 2x + 1 = xu + 2x + 5u + 10$$

Kumpulkan suku dengan $u$ di satu ruas:

$$4ux - xu - 2u - 5u = 2x + 2x + 10 - 1$$

$$3xu - 7u = 4x + 9 \implies u(3x-7) = 4x+9 \implies u = f(x) = \frac{4x+9}{3x-7}$$

Sekarang cari $f^{-1}(3)$, artinya cari $x$ yang membuat $f(x)=3$:

$$\frac{4x+9}{3x-7} = 3 \implies 4x+9 = 3(3x-7) = 9x-21 \implies 30 = 5x \implies x = 6$$

Jadi $f^{-1}(3) = 6$. (Cek: $f(6) = \frac{24+9}{18-7} = \frac{33}{11} = 3$, benar.)
</details>

### Soal 4: Limit dengan Faktorisasi dan Rasionalisasi

Tentukan nilai $\lim\limits_{x \to 16} \left[ \dfrac{x^2-256}{x-16} + \dfrac{\sqrt{x+9}-5}{x-16} \right]$.

<details><summary>Pembahasan</summary>

Kerjakan dua suku secara terpisah.

**Suku pertama (faktorisasi):**

$$\frac{x^2-256}{x-16} = \frac{(x-16)(x+16)}{x-16} = x+16$$

Substitusi $x=16$: hasilnya $16+16=32$.

**Suku kedua (rasionalisasi):** kalikan dengan sekawan $\sqrt{x+9}+5$:

$$\frac{\sqrt{x+9}-5}{x-16} \times \frac{\sqrt{x+9}+5}{\sqrt{x+9}+5} = \frac{(x+9)-25}{(x-16)(\sqrt{x+9}+5)} = \frac{x-16}{(x-16)(\sqrt{x+9}+5)} = \frac{1}{\sqrt{x+9}+5}$$

Substitusi $x=16$: $\sqrt{25}=5$, jadi hasilnya $\dfrac{1}{5+5} = \dfrac{1}{10}$.

**Jumlahkan kedua hasil:**

$$32 + \frac{1}{10} = \frac{321}{10} = 32\frac{1}{10}$$
</details>

### Soal 5: Limit Fungsi Bersyarat

Diberikan $f(x) = \begin{cases} \dfrac{x^2-16}{x-4}, & x<4 \\ ax+b, & 4 \leq x < 6 \\ \dfrac{x^2-36}{x-6}+5, & x \geq 6 \end{cases}$. Jika $f(x)$ memiliki limit pada $x=4$ dan $x=6$, tentukan $a+b$.

<details><summary>Pembahasan</summary>

Supaya limit ada di suatu titik, limit kiri harus sama dengan limit kanan.

**Di $x=4$:**

Limit kiri (pakai persamaan pertama, sudah difaktorkan): $\dfrac{x^2-16}{x-4} = \dfrac{(x-4)(x+4)}{x-4} = x+4$, substitusi $x=4$: hasilnya $8$.

Limit kanan (pakai persamaan kedua): $a(4)+b = 4a+b$.

Syarat limit ada: $4a+b = 8$ ... (i)

**Di $x=6$:**

Limit kiri (pakai persamaan kedua): $a(6)+b = 6a+b$.

Limit kanan (pakai persamaan ketiga, difaktorkan): $\dfrac{x^2-36}{x-6}+5 = (x+6)+5$, substitusi $x=6$: hasilnya $12+5=17$.

Syarat limit ada: $6a+b = 17$ ... (ii)

**Selesaikan sistem persamaan (i) dan (ii):** kurangi (ii) dengan (i):

$$(6a+b)-(4a+b) = 17-8 \implies 2a = 9 \implies a = \frac{9}{2}$$

Substitusi ke (i): $4\left(\frac{9}{2}\right)+b = 8 \implies 18+b=8 \implies b=-10$

**Jadi:**

$$a+b = \frac{9}{2} - 10 = \frac{9}{2} - \frac{20}{2} = -\frac{11}{2}$$
</details>

## Dokumentasi

Foto latihan soal 1 dan soal 2 (persis sama dengan yang ada di kisi-kisi) yang dibahas bersama di kelas:

![Latihan domain fungsi komposisi di papan tulis](/assets/img/week3_1.jpeg)

![Latihan invers komposisi fungsi di papan tulis](/assets/img/week3_2.jpeg)

## Refleksi

Minggu ini lebih ke arah konsolidasi daripada belajar hal baru, karena fokusnya menyiapkan diri untuk AFL 1. Justru dari proses mengerjakan ulang soal latihan ini aku sadar ada detail kecil yang gampang terlewat, misalnya soal domain fungsi komposisi di Soal 1, ternyata proses pengkuadratan saat mencari syarat penyebut bisa menghasilkan akar palsu yang sebenarnya tidak valid. Kalau tidak dicek ulang dengan logika (akar kuadrat tidak pernah negatif), bisa saja salah menyimpulkan domainnya lebih sempit dari yang seharusnya.

Soal 2 juga memberi insight menarik: tidak semua fungsi komposisi punya invers di setiap titik, karena ada nilai yang memang tidak termasuk dalam range-nya (di sini karena fungsi rasionalnya punya asimtot horizontal). Ini mengingatkan untuk tidak buru-buru menyamakan sebuah persamaan dan menyelesaikannya secara mekanis, tapi mengecek dulu apakah penyelesaiannya masuk akal.

Target sebelum AFL 1: ulang semua 5 tipe soal di kisi-kisi beberapa kali dengan angka berbeda (karena Paket B dan C beda angka tapi pola sama), supaya lebih terbiasa dengan langkah-langkahnya, bukan cuma hafal hasil akhirnya.