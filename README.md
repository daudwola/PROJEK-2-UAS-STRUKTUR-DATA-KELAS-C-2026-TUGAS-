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


BAB 1 – PENDAHULUAN

1.1 Latar Belakang

Labuan Bajo merupakan salah satu destinasi pariwisata prioritas nasional di Indonesia yang terletak di ujung barat Pulau Flores, Nusa Tenggara Timur. Sebagai gerbang utama menuju Taman Nasional Komodo, kota ini mengalami pertumbuhan kunjungan wisatawan yang sangat pesat dalam beberapa tahun terakhir. Hal ini berdampak langsung pada kebutuhan layanan transportasi publik yang efisien, andal, dan mudah diakses oleh masyarakat lokal maupun wisatawan.

Transportasi bus kota di Labuan Bajo melayani sejumlah rute strategis yang menghubungkan titik-titik penting seperti Terminal, Pelabuhan, Bandara Internasional Komodo, kawasan wisata Waterfront, Batu Cermin, hingga destinasi alam Goa Rangko. Namun, informasi mengenai rute dan jarak antar halte masih sulit diakses secara sistematis, menyebabkan penumpang sering mengalami ketidakpastian dalam merencanakan perjalanan.

Dalam konteks ini, pengembangan Sistem Pendukung Keputusan (Decision Support System / DSS) berbasis teknologi komputasi menjadi sangat relevan. Dengan memanfaatkan struktur data graph dan algoritma Dijkstra, sistem dapat memberikan rekomendasi rute terpendek secara otomatis, membantu pengguna membuat keputusan perjalanan yang lebih baik, efisien, dan tepat waktu.

1.2 Rumusan Masalah

Berdasarkan latar belakang yang telah diuraikan, rumusan masalah dalam proyek ini adalah:

•	Bagaimana merepresentasikan jaringan rute bus kota Labuan Bajo ke dalam struktur data graph yang tepat?

•	Bagaimana mengimplementasikan algoritma Dijkstra untuk menentukan rute terpendek antara dua halte yang dipilih pengguna?

•	Bagaimana membangun antarmuka DSS yang interaktif dan mudah digunakan berbasis aplikasi web?

•	Bagaimana menganalisis kompleksitas algoritma yang diterapkan dalam sistem?



1.3 Tujuan

Tujuan dari proyek ini adalah:

•	Membangun sistem pendukung keputusan berbasis graph untuk rute transportasi bus kota Labuan Bajo.

•	Mengimplementasikan algoritma Dijkstra untuk pencarian jalur terpendek antar halte.

•	Menyajikan visualisasi jaringan graph secara interaktif menggunakan aplikasi Streamlit.

•	Menganalisis performa dan kompleksitas algoritma yang digunakan dalam sistem.



1.4 Manfaat

Manfaat yang diharapkan dari pengembangan sistem ini antara lain:

•	Bagi penumpang: memudahkan perencanaan perjalanan dengan informasi rute terpendek yang akurat.

•	Bagi pengelola transportasi: menyediakan dasar data untuk optimasi jaringan rute bus.

•	Bagi akademisi: menjadi referensi implementasi struktur data graph dan algoritma Dijkstra dalam kasus nyata.

•	Bagi pengembangan kota: mendukung digitalisasi layanan transportasi publik Labuan Bajo.



 

BAB 2 – DASAR TEORI

2.1 Struktur Data Graph

Graph adalah struktur data non-linear yang terdiri dari kumpulan simpul (node/vertex) yang dihubungkan oleh sejumlah sisi (edge/arc). Secara formal, graph G didefinisikan sebagai pasangan terurut G = (V, E), di mana V adalah himpunan simpul dan E adalah himpunan sisi yang menghubungkan pasangan simpul.

Berdasarkan arah sisinya, graph dibedakan menjadi dua jenis utama:

•	Directed Graph (Digraph): sisi memiliki arah, sehingga edge (u, v) berbeda dengan edge (v, u). Digunakan untuk merepresentasikan hubungan yang bersifat satu arah.

•	Undirected Graph: sisi tidak memiliki arah, sehingga edge (u, v) identik dengan edge (v, u). Cocok untuk representasi jalur dua arah seperti jalan raya.



Berdasarkan bobotnya, graph dibedakan menjadi:

•	Unweighted Graph: setiap sisi memiliki bobot yang sama (umumnya 1).

•	Weighted Graph: setiap sisi memiliki bobot berbeda yang merepresentasikan biaya, jarak, waktu, atau metrik lain.



Dalam proyek ini digunakan Undirected Weighted Graph karena rute bus dapat ditempuh dua arah dan setiap ruas jalan memiliki jarak (km) yang berbeda-beda.

2.2 Decision Support System (DSS)

Decision Support System (DSS) atau Sistem Pendukung Keputusan adalah sistem informasi interaktif berbasis komputer yang dirancang untuk membantu pengambil keputusan dalam memecahkan masalah semi-terstruktur dan tidak terstruktur. DSS menggabungkan data, model analitik, dan antarmuka pengguna untuk menghasilkan rekomendasi yang dapat dijadikan dasar pengambilan keputusan.

Komponen utama DSS terdiri dari tiga subsistem:

•	Management Data: basis data yang menyimpan dan mengelola data relevan, dalam kasus ini berupa data node (halte) dan edge (rute beserta jaraknya).

•	Management Model: kumpulan model analitik dan algoritma yang memproses data; pada sistem ini berupa algoritma Dijkstra untuk optimasi rute.

•	Management Dialog (User Interface): antarmuka interaktif yang memungkinkan pengguna memasukkan preferensi dan menerima hasil rekomendasi; diimplementasikan menggunakan Streamlit.



2.3 Algoritma Dijkstra

Algoritma Dijkstra, dikembangkan oleh Edsger W. Dijkstra pada tahun 1956, merupakan algoritma greedy untuk menemukan jalur terpendek antara satu simpul sumber ke semua simpul lain dalam graf berbobot non-negatif.

Langkah-langkah kerja algoritma Dijkstra:

•	Inisialisasi: tetapkan jarak sumber ke dirinya sendiri = 0, dan jarak ke semua simpul lain = tak terhingga (infinity).

•	Pilih simpul dengan jarak terkecil yang belum dikunjungi sebagai simpul aktif.

•	Perbarui jarak semua tetangga simpul aktif jika ditemukan jalur yang lebih pendek melalui simpul aktif tersebut (relaksasi sisi).

•	Tandai simpul aktif sebagai telah dikunjungi.

•	Ulangi langkah 2-4 hingga semua simpul dikunjungi atau simpul tujuan tercapai.



Kompleksitas waktu algoritma Dijkstra adalah O((V + E) log V) dengan implementasi menggunakan priority queue (binary heap), di mana V adalah jumlah simpul dan E adalah jumlah sisi. Pada proyek ini, NetworkX menggunakan implementasi heap yang efisien untuk komputasi jalur terpendek.

 

BAB 3 – ANALISIS DAN PERANCANGAN

3.1 Analisis Masalah

Permasalahan inti yang diselesaikan oleh sistem ini adalah menemukan rute bus optimal di jaringan transportasi Labuan Bajo. Dengan 8 halte dan 9 ruas jalan, pencarian manual rute terpendek membutuhkan waktu dan rentan terhadap kesalahan, terutama bagi penumpang yang tidak familiar dengan kota tersebut. Sistem DSS yang dibangun mengotomatisasi proses ini dengan memberikan rekomendasi rute secara instan berdasarkan input halte asal dan tujuan.

3.2 Desain Graph

Jaringan transportasi bus Labuan Bajo dimodelkan sebagai Undirected Weighted Graph dengan spesifikasi berikut:

•	Jumlah Node (Halte): 8 titik pemberhentian bus

•	Jumlah Edge (Rute): 9 jalur yang menghubungkan antar-halte

•	Bobot Edge: jarak dalam satuan kilometer (km)

•	Tipe Graph: undirected (jalur dua arah) dan weighted (berbobot)



Data Node yang digunakan dalam sistem:

<img width="828" height="400" alt="153336" src="https://github.com/user-attachments/assets/a07c1fad-a943-4f42-bade-d814cb3e2630" />

![153340](https://github.com/user-attachments/assets/395a62b2-1bc2-4927-ba6a-86975e89af66)



