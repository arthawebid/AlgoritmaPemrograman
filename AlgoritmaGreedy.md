[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

#### 1. **Pengertian Algoritma Greedy**
   
Algoritma **Greedy** adalah sebuah pendekatan dalam menyelesaikan masalah optimasi, di mana solusi dibangun secara bertahap dengan membuat pilihan terbaik atau optimal pada setiap langkahnya. Algoritma ini bekerja berdasarkan prinsip bahwa dengan memilih keputusan terbaik di setiap langkah, maka solusi keseluruhan akan menjadi optimal.

Namun, perlu dicatat bahwa **Algoritma Greedy** tidak selalu menghasilkan solusi yang optimal untuk semua masalah. Meskipun begitu, untuk beberapa masalah, algoritma ini dapat memberikan solusi yang sangat mendekati optimal dengan cara yang lebih cepat dan efisien.

#### 2. **Prinsip Algoritma Greedy**

Prinsip dasar dari algoritma greedy adalah sebagai berikut:

- **Pemilihan Langkah Lokal yang Optimal**: Pada setiap langkah, algoritma memilih solusi yang terbaik berdasarkan kriteria tertentu tanpa mempertimbangkan langkah-langkah yang akan diambil selanjutnya.
- **Keputusan Tidak Dapat Dibalik**: Setelah membuat pilihan di setiap langkah, keputusan tersebut tidak dapat diubah lagi. Artinya, algoritma akan melanjutkan dengan pilihan yang sudah dibuat sebelumnya tanpa mempertimbangkan alternatif lain.
- **Mencapai Solusi Global**: Meskipun setiap langkah dipilih dengan cara lokal yang optimal, diharapkan bahwa pilihan tersebut akan membentuk solusi yang optimal secara keseluruhan.

#### 3. **Kelebihan dan Kekurangan Algoritma Greedy**
   
- **Kelebihan**:
  - Algoritma Greedy umumnya lebih cepat dibandingkan algoritma lainnya karena tidak memerlukan pencarian melalui semua kemungkinan solusi.
  - Sederhana dan mudah dipahami.
  
- **Kekurangan**:
  - Tidak selalu menghasilkan solusi yang optimal untuk semua masalah.
  - Tidak memperhitungkan konsekuensi dari keputusan yang diambil pada langkah selanjutnya.

#### 4. **Contoh Kasus: Masalah Knapsack**

Masalah **Knapsack** adalah salah satu contoh klasik di mana algoritma greedy sering digunakan. Masalah ini dapat dijelaskan sebagai berikut:

**Deskripsi Masalah**:
Seorang pengambil keputusan memiliki tas yang hanya bisa menampung sejumlah barang tertentu, yang masing-masing barang memiliki nilai dan berat. Tujuannya adalah untuk memilih barang-barang mana yang akan dimasukkan ke dalam tas sehingga total nilai barang yang dibawa adalah maksimal, tetapi total berat tidak melebihi kapasitas tas.

**Model Masalah Knapsack**:
- **Barang**: Sebuah barang \( i \) memiliki dua atribut: berat \( w_i \) dan nilai \( v_i \).
- **Kapasitas Tas**: Kapasitas tas adalah \( C \), sehingga berat total barang yang dimasukkan ke dalam tas tidak boleh melebihi kapasitas tas \( C \).

**Pendekatan Algoritma Greedy**:
Salah satu pendekatan greedy yang umum digunakan untuk masalah knapsack adalah **memilih barang berdasarkan rasio nilai terhadap berat** (Value-to-Weight Ratio). Barang dengan rasio nilai per berat tertinggi akan dipilih terlebih dahulu.

**Langkah-langkah Algoritma Greedy untuk Knapsack**:
1. Hitung rasio nilai terhadap berat untuk setiap barang \( r_i = \frac{v_i}{w_i} \).
2. Urutkan barang-barang berdasarkan rasio nilai terhadap berat, dari yang terbesar.
3. Pilih barang-barang yang dapat dimasukkan ke dalam tas, satu per satu, sampai kapasitas tas tercapai.

**Contoh**:

Misalkan kita memiliki tas dengan kapasitas \( C = 50 \), dan barang-barang berikut:

| Barang | Berat (w) | Nilai (v) | Rasio (v/w) |
|--------|-----------|-----------|-------------|
| 1      | 10        | 60        | 6           |
| 2      | 20        | 100       | 5           |
| 3      | 30        | 120       | 4           |

1. Urutkan berdasarkan rasio nilai terhadap berat: Barang 1 (6), Barang 2 (5), Barang 3 (4).
2. Pilih Barang 1 (10 berat, 60 nilai), sisa kapasitas \( 50 - 10 = 40 \).
3. Pilih Barang 2 (20 berat, 100 nilai), sisa kapasitas \( 40 - 20 = 20 \).
4. Pilih Barang 3 (30 berat, 120 nilai) tidak bisa dipilih karena beratnya melebihi sisa kapasitas 20.

**Total nilai yang didapat**: 60 + 100 = 160.

#### 5. **Contoh Kasus: Pencarian Jalur Terpendek (Shortest Path)**

Masalah **Pencarian Jalur Terpendek** adalah masalah untuk menemukan jalur dengan biaya terendah dari satu titik ke titik lain di dalam sebuah graf. Dalam graf tersebut, setiap sisi memiliki bobot atau biaya tertentu.

Salah satu algoritma greedy yang sering digunakan untuk masalah pencarian jalur terpendek adalah **Algoritma Dijkstra**.

**Deskripsi Masalah**:
Diberikan sebuah graf dengan simpul-simpul dan sisi-sisi yang terhubung, masing-masing sisi memiliki bobot atau biaya. Tujuannya adalah untuk menemukan jalur terpendek dari simpul sumber ke simpul tujuan.

**Langkah-langkah Algoritma Dijkstra**:
1. Tentukan simpul awal dan setel jarak awal ke 0, sementara jarak ke semua simpul lainnya diset ke tak terhingga.
2. Tentukan simpul yang belum diproses dengan jarak terkecil.
3. Untuk simpul tersebut, perbarui jarak ke tetangga-tetangganya jika jalur melalui simpul tersebut lebih pendek dari yang sebelumnya.
4. Tandai simpul yang telah diproses.
5. Ulangi langkah 2 hingga simpul tujuan ditemukan atau semua simpul telah diproses.

**Contoh**:
Misalkan kita memiliki graf berikut:

```
       (10)
  A -------- B
  |         /|
  |       /  |
 (5)    (2)  |
  |   /      |
  D -------- C
       (1)
```

Untuk mencari jalur terpendek dari **A ke C**, algoritma Dijkstra akan melakukan langkah-langkah berikut:

1. **Inisialisasi**: Jarak A = 0, Jarak B = tak terhingga, Jarak C = tak terhingga, Jarak D = tak terhingga.
2. **Proses simpul A**: Jarak A ke B adalah 10, Jarak A ke D adalah 5. Jadi, perbarui jarak B menjadi 10 dan D menjadi 5.
3. **Proses simpul D**: Jarak D ke C adalah 1, jadi perbarui jarak C menjadi 6.
4. **Proses simpul B**: Jarak B ke C adalah 2, jadi jarak C diperbarui menjadi 7 (meskipun jalur dari D ke C lebih pendek).
5. **Proses simpul C**: Jalur terpendek dari A ke C adalah 6, dengan jalur A -> D -> C.

#### 6. **Kesimpulan**

Algoritma Greedy adalah pendekatan yang efisien dan sederhana untuk beberapa masalah optimasi. Meskipun tidak selalu memberikan solusi optimal, pendekatan ini sering kali memberikan solusi yang cukup baik dalam waktu yang cepat. Dalam masalah seperti **Knapsack** dan **Pencarian Jalur Terpendek**, Algoritma Greedy seperti rasio nilai/berat dan Dijkstra sering digunakan untuk mencapai solusi yang optimal atau mendekati optimal.



---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

