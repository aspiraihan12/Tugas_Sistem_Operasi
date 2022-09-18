## <center> Layanan Sistem Operasi, System Calls, & System Program

#### Layanan Sistem Operasi

<p align = "center">
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/gambar1.1.png"></p>
<center>Gambar 1.1</center>

<center><i>Sumber :Abraham-Silberschatz,et.al, Operating System Concepts, 10th ed 2018: halaman 56. </i></center>


Gambar 1.1 menunjukkan satu pandangan dari berbagai layanan sistem operasi dan bagaimana mereka saling berhubungan. Catatan bahwa layanan ini juga membuat tugas pemrograman lebih mudah bagi programmer.Satu set layanan sistem operasi menyediakan fungsi yang berguna untuk pengguna.
1.Antarmuka pengguna.
 Hampir semua sistem operasi memiliki antarmuka pengguna (UI). Antarmuka ini  dapat mengambil beberapa bentuk. Paling umum, pengguna grafis antarmuka (GUI) digunakan. Di sini, antarmuka adalah sistem jendela dengan
mouse yang berfungsi sebagai alat penunjuk untuk mengarahkan I/O, memilih dari menu, dan membuat pilihan dan keyboard untuk memasukkan teks. Sistem seluler seperti:
karena ponsel dan tablet menyediakan antarmuka layar sentuh, memungkinkan pengguna untuk
geser jari mereka di layar atau tekan tombol di layar untuk memilih
pilihan. Pilihan lain adalah antarmuka baris perintah (CLI = command-line interface), yang menggunakan teks perintah dan metode untuk memasukkannya (misalnya, keyboard untuk mengetik dalam perintah dalam format tertentu dengan opsi tertentu). Beberapa sistem memberikan dua atau ketiga variasi ini.

<p align = "center">
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/cli.png"></p>

<center> Gambar 1.2</center>
<center><h6>CLI di windows 10</h6></center>


2.Pembuatan Program

   Sistem operasi menyediakan berbagai  fasilitas yang membantu programmer dalam membuat program seperti editor. Walaupun bukan bagian dari sistem operasi , tapi layanan ini diakses melalui sistem operasi.

3.Eksekusi Program
   
   Sistem harus bisa me-load program ke memori, dan menjalankan program tersebut. Program harus bisa menghentikan pengeksekusiannya baik secara normal maupun tidak (ada error).

4.Operasi I/O

   Program yang sedang di jalankan kadang kala membutuhkan I/O. Untuk efisiensi dan keamanan, pengguna biasanya tidak bisa mengatur peranti I/O secara langsung, untuk itulah sistem operasi harus menyediakan mekanisme dalam melakukan operasi I/O.

5.Manipulasi Sistem Berkas

   Program harus membaca dan menulis berkas, dan kadang kala juga harus membuat dan menghapus berkas.

6.Komunikasi

   Kadang kala sebuah proses memerlukan informasi dari proses yang lain. Ada dua cara umum dimana  komunikasi dapat dilakukan. Komunikasi dapat terjadi antara proses dalam satu komputer, atau antara proses yang berada dalam komputer yang berbeda, tetapi dihubungkan oleh jaringan komputer. Komunikasi dapat dilakukan dengan pembagian memori(pengguna bersama, share-memory) atau message-passing, dimana sejumlah informasi dipindahkan antara proses oleh sistem operasi.

7.Deteksi Error

Sistem operasi harus selalu waspada terhadap kemungkinan error. Error dapat terjadi di CPU dan memori perangkat keras, I/O, dan di dalam program yang di jalankan pengguna. Untuk setiap jenis error sistem operasi,harus bisa mengambil langkah yang tepat untuk mempertahankan jalannya proses komputasi.

Disamping pelayanan diatas, sistem operasi juga menyediakan layanan lain. Layanan ini bukan untuk membantu pengguna tapi lebih pada mempertahankan efisiensi sistem itu sendiri. Layanan tambahan itu yaitu :


1.Alokasi sumber daya

  Ketika beberapa pengguna  menggunakan sistem atau beberapa program dijalankan secara bersamaan, sumber daya harus dialokasikan bagi masing-masing pengguna dan program tersebut.

2.Accounting

  Kita menginginkan agar jumlah pengguna yang menbggunakan sumber daya , dan jenis sumber daya yang di gunakan selalu terjaga . Untuk itu maka diperlukan suatu perhitungan dan statistik. Perhitungan ini diperlukan bagi seseorang yang ingin merubah konfigurasi sistem untuk meningkatkan pelayanan.

3.Proteksi Layanan

 Proteksi memastikan bahwa sehala akses ke sumber daya terkontrol. Dan tentu saja keamanan terhadap gangguan dari luar sistem tersebut. Keamanan bisa saja di lakukan dengan terlebih dahulu mengidentidikasi pengguna. Ini bisa dilakukan dengan meminta password bila ingin mengunakan sumber daya.

System Calls


Biasanya tersedia sebagai instruksi bahasa rakitan. Beberapa sistem mengizinkan system calls dibuat langsung dari program bahasa tingkat tinggi. Beberapa bahasa pemograman (contoh : C, C++) telah didefinisikan untuk menggantikan bahasa rakitan untuk sistem pemograman.

Tiga metode umum yang di gunakan dalam memberikan parameter pada sistem operasi.

<ul>
<li>Melalui register</li>
<li>Menyimpan parameter dalam blok atau tabel pada memori dan alamat blok tersebut diberikan sebagai parameter dalam register</li
<li>Menyimpan parameter (push) ke dalam dalam stack (oleh program), dan melakukan pop off pada stack (oleh sistem operasi)</li>

#### Memberikan parameter melalui tabel

<p align = "center">
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/tabel.png"></p>
 <center>1.3</center>
 <center><i>Sumber :Abraham-Silberschatz,et.al, Operating System Concepts, 10th ed 2018: halaman 66. </i></center>

### Jenis System Calls

1.Kontrol Proses

   System calls yang berhubungan dengan kontrol proses antara lain ketika penghentian pegeksekusian program. Baik secara normal (end) maupun tidak normal (abort). Selama proses dieksekusi kadang kala diperlukan untuk meload atau mengeksekusi program lain, disini diperlukan lagi suatu system calls. Juga ketika membuat sesuatu proses baru dan menghentikan sebuah proses. Ada juga system calls yang dipanggil ketika kita ingin meminta dan merubah atribut dari suatu proses.

MS-DOS adalah contoh dari sistem single-tasking. MS-DOS menggunakan metode yang sederhana dalam menjalankan program dan tidak menciptakan proses baru. Program di-load ke dalam memori,kemudian program dijalankan 


#### Eksekusi MS-Dos

<p align = "center">
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/eksekusimsdos.jpg"></p>
 <center>2.1</center>
 <center><i>Sumber :Abraham-Silberschatz,et.al, Operating System Concepts, 10th ed 2018: halaman 70. </i></center>
