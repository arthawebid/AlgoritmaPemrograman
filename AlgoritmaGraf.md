[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

### **1. Pengertian Graf dan Terminologi**
Graf adalah struktur data yang digunakan untuk menggambarkan hubungan antar objek yang disebut **simpul** atau **vertex**, yang dihubungkan oleh **sisi** atau **edge**. Graf sering digunakan untuk memodelkan berbagai masalah dalam kehidupan nyata, seperti jaringan sosial, peta rute, dan hubungan antara entitas.

**Terminologi Graf:**
- **Vertex (V)**: Titik-titik yang saling terhubung dalam graf.
- **Edge (E)**: Hubungan atau sisi yang menghubungkan pasangan vertex.
- **Derajat (Degree)**: Banyaknya sisi yang terhubung ke suatu vertex.
  - **Derajat masuk (in-degree)**: Jumlah sisi yang masuk ke suatu vertex (untuk graf terarah).
  - **Derajat keluar (out-degree)**: Jumlah sisi yang keluar dari suatu vertex (untuk graf terarah).
- **Graf Terarah (Directed Graph)**: Graf di mana sisi memiliki arah (dari satu vertex ke vertex lainnya).
- **Graf Tak Terarah (Undirected Graph)**: Graf di mana sisi tidak memiliki arah.
- **Graf Berbobot (Weighted Graph)**: Setiap sisi pada graf memiliki bobot atau nilai numerik.
- **Graf Lengkap (Complete Graph)**: Setiap pasangan vertex dihubungkan oleh sisi.
- **Graf Terhubung (Connected Graph)**: Setiap vertex dalam graf dapat dijangkau dari vertex lainnya melalui sisi.

---

### **2. Representasi Graf**
Ada dua cara utama untuk merepresentasikan graf dalam pemrograman:

#### **a. Matriks Ketetanggaan (Adjacency Matrix)**
Matriks ketetanggaan adalah matriks dua dimensi yang digunakan untuk menyimpan informasi mengenai keberadaan sisi antara pasangan vertex.

- **Untuk graf tak terarah**, matriks ini simetris, artinya jika ada sisi antara vertex `u` dan `v`, maka `matriks[u][v]` dan `matriks[v][u]` keduanya bernilai 1.
- **Untuk graf terarah**, matriks ini tidak simetris, artinya jika ada sisi dari vertex `u` ke vertex `v`, maka `matriks[u][v]` bernilai 1, tetapi tidak ada nilai pada `matriks[v][u]` kecuali jika ada sisi terarah dari `v` ke `u`.

Contoh Matriks Ketetanggaan:
```
    0  1  2  3
0   0  1  0  1
1   1  0  1  0
2   0  1  0  0
3   1  0  0  0
```

#### **b. Daftar Ketetanggaan (Adjacency List)**
Daftar ketetanggaan adalah representasi graf yang lebih efisien dalam hal ruang, di mana setiap vertex disimpan sebagai simpul dengan daftar sisi yang terhubung ke simpul tersebut.

Contoh Daftar Ketetanggaan:
```
0 → [1, 3]
1 → [0, 2]
2 → [1]
3 → [0]
```

---

### **3. Algoritma Penelusuran Graf (DFS dan BFS)**
Dua algoritma dasar untuk penelusuran graf adalah **Depth-First Search (DFS)** dan **Breadth-First Search (BFS)**.

#### **a. Depth-First Search (DFS)**
DFS adalah algoritma yang digunakan untuk menjelajahi graf dengan cara mendalam. Dimulai dari sebuah vertex, DFS akan mengunjungi vertex tetangga yang belum dikunjungi, lalu terus menjelajah lebih dalam ke vertex-vertex yang terhubung.

- **Ciri khas**: DFS menggunakan prinsip **LIFO (Last In, First Out)**, biasanya diimplementasikan menggunakan **stack**.
- **Proses**:
  1. Mulai dari simpul awal.
  2. Kunjungi simpul yang belum dikunjungi dan masukkan simpul ke stack.
  3. Kunjungi semua tetangga simpul yang belum dikunjungi secara rekursif.
  4. Kembali ke simpul sebelumnya ketika tidak ada simpul tetangga yang belum dikunjungi.

#### **b. Breadth-First Search (BFS)**
BFS adalah algoritma yang digunakan untuk menjelajahi graf dengan cara meluas. Dimulai dari sebuah vertex, BFS mengunjungi semua tetangga pada tingkat pertama sebelum melanjutkan ke tingkat berikutnya.

- **Ciri khas**: BFS menggunakan prinsip **FIFO (First In, First Out)**, biasanya diimplementasikan menggunakan **queue**.
- **Proses**:
  1. Mulai dari simpul awal.
  2. Kunjungi semua tetangga simpul secara berurutan dan masukkan ke dalam antrian.
  3. Kunjungi simpul dari antrian secara berurutan hingga semua simpul terkunjungi.

---

### **4. Algoritma Dijkstra dan Bellman-Ford**
Kedua algoritma ini digunakan untuk menemukan jalur terpendek dalam graf berbobot.

#### **a. Algoritma Dijkstra**
Dijkstra adalah algoritma yang digunakan untuk mencari jalur terpendek dari satu sumber ke semua simpul lainnya dalam graf berbobot. Algoritma ini hanya berlaku untuk graf dengan bobot sisi positif.

- **Langkah-langkah**:
  1. Inisialisasi jarak dari sumber ke semua simpul sebagai tak terhingga, kecuali sumber yang bernilai 0.
  2. Pilih simpul dengan jarak terkecil yang belum diproses.
  3. Perbarui jarak ke semua tetangga simpul yang terpilih.
  4. Tandai simpul tersebut sebagai diproses dan ulangi hingga semua simpul diproses.

#### **b. Algoritma Bellman-Ford**
Bellman-Ford adalah algoritma yang digunakan untuk mencari jalur terpendek dari satu sumber ke semua simpul lainnya dalam graf berbobot, termasuk graf dengan bobot negatif. Bellman-Ford dapat mendeteksi adanya siklus negatif.

- **Langkah-langkah**:
  1. Inisialisasi jarak dari sumber ke semua simpul sebagai tak terhingga, kecuali sumber yang bernilai 0.
  2. Perbarui jarak setiap simpul melalui relaksasi pada semua sisi.
  3. Ulangi langkah 2 sebanyak (V-1) kali, di mana V adalah jumlah simpul.
  4. Periksa apakah ada siklus negatif dengan memeriksa apakah masih ada sisi yang bisa dipercepat.

---

### **5. Algoritma Kruskal dan Prim (Minimum Spanning Tree - MST)**
Untuk mencari pohon penjelajah minimum (Minimum Spanning Tree / MST) dari sebuah graf berbobot, kita bisa menggunakan algoritma Kruskal atau Prim.

#### **a. Algoritma Kruskal**
Kruskal adalah algoritma untuk menemukan MST dengan cara memilih sisi-sisi dengan bobot terkecil secara bertahap, dengan memperhatikan agar tidak terjadi siklus.

- **Langkah-langkah**:
  1. Urutkan semua sisi graf berdasarkan bobotnya.
  2. Ambil sisi dengan bobot terkecil yang tidak membentuk siklus dan tambahkan ke MST.
  3. Ulangi langkah 2 hingga semua simpul terhubung.

#### **b. Algoritma Prim**
Prim adalah algoritma untuk menemukan MST yang dimulai dari simpul asal dan terus memperluas pohon dengan memilih sisi terkecil yang menghubungkan pohon dengan simpul baru.

- **Langkah-langkah**:
  1. Pilih simpul awal sebagai titik start.
  2. Pilih sisi dengan bobot terkecil yang menghubungkan simpul dalam pohon dengan simpul di luar pohon.
  3. Tambahkan sisi tersebut ke MST dan perbarui pohon.
  4. Ulangi hingga semua simpul terhubung.

---

### **Kesimpulan**
- **Graf** adalah struktur data yang digunakan untuk merepresentasikan hubungan antara objek-objek.
- **Penelusuran Graf** dapat dilakukan dengan **DFS** (depth-first) atau **BFS** (breadth-first).
- **Algoritma Dijkstra** dan **Bellman-Ford** digunakan untuk menemukan jalur terpendek dalam graf berbobot.
- **Algoritma Kruskal** dan **Prim** digunakan untuk menemukan Minimum Spanning Tree (MST) dari graf berbobot.

Materi ini memberikan gambaran dasar tentang konsep-konsep graf dan algoritma-algoritma yang terkait dengan graf dalam pemrograman.
---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

