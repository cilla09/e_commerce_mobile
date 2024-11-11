### Cilla's Minimart - Mobile

<details>
<summary>Tugas 7</summary>

**Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.**

Stateless widget merupakan widget yang tidak memiliki state, sehingga widget tidak bisa berubah/memperbarui tampilan dengan sendirinya melalui aksi internal. Stateless widget hanya dapat berubah dari event eksternal pada widget parent di widget tree. Stateless widget juga hanya memiliki properti `final` yang didefinisikan ketika proses konstruksi, dan hanya itu yang digunakan untuk membangun tampilan di layar perangkat.

Stateful widget merupakan widget yang dapat mengubah tampilannya dengan sendirinya secara dinamis selama siklus hidupnya. Stateful widget bersifat immutable (tidak dapat diubah langsung), namun memiliki sebuah class bernama `State` yang menyimpan informasi atau keadaan terbaru dari widget tersebut. Class `State` ini yang memungkinkan Stateful Widget untuk memperbarui tampilannya sendiri berdasarkan perubahan internal, seperti respons terhadap interaksi pengguna atau perubahan data. Pembaharuan dapat dilakukan dengan method `setState()`.

Perbedaan antara stateless dan stateful widget terletak di cara mereka dapat berubah. Stateless Widget hanya dapat berubah sebagai respons terhadap event eksternal dari parent widget, sehingga tampilannya statis dan tidak dipengaruhi oleh keadaan internalnya. Stateful widget dapat berubah dengan sendirinya secara dinamis menggunakan class `State`.

**Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.**

- MaterialApp: container utama aplikasi flutter untuk mengatur tema seluruh aplikasi
- Scaffold: struktur dasar 
- AppBar: bagian atas halaman yang dapat menampilkan judul, icon, dan lainnya.
- Column: menyusun widget secara vertikal.
- Row: menyusun widget secara horizontal.
- GridView: menampilkan item dalam tata letak grid.
- Card: membuat kartu yang menampilkan informasi.
- ItemCard: menampilkan tombol dalam bentuk kartu berisi icon dan text.
- InkWell: meng-handle event dari ItemCard dan menampilkan pesan pada SnackBar.
- SnackBar: menampilkan pesan yang bersifat sementara

**Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.**

setState() berguna untuk pembaharuan pada UI Stateful Widget. Ketika fungsi dipanggil, flutter akan dipicu untuk rebuild (memanggil fungsi `build()`) dengan memperbarui tampilan dengan data yang sudah berubah. Variabel yang terdampak dengan fungsi `setState()` adalah variabel yang disimpan dalam state dari Stateful Widget.

**Jelaskan perbedaan antara const dengan final.**

Perbedaan utama antara `const` dan `final` terletak pada kapan nilai variabel diinisialisasi dan fleksibilitasnya. Untuk `const`, nilai variabel harus sudah diketahui/bersifat konstan ketika compile-time/kode dikompilasi. Sementara, nilai variabel dengan properti `final` lebih fleksibel karena boleh baru diketahui ketika runtime/kode berjalan. Kedua properti ini sama-sama membuat nilai variabel tidak dapat diubah setelah pertama diinisialisasi, namun `const` bersifat compile-time constant (lebih cocok untuk objek yang benar-benar tidak akan berubah karena dibagikan di memori), sementara `final` bersifat runtime constant (lebih fleksibel untuk nilai yang diketahui belakangan). 

**Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.**

1. Membuat proyek baru Flutter

Menjalankan command `flutter create e_commerce` di terminal untuk membuat proyek Flutter baru.

2. Membuat tiga tombol dengan ikon dan teks yang diingini

Pada file `menu.dart`, dibuat class `ItemHomePage` yang berisi tombol dalam bentuk `ItemCard` yang mempunyai properti `name`, `icon`, `color`. Ketiga tombol disusun dalam layout grid menggunakan GridView. 

3. Membuat ketiga tombol berwarna beda.
   
Untuk membedakan warna setiap tombol, atribut baru yaitu `color` ditambahkan ke `ItemHomepage`. Lalu, pada list `ItemHomepage` di class MyHomepage setiap `ItemHomepage` didefinisikan warnanya.  

4. Menampilkan Snackbar yang berisi pesan ketika tombol ditekan.
   
Pada ItemCard terdapat widget `InkWell` yang memiliki fungsi onTap untuk menampilkan `SnackBar` (pesan sementara) yang berbeda-beda sesuai tombol yang ditekan.

</details>

<details>
   <summary>Tugas 8</summary>

**Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?**


**Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!**


**Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!**


**Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?**


**Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?**



</details>
