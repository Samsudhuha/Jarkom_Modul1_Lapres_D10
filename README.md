# Jarkom_Modul1_Lapres_D10

### RYU & Samsu
### Kelompok D10

## Soal
1. Sebutkan webserver yang digunakan pada "​testing.mekanis.me​"!
2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
3. Cari username dan password ketika login di "​ppid.dpr.go.id​"!
4. Temukan paket dari ​web-web ​yang menggunakan ​basic authentication ​method!
5. Ikuti perintah di​ ​aku.pengen.pw​! Username dan password bisa didapatkan dari file .​pcapng!​
6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf".
8. ​Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
9. ​Cari username dan password ketika login FTP pada localhost!
10.​ ​Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"
11. ​Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
12. ​Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
13. ​Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
14. ​Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!

## Jawab
1.
``` 
http.host == testing.mekanis.me -> klik kanan -> follow -> http stream 
```
<center>
  
![img](/img/1.png)

</center>

<br>

2. 
``` 
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"! frame contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg" -> klik kanan -> follow -> tcp stream -> ubah jadi raw -> save as [nama].jpg
[ketika saya pake filter dan download, malah gabisa kebuka]
[ketika saya download manual dengan file -> export object -> http -> cari namanya lalu download]
```
<center>
  
![img](/img/2.png)

</center>

<br>

3. 
```
http.host contains "ppid.dpr.go.id" && http.request.method == POST
```
<center>
  
![img](/img/3.png)

</center>
<center>
  
![img](/img/3.1.png)

</center>

<br>

4. 
```
http.authbasic
```
<center>
  
![img](/img/4.png)

</center>

<br>

5. 
```
http.authbasic && http.host contains "aku.pengen.pw"
```
<center>
  
![img](/img/5.png)

</center>
<center>
  
![img](/img/5.1.png)

</center>
<center>
  
![img](/img/5.2.png)

</center>

<br>

6. 
```
pada display filter ketik ftp-data, lalu pada info cari yang (STOR Answer.zip) 
lalu klik kanan klik follow TCP stream, pada show and save data as ganti ke RAW lalu save as ke folder dengan nama answer.zip, 
kembali lagi ke display filter ketik ftp-data, lalu pada info yang (STOR zipkey.txt) lalu buka file zip dan masukkan password yang kita dapat dari file zipkey.txt
```
<center>
  
![img](/img/6.png)

</center>

<br>

7. 
```
frame contains “Yes.pdf” -> klik kanan -> follow -> tcp stream -> ubah raw -> save as kasih nama [nama].zip
```
<center>
  
![img](/img/7.png)

</center>

<br>

```
buka file .zipnya
```
<center>
  
![img](/img/7.1.png)

</center>

<br>

8.
```
pada display filter ketik ftp.request.command == RETR
```
<center>
  
![img](/img/8.png)

</center>

<br>

9.
```
pada display filter -> ketik ftp lalu akan muncul data seperti berikut
```
<center>
  
![img](/img/9.png)

</center>

<br>

10.
```
frame contains "application/pdf" -> klik kanan -> follow -> tcp stream -> ubah raw -> save as kasih [nama].pdf
```
<center>
  
![img](/img/10.png)

</center>
<center>
  
![img](/img/10.1.png)

</center>

<br>

11.
```
klik adapter for loopback traffic capture -> pada kolom “...using this filter” ketik port 21
```
<center>
  
![img](/img/11.png)

</center>

<br>

12.
```
klik Wi-Fi -> pada kolom “...using this filter” ketik src port 80
```
<center>
  
![img](/img/12.png)

</center>

<br>

13.
```
klik Wi-Fi -> pada kolom “...using this filter” ketik dst port 443
```
<center>
  
![img](/img/13.png)

</center>

<br>

14.
```
klik Wi-Fi -> pada kolom “...using this filter” ketik src host 192.168.1.14 (ip masing”)
```
<center>
  
![img](/img/14.png)

</center>

<br>

15.
```
klik Wi-Fi -> pada kolom “...using this filter” ketik dst host monta.if.its.ac.id
```
<center>
  
![img](/img/15.png)

</center>

<br>
