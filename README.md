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

Kegunaan `const` di Flutter adalah membuat objek yang bersifat immutable (tidak bisa diubah) dan juga compile-time constant. Keuntungan ketika menggunakan `const` pada kode Flutter, yaitu:
1. Menghemat memori, karena Flutter hanya menyimpan objek const sekali di memori.
2. Meningkatkan performa, karena objek `const` sudah dihitung ketika kode dikompilasi, sehingga tidak perlu dihitung ulang oleh Flutter ketika aplikasi dijalankan.
3. Menjamin immutabilitas dan stabilitas kode, karena objek `const` tidak bisa diubah setelah dibuat, sehingga kita tidak perlu mengkhawatirkan terjadi bug akibat perubahan tak terduga dalam aplikasi.

Sebaiknya kita menggunakan `const` ketika ingin membuat widget yang tidak perlu berubah selama aplikasi berjalan (contoh: `Text('Hello')`, `Icon(Icons.home)`). Sebaiknya kita tidak menggunakan `const` ketika widget perlu berubah saat aplikasi berjalan (contoh: ListView dan Stateful Widget yang akan berubah jika ada perubahan data dari pengguna).

**Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!**

Column: mengatur widget secara vertikal dari atas ke bawah, umumnya digunakan untuk layout vertikal seperti daftar atau formulir yang diisi dari atas ke bawah.

``` dart
Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  children: [
    Text('Nama: $_name'),
    Text('Deskripsi: $_description'),
    Text('Harga: $_price'),
  ],
),
```

Row: mengatur widget secara horizontal dari kiri ke kanan, umumnya digunakan untuk layout horizontal seperti bar navigasi yang berupa baris dari kiri ke kanan.

``` dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    InfoCard(title: 'NPM', content: npm),
    InfoCard(title: 'Name', content: name),
    InfoCard(title: 'Class', content: className),
  ],
)
```

**Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!**

Elemen input yang saya gunakan dalam tugas kali ini:
- `TextFormField` yang menerima input teks dari pengguna. Elemen ini saya gunakan untuk menerima input nama produk, deskripsi produk, dan harga produk.

Elemen input yang tidak saya gunakan dalam tugas kali ini:
- `Radio` yang berguna untuk memilih satu opsi dari beberapa opsi yang tersedia.
- `CheckBox` yang berguna untuk memilih satu atau lebih opsi dari beberapa opsi yang tersedia.
- `Switch` yang berguna untuk memilih 1 dari 2 opsi.
- `DropdownButton` yang berguna untuk memilih satu opsi dari banyak pilihan tersedia (pilihan ditampilkan dalam container kotak ketika kotak pengisian ditekan)
- `showTimePicker` dan `showDatePicker` yang berguna untuk menginput waktu dan tanggal.
- `Slider` yang berguna untuk menginput suatu nilai dari sebuah range dengan menggeser kursor pada sebuah jalur garis.

**Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?**

Saya menggunakan `ThemeData` pada class `MyApp` di `main.dart` untuk mengatur tema aplikasi Flutter agar tetap konsisten. Pada `ThemeData`, saya mengimplementasikan tema aplikasi dengan menetapkan warna utama (primaryColor), warna aksen (accentColor), gaya teks (textTheme), dan banyak elemen visual lainnya dalam satu tempat. `ThemeData` menjaga konsistensi karena setiap perubahan pada tema dapat diterapkan di seluruh aplikasi secata otomatis, tanap harus mengubah setiap widget satu per satu secara manual.

``` dart
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSwatch(
        primarySwatch: Colors.deepPurple,
        ).copyWith(secondary: Colors.deepPurple[400]),
        useMaterial3: true,
      ),
      home: MyHomePage(),
    );
  }
}
```



**Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?**

Saya menangani navigasi dalam aplikasi dengan 2 cara. Pertama, dengan cara membuat Left Drawer, yaitu drawer menu yang dapat dibuka dengan menekan tombol hamburger di pojok kiri atas. Dalam menu tersebut, terdapat tombol-tombol yang berlabel nama halaman yang tersedia (`Halaman Utama`, `Tambah Produk`), jika ditekan maka user akan diarahkan ke halaman yang sesuai. Kedua, dengan menaruh tombol di halaman utama yang akan mengarahkan ke halaman yang sesuai, yaitu `Lihat Daftar Produk`, `Tambah Produk`, dan `Logout`.

</details>

<details>
  <summary>Tugas 9</summary>

**Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?**

Membuat model untuk pengambilan ataupun pengiriman data JSON sangat berguna untuk beberapa hal. Pertama, membantu menjaga konsistensi data karena atribut sudah didefinisikan di model sehingga model memastikan data sesuai dengan yang diharapkan. Kedua, mempermudah manipulasi data dan mengurangi kesalahan karena kita tidak berurusan langsung dengan string JSON mentah.

Jika tidak membuat model terlebih dahulu, tidak akan langsung menyebabkan error. Namun, resiko terjadi kesalahan akses data, tipe data tidak konsisten, dan kesulitan dalam debugging meningkat. Hal ini disebabkan kita akan bekerja dengan JSON mentah sehingga akan mempersulit kita.

**Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini**

Fungsi dari library HTTP adalah untuk menghubungkan aplikasi ke backend, yaitu aplikasi mengambil data produk dari backend Django menggunakan permintaan GET ke http://127.0.0.1:8000/json/. Library HTTP juga memungkinkan dinamisitas data karena data yang diambil langsung dari server tidak statis, sehingga mudah diperbarui atau diperluas. 

**Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.**

CookieRequest berguna untuk menangani komunikasi antara aplikasi Flutter dan server berbasis Django. Dengan CookieRequest, pengelolaan cookie untuk autentikasi dan pelacakan sesi pengguna dimungkinkan. Instance CookieRequest perlu dibagikan ke semua komponen di aplikasi untuk memastikan sesi pengguna tetap konsisten dengan data yang sesuai pengguna. Ini juga mempermudah autentikasi karena hanya perlu dilakukan sekali, lalu sesi pengguna dapat diakses semua komponen.

**Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.**

Pertama, input diambil dari pengguna memasukkan data pada form dan menekan tombol Submit. Kedua, data akan dikirim ke backend dengan Flutter yang menggunakan perminttan HTTP POST. Ketiga, data disimpan pada database di backend. Keempat, data tersebut dapat diambil versi terbarunya dengan Flutter melakukan permintaan GET. Keempat, data yang diambil ditampilkan di UI menggunakan widget seperti ListView atau GridView.

**Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.**

Proses registrasi, yaitu user mengisi form registrasi untuk membuat akun dengan kredensial yang diinginkan (username dan password). Data kredensial dikirim ke backend Django dan disimpan di database setelah proses validasi. Jika penyimpanan berhasil, Django mengirim respons ke Flutter untuk menampilkan pesan sukses atau gagal.

Proses login, yaitu user menginput data kredensial pada form login. Data ini kemudian dikirim ke Django dengan Flutter mengirim permintaan POST ke endpoint `/login/` di Django. Jika data sesuai dengan yang ada pada database, Django membuat sesi pengguna dan mengembalikan cookie autentikasi. Cookie ini akan disimpan di Flutter oleh library pbp_django_auth, lalu pengguna diarahkan ke halaman menu utama.

Proses logout, yaitu pengguna menekan tombol Logout, lalu FLutter mengirim permintaan GET atau POST ke Django. Django menghapus sesi pengguna dan mengembalikan respons sukses. Pada Flutter, cookie juga akan dihapus oleh library pbp_django_auth. Setelah logout berhasil, Flutter mengarahkan pengguna ke halaman login.

**Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).**

- Membuat aplikasi bernama `authentication` di Django untuk menangani autentikasi pengguna yang akan digunakan untuk aplikasi Flutter. Pada aplikasi ini, view diisi dengan fungsi-fungsi autentikasi, yaitu `login()`, `register()`, dan `logout()`.
- Membuat halaman login dan register yang berupa form untuk input kredensial pengguna.
- Membuat model kustom untuk menerima data JSON dari endpoint `/json/` di Django.
- Menerapkan fetch data dari Django dengan cara menambah dependensi HTTP dengan memodifikasi AndroidManifest.xml pada proyek Flutter.
- Membuat fungsi baru pada `main/views.py` yang bernama `create_product_flutter` untuk menambah produk melalui form pada Flutter.
- Membuat halaman list produk melalui `list_productentry.dart` yang menampilkan semua produk yang telah diinput baik dari Django maupun Flutter (yang ditampilkan hanya produk yang diinput oleh user yang sedang login).
- Untuk setiap item pada list produk, jika diklik akan mengarahkan ke halaman detail produk (ditangani pada `productentry_details.dart`). 
- Menyambungkan tombol-tombol pada halaman menu utama dan left drawer untuk mengarah pada halaman-halaman yang sesuai. Halaman menu utama: Lihat Produk, Tambah Produk, Logout. Left Drawer: Halaman Utama, Tambah Produk, Lihat Produk.

</details>