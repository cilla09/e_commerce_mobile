### Cilla's Minimart - Mobile

## Tugas 7

**Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.**

Stateless widget merupakan widget yang tidak memiliki state, sehingga widget tidak bisa berubah/memperbarui tampilan dengan sendirinya melalui aksi internal. Stateless widget hanya dapat berubah dari event eksternal pada widget parent di widget tree. Stateless widget juga hanya memiliki properti `final` yang didefinisikan ketika proses konstruksi, dan hanya itu yang digunakan untuk membangun tampilan di layar perangkat.

Stateful widget merupakan widget yang dapat mengubah tampilannya dengan sendirinya secara dinamis selama siklus hidupnya. Stateful widget bersifat immutable (tidak dapat diubah langsung), namun memiliki sebuah class bernama `State` yang menyimpan informasi atau keadaan terbaru dari widget tersebut. Class `State` ini yang memungkinkan Stateful Widget untuk memperbarui tampilannya sendiri berdasarkan perubahan internal, seperti respons terhadap interaksi pengguna atau perubahan data.

Perbedaan antara stateless dan stateful widget terletak di cara mereka dapat berubah. Stateless Widget hanya dapat berubah sebagai respons terhadap event eksternal dari parent widget, sehingga tampilannya statis dan tidak dipengaruhi oleh keadaan internalnya. Stateful widget dapat berubah dengan sendirinya secara dinamis menggunakan class `State`.

**Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.**



**Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.**



**Jelaskan perbedaan antara const dengan final.**

Perbedaan utama antara `const` dan `final` terletak pada kapan nilai variabel diinisialisasi dan fleksibilitasnya. Untuk `const`, nilai variabel harus sudah diketahui/bersifat konstan ketika compile-time/kode dikompilasi. Sementara, nilai variabel dengan properti `final` lebih fleksibel karena boleh baru diketahui ketika runtime/kode berjalan. Kedua properti ini sama-sama membuat nilai variabel tidak dapat diubah setelah pertama diinisialisasi, namun `const` bersifat compile-time constant (lebih cocok untuk objek yang benar-benar tidak akan berubah karena dibagikan di memori), sementara `final` bersifat runtime constant (lebih fleksibel untuk nilai yang diketahui belakangan). 

**Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.**

