# Modul 3 - HTTP

**Nama:** ARYNAL HAQ SYAFI'I 
**NIM:** 103072400155

## Laporan Praktikum Jarkom
Memahami semua cara kerja protokol HTTP dan menganalisis komunikasi antara browser dengan server menggunakan wireshark

## Percobaan Praktikum

### 1. Basic HTTP GET / Response Langkah
1. Jalankan Wireshark dan gunakan filter: `http`
2. Mulai capture paket
3. Buka browser dan akses:  
   http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html
4. Hentikan capture setelah halaman muncul


## Hasil
Terlihat dua pesan utama: HTTP GET (Request) Browser meminta file dari server. HTTP Response Server mengirimkan file HTML sebagai respon.

### 2. HTTP Conditional GET Langkah
1. Setiap ingin memulai step awal bersihkan cache pada browser  
2. Setelah itu Start capture Wireshark  
3. Lalu akses Link: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html  
4. Setelah mengakses link tersebut kita lakukan refresh pada halaman web  
5. Stop capture

## Hasil
Memanfaatkan header If-Modified-Since untuk validasi berkas, jika versi berkas disisi server tidak mengalami perubahan sejak terakhir diakses, server akan mengirimkan kode status 304 Not Modified tanpa mengirimkan isi berkas tersebut kembali. Langkah ini efektif untuk memangkas konsumsi bandwidth secara signifikan.

### 3. Retriving Long Documents Langkah
1. Start capture
2. Buka link:http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html
3. Stop capture

## Hasil
Analisis paket menunjukkan bahwa peramban melakukan request HTTP standar untuk mendapatkan dokumen HTML, karena ukuran file yang cukup besar melebihi kapasitas satu paket TCP, server memecah data tersebut menjadi beberapa bagian. Pada Wireshark proses ini terlihat melalui label 'Reassembled TCP Segments' yang dimana menandakan bahwa protokol lapisan bawah menyatukan kembali potongan-potongan tersebut agar utuh menjadi satu konten HTTP yang terbaca.

### 4. HTML dengan Embedded Objects Langkah
1. Start capture
2. akses link: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html
3. stop capture

## Hasil
Ketika sebuah laman web di akses, peramban tidak hanya memuat kode HTML utama tetapi secara otomatis melakukan request tambahan untuk setiap elemen pendukung yang tersemat (seperti gambar atau icon). Hal ini terbukti dari log Wireshark yang menampilkan rentetan perintah GET terpisah untuk setiap komponen mulai dari file HTML itu sendiri hingga file aset pendukung seperti .jpg .png atau .ico yang ada didalam halaman tersebut.

pada hasil capture Wireshark terlihat beberapa request HTTP: 1. GET /wireshark-labs/HTTP-wireshark-file4.html 2. GET /pearson.png 3. GET /8E_cover_small.jpg

### 5. HTTP Authentication Langkah
1. Start capture
2. Akses:http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html
3. Login menggunakan username: wireshark-student dan password: network
4. Stop capture

## Hasil
Untuk mengakses halaman terbatas, server awalnya menolak akses dengan kode status 401 Unauthorized sebagai tantangan autentikasi, setelah itu peramban akan melakukan pengiriman ulang request dengan menyertakan header Authorization. Informasi kredensial di dalamnua hanya disamarkan menggunakan skema Base64 (bukan enkripsi), sehingga sangat rentan dibaca oleh pihak ketiga jika tidak dilindungi oleh protokol enkripsi seperti HTTPS.

## Kesimpulan
1.Pola Komunikasi: HTTP berfungsi sebagai protokol utama antara browser (klien) dan web server dalam pertukaran data. 2.Efisiensi Caching: Melalui Conditional GET dan header If-Modified-Since, browser dapat memvalidasi cache untuk menghindari pengunduhan ulang konten yang tidak berubah. 3.Fragmentasi Data: Berkas berukuran besar dipecah menjadi beberapa segmen TCP saat transmisi dan akan disatukan kembali oleh browser agar menjadi dokumen utuh. 4.Pemuatan Aset: Setiap elemen pada halaman (seperti gambar atau ikon) memerlukan permintaan HTTP yang terpisah untuk bisa dimuat secara lengkap. 5.Risiko Autentikasi: Mekanisme Basic Authentication hanya menggunakan encoding Base64 yang tidak memberikan enkripsi asli, sehingga data kredensial sangat rentan jika dikirim tanpa proteksi HTTPS.

![Hasil Percobaan](../assets/image/week3%20(1).png)
![Hasil Percobaan](../assets/image/week3%20(2).png)
![Hasil Percobaan](../assets/image/week3%20(3).png)
![Hasil Percobaan](../assets/image/week3%20(4).png)
![Hasil Percobaan](../assets/image/week3%20(5).png)
![Hasil Percobaan](../assets/image/week3%20(6).png)