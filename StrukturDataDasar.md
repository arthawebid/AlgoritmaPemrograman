[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)

---

Berikut adalah materi perkuliahan mengenai **Algoritma Pemrograman** dengan pembahasan tentang **Struktur Data Dasar**, **Array dan Matriks**, **Linked List**, **Stack dan Queue**, **Tree dan Binary Search Tree**, serta **Graph**.

---

### **1. Struktur Data Dasar**
Struktur data adalah cara untuk menyimpan dan mengorganisir data dalam komputer agar dapat digunakan secara efisien. Struktur data dasar mencakup berbagai tipe data yang sering digunakan dalam pemrograman.

#### **Tipe Data Dasar:**
- **Integer**: Bilangan bulat.
- **Float**: Bilangan pecahan.
- **Character**: Tipe data untuk karakter tunggal.
- **Boolean**: Tipe data untuk nilai benar (true) atau salah (false).

#### **Operasi Dasar pada Struktur Data:**
- **Insert**: Menambahkan elemen ke dalam struktur data.
- **Delete**: Menghapus elemen dari struktur data.
- **Search**: Mencari elemen dalam struktur data.
- **Update**: Memperbarui nilai elemen yang ada.
- **Traversal**: Mengakses atau menelusuri seluruh elemen dalam struktur data.

---

### **2. Array dan Matriks**
**Array** adalah struktur data yang digunakan untuk menyimpan elemen-elemen dengan tipe data yang sama dalam urutan tertentu. Elemen-elemen dalam array diakses menggunakan indeks.

#### **Array:**
- **Definisi**: Array adalah kumpulan elemen yang memiliki tipe data yang sama dan diakses menggunakan indeks.
- **Operasi Dasar**:
  - **Akses elemen**: Mengakses elemen dengan menggunakan indeks.
  - **Pencarian elemen**: Mencari elemen dalam array.
  - **Penyisipan elemen**: Menambahkan elemen baru ke dalam array.
  - **Penghapusan elemen**: Menghapus elemen dari array.

Contoh implementasi array dalam bahasa pemrograman C:
```c
int arr[5] = {1, 2, 3, 4, 5};
printf("%d", arr[0]); // Mengakses elemen pertama (output: 1)
```

#### **Matriks:**
Matriks adalah array dua dimensi (atau lebih) yang digunakan untuk menyimpan data dalam bentuk tabel (baris dan kolom).

Contoh matriks 2x3:
```
| 1 | 2 | 3 |
| 4 | 5 | 6 |
```

Operasi dasar matriks:
- **Penjumlahan matriks**: Menambahkan dua matriks dengan ukuran yang sama.
- **Perkalian matriks**: Mengalikan dua matriks dengan kondisi yang sesuai.

---

### **3. Linked List**
Linked List adalah struktur data yang terdiri dari sekumpulan elemen yang disebut **node**, di mana setiap node berisi dua bagian: data dan referensi (pointer) ke node berikutnya.

#### **Jenis-jenis Linked List:**
- **Singly Linked List**: Setiap node hanya mengarah ke node berikutnya.
- **Doubly Linked List**: Setiap node mengarah ke node sebelumnya dan berikutnya.
- **Circular Linked List**: Node terakhir mengarah ke node pertama, membentuk lingkaran.

#### **Operasi Linked List:**
- **Insert**: Menambahkan node baru ke dalam linked list.
- **Delete**: Menghapus node dari linked list.
- **Search**: Mencari node dalam linked list.
- **Traverse**: Menelusuri seluruh node dalam linked list.

Contoh implementasi Singly Linked List dalam bahasa pemrograman C:
```c
struct Node {
    int data;
    struct Node* next;
};
```

---

### **4. Stack dan Queue**
**Stack** dan **Queue** adalah dua struktur data yang digunakan untuk menyimpan elemen-elemen dalam urutan tertentu.

#### **Stack:**
Stack adalah struktur data berbasis prinsip **Last In First Out (LIFO)**, di mana elemen yang terakhir dimasukkan adalah yang pertama dikeluarkan.

Operasi dasar pada Stack:
- **Push**: Menambahkan elemen ke dalam stack.
- **Pop**: Menghapus elemen dari stack.
- **Peek**: Melihat elemen paling atas tanpa menghapusnya.

Contoh penggunaan stack (misal dalam bahasa C):
```c
void push(int stack[], int *top, int value) {
    stack[++(*top)] = value;
}
```

#### **Queue:**
Queue adalah struktur data berbasis prinsip **First In First Out (FIFO)**, di mana elemen yang pertama dimasukkan adalah yang pertama dikeluarkan.

Operasi dasar pada Queue:
- **Enqueue**: Menambahkan elemen ke dalam queue.
- **Dequeue**: Menghapus elemen dari queue.
- **Front**: Melihat elemen paling depan tanpa menghapusnya.

Contoh implementasi Queue dalam C:
```c
void enqueue(int queue[], int *front, int *rear, int value) {
    queue[++(*rear)] = value;
}
```

---

### **5. Tree dan Binary Search Tree**
**Tree** adalah struktur data hierarkis yang terdiri dari node, di mana setiap node dapat memiliki anak (children).

#### **Jenis-jenis Tree:**
- **Binary Tree**: Setiap node memiliki dua anak (kiri dan kanan).
- **Binary Search Tree (BST)**: Binary tree di mana setiap node memiliki nilai lebih kecil di sebelah kiri dan lebih besar di sebelah kanan.

#### **Operasi pada Tree/BST:**
- **Traversal**:
  - **In-order**: Kunjungi kiri, akar, kanan.
  - **Pre-order**: Kunjungi akar, kiri, kanan.
  - **Post-order**: Kunjungi kiri, kanan, akar.
- **Insert**: Menambahkan elemen ke dalam BST.
- **Search**: Mencari elemen di dalam BST.

Contoh implementasi insert pada Binary Search Tree:
```c
struct Node* insert(struct Node* node, int key) {
    if (node == NULL) {
        return newNode(key);
    }
    if (key < node->data) {
        node->left = insert(node->left, key);
    } else if (key > node->data) {
        node->right = insert(node->right, key);
    }
    return node;
}
```

---

### **6. Graph**
Graph adalah struktur data yang digunakan untuk menyimpan kumpulan elemen yang disebut **vertex** (titik) yang saling terhubung oleh **edge** (sisi). Graph dapat digunakan untuk merepresentasikan jaringan, seperti sosial media, rute perjalanan, dan lainnya.

#### **Jenis-jenis Graph:**
- **Undirected Graph**: Edges tidak memiliki arah (dua arah).
- **Directed Graph (Digraph)**: Edges memiliki arah (satu arah).
- **Weighted Graph**: Setiap edge memiliki bobot atau nilai tertentu.

#### **Représentasi Graph:**
- **Adjacency Matrix**: Matriks 2D yang menyatakan hubungan antara vertex.
- **Adjacency List**: Setiap vertex memiliki daftar tetangga yang terhubung.

#### **Operasi pada Graph:**
- **DFS (Depth-First Search)**: Traversal graph dengan mendalami satu jalur terlebih dahulu sebelum berpindah ke jalur lain.
- **BFS (Breadth-First Search)**: Traversal graph dengan mengunjungi vertex-vertex yang berdekatan terlebih dahulu sebelum melanjutkan ke yang lebih jauh.
  
Contoh implementasi BFS dalam C:
```c
void BFS(int graph[MAX][MAX], int visited[MAX], int start) {
    queue.enqueue(start);
    visited[start] = 1;
    while (!queue.isEmpty()) {
        int node = queue.dequeue();
        printf("%d ", node);
        for (int i = 0; i < MAX; i++) {
            if (graph[node][i] == 1 && !visited[i]) {
                queue.enqueue(i);
                visited[i] = 1;
            }
        }
    }
}
```

---

### **Kesimpulan:**
Materi ini memberikan gambaran dasar mengenai berbagai struktur data yang digunakan dalam algoritma pemrograman, seperti array, linked list, stack, queue, tree, binary search tree, dan graph. Pemahaman tentang struktur data ini sangat penting untuk menyelesaikan masalah pemrograman secara efisien dan efektif.




---
[TOC](README.md) | [Pendahuluan](Pendahuluan.md) | [Dasar-Dasar Pemrograman](DasarPemrograman.md) | [Tipe-Tipe Algoritma](TipeAlgoritma.md) | [Struktur Data Dasar](StrukturDataDasar.md) | [Analisis Algoritma](AnalisisAlgoritma.md) | [Algoritma Pencarian](AlgoritmaPencarian.md) | [Algoritma Pengurutan](AlgoritmaPengurutan.md) | [Algoritma Rekursif](AlgoritmaRekursif.md) | [Algoritma Greedy](AlgoritmaGreedy.md) | [Algoritma Dinamis](AlgoritmaDinamis.md) | [Graf dan Algoritma Graf](AlgoritmaGraf.md) | [Kompleksitas dan Optimasi Algoritma](KompleksitasdanOptimasiAlgoritma.md) | [Penerapan Algoritma dalam Kehidupan Nyata](PenerapanAlgoritma.md) | [Studi Kasus dan Proyek](StudiKasus.md) | [Penutupan](Penutupan.md)