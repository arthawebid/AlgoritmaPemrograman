[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---
### **1. Dasar-Dasar Pemrograman**
Pemrograman adalah proses menulis, menguji, dan memelihara kode yang membuat perangkat lunak berjalan. Pemrograman dilakukan dengan menggunakan bahasa pemrograman tertentu yang memiliki aturan sintaksis dan semantik.

#### Konsep Dasar Pemrograman:
- **Algoritma**: Langkah-langkah sistematis untuk memecahkan masalah. Sebuah algoritma harus jelas dan terstruktur.
- **Bahasa Pemrograman**: Kode yang digunakan untuk berkomunikasi dengan komputer, misalnya Python, Java, C, atau C++.
- **Program**: Sekumpulan instruksi yang dapat dieksekusi untuk menyelesaikan tugas tertentu.

### **2. Struktur Program**
Struktur program adalah bagaimana sebuah program diorganisasikan. Pada umumnya, sebuah program memiliki struktur dasar berikut:

```text
Program
    |
    ├── Deklarasi Variabel
    ├── Inisialisasi
    ├── Logika Pemrograman
    └── Output
```

Beberapa komponen penting dalam struktur program:
- **Deklarasi Variabel**: Menyatakan nama dan tipe data variabel yang akan digunakan.
- **Inisialisasi**: Proses pemberian nilai awal kepada variabel.
- **Logika Pemrograman**: Berisi instruksi yang memproses data.
- **Output**: Menampilkan hasil dari pemrosesan.

### **3. Tipe Data dan Variabel**
- **Tipe Data** adalah jenis nilai yang dapat disimpan dalam sebuah variabel. Tipe data yang umum digunakan adalah:
  - **Integer (int)**: Bilangan bulat.
  - **Float (float)**: Bilangan pecahan (desimal).
  - **Char (char)**: Karakter tunggal.
  - **String (str)**: Sekumpulan karakter (teks).
  - **Boolean (bool)**: Nilai benar (True) atau salah (False).

- **Variabel** adalah tempat penyimpanan data yang memiliki nama dan tipe data tertentu. Contoh deklarasi variabel:
  ```python
  int a = 5;        // variabel integer
  float b = 3.14;   // variabel float
  char c = 'A';     // variabel karakter
  string name = "John";  // variabel string
  bool isTrue = true;    // variabel boolean
  ```

### **4. Operator dan Ekspresi**
- **Operator** adalah simbol yang digunakan untuk melakukan operasi pada variabel dan nilai. Ada beberapa jenis operator:
  - **Operator Aritmatika**: Digunakan untuk operasi matematika.
    - `+`, `-`, `*`, `/`, `%` (modulus)
  - **Operator Relasional**: Digunakan untuk membandingkan dua nilai.
    - `==`, `!=`, `>`, `<`, `>=`, `<=`
  - **Operator Logika**: Digunakan untuk operasi logika.
    - `and`, `or`, `not`
  - **Operator Penugasan**: Digunakan untuk memberikan nilai ke variabel.
    - `=`, `+=`, `-=`, `*=`, `/=`
  
- **Ekspresi** adalah kombinasi variabel, konstanta, operator, dan tanda kurung yang menghasilkan suatu nilai. Contoh ekspresi:
  ```python
  x = (a + b) * 2
  ```

### **5. Input dan Output**
- **Input** adalah proses untuk menerima data dari pengguna atau sumber lain.
- **Output** adalah proses untuk menampilkan data ke layar atau perangkat lain.

Contoh input dan output dalam Python:
```python
# Input
nama = input("Masukkan nama Anda: ")

# Output
print("Halo, " + nama)
```

### **6. Kontrol Alur Program**
Kontrol alur program digunakan untuk menentukan urutan eksekusi instruksi dalam program. Ada dua jenis kontrol alur utama: **Percabangan** dan **Perulangan**.

#### **Percabangan**
Percabangan digunakan untuk mengambil keputusan, yaitu memilih jalur eksekusi yang berbeda berdasarkan kondisi yang diberikan. Bentuk umum percabangan adalah `if`, `else`, dan `elif`.

Contoh percabangan dalam Python:
```python
# Struktur If-Else
age = int(input("Masukkan umur: "))
if age >= 18:
    print("Anda sudah dewasa.")
else:
    print("Anda masih remaja.")
```

#### **Perulangan**
Perulangan digunakan untuk mengeksekusi sekelompok instruksi berulang kali, selama kondisi tertentu terpenuhi. Ada dua jenis perulangan yang umum digunakan: `for` dan `while`.

- **Perulangan for** digunakan untuk perulangan yang jumlahnya sudah diketahui.
  ```python
  for i in range(5):
      print(i)
  ```

- **Perulangan while** digunakan untuk perulangan yang berlangsung selama kondisi tertentu terpenuhi.
  ```python
  i = 0
  while i < 5:
      print(i)
      i += 1
  ```

#### **Break dan Continue**
- **Break**: Menghentikan perulangan.
- **Continue**: Melewati iterasi saat ini dan melanjutkan ke iterasi berikutnya.

Contoh:
```python
for i in range(10):
    if i == 5:
        break  # Menghentikan perulangan saat i == 5
    print(i)
```

---

### **Ringkasan Materi**
- **Dasar-dasar pemrograman** adalah memahami bagaimana menulis kode dan memecahkan masalah.
- **Struktur program** penting untuk mengorganisir alur eksekusi.
- **Tipe data dan variabel** adalah elemen dasar dalam menyimpan informasi.
- **Operator dan ekspresi** digunakan untuk manipulasi data.
- **Input dan output** berfungsi untuk interaksi dengan pengguna.
- **Kontrol alur program** melalui percabangan dan perulangan mengatur jalannya eksekusi program.

Materi ini mencakup dasar-dasar yang sangat penting untuk memahami bagaimana program bekerja dan bagaimana algoritma dapat diterjemahkan menjadi kode yang berjalan di komputer.

---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

