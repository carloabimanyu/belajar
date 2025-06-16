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

