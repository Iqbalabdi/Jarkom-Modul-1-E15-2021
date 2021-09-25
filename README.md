# Jarkom-Modul-1-E15-2021

- M. Iqbal Abdi (05111940000151)

### No 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!

Jawab :

<pre>Display filter : http.host == ichimarumaru.tech</pre>

Screenshot :  

Saat melakukan TCP Stream pada salah satu paket yang telah difilter, akan muncul nama webserver
![image](https://user-images.githubusercontent.com/75016595/134755248-3a6e2351-06ae-40f8-9d36-a1e816513b2b.png)

### No 2
Temukan paket dari web-web yang menggunakan basic authentication method!

Jawab :
<pre>http.authbasic</pre>

Screenshot :  

Dengan menggunakan expression `http.authbasic` kita bisa menemukan paket yang menggunakan basic authentication  
![image](https://user-images.githubusercontent.com/75016595/134755291-d0542c2d-bd91-459f-8ae5-72b3644dac85.png)

### No 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Jawab :
<pre>http contains “basic”</pre>

Screenshot :

Untuk mendapatkan username dan password, dapat menggunakan expression `contains "basic"` untuk menemukan paket yang mengandung statement `basic`. Lalu pada paket `favicon.ico` akan muncul keterangan credentials yang berisi username dan password  
![image](https://user-images.githubusercontent.com/75016595/134755364-c56d2110-badc-462a-af32-e77d7d3006cc.png)  
username : kuncimenujulautan  
password : tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN

Setelah memasukkan username dan password ke web `basic.ichimarumaru.tech!`, akan muncul halaman untuk mengisi konfigurasi pengkabelan T568A  
![image](https://user-images.githubusercontent.com/75016595/134755521-0a5c0d9c-bb48-4dc5-ba29-df43d9e6c947.png)

### No 4
Temukan paket mysql yang mengandung perintah query select

Jawab :
<pre>mysql.query and frame matches "select"</pre>

Screenshot :

Dengan menggunakan expression `frame matches "select"` akan memunculkan paket-paket yang mengandung statement `select`  
![image](https://user-images.githubusercontent.com/75016595/134755814-b24ad0f9-0046-4ba8-9841-30c778443d23.png)

### No 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

Jawab :
<pre>mysql.query and frame matches "insert"</pre>

Screenshot :

Dengan menggunakan expression `frame mathces "insert"` akan memunculkan paket yang mengandung statement `insert`. Pada paket tersebut akan terlihat query yang berisi username dan password yang dapat digunakan untuk login pada `portal.ichimarumaru.tech`  
![image](https://user-images.githubusercontent.com/75016595/134755816-5a889c40-2cfa-49fa-8b13-9173ca9da383.png)  
username : akakanomi  
password : pemisah4lautan

Setelah login, akan muncul halaman untuk mengisi konfigurasi pengkabelan T568B  
![image](https://user-images.githubusercontent.com/75016595/134755767-f5094ab2-cf7d-4bbd-995b-91db97254c81.png)

### No 6
Cari username dan password ketika melakukan login ke FTP Server!

Jawab :
<pre>ftp.request.command == USER || ftp.request.command == PASS</pre>

Screenshot :

![image](https://user-images.githubusercontent.com/75016595/134759992-579bc1f0-7693-4bc8-bff8-4c56300741ac.png)

username : secretuser  
password : aku.pengen.pw.aja

### No 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

Jawab :
<pre>ftp-data</pre>
Lalu setelah melakukan filter paket, ubah string `Real.pdf` menjadi hex value, dan gunakan hex value tersebut untuk mencari paketnya
<pre>“Real.pdf” hex value : 5265616c2e706466</pre>

Screenshot :

![image](https://user-images.githubusercontent.com/75016595/134760071-3e4e2d38-529f-453f-9d04-2e9e7cd04eb2.png)

Selanjutnya lakukan TCP Stream, dan ubah show data as menjadi `RAW`, lalu save as file tersebut  
![image](https://user-images.githubusercontent.com/75016595/134760122-dbcea25c-4926-414d-b8d1-87cf913483ba.png)  
![image](https://user-images.githubusercontent.com/75016595/134760123-42e8d2de-4e06-4c44-8da3-523866dc4067.png)

Saat filenya dibuka akan muncul seperti berikut  
![image](https://user-images.githubusercontent.com/75016595/134760149-e1e0c84f-44ff-420a-85fa-94b4078982f8.png)

### No 8
Cari paket yang menunjukan pengambilan file dari FTP tersebut!

Jawab :
<pre>ftp.request.command == RETR</pre>

Screenshot :
Tidak ada hasil. Tidak ada file yang diambil dari FTP server  
![image](https://user-images.githubusercontent.com/75016595/134760178-09b412c5-5eb4-4c47-b4e0-34114e7cc88b.png)

### No 9
Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

Jawab : 
<pre>ftp-data.command contains "secret.zip"</pre>

Screenshot :  
Dengan expression `contains "secret.zip` dapat menemukan semua paket dengan statement `secret.zip`
![image](https://user-images.githubusercontent.com/75016595/134760216-22d82ec5-e7ec-4808-ad6e-9680d3632cba.png)  

Lalu lakukan TCP Stream, ubah data ke `RAW`, dan save as paket tersebut  
![image](https://user-images.githubusercontent.com/75016595/134760256-470d40a8-259a-491d-ba1a-d1f66198f5a4.png)  
![image](https://user-images.githubusercontent.com/75016595/134760260-d4b39e2d-3a86-4763-89b8-789dad0b4dd7.png) 

### No 10
Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

Jawab :
<pre>ftp-data.command contains "history.txt"</pre>

Screenshot:  
![image](https://user-images.githubusercontent.com/75016595/134760304-b55eb2af-686b-49ac-a756-671d69b1566b.png)

Saat melakukan TCP Stream, akan terlihat clue untuk membuka file `bukanapapa.txt`. 
![image](https://user-images.githubusercontent.com/75016595/134760346-807fa67e-75e5-42f6-9a40-459d1161dfa1.png)

Lakukan pencarian file `bukanapapa.txt` dengan expresion berikut
<pre>ftp-data.command contains "bukanapapa.txt"</pre>  
Lakukan TCP Stream kembali, lalu akan terlihat password untuk membuka file `wanted.pdf` pada soal no. 9
![image](https://user-images.githubusercontent.com/75016595/134760354-411ee10e-dcd1-4e8b-87a2-26d1793e14dd.png)  

Gunakan password tersebut untuk membuka file `wanted.pdf`  
![image](https://user-images.githubusercontent.com/75016595/134760398-7349d190-0841-4f02-b3fa-f204d19fb039.png)  
password : d1b1langbukanapaapajugagapercaya

### No 11
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

Jawab :  
Capture Filter  
<pre>tcp src port 80 or udp src port 80</pre>

Screenshot :  
![image](https://user-images.githubusercontent.com/75016595/134760438-5270b391-8dcc-49f8-a53a-930bb700c34d.png)

### No 12
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Jawab :  
Capture Filter
<pre>tcp port 21 or udp port 21</pre>

Screenshot :  
![image](https://user-images.githubusercontent.com/75016595/134760452-928588ca-d1fc-4735-afb1-dda09425490a.png)

### No 13
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

Jawab :  
Display filter
<pre>tcp.dstport == 443 or udp.dstport == 443</pre>

Screenshot :  
![image](https://user-images.githubusercontent.com/75016595/134760618-821a45e3-598e-4619-b7bb-c0ee62dc6d1e.png)

### No 14
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

Jawab :  
Capture filter  
<pre>dst host www.kemenag.go.id</pre>

Screenshot :  
![image](https://user-images.githubusercontent.com/75016595/134760634-2b5ab6ac-72ec-4245-b0e8-77973366c3cd.png)

### No 15
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

Jawab:  
Capture Filter
<pre>src host 192.168.100.8</pre>

Screenshot :  
![image](https://user-images.githubusercontent.com/75016595/134760658-827e0b7c-5859-4ff6-9a57-ace59a73d0a0.png)









