# Jarkom-Modul-1-D09-2022
Pembahasan soal praktikum Modul 1 Jaringan Komputer 2022

**Anggota Kelompok**:

- Monica Narda Davita - 5025201009
- Alya Shofarizqi Inayah - 5025201113
- Meisya Salsabila Indrijo Putri - 5025201114
---
## Soal 1
### Deskripsi Soal
Menyebutkan web server yang digunakan pada "monta.if.its.ac.id"
### Langkah-langkah
a. Membuka file soal1-2.pcapng, lalu mengeksekusi display filter dengan sintaks `tcp contains monta`
![Screenshot (251)](https://user-images.githubusercontent.com/94627623/191756086-81996dec-71fc-42af-bf69-67a660ecfe5c.png)

b. Selanjutnya `ctrl+alt+shift+T` untuk menggunakan `TCP stream`
![Screenshot (252)](https://user-images.githubusercontent.com/94627623/191756338-ada680b8-2b70-414f-82c9-053f0c206ecd.png)

## Soal 2
### Deskripsi Soal
Membantu Ishaq mencari topik TA untuk semester ini , dengan mencari detail topik pada website “monta.if.its.ac.id”, lalu melihat judul TA apa yang dibuka Ishaq
### Langkah-langkah
a. Setelah membuka soal1-2.pcapng, perlu melakukan display filter dengan sintaks `http contains “detail”` untuk mencari paket dengan protokol monta (yaitu http) yang mengandung token `“detail”` . Telah ditemukan paket dengan Info `“.../detailTopik/…”` sesuai permintaan soal.
![Screenshot (255)](https://user-images.githubusercontent.com/94627623/191756869-8401d3f2-b5f9-4100-9458-2530432ed595.png)

b. Selanjutnya `ctrl+alt+shift+H` untuk menggunakan `HTTP stream`, lalu mencari dengan kata kunci “Topik Tugas Akhir” hingga menemukan judul TA yang sesuai yaitu “Evaluasi untuk kerja User Space Filesystem” seperti pada gambar di bawah ini
![Screenshot (256)](https://user-images.githubusercontent.com/94627623/191757024-80907659-6876-4de1-8c0a-a48000b5f2bf.png)

## Soal 3
### Deskripsi Soal
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80
### Langkah-langkah
Membuka file soal3-6.pcapng, lalu menggunakan display filter `tcp.dstport == 80` (karena yang dicari menuju, sehingga menggunakan .dstport)
![Screenshot (253)](https://user-images.githubusercontent.com/94627623/191757385-665ced01-9aa0-4e6f-a794-03dc5548ab8d.png)

## Soal 4
### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!
### Langkah-langkah
Setelah membuka file soal3-6.pcapng, maka yang perlu dilakukan adalah mengeksekusi display filter dengan sintaks **tcp.srcport == 21** (karena yang dicari hanya yang berasal dari, maka yang digunakan adalah .srcport)
![Soal4](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/4.jpg?raw=true)

## Soal 5
### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!
### Langkah-langkah
Sama seperti nomor 4, namun port yang digunakan kini 443. Sintaks dalam display filter yang digunakan adalah **tcp.srcport == 443**.
![Soal5](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/5.jpg?raw=true)

## Soal 6
### Deskripsi Soal
Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !
### Langkah-langkah
a. Setelah membuka soal3-6.pcapng, maka perlu melakukan display filter dengan sintaks http contains “lipi.go.id” untuk mencari jejak website lipi.go.id dengan protokol http. Setelah ditemukan, maka dicari IP dari lipi.go.id sesuai dengan gambar di bawah.
![Soal6a](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/6.1.jpg?raw=true)
b. Telah ditemukan bahwa IP lipi.go.id adalah **203.160.128.158**, maka perlu dicek apakah IP tersebut memang menuju lipi.go,id atau tidak.
![Soal6b](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/6.2.jpg?raw=true)
c. Setelah dicek, ternyata alamat IP tersebut memang menuju laman lipi.go.id seperti gambar di bawah.
![Soal6c](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/6.3.jpg?raw=true)
d. Maka perlu dicek kembali dengan display filter **ip.dst == 203.160.128.158** untuk mencari packages yang tujuannya ke lipi.go.id.
![Soal6d](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/6.4.jpg?raw=true)

## Soal 7
### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
### Langkah-langkah
a. Untuk mencari alamat IP kita saat ini yang perlu dilakukan adalah membukan Command Prompt (cmd) lalu mengetikkan **ipconfig**. Lalu akan muncul tampilan seperti gambar di bawah ini. Alamat IP yang digunakan adalah IPv4 Address yaitu **192.168.1.57**
![Soal7a](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/7.1.jpg?raw=true)
b. Membuka wireshark dan melakukan capture filter dengan sintaks **src host 192.168.1.57** untuk mengambil packages yang berasal dari alamat IP yang sedang digunakan.
![Soal7b](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/7.2.jpg?raw=true)
c. Lalu akan muncul packages yang menunjukkan Source berupa alamat IP kita dengan Destination yang beragam.
![Soal7c](https://github.com/MonicaDavita/Asset-Jarkom/blob/main/Modul%201/7.3.jpg?raw=true)

## Soal 8
### Deskripsi Soal
Menelusuri aliran paket dalam file soal8-10.pcap dan mencari informasi mengenai percakapan kedua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum dengan menerapkan filter 
### Langkah-langkah
a. Setelah mendownload dan membuka file8-10.pcap, langkah selanjutnya adalah mencari informasi percakapan mahasiswa dengan menerapkan filter **tcp.stream eq 12**
b. Lalu, klik kanan **follow -> TCP stream** maka akan muncul informasi mengenai percakapan mahasiswa seperti dibawah ini.

## Soal 9
### Deskripsi Soal
Mencari file laporan pertukaran file yang ada di soal8-10.pcap dan diberi format [nama_kelompok.des3] dan menyimpan output file dengan format [flag.txt]
### Langkah-langkah
a. Setelah membuka file soal8-10.pcap, langkah selanjutnya adalah mencari file laporan pertukaran yang dimaksud pada soal, setelah diketahui ternyata ada pada line 61, setelah itu bisa di export packet bytes dan disimpan dengan format D08.des3
b. Kemudian, membuka terminal pada linux, dan mengetikkan **openssl des3 -d -salt -in D08.des3 -out flag.txt -k nakano** dengan memasukkan password yang sesuai pada soal. lalu, klik enter.

## Kendala
1. Kebingungan di nomor 6. Awalnya hanya menemukan 1 package tapi setelah ditelusuri ternyata ditemukan packages yang menuju lama lipi.go.id
2. Kebingungan di nomor 7, jenis capture apa yang harus dipilih. Setelah melakukan beberapa percobaan akhirnya solved
