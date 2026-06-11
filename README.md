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

* 1.1  Latar Belakang
Labuan Bajo merupakan salah satu destinasi wisata unggulan di Indonesia yang terletak di ujung barat Pulau Flores, Nusa Tenggara Timur. Seiring dengan meningkatnya kunjungan wisatawan domestik maupun mancanegara, kebutuhan akan sistem transportasi yang efisien dan terencana menjadi sangat krusial. Keterbatasan informasi mengenai jalur bus, jarak antar halte, dan waktu tempuh seringkali menjadi kendala utama bagi penumpang yang baru pertama kali mengunjungi kota ini.

Sistem Pendukung Keputusan (DSS) berbasis teknologi informasi hadir sebagai solusi untuk mengatasi permasalahan tersebut. Dengan memanfaatkan konsep struktur data Graf (Graph) dan algoritma pencarian jalur terpendek, sistem ini mampu memberikan rekomendasi rute bus yang optimal kepada pengguna secara real-time. Pendekatan ini tidak hanya meningkatkan efisiensi perjalanan, tetapi juga berkontribusi pada pengembangan infrastruktur transportasi cerdas di kawasan wisata.

1.2 Rumusan Masalah
Berdasarkan latar belakang di atas, rumusan masalah dalam proyek ini adalah:
Bagaimana merancang representasi jaringan transportasi bus Labuan Bajo menggunakan struktur data Graf?
Bagaimana mengimplementasikan algoritma Dijkstra untuk menemukan jalur terpendek antar halte bus?
Bagaimana membangun antarmuka DSS yang interaktif dan informatif bagi pengguna?

1.3 Tujuan Proyek
Tujuan dari proyek ini adalah:
Merancang dan mengimplementasikan representasi graf berbobot (weighted graph) untuk jaringan bus kota Labuan Bajo.
Mengimplementasikan algoritma Dijkstra untuk menentukan rute bus dengan jarak terpendek.
Membangun aplikasi DSS berbasis web menggunakan framework Streamlit yang dapat digunakan secara interaktif.
Menampilkan visualisasi graf transportasi beserta estimasi jarak dan waktu perjalanan.

1.4 Manfaat Proyek
Proyek ini diharapkan memberikan manfaat sebagai berikut:
Bagi pengguna transportasi: memperoleh informasi rute bus tercepat dan efisien.
Bagi pengelola transportasi: sebagai alat bantu perencanaan dan pengembangan rute.
Bagi akademisi: sebagai contoh penerapan konsep struktur data graf dalam kehidupan nyata.

BAB II: LANDASAN TEORI

2.1 Sistem Pendukung Keputusan (DSS)
Sistem Pendukung Keputusan (Decision Support System / DSS) adalah sistem berbasis komputer yang dirancang untuk membantu pengambilan keputusan dalam situasi yang semi-terstruktur maupun tidak terstruktur. DSS menggabungkan data, model analitis, dan antarmuka pengguna yang interaktif untuk menghasilkan rekomendasi yang relevan dan akurat.

Dalam konteks transportasi, DSS berperan sebagai sistem yang mengolah data jaringan jalan, jarak, dan waktu tempuh untuk memberikan rekomendasi rute perjalanan yang optimal kepada pengguna.

2.2 Struktur Data Graf
Graf (Graph) adalah struktur data non-linear yang terdiri dari sekumpulan simpul (node/vertex) yang dihubungkan oleh sisi (edge/arc). Graf dapat diklasifikasikan sebagai berikut:

<img width="719" height="265" alt="153318" src="https://github.com/user-attachments/assets/59d81587-3cd7-435b-b148-1aecb202854e" />

2.3 Algoritma Dijkstra
Algoritma Dijkstra adalah algoritma pencarian jalur terpendek pada graf berbobot yang dikembangkan oleh Edsger W. Dijkstra pada tahun 1956. Algoritma ini bekerja dengan prinsip greedy, yaitu secara bertahap memilih simpul dengan jarak terpendek yang belum dikunjungi.

Langkah-langkah Algoritma Dijkstra:
Inisialisasi: tetapkan jarak semua simpul sebagai tak terhingga (infinity), kecuali simpul asal yang bernilai 0.
Masukkan simpul asal ke dalam priority queue.
Ambil simpul dengan jarak terkecil dari queue.
Untuk setiap tetangga simpul tersebut, hitung jarak baru (jarak simpul saat ini + bobot sisi).
Jika jarak baru lebih kecil dari jarak tersimpan, perbarui dan masukkan ke queue.
Ulangi langkah 3-5 hingga semua simpul telah diproses atau simpul tujuan ditemukan.

Kompleksitas waktu algoritma Dijkstra dengan priority queue adalah O((V + E) log V), di mana V adalah jumlah simpul dan E adalah jumlah sisi.

2.4 NetworkX Library
NetworkX adalah library Python yang digunakan untuk pembuatan, manipulasi, dan analisis struktur jaringan (graf). Library ini menyediakan implementasi berbagai algoritma graf termasuk Dijkstra, BFS (Breadth-First Search), dan DFS (Depth-First Search). Fungsi utama yang digunakan dalam proyek ini:
nx.Graph(): membuat objek graf tidak berarah.
G.add_edge(u, v, weight=w): menambahkan sisi berbobot antara dua simpul.
nx.dijkstra_path(): mengembalikan jalur terpendek antara dua simpul.
nx.dijkstra_path_length(): mengembalikan total jarak jalur terpendek.
nx.draw(): memvisualisasikan graf ke dalam plot matplotlib.

2.5 Streamlit Framework
Streamlit adalah framework Python open-source untuk membangun aplikasi web data science dan machine learning secara cepat tanpa memerlukan pengetahuan HTML/CSS/JavaScript. Streamlit memungkinkan pengembang untuk membuat antarmuka interaktif hanya dengan kode Python.


BAB III: ANALISIS DAN PERANCANGAN

3.1 Analisis Kebutuhan Sistem
Sistem DSS Transportasi Bus Labuan Bajo dirancang untuk memenuhi kebutuhan fungsional berikut:

Kebutuhan Fungsional:
Sistem dapat menerima input halte asal dan halte tujuan dari pengguna.
Sistem dapat menghitung dan menampilkan jalur terpendek antara dua halte menggunakan algoritma Dijkstra.
Sistem menampilkan total jarak perjalanan dalam satuan kilometer.
Sistem memberikan estimasi waktu perjalanan berdasarkan jarak.
Sistem memvisualisasikan jaringan graf transportasi secara grafis.
Sistem menampilkan tabel data jalur bus lengkap.
Kebutuhan Non-Fungsional:
Antarmuka mudah digunakan (user-friendly).
Sistem merespons dalam waktu kurang dari 2 detik.
Visualisasi graf jelas dan mudah dipahami.
3.2 Perancangan Graf Transportasi
Jaringan transportasi bus Labuan Bajo dimodelkan sebagai Undirected Weighted Graph dengan 7 simpul (halte) dan 9 sisi (rute). Berikut adalah data topologi jaringan:

<img width="829" height="446" alt="153320" src="https://github.com/user-attachments/assets/77c8712a-56de-4dc6-a45d-2ddb0fdec04d" />

3.3 Deskripsi Simpul (Halte)
Berikut adalah deskripsi singkat setiap simpul dalam graf:

<img width="788" height="462" alt="153322" src="https://github.com/user-attachments/assets/eaf858da-d309-4395-bed9-c4bba42c9106" />
