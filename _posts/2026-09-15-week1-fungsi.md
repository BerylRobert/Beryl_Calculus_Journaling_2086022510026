---
title: "Week 1: Mengenal Fungsi Real"
date: 2026-09-15 09:00:00 +0800
categories: [Calculus, Journaling]
tags: [fungsi, domain, range, komposisi-fungsi, invers-fungsi]
math: true
---

## Pengantar

Minggu pertama kuliah Calculus ini membahas Bab II: **Fungsi Real**. Materinya mencakup definisi fungsi, domain dan range, fungsi genap/ganjil, operasi aljabar pada fungsi, fungsi komposisi, dan fungsi invers. Berikut rangkuman dan catatan refleksi saya.

## 1. Apa itu Fungsi?

Fungsi bisa dibayangkan sebagai "mesin hitung": ia menerima masukan $x$ dan menghasilkan satu keluaran tunggal $f(x)$.

**Definisi formal:** Misalkan $A, B \subseteq \mathbb{R}$ yang tidak kosong. Sebuah fungsi $f: A \to B$ adalah aturan yang mengaitkan **setiap** unsur $x \in A$ dengan **tepat satu** nilai $y = f(x) \in B$.

- **Domain** ($D_f$): himpunan $A$, daerah asal
- **Kodomain**: himpunan $B$
- **Range** ($R_f$): himpunan semua nilai $f(x)$ yang benar-benar dihasilkan, $R_f = \{f(x) : x \in A\}$

Kalau domain tidak disebutkan secara spesifik, kita pakai **domain alami**: himpunan $x$ terbesar sehingga $f(x)$ menghasilkan bilangan real.

Contoh dari materi:
- $f(x) = 3 + \sqrt{1-2x}$ → syarat $1-2x \geq 0$, jadi $D_f = \left(-\infty, \tfrac{1}{2}\right]$
- $g(x) = \dfrac{x+1}{x-2}$ → syarat $x \neq 2$, jadi $D_g = \mathbb{R} - \{2\}$

## 2. Fungsi Genap dan Fungsi Ganjil

- **Fungsi genap**: $f(-x) = f(x)$ untuk semua $x \in D_f$ → grafik simetris terhadap sumbu $y$
- **Fungsi ganjil**: $f(-x) = -f(x)$ untuk semua $x \in D_f$ → grafik simetris terhadap titik asal $(0,0)$

Contoh: $f(x) = x^2 + 3$ adalah fungsi genap, sedangkan $f(x) = 2x^3 + 4x$ adalah fungsi ganjil. Ada juga fungsi yang bukan keduanya, misalnya $f(x) = x^4 + x^3 - 2x^2 + 3$.

## 3. Operasi Aljabar pada Fungsi

Jika $f$ dan $g$ punya domain $D$, maka:

$$(f+g)(x) = f(x)+g(x) \qquad (f-g)(x) = f(x)-g(x)$$

$$(fg)(x) = f(x)\,g(x) \qquad \left(\frac{f}{g}\right)(x) = \frac{f(x)}{g(x)},\ g(x)\neq 0$$

Domain hasil operasi adalah irisan domain $f$ dan $g$ (untuk pembagian, ditambah syarat $g(x) \neq 0$).

## 4. Fungsi Komposisi

Ini bagian yang paling banyak saya latih di kelas (lihat foto papan tulis). Fungsi komposisi $g \circ f$ artinya "f dilanjutkan g":

$$(g \circ f)(x) = g(f(x))$$

**Contoh latihan di kelas:** diketahui $f(x) = 2x+1$ dan $(f \circ g)(x) = 4x+2$, cari $g(x)$.

Karena $(f \circ g)(x) = f(g(x)) = 2\,g(x) + 1$, maka:

$$2g(x) + 1 = 4x + 2 \implies g(x) = \frac{4x+1}{2}$$

Pola pengerjaannya: substitusi aturan $f$ ke variabel $g(x)$, lalu samakan dengan hasil yang diketahui, baru selesaikan $g(x)$ secara aljabar.

Catatan penting: **komposisi tidak komutatif**, $g \circ f \neq f \circ g$ secara umum.

## 5. Fungsi Invers

Fungsi invers $f^{-1}$ "membalik" fungsi $f$, dengan sifat:

$$f\left(f^{-1}(x)\right) = x \qquad f^{-1}\left(f(x)\right) = x$$

**Contoh dari papan tulis:** $f(x) = 3x - 1$. Untuk mencari invers:

1. Tulis $y = 3x - 1$
2. Selesaikan $x$ dalam $y$: $x = \dfrac{y+1}{3}$
3. Tukar peran, jadi $f^{-1}(x) = \dfrac{x+1}{3}$

## Contoh Soal dan Pembahasan

**Soal 1 (Domain).** Tentukan domain dari $f(x) = \dfrac{\sqrt{x+2}}{x-1}$.

*Pembahasan:* Ada dua syarat yang harus dipenuhi sekaligus:
- Nilai di dalam akar tidak boleh negatif: $x + 2 \geq 0 \implies x \geq -2$
- Penyebut tidak boleh nol: $x - 1 \neq 0 \implies x \neq 1$

Jadi domainnya $\{x \mid x \in \mathbb{R},\ x \geq -2,\ x \neq 1\}$.

**Soal 2 (Invers).** Diketahui $f(x) = 5x - 2$. Tentukan nilai $f^{-1}(18)$.

*Pembahasan:* Ada dua cara. Cara cepat: cari $x$ sehingga $f(x) = 18$.

$$5x - 2 = 18 \implies 5x = 20 \implies x = 4$$

Jadi $f^{-1}(18) = 4$. (Cara lain: cari dulu rumus $f^{-1}(x) = \dfrac{x+2}{5}$, lalu substitusi $x=18$, hasilnya sama.)

**Soal 3 (Komposisi).** Diketahui $f(x) = x^2$ dan $g(x) = x+2$. Tentukan $(g \circ f)(3)$.

*Pembahasan:* $(g \circ f)(x) = g(f(x))$, jadi hitung $f(3)$ dulu, baru masukkan hasilnya ke $g$.

$$f(3) = 3^2 = 9 \qquad g(9) = 9 + 2 = 11$$

Jadi $(g \circ f)(3) = 11$. Urutan pengerjaan ini penting, jangan dibalik.

**Soal 4 (Konsep).** Mengapa $f(x) = x^2$ tidak punya invers pada domain bilangan real?

*Pembahasan:* Karena fungsi ini tidak **satu-satu** (tidak injektif): ada dua nilai $x$ berbeda yang menghasilkan $y$ yang sama, misalnya $f(2) = 4$ dan $f(-2) = 4$. Supaya punya invers, setiap output harus berasal dari tepat satu input.

## Quiz Week 1

Berikut soal pilihan ganda dari materi minggu ini. Coba jawab dulu sebelum membuka pembahasannya.

### A. Domain dan Range

1. Domain dari $f(x) = \dfrac{2}{x-3}$ adalah . . .
   A. $\{x \mid x \neq 2\}$　B. $\{x \mid x \neq 3\}$　C. $\{x \mid x > 3\}$　D. $\{x \mid x < 3\}$　E. $\mathbb{R}$

   <details><summary>Pembahasan</summary>
   Jawaban: B.<br>
   Bentuk ini adalah pecahan, jadi syaratnya cuma satu: penyebut tidak boleh nol. $x - 3 \neq 0 \implies x \neq 3$. Tidak ada syarat lain (tidak ada akar), jadi domainnya semua bilangan real kecuali 3.
   </details>

2. Domain dari $f(x) = \sqrt{5-x}$ adalah . . .
   A. $x \geq 5$　B. $x \leq 5$　C. $x < 5$　D. $x \neq 5$　E. $\mathbb{R}$

   <details><summary>Pembahasan</summary>
   Jawaban: B.<br>
   Nilai di dalam akar kuadrat tidak boleh negatif (karena akar dari bilangan negatif bukan bilangan real). Jadi syaratnya $5 - x \geq 0$. Pindahkan $x$ ke kanan: $5 \geq x$, atau ditulis $x \leq 5$.
   </details>

3. Range dari $f(x) = x^2+1$ dengan domain $\mathbb{R}$ adalah . . .
   A. $y \geq 0$　B. $y < 1$　C. $y \geq 1$　D. $y \leq 1$　E. $\mathbb{R}$

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   $x^2$ nilai terkecilnya adalah 0 (tercapai saat $x=0$), dan tidak pernah negatif untuk $x$ real berapa pun. Jadi nilai terkecil $f(x) = x^2+1$ adalah $0+1=1$, dan nilainya terus naik tanpa batas atas. Jadi range-nya $y \geq 1$.
   </details>

4. $f(x)=2x-5$ dengan domain $-1 \leq x \leq 4$. Range-nya adalah . . .
   A. $-7 \leq y \leq 3$　B. $-3 \leq y \leq 8$　C. $-7 \leq y \leq 3$　D. $-5 \leq y \leq 3$　E. $3 \leq y \leq 8$

   <details><summary>Pembahasan</summary>
   Jawaban: $-7 \leq y \leq 3$ (opsi A).<br>
   Karena $f(x)=2x-5$ adalah fungsi linear dengan koefisien $x$ positif, fungsinya selalu naik. Artinya nilai minimum dan maksimum $f(x)$ pasti terjadi tepat di ujung-ujung domainnya. Substitusi batas bawah: $f(-1) = 2(-1)-5 = -7$. Substitusi batas atas: $f(4) = 2(4)-5 = 3$. Jadi range-nya dari $-7$ sampai $3$.
   </details>

5. Domain dari $f(x) = \dfrac{\sqrt{x+2}}{x-1}$ adalah . . .
   A. $x \geq -2$　B. $x < -2$　C. $x \geq -2,\ x \neq 1$　D. $x \neq 1$　E. $\mathbb{R}$

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Ini gabungan dua aturan sekaligus karena ada akar DAN pecahan. Syarat dari akar: $x+2 \geq 0 \implies x \geq -2$. Syarat dari penyebut: $x - 1 \neq 0 \implies x \neq 1$. Keduanya harus dipenuhi bersamaan, jadi domainnya $x \geq -2$ tapi $x$ tidak boleh sama dengan 1.
   </details>

### B. Invers Fungsi

6. Invers dari $f(x) = 2x+7$ adalah . . .
   A. $\dfrac{x+7}{2}$　B. $\dfrac{x-7}{2}$　C. $2x-7$　D. $\dfrac{7-x}{2}$　E. $2x+7$

   <details><summary>Pembahasan</summary>
   Jawaban: B.<br>
   Langkah mencari invers: tulis sebagai $y = 2x+7$, lalu selesaikan $x$ dalam $y$: $y - 7 = 2x \implies x = \dfrac{y-7}{2}$. Terakhir, tukar peran $x$ dan $y$ (karena invers membalik arah fungsi), sehingga $f^{-1}(x) = \dfrac{x-7}{2}$.
   </details>

7. Jika $f(x) = \dfrac{x-4}{3}$, maka $f^{-1}(x)$ adalah . . .
   A. $3x-4$　B. $3x+4$　C. $\dfrac{x+4}{3}$　D. $\dfrac{x-4}{3}$　E. $4-3x$

   <details><summary>Pembahasan</summary>
   Jawaban: B.<br>
   Tulis $y = \dfrac{x-4}{3}$. Kalikan kedua ruas dengan 3: $3y = x - 4$. Selesaikan $x$: $x = 3y+4$. Tukar peran $x$ dan $y$: $f^{-1}(x) = 3x+4$.
   </details>

8. Diketahui $f(x)=5x-2$. Nilai $f^{-1}(18)$ adalah . . .
   A. 2　B. 3　C. 4　D. 5　E. 6

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Cara paling cepat tanpa mencari rumus invers dulu: $f^{-1}(18)$ artinya "nilai $x$ yang kalau dimasukkan ke $f$ menghasilkan 18". Jadi selesaikan $5x - 2 = 18 \implies 5x = 20 \implies x = 4$.
   </details>

9. Fungsi $f(x)=x^2$ tidak punya invers pada domain real karena . . .
   A. tidak punya range　B. tidak kontinu　C. tidak satu-satu　D. tidak terdefinisi　E. tidak punya domain

   <details><summary>Pembahasan</summary>
   Jawaban: C.<br>
   Syarat fungsi punya invers adalah harus satu-satu (setiap output cuma berasal dari satu input). Pada $f(x)=x^2$, ada dua input berbeda yang menghasilkan output sama, contoh $f(2)=4$ dan $f(-2)=4$. Karena satu output (4) berasal dari dua input berbeda, fungsi ini tidak satu-satu, jadi tidak punya invers di seluruh domain real.
   </details>

10. Diketahui $f(x) = \dfrac{3x+1}{2}$. Nilai $f^{-1}(8)$ adalah . . .
    A. 3　B. 4　C. 5　D. 6　E. 7

    <details><summary>Pembahasan</summary>
    Jawaban: C.<br>
    Sama seperti soal 8, cari $x$ yang menghasilkan 8: $\dfrac{3x+1}{2} = 8 \implies 3x+1 = 16 \implies 3x = 15 \implies x = 5$.
    </details>

### C. Fungsi Komposisi

11. Diketahui $f(x)=2x+1$ dan $g(x)=x-3$. Bentuk $(f \circ g)(x)$ adalah . . .
    A. $2x-5$　B. $2x+4$　C. $x-2$　D. $2x-2$　E. $x+1$

    <details><summary>Pembahasan</summary>
    Jawaban: A.<br>
    $(f \circ g)(x) = f(g(x))$, artinya $g(x)$ dimasukkan ke posisi $x$ pada rumus $f$. $f(g(x)) = 2 \cdot g(x) + 1 = 2(x-3)+1 = 2x-6+1 = 2x-5$.
    </details>

12. Diketahui $f(x)=x^2$ dan $g(x)=x+2$. Nilai $(g \circ f)(3)$ adalah . . .
    A. 9　B. 11　C. 13　D. 25　E. 27

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    $(g \circ f)(3) = g(f(3))$, jadi hitung $f(3)$ dulu, baru masukkan ke $g$. $f(3) = 3^2 = 9$, lalu $g(9) = 9+2 = 11$. Urutan ini penting: fungsi yang ditulis paling dekat dengan $x$ (di sini $f$) dikerjakan lebih dulu.
    </details>

13. Jika $f(x)=3x$ dan $g(x)=x+4$, maka $(g \circ f)(x)$ adalah . . .
    A. $3x$　B. $3x+4$　C. $3x+12$　D. $x+12$　E. $7x$

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    $(g \circ f)(x) = g(f(x))$, hitung $f(x)$ dulu lalu masukkan ke $g$: $g(3x) = 3x+4$ (tinggal substitusi $3x$ ke posisi $x$ pada rumus $g(x) = x+4$).
    </details>

14. Diketahui $f(x)=x-1$ dan $g(x)=2x$. Nilai $(f \circ g)(5)$ adalah . . .
    A. 8　B. 9　C. 10　D. 11　E. 12

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    Hitung $g(5)$ dulu karena $g$ ditulis paling dekat dengan $x$: $g(5) = 2(5) = 10$. Lalu masukkan ke $f$: $f(10) = 10-1 = 9$.
    </details>

15. Jika $f(x)=x+1$ dan $g(x)=x^2$, maka $(f \circ g)(x)$ adalah . . .
    A. $x^2$　B. $(x+1)^2$　C. $x^2+1$　D. $2x+1$　E. $x^2+x$

    <details><summary>Pembahasan</summary>
    Jawaban: C.<br>
    $(f \circ g)(x) = f(g(x))$, substitusi $g(x) = x^2$ ke posisi $x$ pada rumus $f(x) = x+1$, sehingga $f(x^2) = x^2+1$. Hati-hati jangan tertukar dengan opsi B, yang itu hasil kalau urutannya dibalik jadi $(g \circ f)(x) = (x+1)^2$.
    </details>

### D. Pemahaman Konsep

16. Pernyataan yang benar tentang domain adalah . . . (1) himpunan nilai masukan (2) himpunan nilai keluaran (3) ditentukan dari syarat fungsi terdefinisi (4) selalu sama dengan range
    A. 1 dan 2　B. 1 dan 3　C. 2 dan 4　D. 3 dan 4　E. 1,2,3,4

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    Pernyataan (1) benar, sesuai definisi: domain adalah himpunan nilai $x$ (masukan). Pernyataan (2) salah, karena itu justru definisi range, bukan domain. Pernyataan (3) benar, domain memang ditentukan dari syarat supaya fungsi terdefinisi (misalnya akar tidak negatif, penyebut tidak nol). Pernyataan (4) salah, karena pada umumnya domain dan range adalah dua himpunan yang berbeda. Jadi yang benar (1) dan (3).
    </details>

17. Mengapa $f(x)=\sqrt{x-2}$ punya syarat domain $x \geq 2$?
    A. Agar hasil selalu positif　B. Penyebut tidak boleh nol　C. Nilai di dalam akar harus ≥ 0　D. x tidak boleh negatif　E. Agar fungsi punya invers

    <details><summary>Pembahasan</summary>
    Jawaban: C.<br>
    Akar kuadrat dari bilangan negatif tidak menghasilkan bilangan real, jadi syarat dasarnya adalah bilangan di dalam akar harus $\geq 0$. Di sini $x - 2 \geq 0 \implies x \geq 2$. Opsi B tidak relevan karena tidak ada pecahan di soal ini.
    </details>

18. Suatu fungsi memiliki invers jika . . .
    A. Domain dan range sama banyak　B. Grafik memotong sumbu-X sekali　C. Setiap domain punya tepat satu pasangan　D. Setiap output berasal dari tepat satu input (satu-satu)　E. Fungsi berbentuk garis lurus

    <details><summary>Pembahasan</summary>
    Jawaban: D.<br>
    Syarat kunci punya invers adalah fungsi tersebut satu-satu (injektif): tidak boleh ada dua input berbeda yang menghasilkan output yang sama. Kalau syarat ini dilanggar (seperti pada $f(x)=x^2$ di soal 9), proses "membalik" fungsi jadi ambigu karena tidak jelas input mana yang harus dikembalikan.
    </details>

19. Pernyataan yang benar tentang $(f \circ g)(x)$ adalah . . .
    A. f dihitung dulu, baru g　B. g dihitung dulu, hasilnya jadi masukan f　C. f dan g selalu sama　D. Hanya berlaku untuk fungsi linear　E. $(f \circ g)(x) = (g \circ f)(x)$ selalu

    <details><summary>Pembahasan</summary>
    Jawaban: B.<br>
    Notasi $(f \circ g)(x)$ dibaca sebagai $f(g(x))$, jadi $g$ yang berada paling dekat dengan $x$ dikerjakan lebih dulu, dan hasilnya baru dimasukkan sebagai input untuk $f$. Ini juga kenapa urutannya penting, seperti terlihat di soal 12 dan 14.
    </details>

20. Pernyataan yang benar tentang domain, range, invers, dan komposisi . . .
    A. Range adalah himpunan nilai masukan　B. Semua fungsi pasti punya invers　C. Komposisi selalu komutatif　D. Invers diperoleh dengan menukar peran input-output pada fungsi satu-satu　E. Domain ditentukan oleh himpunan hasil fungsi

    <details><summary>Pembahasan</summary>
    Jawaban: D.<br>
    Opsi A salah (itu domain, bukan range). Opsi B salah (lihat soal 9 dan 18, harus satu-satu dulu). Opsi C salah (lihat catatan di materi: $g \circ f \neq f \circ g$ secara umum). Opsi E salah (domain ditentukan dari nilai masukan yang valid, bukan dari hasil). Opsi D benar dan sesuai cara kerja mencari invers yang dibahas di bagian B.
    </details>

## Dokumentasi

Foto catatan dan diskusi fungsi komposisi serta invers fungsi di kelas:

![Diskusi fungsi komposisi di papan tulis](/assets/img/week1_1.jpeg)

![Latihan invers fungsi di papan tulis](/assets/img/week1_2.jpeg)

## Refleksi

Materi minggu ini sebenarnya bukan hal baru total, karena konsep domain dan range mirip dengan yang pernah dibahas sepintas waktu SMA. Yang terasa lebih menantang adalah bagian **fungsi komposisi**, terutama saat soalnya dibalik, yaitu diketahui hasil komposisinya lalu diminta mencari salah satu fungsi penyusunnya. Butuh beberapa kali coba untuk terbiasa dengan urutan substitusinya.

Bagian **invers fungsi** terasa lebih mudah karena polanya cukup jelas: tulis sebagai $y = f(x)$, selesaikan $x$ dalam $y$, lalu tukar perannya. Konsep "fungsi harus satu-satu untuk punya invers" juga jadi lebih masuk akal setelah lihat contoh $f(x) = x^2$ yang gagal karena dua input berbeda bisa menghasilkan output yang sama.

Kalau dikaitkan dengan pemrograman, konsep fungsi di sini sebenarnya mirip dengan fungsi murni (pure function) di coding, satu input selalu menghasilkan satu output yang pasti. Komposisi fungsi juga mengingatkan pada kebiasaan memanggil fungsi di dalam fungsi lain.

Target minggu depan: lebih cepat mengenali syarat domain di soal gabungan (akar dan pecahan sekaligus), karena itu bagian yang masih sering bikin ragu.