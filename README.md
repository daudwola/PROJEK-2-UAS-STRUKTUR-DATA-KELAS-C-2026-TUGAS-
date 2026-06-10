
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

Labuan Bajo, sebagai destinasi wisata kelas dunia di Nusa Tenggara Timur, mengalami pertumbuhan kunjungan wisatawan yang signifikan dalam beberapa tahun terakhir. Pertumbuhan ini membawa konsekuensi langsung pada meningkatnya mobilitas penduduk dan wisatawan di dalam kota, yang pada akhirnya menimbulkan tantangan serius dalam pengelolaan sistem transportasi publik.

Sistem transportasi publik yang ada saat ini belum mampu merespons kebutuhan mobilitas secara optimal. Rute bus yang tidak efisien, ketidakjelasan informasi jadwal dan tarif, serta ketidakmampuan sistem dalam memberikan rekomendasi rute yang dipersonalisasi menjadi keluhan utama pengguna transportasi di kota ini.

Dalam konteks ilmu komputer, permasalahan jaringan transportasi dapat dimodelkan secara elegan menggunakan struktur data Graf (Graph). Setiap halte bus direpresentasikan sebagai simpul (node), sementara rute yang menghubungkan dua halte direpresentasikan sebagai sisi (edge) berbobot. Model ini memungkinkan penerapan berbagai algoritma graf klasik untuk menganalisis dan mengoptimalkan jaringan transportasi.

Salah satu algoritma yang relevan adalah Algoritma Prim untuk mencari Minimum Spanning Tree (MST). MST memberikan representasi jaringan rute backbone paling efisien yang menghubungkan seluruh halte dengan total jarak minimum — sangat berguna dalam perencanaan pengembangan infrastruktur transportasi.

Proyek ini merupakan implementasi Decision Support System (DSS) berbasis Directed Graph untuk sistem transportasi pintar di Labuan Bajo. Program diimplementasikan dalam bahasa Python dengan mengintegrasikan Algoritma Prim (MST), Breadth-First Search (BFS), dan Depth-First Search (DFS) sebagai komponen inti pengambilan keputusan.

* 1.2  Rumusan Masalah
  
1.	Bagaimana merepresentasikan jaringan rute bus Labuan Bajo dalam bentuk Directed Graph yang dapat diproses secara komputasional?
2.	Bagaimana mengimplementasikan Algoritma Prim untuk menemukan Minimum Spanning Tree pada jaringan transportasi guna mengidentifikasi rute backbone paling efisien?
3.	Bagaimana mengintegrasikan algoritma pencarian jalur (BFS dan DFS) untuk memberikan rekomendasi rute berdasarkan preferensi pengguna (jarak, waktu, atau biaya)?
4.	Bagaimana merancang sistem DSS yang dapat menganalisis dan menyajikan informasi jaringan transportasi secara informatif kepada pengguna?

* 1.3  Tujuan
  
▸	Mengimplementasikan Directed Graph sebagai struktur data utama untuk merepresentasikan jaringan bus Labuan Bajo dengan 8 halte dan 20 rute.

▸	Menerapkan Algoritma Prim untuk menemukan MST yang merepresentasikan jaringan rute bus paling efisien dari sisi total jarak tempuh.

▸	Mengembangkan modul pencarian jalur menggunakan BFS (pencarian jalur terpendek berdasarkan jumlah hop) dan DFS (pencarian jalur alternatif) antara dua halte.

▸	Membangun modul DSS yang mengintegrasikan seluruh komponen di atas untuk menghasilkan rekomendasi rute dan analisis jaringan transportasi yang komprehensif.

* 1.4  Manfaat
  
Manfaat Akademis

▸	Penerapan nyata konsep struktur data Graf dalam konteks problem solving transportasi.

▸	Pemahaman mendalam terhadap Algoritma Prim dan MST melalui implementasi langsung.

▸	Demonstrasi integrasi beberapa algoritma (Prim, BFS, DFS) dalam satu sistem terpadu.

▸	Referensi pembelajaran DSS berbasis struktur data untuk mahasiswa Teknik Informatika.

Manfaat Praktis

▸	Memberikan model komputasi untuk optimasi rute bus di Labuan Bajo.

▸	Mendukung pengambilan keputusan dalam perencanaan pengembangan infrastruktur transportasi.

▸	Menyediakan dasar pengembangan aplikasi transportasi publik berbasis data.

▸	Meningkatkan aksesibilitas informasi rute bagi wisatawan dan warga lokal.


# BAB 2 — DASAR TEORI

* 2.1  Struktur Data Graph
  
Graf (Graph) adalah struktur data yang merepresentasikan hubungan antara kumpulan objek. Secara formal, graf G didefinisikan sebagai pasangan terurut G = (V, E), di mana V adalah himpunan simpul (vertices/nodes) dan E adalah himpunan sisi (edges) yang menghubungkan pasangan simpul

* 2.1.1  Jenis-Jenis Graf
<img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/db305c0c-5283-4bc7-9dac-0f4f8fc378d2" />

* 2.1.2  Representasi Graf — Adjacency List
  
Proyek ini menggunakan Adjacency List sebagai representasi internal graf. Setiap simpul menyimpan daftar tetangga beserta atribut sisi (jarak, waktu, biaya). Kompleksitas ruang: O(V + E), lebih efisien dibanding Adjacency Matrix O(V²) untuk graf jarang (sparse graph).

<img width="866" height="154" alt="image" src="https://github.com/user-attachments/assets/99646f98-712b-4561-abbd-d436ec1c8941" />

* 2.2  Decision Support System (DSS)

Decision Support System (DSS) adalah sistem berbasis komputer yang membantu pengambil keputusan dalam menghadapi masalah semi-terstruktur atau tidak terstruktur. DSS mengintegrasikan data, model analitik, dan antarmuka pengguna untuk menghasilkan rekomendasi yang mendukung proses pengambilan keputusan.

# Komponen utama DSS dalam proyek ini:

▸	Data Management: Struktur data Directed Graph untuk menyimpan informasi halte dan rute bus.

▸	Model Management: Algoritma Prim, BFS, dan DFS sebagai model analitik.

▸	Knowledge Base: Aturan rekomendasi berdasarkan preferensi pengguna (jarak/waktu/biaya).

▸	User Interface: Output terformat di terminal dengan analisis skor keputusan multi-kriteria.

<img width="699" height="200" alt="image" src="https://github.com/user-attachments/assets/a344eb2a-024e-4022-941e-b25612ebff3c" />

* 2.3  Algoritma Graf yang Digunakan

* 2.3.1  Algoritma Prim — Minimum Spanning Tree

Algoritma Prim adalah algoritma greedy untuk menemukan Minimum Spanning Tree (MST) pada graf berbobot. MST adalah subgraf pohon (tree) yang menghubungkan semua simpul dengan total bobot sisi minimum tanpa membentuk siklus.

<img width="954" height="310" alt="image" src="https://github.com/user-attachments/assets/95a405f3-1eb3-42a4-8932-eee0654f3e5e" />

# Langkah-langkah Algoritma Prim:

1.	Pilih simpul awal secara arbitrer (proyek: Terminal Labuan Bajo / LBJ).

2.	Masukkan simpul awal ke dalam himpunan MST (dikunjungi).

3.	Tambahkan semua sisi dari simpul di MST ke dalam priority queue (min-heap berdasarkan bobot).

4.	Pilih sisi berbobot minimum dari priority queue yang menghubungkan simpul dalam MST ke simpul di luar MST.

5.	Tambahkan simpul tujuan ke MST, tambahkan sisi ke hasil MST.

6.	Ulangi langkah 3-5 hingga semua simpul masuk MST

2.3.2  Breadth-First Search (BFS)
BFS adalah algoritma traversal graf yang mengeksplorasi simpul-simpul berdasarkan jarak (jumlah hop) dari simpul asal. BFS menggunakan struktur data antrian (queue) dan menjamin ditemukannya jalur dengan jumlah hop minimum.
▸	Kompleksitas Waktu: O(V + E)
▸	Kompleksitas Ruang: O(V)
▸	Penggunaan dalam DSS: Mencari jalur terpendek berdasarkan jumlah halte transit minimum.

* 2.3.3  Depth-First Search (DFS)

DFS adalah algoritma traversal yang mengeksplorasi sedalam mungkin pada satu cabang sebelum backtrack. DFS menggunakan tumpukan (stack) atau rekursi.

▸	Kompleksitas Waktu: O(V + E)

▸	Kompleksitas Ruang: O(V) untuk call stack

▸	Penggunaan dalam DSS: Menemukan rute alternatif yang mungkin berbeda dari BFS.
 
# BAB 3 — ANALISIS DAN PERANCANGAN
3.1  Analisis Masalah
Permasalahan inti yang diselesaikan dalam proyek ini adalah optimasi jaringan transportasi bus di Labuan Bajo menggunakan pendekatan struktur data dan algoritma graf. Analisis masalah dilakukan dari dua perspektif:

* 3.1.1  Perspektif Jaringan Transportasi

▸	Terdapat 8 titik perhentian (halte/terminal) yang perlu dihubungkan secara efisien.

▸	Setiap rute bus memiliki atribut multibobot: jarak (km), waktu tempuh (menit), dan biaya (Rp).

▸	Beberapa rute bersifat satu arah, sehingga membutuhkan Directed Graph.

▸	Pengguna membutuhkan rekomendasi rute yang disesuaikan dengan preferensi mereka.

* 3.1.2  Perspektif Algoritma

▸	MST via Prim: Mengidentifikasi backbone rute minimum yang menghubungkan semua 8 halte.

▸	BFS: Memberikan jalur dengan jumlah transit minimum antara dua halte.

▸	DFS: Menyediakan jalur alternatif sebagai opsi cadangan.

▸	Skor keputusan multi-kriteria: Menggabungkan jarak (40%), waktu (40%), biaya (20%) dalam formula tunggal.

3.2  Desain Graf — Visualisasi Jaringan

<img width="755" height="502" alt="image" src="https://github.com/user-attachments/assets/8ff3c7a2-779c-418b-b8b3-7b459661a429" />

* 3.2.1  Daftar Node (Halte Bus)
* 
<img width="700" height="1000" alt="image" src="https://github.com/user-attachments/assets/2c4ac6a8-341f-476c-8ecb-01975b4454fc" />
<img width="800" height="300" alt="image" src="https://github.com/user-attachments/assets/87e7a69f-8bef-46c0-a1c3-b46205c804db" />

* 3.3  Flowchart Sistem
<img width="600" height="1111" alt="image" src="https://github.com/user-attachments/assets/cfcde8b9-a300-4e6c-b260-3c440e687852" />

Flowchart di atas menggambarkan alur kerja lengkap sistem DSS Transportasi Pintar Labuan Bajo secara menyeluruh, mulai dari inisialisasi data hingga penyajian hasil rekomendasi kepada pengguna. Sistem ini dirancang dengan alur yang sistematis dan terstruktur, terdiri dari 11 tahap utama yang saling berkaitan.

# Penjelasan Setiap Tahap Flowchart:

* Tahap 1 — Inisialisasi Data Graf: Sistem membangun struktur Directed Graph dengan 8 Node (halte bus) dan 20 Edge (rute bus). Setiap node merepresentasikan satu halte atau terminal di Labuan Bajo, sementara setiap edge merepresentasikan rute bus berarah antara dua halte. Proses ini merupakan fondasi seluruh komputasi berikutnya.

* Tahap 2 — Simpan Data dalam Adjacency List: Seluruh data rute disimpan dalam struktur Adjacency List berbasis defaultdict Python. Setiap node menyimpan daftar tetangganya beserta atribut multibobot: jarak (km), waktu tempuh (menit), dan biaya perjalanan (Rp). Pendekatan ini memberikan kompleksitas ruang O(V+E) yang efisien untuk graf jarang (sparse graph).

* Tahap 3 — Tampilkan Struktur Graf: Sistem menampilkan daftar seluruh halte, rute bus, dan representasi Adjacency List secara lengkap kepada pengguna. Output ini memungkinkan verifikasi data masukan sekaligus memberikan gambaran menyeluruh tentang topologi jaringan transportasi Labuan Bajo.

* Tahap 4 — Jalankan Algoritma Prim: Algoritma Prim dieksekusi untuk mencari Minimum Spanning Tree (MST) yang menghubungkan 
seluruh 8 halte dengan total jarak minimum. Algoritma bekerja secara greedy menggunakan Priority Queue (min-heap) berbasis heapq Python, dengan kompleksitas waktu O(E log V). Karena graf bersifat directed, representasi undirected dibuat sementara agar MST dapat mencakup semua node.

* Tahap 5 — Tampilkan Hasil MST: Sistem menampilkan seluruh edge MST beserta total jarak, total waktu, dan total biaya backbone rute. Hasil MST ini merepresentasikan jaringan rute paling efisien yang dapat dijadikan acuan dalam perencanaan infrastruktur dan pengembangan jaringan bus Labuan Bajo.

* Tahap 6 — Input Pengguna: Pengguna memasukkan tiga parameter: (1) Halte Asal — titik keberangkatan perjalanan, (2) Halte Tujuan — titik akhir yang ingin dicapai, dan (3) Preferensi optimasi — pilihan antara Jarak minimum, Waktu minimum, atau Biaya minimum. Input ini menentukan bobot kriteria yang digunakan dalam skor keputusan DSS.

* Tahap 7 — Cari Jalur (Percabangan BFS / DFS): Pada tahap ini terdapat Decision Point yang memisahkan alur ke dua cabang pencarian jalur secara paralel. Cabang 7A (BFS) menggunakan algoritma Breadth-First Search berbasis antrian (queue) untuk menemukan jalur dengan jumlah transit (hop) minimum. Cabang 7B (DFS) menggunakan algoritma Depth-First Search berbasis tumpukan (stack/rekursi) untuk menelusuri jalur alternatif secara lebih mendalam. Kedua cabang berjalan secara terpisah dan menghasilkan kandidat rute yang berbeda.

*Tahap 8 — Hitung Detail Jalur: Untuk setiap jalur yang ditemukan oleh BFS maupun DFS, sistem menghitung total jarak (km), total waktu tempuh (menit), dan total biaya perjalanan (Rp) secara akumulatif berdasarkan atribut edge pada Adjacency List. Detail ini menjadi masukan untuk proses perhitungan skor DSS.

* Tahap 9 — Hitung Skor DSS (Weighted Sum Model): Setiap jalur kandidat diberi skor menggunakan formula Weighted Sum Model (WSM): Skor = (0.4 × Jarak) + (0.4 × Waktu) + (0.2 × Biaya/1000). Bobot 40% diberikan masing-masing untuk jarak dan waktu sebagai faktor dominan, sementara biaya mendapat bobot 20%. Biaya dinormalisasi dengan pembagi 1.000 agar satuan sebanding dengan jarak (km) dan waktu (menit). Skor yang lebih rendah menunjukkan rute yang lebih optimal.

* Tahap 10 — Tentukan Rekomendasi: Sistem membandingkan seluruh jalur kandidat berdasarkan skor WSM yang telah dihitung, kemudian memilih rute dengan skor terendah sebagai rekomendasi terbaik sesuai preferensi pengguna. Hasil perbandingan juga menampilkan seluruh rute alternatif beserta skor masing-masing agar pengguna dapat mempertimbangkan pilihan lain.

* Tahap 11 — Tampilkan Hasil: Sistem menampilkan output akhir berupa rute terbaik yang direkomendasikan, lengkap dengan detail jarak, waktu, biaya, dan skor DSS, serta statistik jaringan secara keseluruhan. Setelah hasil ditampilkan, terdapat Decision Point “Ulangi Pencarian?” — jika pengguna memilih YA, sistem kembali ke Tahap 6 (Input Pengguna) untuk pencarian baru; jika TIDAK, sistem mengakhiri proses (SELESAI).

* Keterangan Simbol Flowchart:

* • Terminator (Oval Hijau): Menandai titik MULAI dan SELESAI dari alur sistem.
* • Process (Persegi Biru): Mewakili tahap pemrosesan data oleh sistem, seperti inisialisasi, komputasi algoritma, dan kalkulasi skor.
* • Input/Output (Jajar Genjang Kuning): Mewakili interaksi dengan pengguna, baik berupa masukan data (Input Pengguna) maupun tampilan hasil kepada pengguna (Tampilkan Hasil).
* • Decision (Belah Ketupat Merah Muda): Mewakili titik pengambilan keputusan percabangan alur, yaitu pemilihan algoritma pencarian (BFS atau DFS) dan keputusan untuk mengulangi pencarian.
* • Subprocess/Proses Pencarian (Persegi Ungu): Mewakili modul pencarian jalur BFS dan DFS sebagai subproses yang berdiri sendiri dalam sistem.

* 3.4  Use Case
<img width="874" height="461" alt="image" src="https://github.com/user-attachments/assets/7d84786b-6fbc-48f8-95e4-5de34aecbe15" />

3.5  Struktur Node dan Edge
<img width="910" height="286" alt="image" src="https://github.com/user-attachments/assets/2fcaa769-fe19-416c-a046-de55a4924035" />

# BAB 4 — IMPLEMENTASI

* 4.1  Struktur Program
  
Program diimplementasikan dalam Python dengan arsitektur berorientasi objek (OOP). Terdiri dari 5 kelas utama yang saling berinteraksi:

<img width="904" height="486" alt="151518" src="https://github.com/user-attachments/assets/8267a201-612d-47cf-a53f-b77afb7179d2" />


* 4.2  Penjelasan Kode

* 4.2.1  Kelas DirectedGraph

Kelas inti yang merepresentasikan jaringan bus menggunakan adjacency list berbasis defaultdict dari Python. Desain ini memungkinkan akses O(1) ke daftar tetangga setiap node.

<img width="907" height="280" alt="151528" src="https://github.com/user-attachments/assets/24b4b402-1679-4546-b796-2840157f1280" />

4.2.2  Algoritma Prim — Core Logic
Inti implementasi Prim menggunakan heapq Python sebagai min-heap. Karena graf bersifat directed, sisi dua arah dibuat secara sementara untuk keperluan MST:

<img width="913" height="378" alt="151534" src="https://github.com/user-attachments/assets/5cb49dd8-35af-41ef-a277-5c6b40fee4e5" />

* 4.2.3  Modul BFS
  
BFS menggunakan collections.deque sebagai antrian FIFO yang efisien. Menyimpan jalur lengkap di setiap state untuk rekonstruksi rute: ada 

<img width="926" height="323" alt="151579" src="https://github.com/user-attachments/assets/9532e175-8460-4564-bb0d-7876c015b9aa" />

* 4.2.4  Skor Keputusan Multi-Kriteria
  
Formula skor keputusan menggunakan pendekatan weighted sum model (WSM) dengan bobot yang dapat dikustomisasi:

<img width="1080" height="246" alt="151583" src="https://github.com/user-attachments/assets/a3cfe720-1e86-4b11-9030-a43d30ac6788" />

"Biaya dinormalisasi dengan membagi 1000 agar satuan sebanding dengan jarak (km) dan waktu (menit). Rute dengan skor lebih rendah dianggap lebih optimal."












