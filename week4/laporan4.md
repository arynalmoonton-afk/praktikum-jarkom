# Modul 4-DNS

**NAMA:** ARYNAL HAQ SYAFI'I 
**NIM:** 103072400155

## Tujuan

memahami cara kerja DNS menggunakan Wireshark dan CMD

## 4.2 Nslookup

### 1. Jalankan nslookup untuk mendapatkan alamat IP dari server web di Asia. Berapa alamat IP server tersebut?

![Hasil Percobaan](../assets/image/week4%20(1).png)

### 2. Jalankan nslookup agar dapat mengetahui server DNS otoritatif untuk universitas di Eropa

![Hasil Percobaan](../assets/image/week4%20(2).png)

### 3. alankan nslookup untuk mencari tahu informasi mengenai server email dari Yahoo! Mail melalui salah satu server yang didapatkan di pertanyaan nomor 2. Apa alamat IP-nya?

![Hasil Percobaan](../assets/image/week4%20(3).png)
g
## 4.3 Ipconfig

### 1.ketik ipconfig saja maka akan muncul informasi mengenai TCP/IP termasuk alamat IP Anda, alamat server DNS jenis adaptor dan sebagainya

![Hasil Percobaan](../assets/image/week4.3%20(1).png)

### 2. Lanjutkan dengan ipconfig /all maka akan muncul dari nama device atau host name, di bagian wifi dapat melihat ip4v address, subnet mask, dns server tidak hanya satu juga ada lebih untuk cadangan, dll

![Hasil Percobaan](../assets/image/week4.3%20(2).png)

### 3. Lalu ketikan ipconfig /displaydns akan memunculkan informasi DNS yang tersimpan dalam host. Hasil yang didapatkan akan menampilkan record dan sisa Time To Live (TTL) dalam

![Hasil Percobaan](../assets/image/week4.3%20(3).png)

### 4. Terakhir untuk menghapus catatan ketik ipconfig /flushdns. Akan Mengosongkan catatan DNS berarti menghapus semua record dan memuat ulang record dari file host

![Hasil Percobaan](../assets/image/week4.3%20(4).png)

## 4.4 Tracing DNS dengan Wireshark

### Soal Pertama

#### 1. Cari pesan permintaan DNS dan balasannya. Apakah pesan tersebut dikirimkan melalui UDP atau TCP? YA

![Hasil Percobaan](../assets/image/week4.4%20(1).png)

#### 2. Port tujuan pada permintaan dns yaitu 53. Port sumber pada pesan balasannya yaitu 58843

![Hasil Percobaan](../assets/image/week4.4%20(2.1).png)
![Hasil Percobaan](../assets/image/week4.4%20(2.2).png)

#### 3. Sesuaikan pesan permintaan DNS dari alamat IP dan alamat IP server DNS lokal

![Hasil Percobaan](../assets/image/week4.4%20(3).png)

#### 4. Pada pesan permintaan jenis atau typenya adalah AAAA. Tidak mengandung jawaban atau answer

![Hasil Percobaan](../assets/image/week4.4%20(4).png)

#### 5. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau ”answers” yang terdapat di dalamnya? Apa saja isi yang terkandung dalam setiap jawaban tersebut? Ada 2 answers

![Hasil Percobaan](../assets/image/week4.4%20(5).png)

#### 6. Perhatikan paket TCP SYN yang selanjutnya dikirimkan oleh host Anda. Apakah alamat IP pada paket tersebut sesuai dengan alamat IP yang tertera pada pesan balasan DNS? Ya

#### 7. Host tidak selalu mengirimkan dns baru untuk setiap objek di suatu web karena browser sudah menyimpan hasil resolusi dns dalam page

### Soal Kedua

#### 1. Port tujuannya yaitu 53 dan sumbernya adalah 50944

![Hasil Percobaan](../assets/image/week4.4.2%20(1).png)

#### 2. Ke alamat IP manakah pesan permintaan DNS dikirimkan? Apakah alamat IP tersebut merupakan default alamat IP server DNS lokal Anda?

![Hasil Percobaan](../assets/image/week4.4.2%20(2).png)

#### 3. Periksa pesan permintaan DNS. Apa ”jenis” atau ”type” dari pesan tersebut? Apakah pesan tersebut mengandung ”jawaban” atau ”answers”?

![Hasil Percobaan](../assets/image/week4.4.2%20(3).png)

#### 4. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau “answers” yang terdapat di dalamnya. Apa saja isi yang terkandung dalam setiap jawaban tersebut?

![Hasil Percobaan](../assets/image/week4.4.2%20(4).png)

#### 5. Sertakan hasil tangkapan layar.

![Hasil Percobaan](../assets/image/week4.4.2%20(4).png)

### Soal Ketiga

#### 1. Port tujuannya itu 53 dan sumbernya 57219

![Hasil Percobaan](../assets/image/week4.4.3%20(1).png)

#### 2. Jenis atau tipe AAAA, dan ada dua jawaban

![Hasil Percobaan](../assets/image/week4.4.3%20(3).png)

#### 3. server DNS tidak menyertakan Additional Records yang berisi daftar Name Server otoritatif untuk domain mit.edu. Namun, pesan tersebut memberikan jawaban atas query AAAA (tipe IPv6) dengan memberikan dua alamat IPv6 untuk mit.edu, yaitu:

- 02:26f0:9100:1591::255e
- 02:26f0:9100:159d::255e
![Hasil Percobaan](../assets/image/week4.4.3%20(3).png)

### Soal Keempat

#### 1. Ke alamat ip 18.0.72.3 bukan default alamat IP server DNS lokal karena defaultnya 192.168.1.5

![Hasil Percobaan](../assets/image/week4.4.4%20(1).png)

#### 2. Berjenis atau tipe AAAA, dan ya mengandung jawaban

![Hasil Percobaan](../assets/image/week4.4.4%20(2).png)

#### 3. ada dua jawaban dan isinya sesuai di screenshot

![Hasil Percobaan](../assets/image/week4.4.4%20(3).png)

