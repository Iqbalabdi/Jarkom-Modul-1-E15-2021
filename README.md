# Jarkom-Modul-1-E15-2021

- M. Iqbal Abdi (05111940000151)

### No 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!

Jawab :

<pre>Display filter : http.host == ichimarumaru.tech</pre>

Screenshot :

Saat TCP Stream pada salah satu paket yang telah difilter, akan muncul nama webserver
![image](https://user-images.githubusercontent.com/75016595/134755248-3a6e2351-06ae-40f8-9d36-a1e816513b2b.png)

### No 2
Temukan paket dari web-web yang menggunakan basic authentication method!

Jawab :
<pre>http.authbasic</pre>

Screenshot : 

Dengan menggunakan expressin `.authbasic` kita bisa menemukan paket yang menggunakan basic authentication
![image](https://user-images.githubusercontent.com/75016595/134755291-d0542c2d-bd91-459f-8ae5-72b3644dac85.png)

### No 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Jawab :
<pre>http contains “basic”</pre>

Screenshot :

Untuk mendapatkan username dan password, dapat menggunakan expression `contains "basic"` untuk menemukan paket yang mengandung kata `basic`. Lalu pada paket `favicon.ico` akan muncul keterangan credentials yang berisi username dan password
![image](https://user-images.githubusercontent.com/75016595/134755364-c56d2110-badc-462a-af32-e77d7d3006cc.png)

Setelah memasukkan username dan password ke web `basic.ichimarumaru.tech!`, akan muncul halaman untuk emngisi konfigurasi pengkabelan T568A

![image](https://user-images.githubusercontent.com/75016595/134755521-0a5c0d9c-bb48-4dc5-ba29-df43d9e6c947.png)

### No 4
Temukan paket mysql yang mengandung perintah query select

Jawab :
<pre>mysql.query and frame matches "select"</pre>

Screenshot :

Dengan menggunakan expression `frame matches "select"` akan memunculkan paket-paket yang mengandung statement `select`.
![image](https://user-images.githubusercontent.com/75016595/134755814-b24ad0f9-0046-4ba8-9841-30c778443d23.png)

### No 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

Jawab :
<pre>mysql.query and frame matches "insert"</pre>

Screenshot :

Dengan menggunakan expression `frame mathces "insert` akan memunculkan paket yang mengandung statement `insert`. Papa paket tersebut akan terlihat query yang berisi username dan password yang dapat digunakan untuk login pada `portal.ichimarumaru.tech`
![image](https://user-images.githubusercontent.com/75016595/134755816-5a889c40-2cfa-49fa-8b13-9173ca9da383.png)

Setelah login, akan muncul halaman untuk mengisi konfigurasi pengkabelan T568B

![image](https://user-images.githubusercontent.com/75016595/134755767-f5094ab2-cf7d-4bbd-995b-91db97254c81.png)







