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














