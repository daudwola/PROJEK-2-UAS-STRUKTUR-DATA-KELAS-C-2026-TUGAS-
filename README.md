# PROJEK-2-UAS-STRUKTUR-DATA-KELAS-C-2026-TUGAS-
PROJEK 2 UAS STRUKTUR DATA


# LAPORAN PROJEK 2 UAS #
# Nama anggota:
               1.= Daud Gollu Wola (2501010343)
               2.= Petrus k sanexsel Das Sa (2501010346)
               3.= Claudia F Bunga Na (2501010358)

__________________________________     


# 1.Latar Belakang 
Labuan Bajo merupakan kawasan wisata prioritas nasional di Nusa Tenggara Timur yang mengalami pertumbuhan kunjungan wisatawan secara signifikan. Peningkatan ini membawa tantangan tersendiri dalam pengelolaan transportasi publik, khususnya layanan bus antar halte di dalam kota maupun menuju destinasi wisata.
Permasalahan utama yang dihadapi adalah belum optimalnya penentuan rute transportasi bus, sehingga mengakibatkan pemborosan bahan bakar, waktu tempuh yang tidak efisien, dan pelayanan yang kurang merata. Oleh karena itu, diperlukan sebuah Sistem Pendukung Keputusan (DSS) yang dapat membantu pengelola transportasi dalam menentukan rute paling efisien.

* 1.1 Rumusan Masalah

  * Bagaimana merepresentasikan jaringan transportasi bus sebagai struktur data graf?

  * Bagaimana menentukan rute terpendek antara dua halte menggunakan algoritma Dijkstra?

  * Bagaimana membangun pohon rentang minimum (MST) jaringan bus menggunakan algoritma Prim?

  * Bagaimana mengintegrasikan hasil algoritma dengan metode AHP-TOPSIS untuk menghasilkan rekomendasi rute terbaik?

* 1.2 Tujuan

  * Membangun model graf berbobot untuk jaringan bus Labuan Bajo
  
  * Mengimplementasikan algoritma Dijkstra untuk pencarian rute terpendek
  
  * Mengimplementasikan algoritma Prim untuk pembangunan MST
  
  * Menghasilkan rekomendasi rute melalui metode DSS multi-kriteria

# 2. Metodologi DSS

Sistem mengintegrasikan tiga komponen utama: model graf jaringan jalan, algoritma optimasi rute (Dijkstra & Prim), dan metode pengambilan keputusan multi-kriteria (AHP + TOPSIS).

  ________*Jaringan bus dimodelkan sebagai graf berbobot tak berarah G = (V, E, w) di mana:*________

 * V = himpunan simpul (vertex) merepresentasikan halte bus
   
 * E = himpunan sisi (edge) merepresentasikan jalur langsung antar halte
   
 * w: E -> R+ = fungsi bobot merepresentasikan jarak dalam kilometer

# 2.2 Daftar Halte


  <img width="835" height="457" alt="150473" src="https://github.com/user-attachments/assets/efab7952-1265-44c7-9555-b85dea6ea1c1" />

# 2.3 Daftar Jalur


<img width="817" height="328" alt="150477" src="https://github.com/user-attachments/assets/9bfd6dfc-1d9b-4120-b2b0-e00f6a2f4387" />


<img width="817" height="406" alt="150481" src="https://github.com/user-attachments/assets/80f93d29-6191-41b4-8283-aee97129a47d" />


# 3. Algoritma Dijkstra

Algoritma Dijkstra adalah algoritma pencarian jalur terpendek dari satu simpul sumber ke semua simpul lain dalam graf berbobot non-negatif. Algoritma ini dikembangkan oleh Edsger W. Dijkstra pada tahun 1956.

# 3.1 Konsep Dasar

  Algoritma Dijkstra menggunakan pendekatan greedy dengan mempertahankan satu set simpul yang sudah dikunjungi dan satu set simpul yang belum dikunjungi. Pada setiap iterasi, simpul dengan jarak minimum yang belum dikunjungi dipilih dan diproses.

