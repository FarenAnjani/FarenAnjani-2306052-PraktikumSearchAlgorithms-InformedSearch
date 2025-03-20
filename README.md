# Algoritma Pencarian: Greedy Best-First Search dan A*

## Deskripsi
Repositori ini berisi implementasi algoritma pencarian **Greedy Best-First Search** dan **A* Search** menggunakan bahasa Python. Kedua algoritma ini digunakan untuk menemukan jalur dari titik awal ke tujuan dalam sebuah graf berbobot.

## Algoritma
### Greedy Best-First Search
Greedy Best-First Search adalah algoritma pencarian yang hanya mempertimbangkan nilai heuristik saat memilih jalur terbaik, tanpa memperhitungkan biaya dari titik awal. Fungsi evaluasi yang digunakan adalah:

```
f(n) = h(n)
```

Di mana:
- `h(n)` adalah estimasi biaya dari simpul saat ini ke simpul tujuan.

#### Kelebihan:
- Dapat menemukan solusi dengan cepat dalam beberapa kasus.
- Cocok untuk masalah dengan heuristik yang cukup akurat.

#### Kekurangan:
- Tidak selalu menghasilkan solusi optimal.
- Bisa terjebak dalam jalur yang tidak efisien.

---

### A* (A-Star) Search
A* Search adalah algoritma yang mengombinasikan pendekatan **Greedy Best-First Search** dan **Uniform Cost Search**. Fungsi evaluasinya adalah:

```
f(n) = g(n) + h(n)
```

Di mana:
- `g(n)` adalah biaya dari simpul awal ke simpul saat ini.
- `h(n)` adalah estimasi biaya dari simpul saat ini ke tujuan.

#### Varian A*:
1. **A* Graph Search**
   - Digunakan pada graf yang memiliki siklus.
   - Menyimpan daftar simpul yang telah dikunjungi untuk menghindari eksplorasi ulang.
   - Lebih efisien dalam memori karena menghindari kunjungan berulang.

2. **A* Tree Search**
   - Digunakan dalam struktur pohon tanpa siklus.
   - Tidak menyimpan daftar simpul yang telah dikunjungi.
   - Bisa lebih cepat dalam beberapa kasus, tetapi berpotensi mengeksplorasi ulang simpul yang sudah dikunjungi.

#### Kelebihan A*:
- Menjamin solusi optimal jika heuristik yang digunakan **admissible** dan **consistent**.
- Lebih efisien dibandingkan algoritma pencarian uninformed.

#### Kekurangan A*:
- Membutuhkan banyak memori karena harus menyimpan semua simpul yang dikunjungi.
- Kinerjanya sangat bergantung pada efektivitas fungsi heuristik.

---

## Cara Menjalankan Program
### Persyaratan
Pastikan Anda memiliki **Python 3.x** terinstal di sistem Anda.

### Menjalankan Program
1. Clone repositori ini atau unduh file kode.
2. Buka terminal atau command prompt dan navigasikan ke direktori proyek.
3. Jalankan perintah berikut untuk mengeksekusi skrip:

   ```sh
   python search_algorithm.py
   ```

### Contoh Input
Graf direpresentasikan dalam bentuk adjacency list, dengan heuristik sebagai berikut:

```python
heuristic = {
    'P': 8,
    'Q': 6,
    'R': 5,
    'S': 3,
    'T': 2,
    'Z': 0,
}

graph = {
    'P': {'Q', 'R'},
    'Q': {'S', 'T'},
    'R': {'S', 'T'},
    'S': {'T', 'Z'},
    'T': {'Z'},
}
```

### Output Contoh
Jika algoritma dijalankan dengan titik awal `P` dan tujuan `Z`, hasilnya akan menunjukkan jalur yang diambil dan jumlah akses heuristik yang digunakan.

---

## Kesimpulan
- **Greedy Best-First Search** hanya mempertimbangkan heuristik `h(n)`, sehingga sering kali lebih cepat tetapi tidak selalu optimal.
- **A* Search** mempertimbangkan total biaya `g(n) + h(n)`, sehingga lebih optimal meskipun lebih mahal dalam komputasi.
- **A* Graph Search** lebih efisien dalam eksplorasi ulang dibanding **A* Tree Search**, karena menghindari kunjungan yang sama lebih dari sekali.

---

## Lisensi
Proyek ini menggunakan lisensi **MIT License**. Silakan gunakan dan modifikasi sesuai kebutuhan Anda.

