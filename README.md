# Praktikum Modul 1 Jaringan Komputer

## Anggota Kelompok A08

| No.  | Nama Anggota       | NRP          |
|------|--------------------|--------------|
| 1    |Mohammad Zhafran Dzaky           | 5025211142   |
| 2    | Katarina Inezita Prambudi         | 5025211148   |

## Penjelasan Soal
### Soal 1
>User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

Dari statement pertama pada soal nomor 1 ini, dapat diketahui bahwa:
- Filter expression yang akan digunakan adalah `ftp` 
- Cari kata kunci yang berkaitan dengan aktivitas mengunggah suatu file, yakni `STOR`, pada list paket yang telah difilter

>a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?

Untuk menjawab poin ini, kita dapat mencari sequence number (raw) dengan:
- Klik paket yang dicari, yakni request dengan perintah STOR
- Lihat detail paket yang ditampilkan pada bagian bawah interface wireshark
- Expand bagian *Transmission Control Protocol* dan cari sequence number (raw) nya.

>b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

Untuk menjawab poin ini, kita dapat gunakan cara yang sama dengan sebelumnya namun yang kita cari pada bagian *Transmission Control Protocol* adalah acknowledgment number (raw)

<img width="1274" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/cd9eb280-7143-4d40-bef8-d18ecfbcf33a">

>c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Untuk menjawab poin ini, kita perlu menemukan response dari request aktivitas STOR yang sebelumnya, yakni pada paket nomor 149. Kemudian cari sequence number (raw) nya dengan cara yang sama dengan poin A

>d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Untuk menjawab poin ini, kita dapat gunakan cara yang sama dengan poin B namun untuk paket yang sama dengan poin C

<img width="1274" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/e85a6656-d882-451e-abef-e7b6929abc0c">

![image](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/784912b3-0c0c-4931-bb13-efe136be129d)

## Soal 2
>Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

Dari pernyataan di atas, dapat diketahui bahwa:
- Karena web server, maka filter expression yang dapat kita gunakan adalah filter `http`
- Lalu pilih salah satu paket dengan protocol TCP atau HTTP yang telah difilter agar nantinya dapat difollow
- Klik kanan pada paket dan pilih follow TCP Stream

Di layar akan muncul informasi berupa header yang salah satunya menunjukkan server yang digunakan. Berikut ini adalah detail dari informasi yang didapat:

![image](https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/7a5d10b7-808b-491c-bfff-5bcb9d0d2401)
<img width="846" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/4d1c3efe-e825-4437-86b7-e97b1791550e">
![image](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/f38802f1-599e-460d-998d-86235da7739c)

## Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

b. Protokol layer transport apa yang digunakan?

### Penjelasan 
a. Mencari IP address yang menggunakan port `3702` menggunakan filter expression seperti berikut:

`ip.addr == 239.255.255.250 and udp.port == 3702`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/49747ced-e7aa-49b0-b4e4-97fab82b84c7)

Berdasarkan gambar diatas, dapat dilakukan perhitungan secara manual dan didapatkan jumlah dari paket yang tercapture sebanyak 21.

b. Dari gambar diatas juga dapat dilihat bahwa protokol port yang digunakan adalah protocol `udp`.

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/d504c4a5-6c71-45d1-a0e1-79f6e428b27c)
![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/aee3fc34-fbc3-4e45-8f8a-a78fb8aed068)

## Soal 4
>Berapa nilai checksum yang didapat dari header pada paket nomor 130?

Untuk menjawab soal ini, kita dapat melakukan langkah - langkah berikut ini:
- Cari packet nomor 130 di file pcapng yang disediakan
- Klik paket tersebut dan lihat detail informasinya pada bagian bawah interface wireshark
- Expand bagian *User Datagram Protocol* dan cari checksum yang direpresentasikan dalam format hexadesimal seperti berikut:

<img width="1271" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/346f34bb-f8e2-4e85-857e-243984f97094">

![image](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/3f7221c6-4bf5-4955-ac3b-bdce46fc2eee)

## Soal 5
>Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
>
>a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

Sebelum bisa menjawab poin A, kita perlu mendapatkan terlebih dahulu instance netcat untuk soal ini.
- Melihat konteks soal yang telah menyebutkan smtp, maka filter terlebih dahulu paketnya menggunakan filter expression `smtp`
- Pilih salah satu paket dan follow menggunakan TCP Stream dan dapat dilihat bahwa terdapat clue untuk password yang masih terenkripsi menggunakan base64
- decode password tersebut menggunakan online base64 decoder dan dihasilkan password baru, yakni `5implePas5word`

<img width="1273" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/ca125b1c-e9da-4075-bc3a-1ad9083be78b">

<img width="822" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/514ec99d-c50b-451d-bd70-e113d9645832">

<img width="738" alt="image" src="https://github.com/vronnn/Modul2_Probstat_5025211142/assets/105977864/554b9c75-63f7-4e03-a7ae-8ba78edec3d9">

- buka file zip dengan password yang telah diperoleh untuk mendapatkan instance netcat soal ini

![image](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/f84e93fe-c9d1-43c7-90c2-b7eea6893704)

- Setelah itu baru kita dapat menjawab poin A dengan menghitung paket yang ada pada pcapng secara manual atau dengan melihat nomor paket urutan terakhir atau dengan nomor terbesar, yakni 60.


>b. Port berapakah pada server yang digunakan untuk service SMTP?

Untuk menjawab poin ini, kita dapat melihat modul 1 Jaringan Komputer bahwa SMTP menggunakan port 25 

>c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

Untuk menjawab poin ini, kita hanya perlu memilih antara 3 ip yang ada setelah filter smtp dijalankan di poin sebelumnya, yakni 192.168.1.1, 10.10.1.4, dan 74.53.140.153. Karena ip berawalan 192.xxx itu merupakan ip private dan 10.xxx merupakan ip private vpn its, maka yang tersisa adalah 74.53.140.153 sebagai ip publik

![image](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/b82f7515-544a-4279-b745-8ca3298eb7ef)


## Soal 6
>Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "**server SOURCE ADDRESS 7812 is invalid**". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

Langkah - langkah yang dapat dilakukan adalah:
- Lihat clue pertama berupa huruf besar yang tersebar di deskripsi soal. Clue tersebut membentuk kata 'SUBTITUSI' jika disambung
- Lihat clue kedua yakni kode cipher yang digunakan, dimana a = 1, e = 5, u = 21, dst. Dapat disimpulkan bahwa nanti z = 26 dan akan berulang.
- Lihat clue yang dicetak huruf tebal, yakni **"server SOURCE ADDRESS 7812 is invalid"** yang artinya kita perlu melihat ip source dari paket bernomor 7812, yakni 104.18.14.101
- decode ip source tersebut menggunakan cipher yang telah kita temukan sebelumnya dengan memecah ip tersebut menjadi maksimal 2 2 kelompok menjadi berikut ini:

| 10 | 4 | 18 | 14 | 10 | 1 |
|---|---|---|---|---|---|
| J | D | R | N | J | A |

<img width="1271" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/dae74cc0-d70d-4a43-9522-541764d9a6c1">

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
Untuk mengambil semua protokol paket yang menuju port 80, dapat menggunakan filter expression sebagai berikut:

`tcp.dstport == 80 || udp.dstport == 80`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/2ab3ea6c-f64f-4bf8-9ae0-1676b4cff545)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/67a2ccf8-de09-46df-beed-3c2f45b3ed99)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/75f69241-dd27-4b9a-9c44-567ef5809cae)

## Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

### Penjelasan
Untuk melakukan filter seperti perintah diatas, maka bisa menggunakan kueri sebagai berikut:

`ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/b7f039a3-8e7d-4b5e-a35b-b67e381c4315)

![App Screenshot](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/109232320/5e5b86b2-0597-4398-badb-f1425aeeba2b)

## Soal 10
>Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

Untuk menjawab soal ini, kita dapat melakukan hal - hal berikut: 
- filter paket menggunakan filter expression `telnet`
- Cari data dengan format yang sama dengan contoh format login kredensial yang diberikan

Ditemukanlah data yang benar sebagai berikut:

<img width="1264" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/61839c08-004b-4272-b4df-3742876907f7">

![image](https://github.com/katarinainezita/Jarkom-Modul-1-A08-2023/assets/105977864/fe56114f-df52-4285-a2ef-0277e8d462f7)


## Kendala Selama Pengerjaan
- Mungkin masih belum terbiasa menggunakan wireshark, sehingga terkadang masih perlu membuka modul dan display filter unutk penggunaannya.
- Server praktikum beberapa kali down sehingga tidak bisa membuka soal atau mengirimkan jawaban.