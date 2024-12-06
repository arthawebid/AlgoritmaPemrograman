[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

### 1. **Pengertian Rekursi**

Rekursi adalah suatu teknik pemrograman di mana suatu fungsi memanggil dirinya sendiri untuk menyelesaikan suatu masalah. Biasanya, masalah tersebut dibagi menjadi sub-masalah yang lebih kecil, dan setiap sub-masalah diselesaikan dengan cara yang sama (fungsi itu sendiri dipanggil lagi). Dalam rekursi, kita harus memastikan bahwa ada kondisi dasar yang akan menghentikan pemanggilan berulang tersebut.

**Definisi Rekursi:**
- Fungsi yang memanggil dirinya sendiri disebut fungsi rekursif.
- Untuk mencegah pemanggilan berulang tanpa henti, rekursi membutuhkan *base case* atau kondisi berhenti.

### 2. **Struktur Rekursif**

Struktur rekursif terdiri dari dua bagian utama:
- **Base Case (Kasus Dasar):** Merupakan kondisi yang menentukan kapan rekursi berhenti. Tanpa base case, rekursi akan terus berlanjut dan menyebabkan stack overflow.
- **Recursive Case (Kasus Rekursif):** Merupakan bagian di mana fungsi akan memanggil dirinya sendiri dengan parameter yang lebih sederhana atau lebih kecil dari sebelumnya.

**Contoh Struktur Rekursif:**

```python
def fungsi_rekursif(n):
    if n == 0:  # Base Case
        return 1
    else:  # Recursive Case
        return n * fungsi_rekursif(n - 1)
```

### 3. **Contoh Algoritma Rekursif**

#### a. **Contoh Rekursi untuk Menghitung Faktorial (n!)**

Faktorial adalah hasil perkalian semua bilangan bulat positif dari 1 sampai n. Faktorial dari n dapat didefinisikan sebagai:
- \( n! = n \times (n-1) \times (n-2) \times \dots \times 1 \)
- Basis: \( 0! = 1 \)

**Implementasi Rekursif untuk Faktorial:**

```python
def faktorial(n):
    if n == 0:  # Base case
        return 1
    else:  # Recursive case
        return n * faktorial(n - 1)
```

**Penjelasan:**
- Fungsi `faktorial(n)` akan memanggil dirinya sendiri hingga mencapai base case (n == 0), di mana ia akan mengembalikan 1.
- Setelah mencapai base case, hasil faktorial akan dihitung kembali dari bawah ke atas.

#### b. **Contoh Rekursi untuk Deret Fibonacci**

Deret Fibonacci adalah deret angka di mana setiap angka adalah hasil penjumlahan dua angka sebelumnya, dimulai dengan 0 dan 1. Contoh deret Fibonacci: 0, 1, 1, 2, 3, 5, 8, 13, ...

- Basis: \( F(0) = 0, F(1) = 1 \)
- Rekursif: \( F(n) = F(n-1) + F(n-2) \) untuk n > 1

**Implementasi Rekursif untuk Deret Fibonacci:**

```python
def fibonacci(n):
    if n == 0:  # Base case
        return 0
    elif n == 1:  # Base case
        return 1
    else:  # Recursive case
        return fibonacci(n - 1) + fibonacci(n - 2)
```

**Penjelasan:**
- Fungsi `fibonacci(n)` memanggil dirinya sendiri dengan dua parameter lebih kecil, yaitu `fibonacci(n-1)` dan `fibonacci(n-2)`.
- Proses ini berlanjut hingga mencapai base case (n == 0 atau n == 1).

#### c. **Contoh Rekursi untuk Mencari Pangkat (Exponentiation)**

Pangkat adalah hasil perkalian suatu bilangan dengan dirinya sendiri sebanyak n kali. Misalnya, \( a^n = a \times a \times \dots \) sebanyak n kali.

**Implementasi Rekursif untuk Pangkat:**

```python
def pangkat(a, n):
    if n == 0:  # Base case
        return 1
    else:  # Recursive case
        return a * pangkat(a, n - 1)
```

**Penjelasan:**
- Fungsi `pangkat(a, n)` memanggil dirinya sendiri dengan eksponen yang lebih kecil hingga mencapai 0, di mana hasilnya adalah 1.

### 4. **Pemecahan Masalah dengan Rekursi**

Rekursi sangat berguna dalam pemecahan masalah yang memiliki struktur yang bersifat *divide and conquer* atau masalah yang dapat dibagi menjadi sub-masalah yang lebih kecil.

Beberapa contoh pemecahan masalah dengan rekursi:
- **Pembagian dan Penaklukan (Divide and Conquer):** Seperti algoritma *merge sort* dan *quick sort*, di mana masalah besar dibagi menjadi bagian-bagian yang lebih kecil dan diselesaikan secara rekursif.
- **Pencarian:** Seperti pencarian biner pada array yang sudah terurut.
- **Graf dan Pohon:** Traversal pohon atau graf seperti *Depth-First Search (DFS)* atau *Breadth-First Search (BFS)* dapat dilakukan secara rekursif.

### 5. **Keuntungan dan Kekurangan Rekursi**

#### Keuntungan:
- **Kode yang lebih sederhana:** Dalam banyak kasus, rekursi membuat kode lebih bersih dan lebih mudah dibaca, terutama untuk masalah yang berulang.
- **Solusi untuk masalah berbentuk pohon atau grafik:** Rekursi sangat efektif untuk masalah dengan struktur hierarki atau pohon, seperti pencarian dalam pohon biner.

#### Kekurangan:
- **Konsumsi memori:** Setiap panggilan rekursif membutuhkan ruang di stack (memori), yang dapat menyebabkan *stack overflow* jika rekursi terlalu dalam.
- **Performa yang kurang efisien:** Rekursi dapat memperkenalkan overhead, karena setiap panggilan fungsi memerlukan waktu untuk memanggil fungsi lain.

### 6. **Tips Menghindari Masalah pada Rekursi**

- **Menggunakan Memoization atau Caching:** Untuk menghindari perhitungan yang berulang (misalnya pada deret Fibonacci), kita dapat menyimpan hasil-hasil yang telah dihitung sebelumnya.
- **Tail Recursion:** Dalam beberapa bahasa pemrograman, tail recursion dapat dioptimalkan oleh kompiler, sehingga mengurangi penggunaan memori.

### 7. **Latihan**

- Hitung faktorial dari angka `n` menggunakan rekursi.
- Tulis fungsi rekursif untuk menghitung deret Fibonacci.
- Implementasikan algoritma rekursif untuk mencari nilai pangkat \( a^n \).

---

**Kesimpulan:**
Algoritma rekursif adalah teknik pemrograman yang memecahkan masalah dengan memanggil fungsi itu sendiri. Pemahaman dasar mengenai base case dan recursive case sangat penting dalam mengimplementasikan rekursi dengan benar. Rekursi sangat berguna dalam menyelesaikan masalah yang dapat dibagi menjadi sub-masalah lebih kecil, seperti faktorial, Fibonacci, dan berbagai algoritma lainnya.

---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

