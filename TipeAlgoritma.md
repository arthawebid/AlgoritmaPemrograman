[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

## **1. Tipe-Tipe Algoritma**

Algoritma dapat dibagi menjadi berbagai kategori berdasarkan jenis masalah yang diselesaikan atau pendekatan yang digunakan. Beberapa tipe algoritma yang penting adalah sebagai berikut:

### a. **Algoritma Pencarian (Search Algorithms)**

Algoritma pencarian digunakan untuk menemukan elemen dalam sebuah struktur data seperti array, list, atau graf.

### b. **Algoritma Pengurutan (Sorting Algorithms)**

Algoritma pengurutan digunakan untuk menyusun data dalam urutan tertentu, misalnya urutan menaik atau menurun.

### c. **Algoritma Rekursif (Recursive Algorithms)**

Algoritma rekursif adalah algoritma yang memecahkan masalah dengan cara memanggil dirinya sendiri.

### d. **Algoritma Greedy (Greedy Algorithms)**

Algoritma greedy adalah pendekatan algoritma yang memilih solusi terbaik pada setiap langkah, tanpa mempertimbangkan keputusan-keputusan sebelumnya, dengan harapan solusi globalnya juga optimal.

---

## **2. Algoritma Pencarian (Search Algorithms)**

Algoritma pencarian digunakan untuk menemukan elemen tertentu dalam struktur data. Ada beberapa jenis algoritma pencarian, antara lain:

### a. **Pencarian Linear (Linear Search)**

Pencarian linear adalah metode pencarian sederhana yang memeriksa setiap elemen dalam list secara berurutan.

**Langkah-langkah:**
1. Mulai dari elemen pertama dalam array.
2. Bandingkan elemen dengan nilai yang dicari.
3. Jika ditemukan, kembalikan indeks elemen tersebut.
4. Jika elemen tidak ditemukan hingga akhir array, kembalikan nilai "tidak ditemukan".

**Kompleksitas waktu:** O(n) — karena dalam kasus terburuk, algoritma memeriksa seluruh elemen dalam array.

### b. **Pencarian Biner (Binary Search)**

Pencarian biner hanya dapat digunakan pada data yang sudah terurut. Algoritma ini membagi data menjadi dua bagian secara terus menerus sampai elemen yang dicari ditemukan.

**Langkah-langkah:**
1. Tentukan nilai tengah array.
2. Bandingkan nilai tengah dengan nilai yang dicari.
3. Jika nilai tengah lebih besar dari nilai yang dicari, fokus pada setengah bagian kiri.
4. Jika nilai tengah lebih kecil, fokus pada setengah bagian kanan.
5. Ulangi proses sampai ditemukan atau sampai array tidak bisa dibagi lagi.

**Kompleksitas waktu:** O(log n) — lebih efisien dibandingkan pencarian linear pada data yang besar.

---

## **3. Algoritma Pengurutan (Sorting Algorithms)**

Algoritma pengurutan digunakan untuk menyusun data dalam urutan tertentu. Beberapa algoritma pengurutan yang umum digunakan adalah sebagai berikut:

### a. **Bubble Sort**

Bubble Sort adalah algoritma pengurutan yang membandingkan dua elemen berturut-turut dan menukarnya jika urutannya salah. Proses ini diulang hingga array terurut.

**Langkah-langkah:**
1. Bandingkan dua elemen berturut-turut.
2. Jika elemen pertama lebih besar, tukar posisi mereka.
3. Ulangi langkah 1 dan 2 untuk setiap pasangan elemen hingga tidak ada lagi yang perlu ditukar.

**Kompleksitas waktu:** O(n²) — karena memeriksa setiap elemen untuk membandingkan dan menukar pasangan elemen.

### b. **Selection Sort**

Selection Sort bekerja dengan memilih elemen terkecil (atau terbesar, tergantung urutannya) dan menukarnya dengan elemen pertama yang belum terurut. Proses ini diulang untuk elemen-elemen lainnya.

**Langkah-langkah:**
1. Cari elemen terkecil dalam array.
2. Tukar elemen terkecil dengan elemen pertama yang belum terurut.
3. Ulangi untuk elemen berikutnya hingga array terurut.

**Kompleksitas waktu:** O(n²) — efisien untuk array kecil, tetapi tidak efisien untuk array besar.

### c. **Quick Sort**

Quick Sort adalah algoritma pengurutan yang menggunakan teknik pembagian (divide and conquer). Algoritma ini memilih elemen pivot dan mempartisi array menjadi dua bagian, elemen yang lebih kecil dari pivot di sebelah kiri dan elemen yang lebih besar di sebelah kanan.

**Langkah-langkah:**
1. Pilih elemen pivot.
2. Partisi array dengan meletakkan elemen yang lebih kecil dari pivot di sebelah kiri dan yang lebih besar di sebelah kanan.
3. Rekursi pada bagian kiri dan kanan array.

**Kompleksitas waktu:** O(n log n) — lebih efisien dibandingkan algoritma lain seperti Bubble Sort atau Selection Sort pada data besar.

---

## **4. Algoritma Rekursif (Recursive Algorithms)**

Algoritma rekursif adalah algoritma yang memecahkan masalah dengan memanggil dirinya sendiri. Sebuah masalah rekursif memiliki dua komponen:
- **Kasus dasar (base case)**: Kasus yang menyelesaikan masalah tanpa pemanggilan lebih lanjut.
- **Kasus rekursif**: Pemecahan masalah yang lebih kecil dengan memanggil algoritma itu sendiri.

### Contoh: Faktorial (Factorial)

**Masalah:** Hitung faktorial dari suatu bilangan n, yang didefinisikan sebagai n! = n × (n-1) × (n-2) × ... × 1.

**Langkah-langkah:**
- Kasus dasar: 0! = 1.
- Kasus rekursif: n! = n × (n-1)!

**Implementasi:**
```python
def faktorial(n):
    if n == 0:
        return 1
    else:
        return n * faktorial(n - 1)
```

**Kompleksitas waktu:** O(n) — karena ada n panggilan rekursif.

---

## **5. Algoritma Greedy (Greedy Algorithms)**

Algoritma greedy adalah pendekatan yang memilih solusi terbaik pada setiap langkah, berharap bahwa solusi lokal yang optimal akan menghasilkan solusi global yang optimal. Algoritma ini digunakan dalam berbagai masalah, seperti masalah pemilihan aktivitas, knapsack, atau graf.

### Contoh: Masalah Pemilihan Aktivitas

**Masalah:** Diberikan serangkaian aktivitas dengan waktu mulai dan selesai, pilih sebanyak mungkin aktivitas yang tidak saling tumpang tindih.

**Langkah-langkah:**
1. Urutkan aktivitas berdasarkan waktu selesai.
2. Pilih aktivitas yang pertama kali selesai dan tidak tumpang tindih dengan yang sebelumnya.
3. Ulangi sampai tidak ada aktivitas yang dapat dipilih.

**Implementasi:**
```python
def pemilihan_aktivitas(aktivitas):
    aktivitas.sort(key=lambda x: x[1])  # Urutkan berdasarkan waktu selesai
    hasil = [aktivitas[0]]
    for i in range(1, len(aktivitas)):
        if aktivitas[i][0] >= hasil[-1][1]:  # Jika aktivitas i tidak tumpang tindih
            hasil.append(aktivitas[i])
    return hasil
```

**Kompleksitas waktu:** O(n log n) — karena perlu mengurutkan aktivitas terlebih dahulu.

---

### Kesimpulan

- **Algoritma Pencarian** seperti Linear Search dan Binary Search digunakan untuk menemukan elemen dalam struktur data.
- **Algoritma Pengurutan** seperti Bubble Sort, Selection Sort, dan Quick Sort digunakan untuk mengurutkan data dalam urutan tertentu.
- **Algoritma Rekursif** digunakan untuk menyelesaikan masalah dengan cara memecahnya menjadi sub-masalah yang lebih kecil.
- **Algoritma Greedy** mengambil keputusan optimal pada setiap langkah dengan harapan menghasilkan solusi optimal secara keseluruhan.

Pemahaman terhadap jenis-jenis algoritma ini sangat penting untuk merancang solusi yang efisien dan efektif dalam pemrograman.

---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)
