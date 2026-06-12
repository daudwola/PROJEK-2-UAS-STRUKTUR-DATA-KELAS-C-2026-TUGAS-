
<img width="225" height="225" alt="153362" src="https://github.com/user-attachments/assets/7c9bc340-90e7-409c-9ee5-ec89c98adc6e" />




# PROJEK-2-UAS-STRUKTUR-DATA-KELAS-C-2026-TUGAS-
PROJEK 2 UAS STRUKTUR DATA


# LAPORAN PROJEK 2 UAS #
# Nama anggota:
               1.= Daud Gollu Wola (2501010343)
               2.= Petrus k sanexsel Das Sa (2501010346)
               3.= Claudia F Bunga Na (2501010358)

_____________________________________
# LAPORAN PROYEK AKHIR

# SISTEM PENDUKUNG KEPUTUSAN (DSS)

# TRANSPORTASI BUS KOTA LABUAN BAJO

# *Disusun sebagai pemenuhan tugas proyek akhir mata kuliah Struktur Data dan Algoritma*


# BAB 1 – PENDAHULUAN

* 1.1 Latar Belakang

Labuan Bajo merupakan salah satu destinasi pariwisata prioritas nasional di Indonesia yang terletak di ujung barat Pulau Flores, Nusa Tenggara Timur. Sebagai gerbang utama menuju Taman Nasional Komodo, kota ini mengalami pertumbuhan kunjungan wisatawan yang sangat pesat dalam beberapa tahun terakhir. Hal ini berdampak langsung pada kebutuhan layanan transportasi publik yang efisien, andal, dan mudah diakses oleh masyarakat lokal maupun wisatawan.

Transportasi bus kota di Labuan Bajo melayani sejumlah rute strategis yang menghubungkan titik-titik penting seperti Terminal, Pelabuhan, Bandara Internasional Komodo, kawasan wisata Waterfront, Batu Cermin, hingga destinasi alam Goa Rangko. Namun, informasi mengenai rute dan jarak antar halte masih sulit diakses secara sistematis, menyebabkan penumpang sering mengalami ketidakpastian dalam merencanakan perjalanan.

Dalam konteks ini, pengembangan Sistem Pendukung Keputusan (Decision Support System / DSS) berbasis teknologi komputasi menjadi sangat relevan. Dengan memanfaatkan struktur data graph dan algoritma Dijkstra, sistem dapat memberikan rekomendasi rute terpendek secara otomatis, membantu pengguna membuat keputusan perjalanan yang lebih baik, efisien, dan tepat waktu.

* 1.2 Rumusan Masalah

Berdasarkan latar belakang yang telah diuraikan, rumusan masalah dalam proyek ini adalah:

•	Bagaimana merepresentasikan jaringan rute bus kota Labuan Bajo ke dalam struktur data graph yang tepat?

•	Bagaimana mengimplementasikan algoritma Dijkstra untuk menentukan rute terpendek antara dua halte yang dipilih pengguna?

•	Bagaimana membangun antarmuka DSS yang interaktif dan mudah digunakan berbasis aplikasi web?

•	Bagaimana menganalisis kompleksitas algoritma yang diterapkan dalam sistem?



* 1.3 Tujuan

Tujuan dari proyek ini adalah:

•	Membangun sistem pendukung keputusan berbasis graph untuk rute transportasi bus kota Labuan Bajo.

•	Mengimplementasikan algoritma Dijkstra untuk pencarian jalur terpendek antar halte.

•	Menyajikan visualisasi jaringan graph secara interaktif menggunakan aplikasi Streamlit.

•	Menganalisis performa dan kompleksitas algoritma yang digunakan dalam sistem.



* 1.4 Manfaat

Manfaat yang diharapkan dari pengembangan sistem ini antara lain:

•	Bagi penumpang: memudahkan perencanaan perjalanan dengan informasi rute terpendek yang akurat.

•	Bagi pengelola transportasi: menyediakan dasar data untuk optimasi jaringan rute bus.

•	Bagi akademisi: menjadi referensi implementasi struktur data graph dan algoritma Dijkstra dalam kasus nyata.

•	Bagi pengembangan kota: mendukung digitalisasi layanan transportasi publik Labuan Bajo.



 

# BAB 2 – DASAR TEORI

* 2.1 Struktur Data Graph

Graph adalah struktur data non-linear yang terdiri dari kumpulan simpul (node/vertex) yang dihubungkan oleh sejumlah sisi (edge/arc). Secara formal, graph G didefinisikan sebagai pasangan terurut G = (V, E), di mana V adalah himpunan simpul dan E adalah himpunan sisi yang menghubungkan pasangan simpul.

Berdasarkan arah sisinya, graph dibedakan menjadi dua jenis utama:

•	Directed Graph (Digraph): sisi memiliki arah, sehingga edge (u, v) berbeda dengan edge (v, u). Digunakan untuk merepresentasikan hubungan yang bersifat satu arah.

•	Undirected Graph: sisi tidak memiliki arah, sehingga edge (u, v) identik dengan edge (v, u). Cocok untuk representasi jalur dua arah seperti jalan raya.



Berdasarkan bobotnya, graph dibedakan menjadi:

•	Unweighted Graph: setiap sisi memiliki bobot yang sama (umumnya 1).

•	Weighted Graph: setiap sisi memiliki bobot berbeda yang merepresentasikan biaya, jarak, waktu, atau metrik lain.



Dalam proyek ini digunakan Undirected Weighted Graph karena rute bus dapat ditempuh dua arah dan setiap ruas jalan memiliki jarak (km) yang berbeda-beda.

* 2.2 Decision Support System (DSS)

Decision Support System (DSS) atau Sistem Pendukung Keputusan adalah sistem informasi interaktif berbasis komputer yang dirancang untuk membantu pengambil keputusan dalam memecahkan masalah semi-terstruktur dan tidak terstruktur. DSS menggabungkan data, model analitik, dan antarmuka pengguna untuk menghasilkan rekomendasi yang dapat dijadikan dasar pengambilan keputusan.

Komponen utama DSS terdiri dari tiga subsistem:

•	Management Data: basis data yang menyimpan dan mengelola data relevan, dalam kasus ini berupa data node (halte) dan edge (rute beserta jaraknya).

•	Management Model: kumpulan model analitik dan algoritma yang memproses data; pada sistem ini berupa algoritma Dijkstra untuk optimasi rute.

•	Management Dialog (User Interface): antarmuka interaktif yang memungkinkan pengguna memasukkan preferensi dan menerima hasil rekomendasi; diimplementasikan menggunakan Streamlit.



* 2.3 Algoritma Dijkstra

Algoritma Dijkstra, dikembangkan oleh Edsger W. Dijkstra pada tahun 1956, merupakan algoritma greedy untuk menemukan jalur terpendek antara satu simpul sumber ke semua simpul lain dalam graf berbobot non-negatif.

Langkah-langkah kerja algoritma Dijkstra:

•	Inisialisasi: tetapkan jarak sumber ke dirinya sendiri = 0, dan jarak ke semua simpul lain = tak terhingga (infinity).

•	Pilih simpul dengan jarak terkecil yang belum dikunjungi sebagai simpul aktif.

•	Perbarui jarak semua tetangga simpul aktif jika ditemukan jalur yang lebih pendek melalui simpul aktif tersebut (relaksasi sisi).

•	Tandai simpul aktif sebagai telah dikunjungi.

•	Ulangi langkah 2-4 hingga semua simpul dikunjungi atau simpul tujuan tercapai.



Kompleksitas waktu algoritma Dijkstra adalah O((V + E) log V) dengan implementasi menggunakan priority queue (binary heap), di mana V adalah jumlah simpul dan E adalah jumlah sisi. Pada proyek ini, NetworkX menggunakan implementasi heap yang efisien untuk komputasi jalur terpendek.

 

# BAB 3 – ANALISIS DAN PERANCANGAN

* 3.1 Analisis Masalah

Permasalahan inti yang diselesaikan oleh sistem ini adalah menemukan rute bus optimal di jaringan transportasi Labuan Bajo. Dengan 8 halte dan 9 ruas jalan, pencarian manual rute terpendek membutuhkan waktu dan rentan terhadap kesalahan, terutama bagi penumpang yang tidak familiar dengan kota tersebut. Sistem DSS yang dibangun mengotomatisasi proses ini dengan memberikan rekomendasi rute secara instan berdasarkan input halte asal dan tujuan.

* 3.2 Desain Graph

Jaringan transportasi bus Labuan Bajo dimodelkan sebagai Undirected Weighted Graph dengan spesifikasi berikut:

•	Jumlah Node (Halte): 8 titik pemberhentian bus

•	Jumlah Edge (Rute): 9 jalur yang menghubungkan antar-halte

•	Bobot Edge: jarak dalam satuan kilometer (km)

•	Tipe Graph: undirected (jalur dua arah) dan weighted (berbobot)



Data Node yang digunakan dalam sistem:

<img width="828" height="400" alt="153336" src="https://github.com/user-attachments/assets/a07c1fad-a943-4f42-bade-d814cb3e2630" />

![153340](https://github.com/user-attachments/assets/395a62b2-1bc2-4927-ba6a-86975e89af66)

* 3.3 Flowchart Sistem

Alur kerja sistem DSS secara keseluruhan dapat digambarkan sebagai berikut:

•	Pengguna memilih halte asal dan halte tujuan melalui antarmuka sidebar Streamlit.

•	Pengguna menekan tombol 'Cari Rute Terbaik'.

•	Sistem memanggil fungsi dijkstra_path() dari library NetworkX dengan parameter halte asal dan tujuan.

•	Algoritma Dijkstra memproses graf dan mengembalikan jalur terpendek beserta total jaraknya.

•	Sistem menghitung estimasi waktu tempuh berdasarkan jarak (asumsi: 3 menit per km).

•	Hasil berupa daftar halte, total jarak, dan estimasi waktu ditampilkan kepada pengguna.

•	Visualisasi graph dirender menggunakan Matplotlib dan ditampilkan di halaman utama.

<img width="664" height="1039" alt="153343" src="https://github.com/user-attachments/assets/d6d88f52-dd6d-40c5-bb33-5ccc14dc583b" />

* 3.4 Use Case Sistem

Sistem memiliki satu aktor utama yaitu Pengguna (penumpang bus). Use case yang tersedia meliputi:

•	UC-01: Melihat visualisasi graph jaringan bus

•	UC-02: Memilih halte asal dari daftar halte yang tersedia

•	UC-03: Memilih halte tujuan dari daftar halte yang tersedia

•	UC-04: Mencari rute terpendek antar halte

•	UC-05: Melihat detail perjalanan (urutan halte, jarak, estimasi waktu)

•	UC-06: Melihat tabel data jalur bus (semua edge dan bobotnya)


<img width="1080" height="278" alt="153345" src="https://github.com/user-attachments/assets/713c842e-8e7f-43d9-b100-f1a6ce597b4c" />

# BAB 4 – IMPLEMENTASI

* 4.1 Implementasi Program

Program diimplementasikan menggunakan bahasa Python dengan framework Streamlit untuk antarmuka web interaktif. Berikut adalah library utama yang digunakan:

•	streamlit: framework web app Python untuk antarmuka pengguna

•	networkx: library untuk pembuatan dan analisis jaringan/graph

•	matplotlib: library visualisasi data untuk menggambar graph

•	pandas: library manipulasi data untuk menampilkan tabel



* 4.2 Penjelasan Kode

* 4.2.1 Inisialisasi Graph

Pembuatan graph dimulai dengan mendefinisikan semua edge beserta bobotnya:

![153347](https://github.com/user-attachments/assets/b8b5fff5-96db-41a0-9371-5d4650c0775c)

<img width="858" height="325" alt="153353" src="https://github.com/user-attachments/assets/63e66834-baf4-4cad-9e4d-09a1bf2c3830" />

<img width="1080" height="248" alt="153355" src="https://github.com/user-attachments/assets/5217d76d-4e0a-4c09-9d46-baaf305b32cc" />

* 4.3 Tampilan Sistem

Sistem memiliki dua area tampilan utama:

•	Sidebar (panel kiri): berisi komponen input berupa dua dropdown untuk memilih halte asal dan tujuan, serta tombol 'Cari Rute Terbaik' untuk memulai proses pencarian.

•	Area utama (panel kanan): menampilkan hasil pencarian rute (jalur, jarak, estimasi waktu), visualisasi graph interaktif, tabel data jalur bus, dan panel analisis DSS.



Antarmuka menggunakan layout wide Streamlit (st.set_page_config(layout='wide')) untuk memanfaatkan lebar layar secara optimal, memberikan pengalaman pengguna yang lebih baik terutama pada layar desktop.

# BAB 5 – PENGUJIAN DAN ANALISIS

* 5.1 Skenario Pengujian

Pengujian dilakukan dengan beberapa skenario untuk memverifikasi kebenaran dan keandalan sistem:

<img width="870" height="331" alt="153357" src="https://github.com/user-attachments/assets/b831271a-5d17-47e5-a3dc-7b9ae5b69a74" />

* 5.2 Analisis Hasil

Berdasarkan hasil pengujian, sistem berhasil menghitung rute terpendek dengan benar untuk seluruh skenario yang diuji. Algoritma Dijkstra yang diimplementasikan melalui NetworkX memberikan hasil yang konsisten dan akurat sesuai dengan data bobot edge yang telah didefinisikan.

Pada skenario 2 (Terminal ke Goa Rangko), algoritma memilih jalur melalui Bandara Komodo dan Batu Cermin dengan jarak total 12 km (5+3+4), bukan melalui jalur langsung Terminal → Pelabuhan → Waterfront → Kampung Ujung → Pede → Goa Rangko yang memiliki total jarak 16 km. Ini membuktikan bahwa algoritma berhasil menemukan jalur optimal yang tidak selalu intuitif.

Estimasi waktu dihitung menggunakan asumsi kecepatan rata-rata 20 km/jam (3 menit per km), yang merupakan perkiraan realistis untuk bus kota di area perkotaan Labuan Bajo dengan kondisi lalu lintas normal.

* 5.3 Kompleksitas Algoritma

Analisis kompleksitas sistem dapat dijabarkan sebagai berikut:

•	Kompleksitas Waktu Dijkstra: O((V + E) log V) dengan priority queue, di mana V = 8 (jumlah node) dan E = 9 (jumlah edge). Untuk skala saat ini, kompleksitas bersifat sangat ringan.

•	Kompleksitas Ruang: O(V + E) untuk menyimpan adjacency list dan O(V) untuk menyimpan array jarak dan visited.

•	Kompleksitas Visualisasi: O(V + E) untuk spring layout, ditambah overhead rendering Matplotlib.



Dengan jumlah node dan edge yang relatif kecil, performa sistem sangat baik dengan waktu komputasi yang hampir instan (< 1 ms) untuk setiap query rute. Sistem berpotensi diskalakan hingga ratusan node tanpa degradasi performa yang signifikan karena kompleksitas algoritmik yang efisien.

# BAB 6 – KESIMPULAN

* 6.1 Kesimpulan

Berdasarkan hasil perancangan, implementasi, dan pengujian yang telah dilakukan, dapat disimpulkan bahwa:

•	Sistem Pendukung Keputusan (DSS) berbasis graph untuk transportasi bus kota Labuan Bajo berhasil dibangun menggunakan Python, Streamlit, NetworkX, dan Matplotlib.

•	Struktur data Undirected Weighted Graph berhasil merepresentasikan jaringan rute bus dengan 8 halte dan 9 jalur secara akurat dan efisien.

•	Algoritma Dijkstra berhasil diimplementasikan untuk menemukan rute terpendek antar halte dengan kompleksitas waktu O((V + E) log V) yang sangat efisien untuk skala sistem ini.

•	Sistem mampu menyajikan rekomendasi rute terpendek, total jarak, dan estimasi waktu tempuh secara instan melalui antarmuka web yang intuitif.

•	Visualisasi graph interaktif membantu pengguna memahami topologi jaringan bus secara visual.

•	Pengujian pada 5 skenario membuktikan kebenaran dan keandalan sistem dalam memberikan rekomendasi yang optimal.



* 6.2 Saran Pengembangan

Beberapa saran untuk pengembangan sistem ke depannya:

•	Integrasi data real-time: menambahkan informasi jadwal keberangkatan, ketersediaan kursi, dan posisi bus secara real-time menggunakan GPS tracking.

•	Perluasan jaringan: menambahkan lebih banyak halte dan rute, termasuk rute menuju objek wisata baru di sekitar Labuan Bajo.

•	Multi-kriteria optimasi: mengembangkan sistem untuk mempertimbangkan tidak hanya jarak, tetapi juga waktu tempuh aktual, tarif, dan frekuensi keberangkatan menggunakan metode MCDM (Multi-Criteria Decision Making).

•	Aplikasi mobile: mengembangkan versi mobile berbasis Android/iOS agar lebih mudah diakses oleh wisatawan.

•	Integrasi peta interaktif: mengganti visualisasi statis dengan peta interaktif berbasis Folium atau Google Maps API untuk pengalaman pengguna yang lebih baik.

•	Database dinamis: memindahkan data dari hardcode ke database (PostgreSQL/MongoDB) agar mudah diperbarui tanpa mengubah kode.

•	Sistem autentikasi: menambahkan fitur login untuk pengelola sistem dalam melakukan pembaruan data rute.

# LAPORAN UAS

https://drive.google.com/drive/folders/1Q9yoRxwi57xfrcXWy5qhBWNAmAKRJl0r
# SLIDE presentasi 
https://canva.link/2pf8mv9h98chh65
