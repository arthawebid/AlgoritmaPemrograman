[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

### **1. Pengertian Algoritma Dinamis**

**Algoritma Dinamis** (Dynamic Programming, DP) adalah sebuah teknik pemrograman yang digunakan untuk menyelesaikan masalah yang dapat dibagi menjadi sub-masalah yang lebih kecil dan saling berhubungan. Teknik ini sangat efektif digunakan pada masalah optimasi yang memiliki *optimal substructure* dan *overlapping subproblems*.

**Optimal Substructure** berarti solusi optimal dari suatu masalah dapat dibangun dari solusi optimal dari sub-masalahnya.

**Overlapping Subproblems** berarti sub-masalah yang sama sering muncul berkali-kali dalam proses pemecahan masalah besar, yang mana bisa diselesaikan dengan menyimpan hasil-hasil sementara (memoization atau tabulation) untuk menghindari perhitungan ulang.

Langkah dasar dalam algoritma dinamis meliputi:
1. Memecah masalah besar menjadi sub-masalah yang lebih kecil.
2. Menyelesaikan setiap sub-masalah satu kali dan menyimpan solusinya.
3. Menggunakan hasil-hasil sub-masalah yang sudah diselesaikan untuk membangun solusi masalah besar.

### **2. Karakteristik Algoritma Dinamis**
- **Sub-masalah yang berulang:** Banyak sub-masalah yang akan diselesaikan lebih dari satu kali.
- **Memoization atau Tabulation:** Penyimpanan hasil perhitungan untuk menghindari perhitungan ulang.
- **Solusi global berdasarkan solusi lokal:** Solusi optimal dari masalah besar bisa dibangun dari solusi optimal sub-masalahnya.

### **3. Contoh Kasus**

#### **a. Fibonacci**

Fibonacci adalah deret angka yang masing-masing angka setelahnya merupakan penjumlahan dari dua angka sebelumnya. Deret Fibonacci dimulai dari 0 dan 1, misalnya:  
F(0) = 0, F(1) = 1, F(2) = F(1) + F(0) = 1, F(3) = F(2) + F(1) = 2, F(4) = F(3) + F(2) = 3, dan seterusnya.

Pada algoritma biasa, Fibonacci dihitung dengan rekursi, tetapi ini membutuhkan waktu yang sangat besar karena ada perhitungan ulang untuk sub-masalah yang sama. Dengan menggunakan algoritma dinamis, kita bisa menghindari perhitungan ulang.

**Implementasi Fibonacci dengan Algoritma Dinamis:**

```python
def fibonacci(n):
    # Membuat array untuk menyimpan nilai Fibonacci
    fib = [0] * (n + 1)
    
    # Nilai dasar
    fib[0] = 0
    fib[1] = 1
    
    # Menghitung Fibonacci dengan cara bottom-up
    for i in range(2, n + 1):
        fib[i] = fib[i - 1] + fib[i - 2]
    
    return fib[n]

# Contoh pemanggilan fungsi
print(fibonacci(10))  # Output: 55
```

#### **b. Knapsack Problem**

**Masalah Knapsack** adalah masalah optimasi di mana kita diberikan sejumlah barang dengan bobot dan nilai tertentu, dan sebuah knapsack (tas) dengan kapasitas tertentu. Tujuannya adalah memilih sejumlah barang untuk dimasukkan ke dalam knapsack sehingga nilai totalnya maksimal tanpa melebihi kapasitas knapsack.

**Solusi Dinamis pada Knapsack:**

Pada masalah Knapsack, kita bisa menggunakan DP untuk menyimpan nilai optimal yang dapat dicapai untuk setiap sub-masalah yang lebih kecil.

**Implementasi Knapsack 0/1 dengan Algoritma Dinamis:**

```python
def knapsack(weights, values, capacity):
    n = len(weights)
    # Membuat tabel untuk menyimpan solusi sub-masalah
    dp = [[0] * (capacity + 1) for _ in range(n + 1)]
    
    # Mengisi tabel dp
    for i in range(1, n + 1):
        for w in range(1, capacity + 1):
            if weights[i - 1] <= w:
                dp[i][w] = max(dp[i - 1][w], values[i - 1] + dp[i - 1][w - weights[i - 1]])
            else:
                dp[i][w] = dp[i - 1][w]
    
    return dp[n][capacity]

# Contoh pemanggilan fungsi
weights = [2, 3, 4, 5]
values = [3, 4, 5, 6]
capacity = 5
print(knapsack(weights, values, capacity))  # Output: 7
```

#### **c. Matrix Chain Multiplication**

**Masalah Matrix Chain Multiplication** adalah masalah optimasi di mana kita diberikan serangkaian matriks dan tujuannya adalah untuk mencari urutan perkalian matriks yang menghasilkan biaya perkalian minimum. Matrices yang diberikan mungkin dapat dikalikan dalam urutan yang berbeda-beda.

**Solusi Dinamis pada Matrix Chain Multiplication:**

Masalah ini dapat diselesaikan dengan menggunakan DP dengan menyimpan biaya minimum untuk setiap sub-masalah. Algoritma ini dikenal dengan nama **Matrix Chain Order**.

**Implementasi Matrix Chain Multiplication dengan Algoritma Dinamis:**

```python
def matrix_chain_order(p):
    n = len(p) - 1  # p adalah array yang berisi dimensi matriks
    m = [[0] * n for _ in range(n)]  # Matriks biaya
    s = [[0] * n for _ in range(n)]  # Matriks untuk menyimpan posisi pembagian optimal

    for length in range(2, n + 1):  # panjang rantai matriks
        for i in range(n - length + 1):
            j = i + length - 1
            m[i][j] = float('inf')
            for k in range(i, j):
                q = m[i][k] + m[k + 1][j] + p[i] * p[k + 1] * p[j + 1]
                if q < m[i][j]:
                    m[i][j] = q
                    s[i][j] = k
    
    return m[0][n - 1]

# Contoh pemanggilan fungsi
p = [30, 35, 15, 5, 10, 20, 25]
print(matrix_chain_order(p))  # Output: 15125
```

---

### **4. Penerapan dan Keuntungan Algoritma Dinamis**

- **Efisiensi:** Mengurangi waktu komputasi dengan menghindari perhitungan ulang untuk sub-masalah yang sama.
- **Sederhana:** Banyak masalah yang lebih kompleks dapat diselesaikan dengan cara yang lebih sederhana dan efisien menggunakan DP.
- **Solusi Optimal:** Algoritma dinamis seringkali digunakan untuk menemukan solusi optimal dari berbagai masalah optimasi.

### **5. Kesimpulan**

Algoritma Dinamis adalah teknik yang kuat untuk menyelesaikan masalah yang memiliki sub-masalah berulang dan dapat dibangun dari solusi sub-masalah tersebut. Beberapa contoh klasik dari masalah yang dapat diselesaikan dengan algoritma dinamis antara lain adalah masalah **Fibonacci**, **Knapsack**, dan **Matrix Chain Multiplication**.

Pemahaman yang baik tentang cara membangun dan menyimpan solusi untuk sub-masalah akan sangat membantu dalam penerapan algoritma dinamis pada masalah lainnya.

---

Semoga materi ini membantu dalam memahami konsep dan penerapan algoritma dinamis!


---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

