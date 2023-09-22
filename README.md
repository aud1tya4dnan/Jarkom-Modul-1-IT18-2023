# Jarkom-Modul-1-IT18-2023

    1. Keisya Nabila Zahra    (5027211058)
    2. Auditya Maulana Adnan  (5027211068)

## Soal 1

1. User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
    1. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?
    2. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?
    3. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
    4. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
    
    ![Untitled](https://i.ibb.co/YhKsLMY/Untitled.png)
    
    ---
    
    untuk menjawab pertanyaan berikut kita dapat menginstall file soal1.pcap dan membukanya di wireshark. kemudian, seperti pada clue, kita diharuskan mencari aktivitas yang menggunakan protokol FTP dengan clue menggugah suatu file. untuk mencarinya kami menggunakan filter dan memasukkan  query `ftp || ftp-data` . Kemudian pada wireshark akan mengeluarkan berbagai packet yang menggunakan protokol ftp seperti berikut. 
    
    ![Untitled](https://i.ibb.co/wywjVkk/Untitled-1.png)
    
    Selanjutnya, sesuai clue, kami mencari packet yang memiliki perintah mengirim file. Disini kami temukan sebagai berikut 
    
    ![Untitled](https://i.ibb.co/GPKVSkp/Untitled-2.png)
    
    disini kami temukan packet dengan perintah “STOR”. Perintah ini dalam FTP digunakan untuk mengirim file dari klien ke server FTP. Oleh karena itu, kami dapatkan sequence number (raw) yaitu jawaban A. Dan selanjutnya juga di temukan acknowledgement number (raw) untuk jawaban B seperti diatas. 
    
    pertanyaan selanjutnya merupakan  sequence number (raw) dan acknowledgement number (raw) pada packet yang menunjukan response (soal c dan d ). untuk menjawab ini dapat dilihat responsenya terdapat pada number 149. dan di dapatkan jawaban seperti berikut. 
    
    ![Untitled](https://i.ibb.co/MRJ8xtG/Untitled-3.png)
    
    dengan jawaban ini kami dapat menjawab pertanyaan C dan D sebagai berikut 
    
    ![Untitled](https://i.ibb.co/NtfPmMQ/Untitled-4.png)
    
    dan didapatkan flag seperti berikut 
    
    **`FLAG : Jarkom2023{y0u_r_g00d_4t_4dr3ssing_LrJyItF51973147}`**
    
    ---
    
    ## Soal 2
    
    Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
    
    ![Untitled](https://i.ibb.co/nfRZCrT/Untitled-5.png)
    
    ---
    
    untuk menjawab soal berikut kami menggunakan command `curl -I <address server>` 
    
    Command ini digunakan untuk mengirim permintaan HTTP HEAD ke suatu URL menggunakan utilitas command-line "curl". Permintaan HTTP HEAD digunakan untuk mengambil informasi header HTTP dari suatu sumber, tetapi tidak mengunduh isi kontennya. Berikut untuk contoh penggunaan kami :
    
    ![Untitled](https://i.ibb.co/TDQyNmQ/Untitled-6.png)
    
    Lalu di dapatkan jawaban berupa gunicorn. dan selanjutnya kami akses netcat dan menjawab gunicorn dan mendapatkan flag berupa berikut :
    
    **`FLAG: Jarkom2023{9unic0rn_1s_JeSx9i242EkY3n9_c00l}`**
    
    ---
    
    ## Soal 3
    
    1. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
        1. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
        2. Protokol layer transport apa yang digunakan?
        
        ![Untitled](https://i.ibb.co/VmwGSfG/Untitled-7.png)
        
        ---
        
        untuk menjawab soal ini, dimulai dari yang A kami mendownload file soal3.pcap dan menggunakan filter dengan query **`ip.addr == 239.255.255.250 and udp.port == 3702`** untuk mendapatkan jumlah paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702. **`ip.addr == 239.255.255.250`** digunakan untuk memilih paket-paket yang memiliki alamat IP sumber atau tujuan yang sama dengan  239.255.255.250. sedangkan **`udp.port == 3702`** digunakan untuk memilih paket-paket yang memiliki port UDP sumber atau tujuan yang sama dengan 3702. Berikut untuk hasil filternya 
        
        ![Untitled](https://i.ibb.co/sskR6Tc/Untitled-8.png)
        
        didapatkan sebanyak 21 packet. 
        
        ![Untitled](https://i.ibb.co/2tBSsBq/Untitled-9.png)
        
        pertanyaan selanjutnya, ditanyakan protokol layer transport apa yang digunakan. seperti yang kita bisa liat di gambar sebelumnya protokol yang digunakan adalah ******UDP******. Oleh karena itu, jawabannya adalah UDP. Dan terakhir, didapatkan flag seperti berikut 
        **`FLAG:**  **Jarkom2023{4nalyz3_is_2618_piCjCvPlOuE_gr3at}**`
        
        ---
        
        ## Soal 4
        
        Berapa nilai checksum yang didapat dari header pada paket nomor 130?
        
        ![Untitled](https://i.ibb.co/K9jT6Fz/Untitled-10.png)
        
        ---
        
        untuk menjawab soal berikut, kami mencari packet header nomor 130 seperti berikut. 
        
        ![Untitled](https://i.ibb.co/jvMWvHx/foto.jpg)
       
    
        Selanjutnya, untuk mencari checksumnya dapat membuka user datagram protocol dan di dapatkan checksum berupa `0x18e5` seperti gambar diatas.
       
        ![Untitled](https://i.ibb.co/4pftpbs/Untitled-12.png)
        
        lalu kami akses netcat seperti diatas, menginput jawaban dan di dapatkan flag seperti berikut : 
        
        **`FLAG : Jarkom2023{ch3cksum_is_u5eful_0x4g0h}`**
        
        ---
        
        ## Soal 7
        
        Berapa jumlah packet yang menuju IP 184.87.193.88?
        
        ![Untitled](https://i.ibb.co/z7jRdrw/Untitled-13.png)
        
        ---
        
        untuk menjawab pertanyaan ini kami memfilter packet dengan menggunakan query **`ip.dst == 184.87.193.88`** untuk mendapat jumlah paket yang menuju IP berikut. dengan begitu didapatkan hasil filter di wireshark sebanyak 6 packet.
        
        ![Untitled](https://i.ibb.co/3rRKJJG/Untitled-14.png)
        
        Kemudian mengakses netcat yang telah diberikan disoal dimana pada netcat tersebut terdapat soal yang bisa kami jawab
        
        ![Untitled](https://i.ibb.co/Ns6VKFt/Untitled-15.png)
        
        dan di dapatkan flag sebagai berikut :
        
        **`Flag : Jarkom2023{LEtYx5VF4H0rK779nX_4n0th3r_f1lt3ring}`**
       
        ---
       
### Soal 7
Diberikan soal sebagai berikut

![image22](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/f950c5d9-3406-4f1f-bfea-248b1092ea96)

Pada soal berikut diberikan sebuah pcap file kemudian 





### Soal 5
Diberikan soal sebagai berikut

![image25](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/c2ca5b80-0c4f-45a7-9548-a2d01e7a7a0f)

Dimana Elshe menemukan sebuah packet yang menarik, pada soal juga disediakan pcap file nya
kali ini dalam soalnya pada point B mengatakan protocol SMTP sehingga kami mulai dengan filter pada wireshark "smtp" dimana didapatkan beberapa packet dengan protocol SMTP

![image](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/096c93fa-f7f3-4ff6-9f37-04310ac17623)

Langkah selanjutnya yaitu memfollow up tcp stream

![image](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/ea9bdedd-1620-4f3f-a6b2-cb4239f8b327)

Dimana pada gambar tersebut terdapat kata-kata
```
I send u a p45sword of a zip file, but you should decode it in Base64.

Here is the p45sword:

NWltcGxlUGFzNXdvcmQ=
```
sehingga kami melakukan decode Base64 menggunakan website

![image27](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/8f6d6639-5720-408a-8788-6e7ff8cd5d3d)

didapatkan password untuk file zippppfileee.zip, di dalam file zip tersebut terdapat file txt dengan nama "connect.txt", jika ingin membukanya harus memasukkan password yang dimana kita sudah mempunyai password itu.
kemudian notepad dibuka dan berisi 

![image20](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/138ce6b1-f262-40fb-9f79-95bd2be375ec)

kemudian di connect kan ke netcat tersebut dan menjawab soal yang diberikan

![image17](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/b86360bd-63b9-4168-b44a-aa6e401aa250)

dan didapatkan flag 
FLAG = Jarkom2023{k0w4lski_3429_liOyjRuEEFB_4nalys1s}

### Soal 8
Diberikan soal seperti berikut

![image11](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/178f4d98-8112-427f-8ffc-eee313d2bc6c)

Pada soal tersebut kita di tuntut untuk memahami bagaimana query wireshark untuk mencari semua protocol packet yang menuju packet 80, dimana rata2 yang dapat menuju port 80 adalah protocol tcp dan udp sehingga query yang dapat diberikan adalah tcp.dstport == 80 || udp.dstport == 80 , dimana dst merupakan destination sehingga hanya memfilter packet yang dikirim kan ke destinasi port 80 saja.

Kemudian membuka netcut yang diberikan dan menjawab soal

![image6](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/8bec1778-b53e-439d-a80a-f9d5cf780782)

Dimana didapatkan flag seperti berikut
FLAG = Jarkom2023{qu3ryyyyying_018623_DmCkBjPkPkS_15_fun}

### Soal 9
Diberikan soal seperti berikut

![image18](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/0eec9cf0-be47-49cc-949a-e3409010e51a)

Sama seperti nomer 8 yaitu dapat menjawab menggunakan query filter wireshark dengan benar. pada soal ini terdapat 2 ip yang berbeda yang harus di filter yaitu 10.51.40.1
dan 10.39.55.34
sehingga filternya adalah ip.src == 10.51.40.1 && ip.dst != 10.39.55.34

Kemudian mengisi netcat yang diberikan 


![image9](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/c576b3c8-9433-4d17-82d9-a08ff5bd2e80)

Disini diberikan flag nya sebagai berikut
FLAG = Jarkom2023{y3s_its_RlPlRmQlSgR_qu3ry1ng}

### Soal 10
Diberikan soal seperti berikut

![image2](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/2fab17e6-c9fc-4c56-be44-8e3972765f68)

Pada soal terdapat protocol yang diberikan merupakan protocol TELNET, pada file yang diberikan hal pertama adalah query filter dengan kata kunci telnet sehingga didapatkan packet seperti berikut

![image](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/0466a207-7761-4bba-95da-a281c8533f8b)

kemudian ketika scrolling ke bawah terlihat beberapa packet yang menarik karena berisi seperti username:password sehingga saya mencoba2 pada netcut yang di berikan kemudian ditemukan username:password nya 
yang berada di packet ke 81

![image](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/7d26926a-2292-47e2-a802-c33342378de3)

cara lain yaitu dengan memfolow tcp stream nya, dan username:password nya terdapat pada tcp.stream ke 2

![follow tcp stream eq2](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/2c27c207-31ea-4c73-bb54-3482a5da105b)

kemudian menjawab soal pada netcat yang diberikan 

![image8](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/96ea2720-6faa-4928-acb4-d1474dc54a1c)

Didapatkan flag seperti berikut
FLAG = Jarkom2023{t3lnet_is_C3z2yC4уC0C0C9xyB_NotSecu2e}
