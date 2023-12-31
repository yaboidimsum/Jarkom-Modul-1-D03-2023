# Praktikum Modul 1 Jaringan Komputer

Perkenalkan kami dari kelas ``Jaringan Komputer D Kelompok D03``, dengan anggota sebagai berikut:

| Nama                      | NRP        |
|---------------------------|------------|
|Alfan Lukeyan Rizki        | 5025211046 |
|Dimas Prihady Setyawan     | 5025211184 |

# Laporan Resmi Praktikum Modul 1 Jarkom
## Soal Nomor 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
- Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? **258040667**
- Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? **1044861039**
- Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? **1044861039**
- Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? **258040696**

**Langkah-Langkah Penyelesaian**
- Filter protokol hanyak untuk ``FTP``
- Mencari packets yang melakukan aktivitas unggah (STOR dan Opening Binary) file ``c75-GrabThePhisher.zip``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/28a00cd3-b807-4fd7-a3d8-0eb079039d1c">
- Lihat nilai ``sequence number (raw)`` dan ``acknowledge number (raw)`` melalui ``Transmission Control Protocol`` pada ``packet 147``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/ed9d1e24-af92-4241-a1e4-53e855a7754c">
- Lanjut ke ``packet 149`` untuk mengecek response dari aktivitas tersebut, cek nilai ``sequence number (raw)`` dan ``acknowledge number (raw)``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/5cf6e490-22e4-4ea8-a1cc-3cd8239294fb">

### Bukti Flag
<img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/2e7e6792-9b21-43cb-af82-78f357be55fa">

## Soal Nomor 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer! **gunicorn**

**Langkah-Langkah Penyelesaian**
- Filter protokol untuk ``http``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/27178ec5-fec3-4f9b-96d9-ab8be2008583">
- Pilih salah satu packet dan pada menu analyze pilih ``Follow`` dan lakukan ``HTTP Stream``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/89ebb57f-6498-4c31-8ab3-476aeb5ad90d">
- Server yang digunakan akan terlihat saat melakukan ``HTTP Stream``. Pada kasus ini, web server yang digunakan adalah ``gunicorn``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/f8d08e3f-fad7-4aa2-9714-4ad29e9904fa">

### Bukti Flag
<img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/182255a2-c37c-4f56-a47e-f4e605462647">


## Soal Nomor 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702? **21**
- Protokol layer transport apa yang digunakan? **UDP**

**Langkah-Langkah Penyelesaian**
- Filter IP ``239.255.255.250`` dan port ``3702`` dengan ``ip.addr == 239.255.255.250 && udp.port == 3702``. (Alternatif lain disini, packet bisa dihitung manual)
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/79edb6f1-f14b-43a0-896a-9b9904d8ccbb">
- Setelah difilter, pilih menu ``Statistics`` dan pilih ``Endpoints``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/0df1564b-a3ae-4341-ab3f-36bc66408846">
- Pilih UDP dan total packet dari IP ``239.255.255.250``dan port ``3702`` akan terlihat. Total packet berjumlah 21
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/8c332c2b-2f4f-4651-a4bd-1895643bcc2d">
- Untuk protokol UDP bisa dilihat diendpoints atau melalui Internet Protocol Version 4 dari salah satu packet
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/e8cc4ea2-1430-48ca-8b8b-3a66b7dab3e2">

### Bukti Flag
<img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/69fb0994-f850-4a5a-8b3d-f3ff679b9f77">

## Soal Nomor 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130? **0x18e5**

**Langkah-Langkah Penyelesaian**
- Scroll ke ``packet 130`` lalu lihat detail dari paket tersebut
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/6e59c5b2-2db4-44b1-b1ea-e5e6fa88d5ce">
- Lihat ``User Datagram Protocol``, checksum akan terlihat dengan nilai ``0x18e5``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/85f00e2a-2458-4ace-9c62-784645385e69">

### Bukti Flag
<img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/c1a60b7f-43a7-40da-81f0-b6b96ad42772">


## Soal Nomor 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut? **60**
- Port berapakah pada server yang digunakan untuk service SMTP? **25**
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP? **74.53.140.153**

**Langkah-Langkah**
- File Zip mengandung sebuah txt file yaitu ``connect.txt`` dan memerlukan sebuah password, yang berarti password berada di suatu tempat di dalam file ``soal5.pcap``.
- Cara yang dilakukan adalah melakukan ``analyze`` dan follow ``TCP Stream``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/a4d8be2b-2a4c-44a9-a25c-84543d4ee12d">
- Setelah diselidiki, ternyata password telah ditemukan yaitu ``NWltcGxlUGFzNXdvcmQ=`` namun harus didecode dari format Base64
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/76c133dd-28a1-4d95-9916-e03a5b724071">
- Berikut adalah hasil dari decode Base64 format yaitu ``5implePas5word``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/b5143819-9805-4906-9a01-601288d7a647">
- Password dapat digunakan untuk membuka ``connect.txt``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/1f2edaa5-0c25-4a8d-8f1d-9bd146cbb341">
- Untuk menjawab pertanyaan berapa packet yang dicapture, kita dapat menghitung jumlah semua packet di ``soal5.cap`` ada berapa. Totalnya ada 60
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/84f84696-c399-4178-88e8-84b038fb8408">
- Untuk menjawab pertanyaan port berapa yang digunakan untuk service SMTP, salah satu file dapat dipilih lalu dilihat detail ``Transmission Control Protocol`` pada bagian ``source port``
  <img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/a862fff6-fcec-43d1-bb32-35b9c8c3fc7a">
- Untuk menjawab IP mana yang terbilang public, dapat dilihat dari IP itu sendiri yaitu selain ``10.10.1.4`` dan ``192.168.1.1``. Private IP address biasanya mulai dengan 192, 172, atau 10. Jadi jawabannya adalah ``74.53.140.153``

### Bukti Flag
<img width="1280" alt="image" src="https://github.com/yaboidimsum/Jarkom-Modul-1-D03-2023/assets/101172637/2e68a59a-f786-4cbd-ad85-16f5cfca9024">



## Soal Nomor 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan __"server SOURCE ADDRESS 7812 is invalid"__. ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
### Pembahasan 
Diberikan beberapa hint yang dapat membantu untuk menyelesaikan soal tersebut. Berikut adalah hint yang diberikan:
 - Clue 1 : Sepertinya ada yang salah dengan penulisan tersebut secara KBBI. Ada sesuatu yang Besar di depan mata.
 - Clue 2 : Jenis cipher merupakan substitusi a1z26 Cipher
 - Clue 3 : Rentang Huruf yang digunakan Huruf A-R, 1-18 dengan Jawaban 6 Huruf.
 - Clue 4 : SOURCE ADDRESS ADALAH KUNCI SEMUANYA.

Berdasarkan hint tersebut, maka dapat disimpulkan bahwa soal tersebut merupakan soal yang menggunakan metode `a1z26 Cipher`. Untuk menyelesaikan soal tersebut, maka dapat menggunakan `wireshark` untuk mencari source address yang dimaksud. Berikut adalah langkah-langkah yang dilakukan untuk menyelesaikan soal tersebut:
1. Pertama, buka wireshark dan langsung menuju ke packet nomor `7812``.
2. Kemudian, simpan source address packet tersebut yang dapat dilihat pada bagian `Internet Protocol Version 4`.
3. Setelah itu, buka [website](https://cryptii.com/pipes/caesar-cipher) untuk melakukan decrypt.
4. Namun, terdapat ketentuan bahwa rentan huruf yang digunakan adalah `A-R` dan `1-18`. Sehingga source address yang telah disimpan perlu di lakukan modifikasi. Source address semula nya adalah `104.18.14.101`, sehingga perlu diubah menjadi `10, 4, 18, 14, 10, 1`. 
5. Setelah itu, masukkan hasil modifikasi tersebut ke dalam website dan decrypt menggunakan metode `a1z26 Cipher`.
6. Maka akan didapatkan hasil berupa `JDRNJA`. 

### Screenshot
![wireshark-soal6](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-6/Screenshot%202023-09-22%20at%2015.37.54.png?raw=true)
![chiper-decode](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-6/Screenshot%202023-09-22%20at%2015.53.00.png?raw=true)
![terminal-soa6](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-6/Screenshot%202023-09-22%20at%2015.54.08.png?raw=true)
### Kendala
Adapun kedala yang dialami selama pengerjaan soal ini adalah deskripsi soal yang masih kurang jelas, sehingga teka teki tersebut sulit diselesaikan

## Soal Nomor 7
Berapa jumlah packet yang menuju IP 184.87.193.88?
### Pembahasan 
Soal tersebut merupakan jenis soal query filter yang dapat di selesaikan hanya dengan menambahkan filter expression berupa `ip.src == 184.87.193.88` pada wireshark. Filter Expression tersebut berarti kita mengambil seluruh packet yang menuju ip source `184.87.193.88`. Pada kasus ini, packet hanya berjumlah `6`.
### Screenshot
![wireshark-soal7](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-7/Screenshot%202023-09-22%20at%2016.07.27.png?raw=true)
![terminal-soal7](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-7/Screenshot%202023-09-22%20at%2016.11.08.png?raw=true)

## Soal Nomor 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
### Pembahasan 
Untuk mejawab soal tersebut, kita hanya cukup memahami logika kueri sederhana. Kueri tersebut adalah `tcp.dstport == 80 || udp.dstport == 80`. Kueri tersebut berarti kita mengambil seluruh packet yang menuju port 80 baik itu menggunakan protokol tcp maupun udp. Pengurutan berdasarkan abjad sudah dilakukan secara otomatis oleh wireshark.

### Screenshot
![terminal-soal8](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-8/Screenshot%202023-09-22%20at%2016.21.17.png?raw=true)
## Soal Nomor 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
### Pembahasan 
Seperti pada soal sebelumnya, soal tersebut merupakan jenis soal query filter yang dapat di selesaikan hanya dengan menambahkan filter expression berupa `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34` pada wireshark. Filter Expression tersebut berarti kita mengambil seluruh packet yang berasal dari ip source `10.51.40.1` namun tidak menuju ke ip destination `10.39.55.34`.
### Screenshot
![terminal-soal9](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-9/Screenshot%202023-09-22%20at%2016.23.01.png?raw=true)

## Soal Nomor 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
### Pembahasan 
Untuk menjawab soal tersebut, kita hanya perlu mencari packet yang menggunakan protokol telnet. Setelah itu, kita dapat melihat isi dari packet tersebut. Pada kasus ini, kita dapat melihat bahwa terdapat kredensial yang digunakan untuk login. 
Berikut adalah langkah-langkah yang dilakukan untuk menyelesaikan soal tersebut:
1. Pertama, buka wireshark dan lakukan filter expression `telnet contains "Login"`.
2. Kemudian, tandai packet yang berisikan data Login tersebut.
3. Setelah itu, kembali lakukan filter expression `telnet`. 
4. Kemudian menuju packet yang telah ditandai sebelumnya.
5. Lakukan pembacaan isi dari packet packet yang berada di bawahnya. Maka di temukan pola kredensial yang digunakan untuk login. Pola tersebut adalah `d`, `h`, `a`, `f`, `i`, `n` untuk username dan `kesayangannyak0k0` untuk password.
6. Sehingga jika di gabung sebagai format jawaban nya `[username]:[password]` adalah `dhafin:kesayangannyak0k0`.

### Screenshot
![wireshark-soal10-1](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.40.52.png?raw=true)
![wireshark-soal10-2](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.42.59.png?raw=true)
![wireshark-soal10-3](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.43.40.png?raw=true)
![wireshark-soal10-4](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.43.55.png?raw=true)
![wireshark-soal10-5](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.44.06.png?raw=true)
![wireshark-soal10-6](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.44.18.png?raw=true)
![wireshark-soal10-7](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.44.25.png?raw=true)
![wireshark-soal10-8](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.44.47.png?raw=true)
![wireshark-soal10-9](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.44.52.png?raw=true)
![terminal-soal10](https://github.com/AlfanLukeyan/trash/blob/main/Jarkom-Modul-1-D03-2023/soal-10/Screenshot%202023-09-22%20at%2016.46.08.png?raw=true)

## Kendala
Kendala ditemukan saat akses dan pengunduhan dari portal partikum Jarkom. Kami membutuhkan waktu lama untuk mengakses situs praktikum dan melakukan penguduhan file soal pcapng bisa sampai 20 menit.
