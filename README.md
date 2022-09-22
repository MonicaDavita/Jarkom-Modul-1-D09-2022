# Jarkom-Modul-1-D09-2022
Pembahasan soal praktikum Modul 1 Jaringan Komputer 2022

**Anggota Kelompok**:

- Monica Narda Davita - 5025201009
- Alya Shofarizqi Inayah - 5025201113
- Meisya Salsabila Indrijo Putri - 5025201114
---
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


## Kendala
1. Kebingungan di nomor 6. Awalnya hanya menemukan 1 package tapi setelah ditelusuri ternyata ditemukan packages yang menuju lama lipi.go.id
2. Kebingungan di nomor 7, jenis capture apa yang harus dipilih. Setelah melakukan beberapa percobaan akhirnya solved
