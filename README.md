# Praktikum Modul 1 Jaringan Komputer

## Anggota Kelompok A08

| No.  | Nama Anggota       | NRP          |
|------|--------------------|--------------|
| 1    |Mohammad Zhafran Dzaky           | 5025211142   |
| 2    | Katarina Inezita Prambudi         | 5025211148   |

## Penjelasan Soal
### Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?

b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

## Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

## Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

b. Protokol layer transport apa yang digunakan?

### Penjelasan 
a. Mencari IP address yang menggunakan port `3702` menggunakan filter expression seperti berikut :

`ip.addr == 239.255.255.250 and udp.port == 3702`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/49747ced-e7aa-49b0-b4e4-97fab82b84c7)

Berdasarkan gambar diatas, dapat dilakukan perhitungan secara manual dan didapatkan jumlah dari paket yang tercapture sebanyak 21.

b. Dari gambar diatas juga dapat dilihat bahwa protokol port yang digunakan adalah protocol `udp`.

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/d504c4a5-6c71-45d1-a0e1-79f6e428b27c)
![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/aee3fc34-fbc3-4e45-8f8a-a78fb8aed068)

## Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

## Soal 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

b. Port berapakah pada server yang digunakan untuk service SMTP?

c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

## Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?

### Penjelasan
Untuk dapat mencari jumlah packet bisa menggunakan filter expression berikut 

`ip.dst == 184.87.193.88`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/15a4c150-a012-4265-9d05-b34e3961e6af)

Dari gambar diatas, didapatkan jumlah packet sebanyak 6.

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/491035a8-47b0-41b4-b341-17510a923491)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/dac3faeb-9035-4b15-947e-bdc3fa9b59f8)

## Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

### Penjelasan
Untuk mengambil semua protokol paket yang menuju port 80, dapat menggunakan filter expression sebagai berikut :

`tcp.dstport == 80 || udp.dstport == 80`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/2ab3ea6c-f64f-4bf8-9ae0-1676b4cff545)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/67a2ccf8-de09-46df-beed-3c2f45b3ed99)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/75f69241-dd27-4b9a-9c44-567ef5809cae)

## Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

### Penjelasan
Untuk melakukan filter seperti perintah diatas, maka bisa menggunakan kueri sebagai berikut :

`ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/b7f039a3-8e7d-4b5e-a35b-b67e381c4315)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/5e5b86b2-0597-4398-badb-f1425aeeba2b)

## Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet


