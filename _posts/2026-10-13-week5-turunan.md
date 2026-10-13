---
title: "Week 5: Pengantar Turunan (Derivatives)"
date: 2026-09-29 09:00:00 +0800
categories: [Calculus, Journaling]
tags: [turunan, derivative, power-rule, linear-approximation]
math: true
---

## Pengantar

Minggu ini masuk ke topik baru: **Turunan (Derivative)**. Intinya, turunan mengukur seberapa cepat suatu fungsi berubah. Kalau $x$ berubah sedikit, seberapa besar $y$ ikut berubah? Konsep ini dibangun dari limit yang sudah dipelajari di week 2, jadi terasa nyambung.

## 1. Definisi Turunan

Turunan fungsi $f$ di suatu titik $x_0$ didefinisikan sebagai:

$$f'(x_0) = \lim_{x \to x_0} \frac{f(x)-f(x_0)}{x-x_0}$$

Bentuk ini sebenarnya adalah **kemiringan (slope)** garis yang menghubungkan titik $(x_0, f(x_0))$ dan $(x, f(x))$, lalu diambil limitnya saat $x$ mendekati $x_0$, sehingga menjadi kemiringan garis singgung (tangent line) di titik itu.

Ada juga bentuk lain pakai notasi $\Delta x$ (atau $h$) untuk jarak antara $x$ dan $x_0$:

$$f'(x) = \lim_{\Delta x \to 0} \frac{f(x+\Delta x)-f(x)}{\Delta x}$$

Kedua bentuk ini sama saja, cuma beda cara penulisan. Notasi lain yang juga dipakai: $\dfrac{dy}{dx}$, dibaca "turunan y terhadap x" (bukan pecahan biasa, ini notasi).

## 2. Interpretasi Turunan sebagai Kecepatan Sesaat

Contoh klasik dari catatan kuliah: bola dilempar ke atas, posisinya mengikuti $f(t) = -16t^2+48t+4$. Kecepatan sesaat di $t=1$ dicari dengan:

$$f'(1) = \lim_{t \to 1} \frac{f(t)-f(1)}{t-1}$$

yang hasilnya 16. Jadi turunan di sini artinya **kecepatan sesaat** pada detik ke-1.

## 3. Aturan Dasar Turunan

**Turunan konstanta selalu nol.** Kalau $f(x) = c$ (konstanta), maka $f'(x) = 0$, untuk $c$ berapapun. Ini juga terlihat di papan tulis: $f(x)=6$ dan $f(x)=10$, dua-duanya punya turunan 0, karena nilainya tidak pernah berubah berapapun $x$-nya (grafiknya garis datar, jadi tidak "naik atau turun").

**Turunan fungsi linear.** Kalau $f(x) = mx+b$, maka $f'(x) = m$. Khususnya, turunan dari $f(x)=x$ adalah 1.

**Linearitas turunan.** Dua sifat penting:

$$\frac{d}{dx}\big[c \cdot f(x)\big] = c \cdot \frac{d}{dx}f(x) \qquad \frac{d}{dx}\big[f(x)+g(x)\big] = f'(x)+g'(x)$$

Artinya turunan dari konstanta kali fungsi = konstanta kali turunan fungsi, dan turunan dari jumlah dua fungsi = jumlah turunan masing-masing. Berlaku juga untuk pengurangan.

## 4. Menurunkan $f(x)=x^2$ dari Definisi (Langkah Lengkap)

Ini contoh yang dibahas detail di kelas:

$$f'(x) = \lim_{\Delta x \to 0} \frac{f(x+\Delta x)-f(x)}{\Delta x} = \lim_{\Delta x \to 0} \frac{(x+\Delta x)^2-x^2}{\Delta x}$$

Jabarkan $(x+\Delta x)^2 = x^2+2x\Delta x+\Delta x^2$:

$$= \lim_{\Delta x \to 0} \frac{x^2+2x\Delta x+\Delta x^2-x^2}{\Delta x} = \lim_{\Delta x \to 0} \frac{2x\Delta x+\Delta x^2}{\Delta x}$$

Sederhanakan (bagi dengan $\Delta x$):

$$= \lim_{\Delta x \to 0} (2x+\Delta x) = 2x$$

Jadi $f'(x) = 2x$. Kalau dihitung di $x=2$: $f'(2) = 2(2) = 4$.

## 5. Aturan Pangkat (Power Rule)

Dari pola di atas, ada aturan umum untuk menurunkan $x^n$:

$$\frac{d}{dx}x^n = n \cdot x^{n-1}$$

Aturan ini terbukti berlaku bahkan untuk pangkat pecahan atau negatif, contoh:

$$\frac{d}{dx}\sqrt{x} = \frac{d}{dx}x^{1/2} = \frac{1}{2}x^{-1/2} = \frac{1}{2\sqrt{x}} \qquad \frac{d}{dx}\frac{1}{x} = \frac{d}{dx}x^{-1} = -x^{-2} = -\frac{1}{x^2}$$

Dengan power rule plus linearitas, turunan **polinomial apa pun** bisa dicari suku per suku. Contoh dari catatan kuliah: $f(x) = x^7-4x^3+x+2$

$$f'(x) = 7x^6 - 4(3x^2) + 1 + 0 = 7x^6-12x^2+1$$

## 6. Turunan Kedua

Turunan dari turunan disebut **turunan kedua**, ditulis $f''(x)$ atau $\dfrac{d^2y}{dx^2}$. Dalam konteks fisika: kalau $f(t)$ adalah posisi, maka $f'(t)$ adalah kecepatan, dan $f''(t)$ adalah **percepatan**.

Contoh: untuk $f(t) = -16t^2+48t+4$ (posisi bola), $f'(t) = -32t+48$ (kecepatan), dan $f''(t) = -32$ (percepatan konstan akibat gravitasi, sekitar −32 ft/s²).

## 7. Pendekatan Linear (Linear Approximation)

Turunan juga bisa dipakai untuk **menaksir nilai fungsi** di titik dekat $x_0$ tanpa menghitung persis:

$$f(x) \approx f(x_0) + f'(x_0)(x-x_0)$$

**Contoh:** taksir $2.01^2$ tanpa kalkulator. Ambil $x_0=2$ (karena $2^2=4$ mudah dihitung), $x=2.01$. Untuk $f(x)=x^2$, sudah diketahui $f'(x)=2x$, jadi $f'(2)=4$.

$$2.01^2 \approx f(2) + f'(2)(2.01-2) = 4 + 4(0.01) = 4.04$$

Nilai sebenarnya $2.01^2 = 4.0401$, jadi taksirannya cukup akurat.

## Contoh Soal dan Pembahasan

**Soal 1.** Tentukan turunan $f(x)=x^3$ langsung dari definisi.

*Pembahasan:* Jabarkan $(x+h)^3 = x^3+3hx^2+3h^2x+h^3$, lalu:

$$f'(x) = \lim_{h \to 0} \frac{(x+h)^3-x^3}{h} = \lim_{h \to 0} \frac{3hx^2+3h^2x+h^3}{h} = \lim_{h \to 0} (3x^2+3hx+h^2) = 3x^2$$

Hasilnya cocok dengan power rule: $\dfrac{d}{dx}x^3 = 3x^{3-1} = 3x^2$.

**Soal 2.** Tentukan turunan $f(x)=\sqrt{x}$ langsung dari definisi (tanpa pakai power rule).

*Pembahasan:* Ini mirip teknik **merasionalkan** di materi limit (week 2). Mulai dari definisi dengan $h$:

$$f'(x) = \lim_{h \to 0} \frac{\sqrt{x+h}-\sqrt{x}}{h}$$

Kalikan dengan sekawan $\sqrt{x+h}+\sqrt{x}$:

$$= \lim_{h \to 0} \frac{(\sqrt{x+h}-\sqrt{x})(\sqrt{x+h}+\sqrt{x})}{h(\sqrt{x+h}+\sqrt{x})} = \lim_{h \to 0} \frac{(x+h)-x}{h(\sqrt{x+h}+\sqrt{x})} = \lim_{h \to 0} \frac{1}{\sqrt{x+h}+\sqrt{x}}$$

Substitusi $h=0$: hasilnya $\dfrac{1}{\sqrt{x}+\sqrt{x}} = \dfrac{1}{2\sqrt{x}}$, cocok dengan hasil power rule di atas.

**Soal 3.** Fungsi $f(x)=10$ (konstanta). Apakah fungsi ini naik atau turun di $x=4$?

*Pembahasan:* Karena $f(x)=10$ untuk semua $x$, nilainya tidak pernah berubah. Turunannya $f'(x) = 0$ (sesuai aturan turunan konstanta). Turunan nol berarti grafiknya **datar**, bukan naik maupun turun, di titik manapun termasuk di $x=4$.

## Quiz Week 5

Latihan soal fokus ke definisi turunan lewat limit.

**1. Definisi turunan $f'(x)$ dari sebuah fungsi $f$ adalah...**

A. $\displaystyle\lim_{h \to 0} \frac{f(x+h)+f(x)}{h}$
B. $\displaystyle\lim_{h \to 0} \frac{f(x+h)-f(x)}{h}$
C. $\displaystyle\lim_{h \to 0} \frac{f(x)-f(x+h)}{h}$
D. $\displaystyle\lim_{h \to 0} \frac{f(x+h)-f(x)}{x}$

<details>
<summary>Pembahasan</summary>

Jawaban: **B**

Ini bentuk baku definisi turunan dari limit: selisih nilai fungsi $f(x+h)-f(x)$ dibagi perubahan $h$, lalu diambil limit saat $h \to 0$. Opsi A salah tanda (seharusnya selisih, bukan jumlah), opsi C terbalik urutan pengurangannya (beda tanda), opsi D salah karena pembaginya harus $h$ (perubahan input), bukan $x$.
</details>

**2. Turunan $f'(x_0)$ secara geometris menyatakan...**

A. Kemiringan garis singgung (tangent line) kurva $y=f(x)$ di titik $x_0$
B. Luas daerah di bawah kurva $y=f(x)$ di titik $x_0$
C. Nilai fungsi $f$ di titik $x_0$
D. Jarak titik $(x_0, f(x_0))$ ke sumbu-x

<details>
<summary>Pembahasan</summary>

Jawaban: **A**

Turunan didefinisikan sebagai limit dari kemiringan garis sekan (yang menghubungkan dua titik pada kurva) saat kedua titik itu semakin berdekatan. Limitnya adalah kemiringan garis singgung di satu titik. Opsi B itu konsep integral, bukan turunan; opsi C itu nilai $f(x_0)$ sendiri, bukan turunannya; opsi D tidak relevan dengan definisi turunan.
</details>

**3. Jika $f(x) = 7$ untuk semua $x$ (fungsi konstan), maka $f'(x)$ sama dengan...**

A. $7$
B. $x$
C. $0$
D. Tidak terdefinisi

<details>
<summary>Pembahasan</summary>

Jawaban: **C**

Fungsi konstan tidak pernah berubah nilainya berapapun $x$-nya, jadi laju perubahannya nol di semua titik. Bisa juga dibuktikan dari definisi: $f(x+h)-f(x) = 7-7 = 0$, sehingga $\lim_{h\to0} \frac{0}{h} = 0$.
</details>

**4. Diketahui $f(x) = 3x+2$. Dengan definisi limit, $f'(x)$ sama dengan...**

A. $2$
B. $x$
C. $3x$
D. $3$

<details>
<summary>Pembahasan</summary>

Jawaban: **D**

$f(x+h)-f(x) = [3(x+h)+2] - [3x+2] = 3h$, sehingga $\dfrac{f(x+h)-f(x)}{h} = \dfrac{3h}{h} = 3$ (untuk $h \neq 0$), dan limitnya saat $h \to 0$ tetap $3$. Ini sesuai aturan: turunan fungsi linear $mx+b$ adalah kemiringannya sendiri, yaitu $m=3$.
</details>

**5. Bentuk $\displaystyle\lim_{h \to 0} \frac{(x+h)^2-x^2}{h}$ adalah definisi turunan dari fungsi...**

A. $f(x) = x^2$
B. $f(x) = x$
C. $f(x) = 2x$
D. $f(x) = x^2+h$

<details>
<summary>Pembahasan</summary>

Jawaban: **A**

Bentuk umum definisi turunan adalah $\lim_{h\to0} \frac{f(x+h)-f(x)}{h}$. Di sini, $f(x+h) = (x+h)^2$ dan $f(x) = x^2$, jadi fungsi aslinya adalah $f(x)=x^2$. (Hasil limitnya sendiri, $2x$, adalah $f'(x)$-nya — tapi pertanyaannya menanyakan $f(x)$ aslinya, bukan $f'(x)$.)
</details>

**6. Nilai dari $\displaystyle\lim_{h \to 0} \frac{(x+h)^2-x^2}{h}$ adalah...**

A. $x^2$
B. $2x$
C. $x$
D. $0$

<details>
<summary>Pembahasan</summary>

Jawaban: **B**

Jabarkan $(x+h)^2 = x^2+2xh+h^2$, sehingga pembilangnya menjadi $2xh+h^2 = h(2x+h)$. Dibagi $h$: $2x+h$. Saat $h \to 0$, hasilnya $2x$. Ini cocok dengan power rule: $\frac{d}{dx}x^2 = 2x^{2-1} = 2x$.
</details>

**7. Sebuah partikel punya posisi $s(t)$. Secara fisis, $s'(t)$ menyatakan...**

A. Kecepatan sesaat partikel pada waktu $t$
B. Percepatan partikel pada waktu $t$
C. Jarak total yang ditempuh partikel
D. Posisi awal partikel

<details>
<summary>Pembahasan</summary>

Jawaban: **A**

Turunan pertama dari fungsi posisi terhadap waktu adalah kecepatan sesaat (instantaneous velocity) — ini sama persis dengan contoh bola dilempar yang dibahas di materi: $f'(1)$ dari fungsi posisi $f(t)$ menghasilkan kecepatan di $t=1$. Percepatan (opsi B) adalah turunan *kedua* dari posisi, yaitu $s''(t)$.
</details>

**8. Sebuah fungsi $f$ dikatakan tidak memiliki turunan di titik $x_0$ jika...**

A. $f(x_0)$ bernilai nol
B. $f$ kontinu di $x_0$
C. Limit $\displaystyle\lim_{h \to 0} \frac{f(x_0+h)-f(x_0)}{h}$ tidak ada
D. $f(x_0)$ bernilai negatif

<details>
<summary>Pembahasan</summary>

Jawaban: **C**

Turunan di suatu titik *didefinisikan* sebagai limit tersebut. Kalau limitnya tidak ada (misalnya karena ada "patahan" tajam/sudut di grafik, atau garis singgungnya vertikal), maka turunan di titik itu tidak terdefinisi — meskipun fungsinya tetap kontinu di titik tersebut. Jadi kontinu (opsi B) tidak menjamin bisa diturunkan (differentiable); ini kebalikan dari yang sering disangka.
</details>

**9. Diberikan $f(x) = x^2+3x$. Nilai $f'(x)$ menggunakan definisi limit adalah...**

A. $x+3$
B. $2x$
C. $2x+x$
D. $2x+3$

<details>
<summary>Pembahasan</summary>

Jawaban: **D**

$f(x+h) = (x+h)^2+3(x+h) = x^2+2xh+h^2+3x+3h$. Maka $f(x+h)-f(x) = 2xh+h^2+3h = h(2x+h+3)$. Dibagi $h$ dan diambil limit saat $h\to0$: hasilnya $2x+3$. Ini juga cocok dengan aturan linearitas + power rule: turunan $x^2$ adalah $2x$, turunan $3x$ adalah $3$, dijumlah jadi $2x+3$.
</details>

**10. Mengapa definisi turunan menggunakan limit saat $h \to 0$, bukan langsung mensubstitusi $h=0$?**

A. Karena substitusi $h=0$ akan menghasilkan bentuk $\frac{0}{0}$ yang tidak terdefinisi secara langsung, sehingga perlu disederhanakan dulu sebelum limitnya bisa dihitung
B. Karena $h$ tidak boleh bernilai nol dalam matematika
C. Karena limit selalu memberi hasil yang berbeda dari substitusi langsung
D. Karena ini hanya aturan notasi, tidak ada alasan matematisnya

<details>
<summary>Pembahasan</summary>

Jawaban: **A**

Kalau $h=0$ langsung disubstitusi ke $\frac{f(x+h)-f(x)}{h}$, pembilang dan penyebutnya sama-sama nol, bentuk $\frac{0}{0}$ yang tidak terdefinisi. Makanya ekspresinya harus disederhanakan dulu (dijabarkan, difaktorkan, atau dirasionalkan — seperti di Soal 1-2 pada bagian Contoh Soal) sampai faktor $h$ di penyebut bisa dicoret, baru limitnya bisa dihitung dengan aman saat $h\to0$. Ini persis teknik yang sama dengan menghitung limit bentuk $\frac{0}{0}$ di materi week 2.
</details>

## Dokumentasi

Foto catatan di kelas membahas definisi turunan dan contoh penurunannya:

![Definisi turunan dari limit, notasi dy/dx](/assets/img/week5_1.jpeg)

![Contoh menurunkan f(x)=x^2 dan f(x)=konstanta](/assets/img/week5_2.jpeg)

![Catatan](/assets/img/week5_3.jpeg)

## Refleksi

Topik turunan minggu ini terasa seperti "lanjutan alami" dari limit di week 2, bahkan definisinya langsung memakai bentuk limit yang sudah dikenal. Yang menarik, teknik merasionalkan yang dipelajari waktu itu ternyata dipakai lagi di sini untuk menurunkan $\sqrt{x}$ dari definisi, jadi materi lama benar-benar kepakai lagi, bukan cuma lewat begitu saja.

Bagian yang paling membantu adalah power rule, karena setelah tahu aturan itu, tidak perlu lagi menurunkan dari limit satu-satu untuk tiap fungsi, tinggal pakai rumus $nx^{n-1}$ langsung. Tapi dengan dijelaskan prosesnya dari limit dulu, jadi lebih paham kenapa aturan itu bisa berlaku, bukan sekadar hafal rumus.

Konsep "turunan sebagai kecepatan sesaat" juga bikin materi ini terasa lebih konkret, karena ada contoh fisika (bola dilempar) yang menunjukkan turunan pertama = kecepatan, turunan kedua = percepatan. Ini jadi gambaran kenapa turunan penting di luar matematika murni.

Target minggu depan: latihan lebih banyak soal power rule untuk polinomial yang lebih kompleks, dan mulai belajar aturan turunan untuk perkalian dan pembagian fungsi (product rule dan quotient rule), karena linearitas saja belum cukup untuk fungsi yang dikalikan atau dibagi.