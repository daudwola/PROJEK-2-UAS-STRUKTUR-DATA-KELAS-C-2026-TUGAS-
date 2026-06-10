# PROJEK-2-UAS-STRUKTUR-DATA-KELAS-C-2026-TUGAS-
PROJEK 2 UAS STRUKTUR DATA


# LAPORAN PROJEK 2 UAS #
# Nama anggota:
               1.= Daud Gollu Wola (2501010343)
               2.= Petrus k sanexsel Das Sa (2501010346)
               3.= Claudia F Bunga Na (2501010358)

__________________________________     

# SISTEM TRANSPORTASI PINTAR LABUAN BAJO

# BAB I  PENDAHULUAN

# * 1.1  Latar Belakang

Labuan Bajo merupakan salah satu destinasi wisata unggulan di Indonesia yang terus berkembang pesat, khususnya setelah ditetapkan sebagai salah satu dari lima destinasi super-prioritas pariwisata nasional. Pertumbuhan jumlah wisatawan yang signifikan membawa tantangan tersendiri bagi sistem transportasi publik di kawasan tersebut.
Sistem transportasi bus di Labuan Bajo saat ini masih menghadapi berbagai permasalahan, antara lain ketidakefisienan rute, kurangnya informasi real-time bagi penumpang, dan belum optimalnya pemanfaatan teknologi dalam perencanaan jaringan transportasi. Hal ini mengakibatkan waktu tempuh yang tidak efisien, biaya operasional yang tinggi, serta ketidakpuasan pengguna layanan.
Struktur data Graph menawarkan solusi yang sangat tepat untuk memodelkan jaringan transportasi. Setiap halte atau terminal dapat direpresentasikan sebagai node/vertex, sedangkan rute bus yang menghubungkan antar halte direpresentasikan sebagai edge. Dengan pendekatan ini, berbagai algoritma graph dapat diterapkan untuk menganalisis dan mengoptimalkan jaringan transportasi secara matematis dan terstruktur.
Decision Support System (DSS) berbasis graph memberikan kemampuan kepada pengambil keputusan untuk menganalisis jaringan transportasi, menemukan rute optimal, dan merekomendasikan kebijakan berdasarkan data relasional yang komprehensif. Implementasi Algoritma Prim sebagai Minimum Spanning Tree memungkinkan penentuan jaringan backbone transportasi yang paling efisien dengan total jarak minimum.

# * 1.2  Rumusan Masalah
  * Bagaimana cara merepresentasikan jaringan rute bus Labuan Bajo menggunakan struktur data Directed Graph?

  * Bagaimana implementasi Algoritma Prim untuk menemukan Minimum Spanning Tree pada jaringan transportasi?

  * Bagaimana DSS dapat memberikan rekomendasi rute yang optimal berdasarkan preferensi pengguna (jarak, waktu, atau biaya)?

  * Bagaimana analisis hubungan antar halte dapat mendukung pengambilan keputusan dalam perencanaan transportasi?

# * 1.3  Tujuan
   * 1.Merancang dan mengimplementasikan Directed Graph sebagai representasi jaringan bus transportasi Labuan Bajo.

   * 2.Mengimplementasikan Algoritma Prim untuk menentukan jaringan rute bus paling efisien menggunakan pendekatan Minimum Spanning Tree.
     
   * 3.Membangun modul DSS yang mampu memberikan rekomendasi rute berdasarkan preferensi jarak, waktu, dan biaya.
  
   * 4.Melakukan analisis topologi jaringan transportasi melalui degree analysis pada Directed Graph.
  
   * 5.Menghasilkan aplikasi berbasis Python yang interaktif dan terstruktur sebagai implementasi nyata struktur data graph.

 # 1.4  Manfaat
 
Manfaat akademis: Memahami secara mendalam implementasi struktur data Graph dalam studi kasus dunia nyata, serta menguasai algoritma Prim sebagai salah satu algoritma graph fundamental.

Manfaat praktis: Memberikan prototype sistem pendukung keputusan yang dapat dikembangkan lebih lanjut oleh Dinas Perhubungan Kabupaten Manggarai Barat untuk perencanaan dan optimasi jaringan transportasi bus di Labuan Bajo.

# BAB II  LANDASAN TEORI

* 2.1  Struktur Data Graph
Graph adalah struktur data non-linear yang terdiri dari sekumpulan vertex (simpul/node) dan sekumpulan edge (sisi/busur) yang menghubungkan pasangan vertex. Secara formal, sebuah graph G dapat didefinisikan sebagai G = (V, E), di mana V adalah himpunan vertex dan E adalah himpunan edge.
Graph memiliki berbagai aplikasi dalam ilmu komputer dan kehidupan nyata, termasuk pemodelan jaringan komputer, peta jalan, jejaring sosial, dan sistem transportasi. Kemampuan graph dalam merepresentasikan hubungan kompleks antar entitas menjadikannya salah satu struktur data yang paling powerful.

* 2.1.1  Directed Graph (Graf Berarah)
Directed Graph (Digraph) adalah jenis graph di mana setiap edge memiliki arah tertentu. Edge dalam directed graph direpresentasikan sebagai pasangan terurut (u, v), yang berarti terdapat koneksi berarah dari vertex u menuju vertex v, tetapi tidak sebaliknya kecuali ada edge (v, u) yang didefinisikan secara terpisah.

Dalam konteks transportasi bus, Directed Graph sangat relevan karena rute bus umumnya memiliki arah yang ditentukan. Sebuah bus yang beroperasi dari Terminal A ke Halte B tidak secara otomatis dapat beroperasi dari Halte B ke Terminal A dengan rute yang sama, melainkan menggunakan rute yang mungkin berbeda.

* 2.1.2  Representasi Graph: Adjacency List
Adjacency List adalah metode representasi graph yang menggunakan array atau dictionary untuk menyimpan daftar tetangga (neighbor) dari setiap vertex. Representasi ini sangat efisien untuk graph sparse (graph dengan jumlah edge jauh lebih sedikit dari jumlah vertex kuadrat).

Dalam implementasi Python, Adjacency List dapat direpresentasikan menggunakan defaultdict(list) dari modul collections. Setiap key merepresentasikan sebuah vertex, dan value-nya adalah list berisi informasi semua edge yang keluar dari vertex tersebut, termasuk tujuan, jarak, waktu, dan biaya.

<img width="876" height="200" alt="150691" src="https://github.com/user-attachments/assets/4c5aee19-bb67-42e3-ab3f-f1b95741eb5a" />


* 2.2  Algoritma Prim

Algoritma Prim adalah algoritma greedy yang digunakan untuk menemukan Minimum Spanning Tree (MST) dari sebuah graph berbobot terhubung. MST adalah sebuah spanning tree (pohon rentang) yang memiliki total bobot edge minimum di antara semua spanning tree yang mungkin dari graph tersebut.

Algoritma ini dinamai sesuai dengan penemunya, Robert C. Prim, yang mempublikasikannya pada tahun 1957. Algoritma Prim bekerja dengan cara membangun MST secara bertahap, dimulai dari sebuah vertex awal, kemudian terus memperluas pohon dengan memilih edge berbobot minimum yang menghubungkan vertex yang sudah ada di MST dengan vertex yang belum.

* 2.2.1  Langkah-langkah Algoritma Prim

* 1.Inisialisasi: Pilih sembarang vertex sebagai titik awal, masukkan ke dalam himpunan MST.

* 2.Eksplorasi: Temukan semua edge yang menghubungkan vertex dalam MST dengan vertex di luar MST.

* 3.Seleksi: Pilih edge dengan bobot minimum dari kumpulan edge yang ditemukan.

* 4.Perluasan: Tambahkan edge tersebut beserta vertex tujuannya ke dalam MST.

* 5.Iterasi: Ulangi langkah 2-4 sampai semua vertex telah masuk ke dalam MST.

# 2.2.2  Kompleksitas Algoritma Prim

![150698](https://github.com/user-attachments/assets/76a744ab-b2da-4fb2-ab7d-386a86a4b60d)
