# 📖 Catatan Course: Fundamentals of Probability

## Coretan

**Permutasi** adalah cara penyusunan suatu kumpulan objek dengan urutan pemilihan yang diperhatikan.

$$
P(n, r) = \frac{n!}{(n - r)!}
$$

dengan $n$ adalah banyaknya elemen dan $r$ adalah banyaknya elemen yang diambil.

**Kombinasi** adalah cara penyusunan suatu kumpulan objek tanpa memperhatikan urutan pemilihan.

$$
C(n, r) = \frac{n!}{r!(n - r)!}
$$

dengan $n$ adalah banyaknya elemen dan $r$ adalah banyaknya elemen yang diambil.

Di Python, kita bisa menggunakan modul `itertools` yang memiliki function `permutations()` dan `combinations()`.

---

Probability adalah sebuah konsep untuk menjawab masalah ketidakpastian. Probabilistic Model adalah model yang menjelaskan kondisi uncertain dengan lebih sistematis.

Sample Space ($\Omega$) adalah kumpulan possible outcomes yang mungkin bisa terjadi dalam suatu experiment. Tidak semua hasil experiment bisa dijadikan Sample Space, karena harus ada syarat yang dipenuhi, seperti:
- Mutually Exclusive (elemen di dalam Sample Space harus unik)
- Collectively Exhaustive (apapun yang terjadi di dalam Experiment, pasti akan selalu mendapatkan outcome di dalam Sample Space tersebut)
- "Right" Granurality (jika ada kondisi yang tidak mempengaruhi suatu Sample Space, tidak perlu dimasukkan)

Event ($A$) adalah kejadian yang terjadi di dalam Sample Space. 

Pendekatan membuat Probabilistic Model paling sederhana adalah dengan menghitung proporsi anggota kejadian suatu Event di dalam Sample Sapce.

$$
P(A) = \frac{n(A)}{n(\Omega)}
$$

Pendekatan menghitung peluang yang lain adalah dengan menghitung frekuensi kemunculan suatu Event di dalam seluruh percobaan.


Axioms of Probability adalah aturan dasar yang harus dipatuhi ketika membuat probabilistic model. Terdapat tiga aturan yang harus dipenuhi:
1. (Non Negativitiy) Hasil Probability dari suatu Event harus lebih dari sama dengan 0 $P(A) \geq 0$
2. (Normlization) Total dari semua probability yang terjadi dari satu Sample Space harus sama dengan 1 $P(\Omega) = 1$
3. (Additivity) Jika ada disjoint event, maka hasil probability union-nya adalah nilai probability dari masing-masing disjoint event tersebut $P(A_1 \cup A_2 \cup ...) = P(A_1) + P(A_2) + ...$

Axioms of Probability memastikan agar probabilistic model tidak meaningless, konsisten dan valid, dan mempermudah interpretasi hasil (0 sampai 1) dan memiliki satuan yang sama. Jika memiliki skala data yang berbeda tidak akan mempengaruhi ke nilai probability.

---

Kalau kita mencari peluang suatu kejadian, jika diketahui kejadian lain telah terjadi, dinamakan conditional probability.

$$
P(A|B) = \frac{n(A \cap B)}{n(B)}
$$

$$
P(A|B) = \frac{P(A \cap B)}{P(B)}
$$

Conditional probability hanya bisa dihitung apabila $P(B) > 0$.

Case #1 - Jadwal Penerbangan

Jadwal penerbangan yang tepat waktu tidak hanya memengaruhi penumpang, namun maskapai penerbangan juga ingin memastikan jadwal-jadwal sesuai waktunya. Berikut adalah informasi mengenai jadwal penerbangan di suatu bandara.
- Peluang suatu penerbangan berangkat tepat waktu adalah 0.83
- Peluang suatu penerbangan tiba tepat waktu adalah 0.82
- Peluang suatu penerbangan berangkat dan tiba tepat waktu adalah 0.78

Pertanyaannya:
- Berapa peluang pesawat tiba tepat waktu diketahui pesawat tersebut berangkat tepat waktu?
- Berapa peluang pesawat berangkat tepat waktu diketahui pesawat tiba tepat waktu?

Diketahui:
$$P(D) = 0.83$$
$$P(A) = 0.82$$
$$P(D \cap A) = 0.78$$

Maka kita bisa dapatkan

$$
P(A|D) = \frac{P(A \cap D)}{P(D)} = \frac{0.78}{0.83} = 0.94
$$

---

Law of Total Probability. Jika terdapat $i$ kejadian yang saling disjoint, maka probabilitas suatu kejadian $A$ dapat didefinisikan sebagai berikut.

$$
P(A) = \sum_{i} P(B_i)P(A|B_i)
$$

Bayes' Rule describes the probability of an event, based on prior knowledge of conditions that might be related to the event. With this rule, we can update our belief to a particular event given an evidence has occurred.

$$
P(A|B) = \frac{P(A)P(B|A)}{P(B)}
$$

---

Dua kejadian dikatakan independen apabila tidak saling mempengaruhi.

$$
P(A \cap B) = P(A) P(B)
$$

Pada event disjoint:

$$
P(A \cap B) = 0
$$

Sebanyak $n$ event dikatakan saling independen jika:

$$
P(A_1 \cap A_2 \cap ... \cap A_n) = P(A_1)P(A_2)...P(A_n)
$$

Kumpulan kejadian dapat independen secara berpasangan, namun secara umum tidak independen.

---

Variabel Random adalah suatu fungsi untuk memetakan kejadian pada ruang sampel dalam bilangan real.

$$
X : \Omega \rightarrow \mathbb{R}
$$

Dalam penulisannya, Variabel Random mempunyai 2 komponen:
1. Nama (ditulis dalam huruf kapital)
2. Nilai (ditulis dalam huruf kecil)

$$
X = \{x_1, x_2, ...\}
$$


Probabilitas dari suatu nilai dalam variabel random dinamakan Probability Mass Function (PMF).

$$
p_x(x) = P(X = x)
$$

Secara formal, PMF adalah fungsi yang menghitung probabilitas nilai dari Variabel Random Diskrit. Nilai PMF dapat dicari dengan menghitung probabilitas nilai dalam variabel random. Dikarenakan PMF adalah probabilitas, maka PMF juga memenuhi Axioms of Probability.

