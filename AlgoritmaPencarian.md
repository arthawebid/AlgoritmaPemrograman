[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

## **1. Algoritma Pencarian**

Algoritma pencarian adalah metode yang digunakan untuk menemukan posisi atau nilai tertentu dalam kumpulan data, seperti array atau list. Algoritma pencarian sering digunakan dalam banyak aplikasi, seperti pencarian data dalam database, pencarian elemen dalam array, atau pencarian pola dalam teks.

Jenis-jenis algoritma pencarian yang umum digunakan antara lain:
- Pencarian Linear
- Pencarian Biner
- Pencarian pada Struktur Data Lainnya (Trie, Hashing)

---

## **2. Pencarian Linear**

**Pencarian Linear** (atau disebut juga Pencarian Secara Berurutan) adalah algoritma yang mencari elemen tertentu dalam sebuah daftar dengan cara memeriksa setiap elemen satu per satu, dimulai dari elemen pertama hingga elemen terakhir.

### **Langkah-langkah Algoritma Pencarian Linear:**
1. Mulai dari elemen pertama dalam array atau list.
2. Bandingkan elemen yang sedang diperiksa dengan nilai yang dicari.
3. Jika elemen yang dicari ditemukan, algoritma berhenti dan mengembalikan posisi elemen tersebut.
4. Jika tidak ditemukan, algoritma akan memeriksa elemen berikutnya.
5. Ulangi langkah 2 dan 3 hingga seluruh elemen diperiksa.
6. Jika elemen tidak ditemukan setelah memeriksa semua elemen, algoritma mengembalikan nilai atau indikator yang menyatakan bahwa elemen tidak ada.

### **Keunggulan Pencarian Linear:**
- Sederhana dan mudah diterapkan.
- Dapat digunakan pada data yang tidak terurut.

### **Kelemahan Pencarian Linear:**
- Kompleksitas waktu adalah O(n), di mana n adalah jumlah elemen dalam daftar. Ini membuatnya kurang efisien untuk data yang sangat besar.

### **Contoh Implementasi Pencarian Linear dalam Python:**
```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # Mengembalikan indeks jika elemen ditemukan
    return -1  # Mengembalikan -1 jika elemen tidak ditemukan

arr = [3, 5, 2, 8, 6]
target = 8
result = linear_search(arr, target)
print("Elemen ditemukan pada indeks:", result)
```

---

## **3. Pencarian Biner**

**Pencarian Biner** adalah algoritma pencarian yang lebih efisien dibandingkan pencarian linear, tetapi hanya dapat digunakan pada daftar yang sudah terurut. Pencarian biner memanfaatkan prinsip divide and conquer, dengan membagi daftar menjadi dua bagian pada setiap langkahnya.

### **Langkah-langkah Algoritma Pencarian Biner:**
1. Tentukan indeks tengah dari array yang terurut.
2. Jika elemen yang dicari adalah elemen tengah, maka pencarian selesai.
3. Jika elemen yang dicari lebih kecil dari elemen tengah, lanjutkan pencarian pada setengah bagian kiri dari array.
4. Jika elemen yang dicari lebih besar, lanjutkan pencarian pada setengah bagian kanan.
5. Ulangi langkah 1 hingga 4 pada subset array yang lebih kecil, hingga elemen ditemukan atau subarray menjadi kosong.

### **Keunggulan Pencarian Biner:**
- Lebih efisien daripada pencarian linear dengan kompleksitas waktu O(log n).
- Dapat digunakan pada data yang terurut.

### **Kelemahan Pencarian Biner:**
- Hanya bekerja pada data yang sudah terurut.

### **Contoh Implementasi Pencarian Biner dalam Python:**
```python
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid  # Elemen ditemukan
        elif arr[mid] < target:
            low = mid + 1  # Cari di bagian kanan
        else:
            high = mid - 1  # Cari di bagian kiri
    return -1  # Elemen tidak ditemukan

arr = [1, 3, 5, 7, 9]
target = 7
result = binary_search(arr, target)
print("Elemen ditemukan pada indeks:", result)
```

---

## **4. Pencarian pada Struktur Data Lainnya**

Selain array atau list, ada beberapa struktur data lainnya yang memungkinkan pencarian lebih efisien, di antaranya **Trie** dan **Hashing**.

### **Pencarian dengan Trie**

**Trie** (atau prefix tree) adalah struktur data pohon yang digunakan untuk menyimpan kumpulan string. Trie memungkinkan pencarian yang cepat berdasarkan karakter atau awalan string.

### **Keunggulan Trie:**
- Pencarian dapat dilakukan dengan sangat cepat, terutama dalam pencarian awalan (prefix search).
- Sangat efisien dalam menyimpan kumpulan string yang berbagi awalan yang sama.

### **Contoh Penggunaan Trie:**
Trie banyak digunakan dalam aplikasi autocomplete atau pencarian kata berdasarkan awalan yang diberikan.

### **Pencarian dengan Hashing**

**Hashing** adalah teknik untuk mengubah data menjadi sebuah nilai hash yang digunakan sebagai indeks dalam struktur data seperti **hash table**. Hashing memungkinkan pencarian, penyisipan, dan penghapusan elemen dengan waktu konstan rata-rata O(1), meskipun dengan kemungkinan terjadinya **tabrakan** (collision).

### **Keunggulan Hashing:**
- Operasi pencarian, penyisipan, dan penghapusan biasanya dilakukan dalam waktu O(1).
- Sangat efisien untuk pencarian cepat dalam kumpulan data besar.

### **Kelemahan Hashing:**
- Mengharuskan penggunaan fungsi hash yang baik untuk menghindari tabrakan.
- Memerlukan penggunaan lebih banyak memori dibandingkan dengan struktur data lainnya.

### **Contoh Implementasi Hashing dalam Python:**
```python
# Menggunakan dictionary untuk hashing di Python
hash_table = {}

# Menyisipkan elemen
hash_table["nama"] = "John"
hash_table["umur"] = 30

# Mencari elemen
print("Nama:", hash_table.get("nama", "Tidak ditemukan"))
print("Umur:", hash_table.get("umur", "Tidak ditemukan"))
```

---

## **5. Perbandingan Algoritma Pencarian**

| Algoritma          | Waktu Rata-rata  | Waktu Terburuk  | Kelebihan                     | Kekurangan                |
|--------------------|------------------|-----------------|-------------------------------|---------------------------|
| **Pencarian Linear** | O(n)             | O(n)            | Sederhana, Tidak memerlukan data terurut | Tidak efisien untuk data besar |
| **Pencarian Biner**  | O(log n)         | O(log n)        | Cepat pada data terurut       | Hanya bekerja pada data terurut |
| **Hashing**          | O(1)             | O(n) (collision) | Cepat, efisien dengan banyak data | Memerlukan memori lebih banyak |
| **Trie**             | O(m) (panjang string) | O(m) (panjang string) | Pencarian awalan sangat cepat | Memerlukan memori lebih banyak |

---

### **Kesimpulan**
- **Pencarian Linear** cocok digunakan untuk data yang tidak terurut dan tidak terlalu besar.
- **Pencarian Biner** sangat efisien untuk data yang terurut, dengan kompleksitas yang lebih rendah.
- **Trie** dan **Hashing** adalah struktur data canggih yang memungkinkan pencarian sangat cepat, terutama untuk kumpulan data besar.

Materi ini memberikan pemahaman dasar mengenai berbagai algoritma pencarian dan perbandingan antara mereka, serta penggunaannya dalam berbagai kasus.

---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)
