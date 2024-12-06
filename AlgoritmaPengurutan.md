[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

### **Materi Kuliah: Algoritma Pemrograman - Pengurutan**

#### **1. Pengertian Algoritma Pengurutan (Sorting)**
Algoritma pengurutan adalah metode untuk mengurutkan sekumpulan data berdasarkan kriteria tertentu (misalnya, urutan angka atau abjad). Pengurutan sangat penting dalam berbagai aplikasi, seperti pencarian data yang lebih cepat, pengolahan data statistik, dan lain-lain.

Tujuan dari pengurutan adalah untuk menyusun elemen-elemen dalam urutan yang telah ditentukan, baik secara naik (ascending) atau turun (descending).

#### **2. Klasifikasi Algoritma Pengurutan**
Algoritma pengurutan dibagi menjadi beberapa jenis berdasarkan cara kerjanya. Berikut adalah beberapa algoritma pengurutan yang umum digunakan:

### **3. Bubble Sort**

**Deskripsi:**
Bubble Sort adalah algoritma pengurutan yang sederhana. Algoritma ini bekerja dengan cara membandingkan dua elemen yang berdekatan, jika urutannya salah, maka elemen-elemen tersebut ditukar.

**Cara Kerja:**
- Melakukan iterasi dari elemen pertama hingga akhir, membandingkan elemen yang berdekatan.
- Jika elemen yang lebih besar ditemukan di sebelah kiri elemen yang lebih kecil, tukar posisi keduanya.
- Ulangi proses ini untuk seluruh elemen hingga tidak ada yang perlu ditukar lagi.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(n²)
- Kasus Terbaik: O(n) (jika sudah terurut)
- Kasus Rata-rata: O(n²)

**Implementasi:**
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```

### **4. Selection Sort**

**Deskripsi:**
Selection Sort adalah algoritma pengurutan yang bekerja dengan cara memilih elemen terkecil (atau terbesar) dari bagian yang belum terurut dan menukarnya dengan elemen pertama.

**Cara Kerja:**
- Temukan elemen terkecil dalam array.
- Tukar elemen terkecil dengan elemen pertama.
- Ulangi langkah di atas untuk subarray yang tersisa.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(n²)
- Kasus Terbaik: O(n²)
- Kasus Rata-rata: O(n²)

**Implementasi:**
```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_index = i
        for j in range(i+1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
```

### **5. Insertion Sort**

**Deskripsi:**
Insertion Sort bekerja dengan cara memasukkan elemen-elemen ke dalam posisi yang sesuai dalam subarray yang sudah terurut.

**Cara Kerja:**
- Ambil elemen dari array satu per satu.
- Tempatkan elemen tersebut pada posisi yang sesuai dalam subarray yang sudah terurut.
- Ulangi langkah ini hingga seluruh array terurut.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(n²)
- Kasus Terbaik: O(n)
- Kasus Rata-rata: O(n²)

**Implementasi:**
```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >= 0 and key < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr
```

### **6. Merge Sort**

**Deskripsi:**
Merge Sort adalah algoritma pengurutan berbasis **Divide and Conquer**. Algoritma ini membagi array menjadi dua bagian, mengurutkan bagian-bagian tersebut secara terpisah, dan kemudian menggabungkannya kembali.

**Cara Kerja:**
- Bagi array menjadi dua subarray.
- Lakukan pengurutan secara rekursif pada masing-masing subarray.
- Gabungkan subarray yang sudah terurut menjadi satu array yang terurut.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(n log n)
- Kasus Terbaik: O(n log n)
- Kasus Rata-rata: O(n log n)

**Implementasi:**
```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        merge_sort(left_half)
        merge_sort(right_half)

        i = j = k = 0
        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1
    return arr
```

### **7. Quick Sort**

**Deskripsi:**
Quick Sort adalah algoritma pengurutan berbasis **Divide and Conquer** yang memilih satu elemen sebagai pivot dan membagi array menjadi dua bagian: elemen yang lebih kecil dari pivot dan yang lebih besar.

**Cara Kerja:**
- Pilih elemen pivot (misalnya, elemen pertama atau terakhir).
- Partisi array ke dalam dua bagian: satu bagian dengan elemen lebih kecil dari pivot dan satu bagian dengan elemen lebih besar.
- Lakukan pengurutan secara rekursif pada kedua bagian.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(n²)
- Kasus Terbaik: O(n log n)
- Kasus Rata-rata: O(n log n)

**Implementasi:**
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)
```

### **8. Radix Sort**

**Deskripsi:**
Radix Sort adalah algoritma pengurutan yang mengurutkan angka berdasarkan digitnya. Pengurutan dilakukan berdasarkan posisi digit, dimulai dari digit yang paling kurang signifikan (Least Significant Digit - LSD) atau paling signifikan (Most Significant Digit - MSD).

**Cara Kerja:**
- Tentukan digit yang akan digunakan untuk pengurutan.
- Lakukan pengurutan berdasarkan digit tersebut, kemudian pindah ke digit berikutnya.
- Ulangi proses ini untuk setiap digit hingga seluruh elemen terurut.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(nk), di mana k adalah jumlah digit
- Kasus Terbaik: O(nk)
- Kasus Rata-rata: O(nk)

**Implementasi:**
```python
def counting_sort(arr, exp):
    n = len(arr)
    output = [0] * n
    count = [0] * 10

    for i in range(n):
        index = arr[i] // exp
        count[index % 10] += 1

    for i in range(1, 10):
        count[i] += count[i - 1]

    i = n - 1
    while i >= 0:
        index = arr[i] // exp
        output[count[index % 10] - 1] = arr[i]
        count[index % 10] -= 1
        i -= 1

    for i in range(n):
        arr[i] = output[i]

def radix_sort(arr):
    max_val = max(arr)
    exp = 1
    while max_val // exp > 0:
        counting_sort(arr, exp)
        exp *= 10
    return arr
```

### **9. Bucket Sort**

**Deskripsi:**
Bucket Sort adalah algoritma pengurutan yang membagi elemen-elemen ke dalam beberapa "bucket", mengurutkan elemen dalam setiap bucket, dan akhirnya menggabungkan hasilnya.

**Cara Kerja:**
- Bagikan elemen-elemen ke dalam bucket.
- Urutkan setiap bucket secara terpisah.
- Gabungkan hasil dari semua bucket yang telah terurut.

**Kompleksitas Waktu:**
- Kasus Terburuk: O(n²) (tergantung pada distribusi data)
- Kasus Terbaik: O(n + k)
- Kasus Rata-rata: O(n + k)

**Implementasi:**
```python
def bucket_sort(arr):
    if len(arr) == 0:
        return arr

    min_val = min(arr

)
    max_val = max(arr)
    bucket_count = len(arr)

    buckets = [[] for _ in range(bucket_count)]

    for num in arr:
        index = (num - min_val) * (bucket_count - 1) // (max_val - min_val)
        buckets[index].append(num)

    for i in range(bucket_count):
        buckets[i] = sorted(buckets[i])

    return [num for bucket in buckets for num in bucket]
```

---

### **10. Kesimpulan**
Berbagai algoritma pengurutan di atas memiliki kelebihan dan kekurangan tergantung pada jumlah data, distribusi data, dan kompleksitas waktu yang dibutuhkan. Berikut adalah ringkasan kompleksitas waktu untuk setiap algoritma:

| Algoritma      | Kasus Terburuk | Kasus Terbaik | Kasus Rata-rata |
|----------------|----------------|----------------|-----------------|
| Bubble Sort    | O(n²)          | O(n)           | O(n²)           |
| Selection Sort | O(n²)          | O(n²)          | O(n²)           |
| Insertion Sort | O(n²)          | O(n)           | O(n²)           |
| Merge Sort     | O(n log n)     | O(n log n)     | O(n log n)      |
| Quick Sort     | O(n²)          | O(n log n)     | O(n log n)      |
| Radix Sort     | O(nk)          | O(nk)          | O(nk)           |
| Bucket Sort    | O(n²)          | O(n + k)       | O(n + k)        |

Pemilihan algoritma tergantung pada kondisi dan ukuran data yang ada.

---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

