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

1. Kontrol Proses

   System calls yang berhubungan dengan kontrol proses antara lain ketika penghentian pegeksekusian program. Baik secara normal (end) maupun tidak normal (abort). Selama proses dieksekusi kadang kala diperlukan untuk meload atau mengeksekusi program lain, disini diperlukan lagi suatu system calls. Juga ketika membuat sesuatu proses baru dan menghentikan sebuah proses. Ada juga system calls yang dipanggil ketika kita ingin meminta dan merubah atribut dari suatu proses.

MS-DOS adalah contoh dari sistem single-tasking. MS-DOS menggunakan metode yang sederhana dalam menjalankan program dan tidak menciptakan proses baru. Program di-load ke dalam memori,kemudian program dijalankan 


#### Eksekusi MS-Dos

<p align = "center">
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/eksekusimsdos.jpg"></p>
 <center>2.1</center>
 <center><i>Sumber :Abraham-Silberschatz,et.al, Operating System Concepts, 10th ed 2018: halaman 70. </i></center>

Barkeley Unix adalah contoh dari sistem *multi-tasking*.*Command Interpereter* masih tetap bisa dijalankan ketika program lain dieksekusi.


#### Multi program pada *Unix*
<p>
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/eksekusimsdos.jpg"></p>
 2.2
 <i>Sumber :Abraham-Silberschatz,et.al, Operating System Concepts, 10th ed 2018: halaman 71. </i>

2. Manajemen Berkas

    *System Calls* yang berhubungan dengan berkas sangat diperlukan. Seperti ketika kita ingin membuat atau menghapus suatu berkas. Atau ketika ingin membuka atau menutup sesuatu berkas yang telag ada, membaca berkas tersebut, dan menulis berkas itu. *System calls* juga diperlukan ketika kita ingin mengetahui atribut dari suatu berkas atau ketika kita juga ingin merubah atribut tersebut. Yang termasuk atribut berkas adalah nama berkas, jenis berkas, dan lain-lain.
    
    Ada juga *System calls* yang menyediakan mekanisme lain yang berhubungan dengan direktori atau sistim berkas secara keseluruhan. Jadi bukan hanya berhubungan dengan satu spesifik berkas . Contohnya menghapus suatu direktori dan lain-lain.
    
 3. Manajemen Peranti
  
    Program yang sedang dijalankan kadang kala memerlukan tambahan sumber daya. Jika banyak pengguna yang menggunakan sistem dan jika diperlukan tambahan sumber daya maka harus meminta peranti terlebih dahulu. DAn setelah selesai penggunkannya harus dilepaskan kembali. Ketika sebuah peranti telah diminta dan dialokasikan maka peranti tersebut bisa dibaca, ditulis, atau di reposisi
     
     
 4. Informasi *Maintenance*
 
    Beberapa *System Calls* disediakan untuk membantu pertukaran informasi antara pengguna dan sistem operasi. Contohnya *system calls* untuk meminta dan mengatur waktu dan tanggal. Atau meminta informasi tentang sistem itu sendiri, seperti jumlah pengguna, jumlah memori dan disk yang masih bisa digunakan, dan lain-lain. Ada juga *system calls* untuk meminta informasi tentang proses yang disimpan oleh sistem dan system calls untuk merubah (reset) informasi tersebut.
    
 5. Komunikasi
 
    Dua model komunikasi
    + *message-passing*
    
        pertukaran informasi dilakukan melalui fasilitas komunikasi antar proses yang sediakan oleh sistem operasi.
        
    + *shared-memory*
    
        Proses menggunakan memori yang bisa digunakan oleh berbagai proses untuk pertukaran informasi dengan membaca dan menulis data pada memori tersebut.
        
   #### Mekanisme komunikasi
   
   <p>
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/mekanismekomunikasi.png"></p>
 
Dalam *message-passing*, sebelum komunikasi dapat dilakukan harus dibangun dulu sebuah koneksi. Untuk itu diperlukan suatu *system calls* dalam pengaturan koneksi tersebut , baik dalam menghubungkan koneksi tersebut maupun dalam memutuskan koneksi tersebut ketika komunikasi sudah selesai dilakukan. Juga diperlukan suatu *system calls* untuk membaca dan menulis pesan (*message*)agar pertukaran informasi dapat dilakukan.


#### System Program

*system program* menyediakan lingkungan yang memungkinkan pengembangan dan eksekusi berjalan dengan baik.

Dapat dikategorikan :
<ul>
<li>Manajemen/manipulasi Berkas</li>
<p>Membuat,menghapus,copy,rename,print,memanipulasi berkas dan direktori</p>
<li>Informasi status</li>
<p> Beberapa program meminta informasi tentang tanggal,jam,jumlah memori dan disk yang tersedia, jumlah pengguna dan informasi lain yang sejenis.
<li>Modifikasi berkas</li>
<p>membuat berkas dan memodifikasi isi berkas yang disimpan pada disk atau tape.</p>
<li>Pendukung bahasa pemprograman</li>
<p>kadang kala kompilator,*assembler* dan *interpreter* dari bahasa pemograman diberikan kepada pengguna dengan bantuan sistem operasi.</p>
<ul>Loading dan eksekusi program</ul>
<p>ketika program di *assembly* atau di *compile*,program tersebut harus di-load ke dalam memori untuk dieksekusi. Untuk itu sistem harus menyediakan *absolute loaders*,*relocatable loaders*,*linkage editors*, dan *overlay loaders*</p>
<li>Komunikasi</li>
<p>menyediakan mekanisme komunikasi antara proses, pengguna, dan sistem komputer yang berbeda. Sehingga pengguna bisa mengirim pesan, menelusuri halaman web, mengirim e-mail, atau mentransfer berkas.
</ul>

Umumnya sistem operasi dilengkapi oleh *system-utilities* atau program aplikasi yang di dalamnya termasuk web browser, word prosesor dan format teks, sistem database, games. System program yang paling penting adalah *Command interpreter*(mengambil dan menerjemahkan *user-specified command* selanjutnya).


### Struktur Sistem

sebuah sistem yang besar dan kompleks seperti sistem operasi modern harus diatur dengan cara membagi task kedalam komponen-komponen kecil agar dapat berfungsi dengan baik dan mudah dimodifikasi. Pada bab ini, kita akan membahas cara komponen-komponen ini di hubungkan satu sama lain. Menurut Avi Silberschatz,Peter Galvin, dan Greg Gagne, ada tiga cara yaitu :

<ul>
<li>Struktur Sederhana</li>
<li>Pendekatan Terlapis</li>
<li>Mikrokernel</li>
</ul>

Sedangkan menurut William Stallings, kita bisa memandang sistem sebagaui seperangkat lapisan. Tiap lapisan menampilkan bagian fungsi yang dibutuhkan oleh sistem operasi. Bagian yang terletak pada lapisan yang lebih rendah akan menampilkan fungsi yang lebih primitif dan menyimpan detail fungsi tersebut.


### Struktur Sederhana
Banyak sistem yang tidak terstruktur dengan baik, sehingga sistem operasi seperti ini dimulai dengan sistem yang lebih kecil, sederhana, dan terbatas. Kemudian berkembang dengan cakupan yang original. Contoh sistem seperti ini adalah MS-DOS, yang disusun untuk mendukung fungsi yang banyak pada ruang yang sedikit karena keterbatasan perangkat keras untuk menjalankannya.

Contoh sistem lainnya adalah UNIX. yang terdiri dari dua bagian yang terpisah, yaitu Kernel dan program sistem. Kerne/ selanjutnya dibagi dua bagian, yaitu antarmuka dan device drivers. Kernel mendukung sistem berkas, penjadwalan CPU, manajemen memori, dan fungsi sistem operasi lainnya melalui *system calls*.
### Pendekatan Terlapis
Sistem operasi dibagi menjadi sejumlah lapisan yang masing-masing dibangun diatas lapisan yang lebih rendah. Lapisan yang lebih rendah menyediakan layanan untuk lapisan yang lebih tinggi. Lapisan yang paling bawah adalah perangkat keras, dan yang paling tinggi adalah *user-interface*.

#### Lapisan pada Sistem Operasi
  
  <p>
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/lapisan.png">
 Sumber: Silberschatz,et.al, Operating System Concepts.6th e, .2003, New York:John Wiley & Son.Inc, halainan 77</p>
 
 
 Sebuah lapisan adalah implementasi dari objek abstrak yang merupakan enkapsulasi dari data dan operasi yang bisa memanipulasi data tersebut. Keuntungan utama dengan sistem in adalab modularitas. Pendekatan ini mempermudah *debug* dan verifikasi sistem.
 Lapisan pertama bisa di debug tapa mengganggu sistem yang lain karena hanya menggunakan perangkat keras dasar untuk implementasi fungsinya. Bila terjadi error saat debugging sejumlah lapisan, error pasti pada lapisan yang baru saja di debug,. karena lapisan dibawahnya sudah di debug.Sedangkan menurut Tanenbaum dan Woodhull, sister terlapis terdiri dari enam lapisan, yaitu :</p>
 
 • Lapisan 0</p>
Mengatur alokasi prosesor, pertukaran antar proses ketika interupsi terjadi atau waktu babis. Lapisan ini mendukung dasar multi-programming pada CPU</p>

 • Lapisan 1</p>
 Mengalokasikan ruang untuk proses di memori utama dan pada 512 kilo word drum yang digunakan untuk menahan bagian proses ketika tidak ada ruang dimemori utama</p>
• Lapisan 2</p>
Menangani komunikasi antara masing-masing proses dan *operator console*. Pada lapis ini masing-masing proses secara efektif memiliki *opertor console* sendiri.</p>
• Lapisan 3</p>
Mengatur peranti I/O dan menampang informasi yang mengalir dari dan ke proses tersebut.</p>
• Lapisan 4</p>
Tempat program pengguna. Pengguna tidak: perlu memikirkan tentang proses. memori, *console*, atau manajemen I/O.</p>

• Lapisan 5</p>
Merupakan operator sistem</p>

Menurut Stallings, model tingkatan sistem operasi yang mengaplikasikan prinsip ini dapat dilihat pada tabel berikut, yang terdiri dari level-level dibawah ini :



<p>
 <img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/tabelso..png">
</p>

• Level 1</p>
terdiri dari sirkuit elektronik dimana objek yang ditangani adalah *register memory cell*, dan gerbang logika operasi pada objek ini seperti membersihkan register atau membaca lokasi memori</p>
• Level 2</p>
Pada level ini adalah set intruksi pada *prosessor*. Operasinya adalah instruksi bahasa-mesin, seperti menambah, mengurangi, *load* *store*.</p>
• Level 3</p>
Tambahan konsep prosedur atau subrutin ditambah operasi *call* atau return.</p>
• Level 4</p>
Mengenalkan interupsi yang menyebabkan prosesor harus menyimpan perintah yang baru dijalankan dan memanggil rutin penanganan intrupsi</p>

Empat level pertama bukan bagian sistem operasi tetapi bagian perangkat keras. Meskipun demikian beberapa elemen sistem operasi mulai tampil pada level-level ini, seperti rutin penanganan interupsi Pada level 5, kita mulai masuk kebagian sistem operasi dan konsep nya berhubungan dengan *multi-programming*.</p>

• Level 5</p>
Level ini mengenalkan ide proses dalam mengeksekusi program. Kebutuhan-kebutuhan dasar pada sistem operasi untuk mendukung proses ganda termasuk kemampuan *mesuspend* dan *meresume* proses. Hal ini membutuhkan register perangkat keras untuk menyimpan agar eksekusi bisa ditukar antara satu proses ke proses lainnva.
• Level 6</p>
Mengatasi penyimpanan sekunder dari komputer, Level in untuk menjadwalkan operasi dan menanggapi permintaan proses dalan melengkapi suatu proses.</p>
• Level 7</p>
Membuat alamat logis untuk proses. Level ini mengatur alamat virtual ke dalam blok yang bisa dipindahkan antara memori utama dan memori tambahan. Cara-cara yang sering dipakai adalah menggunakan ukuran halaman yang tetap. menggunakan segmen sepanjang variabelnya, dan menggunakan cara keduanya Ketika blok yang dibutuhkan tidak ada dimemori utama, alamat logis pada level ini meminta transfer dari level 6.</p>

Sampai point ini, sistem operasi mengatasi sumber daya dari prosesor tunggal. Mulai level 8. sistem operasi mengatasi objek eksternal seperti peranti bagian luar, jaringan, dan sisipan komputer kepada jaringan.</p>
• Level 8</p>
Mengatasi komunikasi informasi dan pesan-pesan antar proses. Dimana pada level 5 disediakan mekanisme penanda yang kuno yang memungkinkan untuk sinkronisasi proses, pada level ini mengatasi pembagian informasi yang lebih banyak. Salah satu peranti yang paling sesuai adalah *pipe* (pipa) yang menerima output suatu proses dan memberi input ke proses lain.
• Level 9</p>
Mendukung penyimpanan jangka panjang yang disebut dengan berkas. Pada level ini, data dari penyimpanan sekunder ditampilkan pada tingkat abstrak, panjang variabel yang terpisah. Hal ini bertentangan tampilan yang berorientasikan perangkat keras dari penyimpanan sekunder</p>
• Level 10</p>
Menyediakan akses ke peranti eksternal menggunakan antarmuka standar.</p>
• Level 11</p>
Bertanggung jawab mempertahankan hubungan antara internal dan eksternal teurifier dari sumber daya dan objek sistem. Eksternal identifier adalah nama yang bisa dimanfaatkan ole aplikasi atau pengguna. Internal idenrifier adalabi alamat atau indiast lain yang bisa digunakan oleh level yang lebih rendah untuk meletakkan dan mengontrol objek</p>
• Level 12</p>
Menyediakan suatu fasilitator yang penuh tampilan untuk mendukung proses. Hal ini merupakan lanjutan dari yang telah disediakan pada level 5. Pada level 12, semua info yang dibutuhkan untuk manajemen proses dengan berurutan disediakan, termasuk: alamat virtual di proses, daftar objek dan proses yang berinteraksi dengan proses tersebut serta batasan interaksi tersebut, parameter yang harus dipenuhi proses saat pembentukan, dan karakteristik lain yang mungkin digunakan sistem operasi untuk mengontrol proses.</p>
• Level 13</p>
Menyediakan antarmuka dari sistem operasi dengan pengguna yang dianggap sebagai *shell* atau dinding karena memisahkan pengguna dengan sistem operasi dan menampilkan sistem operasi dengan sederhana sebagai kumpulan servis atau pelayanan.</p>

Dari ketiga sumber diatas dapat kita simpulkan bahwa lapisan sistem operasi secara umum terdiri atas 4 bagian yaitu:</p>

1. Perangkat keras</p>
lebih berhubungan kepada perancang sistem. Lapisan mencakup lapisan 0 dan 1 menurut Tanebaum, dan level 1 sampai dengan level 4 menurut Stallings. 

2. Sistem operasi

    lebih berhubungan dengan programmer. Lapisan ini mencakup lapisan 2 menurut Tanebaum, dan level 5 sampai dengan level 7 menurut Stallings.

3. Kelengkapan 

    lebih berhubungan kepada programmer. Lapisan ini mencakup lapisan 3 menurut Tanebaum, dan level 8 sampai dengan 11 menuru Stallings.

4. Program aplikasi

    lebih berhubungan kepada pengguna aplikasi komputer. Lapisan ini mencakup lapisan 4 dan lapisan 5 menurut Tanebaum, dan level 12 dan 13 menurut Stalling</p>
    
 <p><img src="file:///F:/Kuliah%20ULM/semester%203%20ulm/S3/SISTEM%20OPERASI/lapisanos.png"></p>
 
 Salah satu kesulitan besar dalam sistem terlapis disebabkan karena sebuah lapisan hanya bisa menggunakan lapisan-lapisan dibawahnya, misalnya : *backing-store driver*, normalnya diatas penjadwal CPU sedangkan pada sistem yang besar, penjadwal CPU punya informasi tentang proses yang aktif yang ada di memori. Oleh karena itu, info ini harus dimasukkan dan dikeluarkan dari memori, sehingga membutuhkan backing-store driver dibawah penjadwal CPU. Kesulitan lainnya adalah paling tidak efisien dibandingkan tipe lain. Retika pengguna mengeksekusi 1/O, akan mengeksekusi lapisan I/O, lapisan manajemen memori, yang memanggil lapisan penjadwal CPU.</p>
 
### Mikrokernel</p>
Metode ini menyusun sistem operasi dengan menghapus semua komponen yang tidak esensial dari Kernel, dan mengimplementasikannya sebagai program sistem dan level pengguna. Hasilnya kerne/ yang lebih kecil. Pada umumnya mikrokernel mendukung proses dan manajemen memori yang minimal, sebagai tambahan utnuk fasilitas komnikasi.</p>

Fungsi utama mikrokernel adalah mendukung fasilitas komunikasi antara program Klien dan bermacam-macam layanan yang juga berjalan di *user space*. Komunikasi yang dilakukan secara tidak langsung, didukung oleh sistem *message passing*, dengan bertukar pesan melalui mikrokernel.</p>

Salah satu keuntungan mikrokernel adalah ketika layanan baru akan ditambahkan ke *user, space*, Kernel tidak perlu dimodifikasi. Kalau pun harus perubahan akan lebih sedikit. Hasil sistem operasinya lebih mudah untuk ditempatkan pada suatu desain perangkat keras ke desain lainnya. Mikrokernel juga mendukung keamanan reliabilitas lebih, karena kebanyakan layanan berjalan sebagai pengguna proses. Jika layana gagal, sistem operasi lainnya tetap terjaca. Beberapa sistem operasi yang menggunakan metode in adalah TRU 64 UNIX. MacosX. dan ONX 