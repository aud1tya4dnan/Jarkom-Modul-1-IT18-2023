# Jarkom-Modul-1-IT18-2023

## Soal 1

1. User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
    1. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?
    2. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?
    3. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
    4. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled.png)
    
    ---
    
    untuk menjawab pertanyaan berikut kita dapat menginstall file soal1.pcap dan membukanya di wireshark. kemudian, seperti pada clue, kita diharuskan mencari aktivitas yang menggunakan protokol FTP dengan clue menggugah suatu file. untuk mencarinya kami menggunakan filter dan memasukkan  query `ftp || ftp-data` . Kemudian pada wireshark akan mengeluarkan berbagai packet yang menggunakan protokol ftp seperti berikut. 
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%201.png)
    
    Selanjutnya, sesuai clue, kami mencari packet yang memiliki perintah mengirim file. Disini kami temukan sebagai berikut 
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%202.png)
    
    disini kami temukan packet dengan perintah “STOR”. Perintah ini dalam FTP digunakan untuk mengirim file dari klien ke server FTP. Oleh karena itu, kami dapatkan sequence number (raw) yaitu jawaban A. Dan selanjutnya juga di temukan acknowledgement number (raw) untuk jawaban B seperti diatas. 
    
    pertanyaan selanjutnya merupakan  sequence number (raw) dan acknowledgement number (raw) pada packet yang menunjukan response (soal c dan d ). untuk menjawab ini dapat dilihat responsenya terdapat pada number 149. dan di dapatkan jawaban seperti berikut. 
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%203.png)
    
    dengan jawaban ini kami dapat menjawab pertanyaan C dan D sebagai berikut 
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%204.png)
    
    dan didapatkan flag seperti berikut 
    
    **`FLAG : Jarkom2023{y0u_r_g00d_4t_4dr3ssing_LrJyItF51973147}`**
    
    ---
  ## Soal 2
    
    Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%205.png)
    
    ---
    
    untuk menjawab soal berikut kami menggunakan command `curl -I <address server>` 
    
    Command ini digunakan untuk mengirim permintaan HTTP HEAD ke suatu URL menggunakan utilitas command-line "curl". Permintaan HTTP HEAD digunakan untuk mengambil informasi header HTTP dari suatu sumber, tetapi tidak mengunduh isi kontennya. Berikut untuk contoh penggunaan kami :
    
    ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%206.png)
    
    Lalu di dapatkan jawaban berupa gunicorn. dan selanjutnya kami akses netcat dan menjawab gunicorn dan mendapatkan flag berupa berikut :
    
    **`FLAG: Jarkom2023{9unic0rn_1s_JeSx9i242EkY3n9_c00l}`**
    
    ---
    
   ## Soal 3
    
    1. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
        1. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
        2. Protokol layer transport apa yang digunakan?
        
        ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%207.png)
        
        ---
        
        untuk menjawab soal ini, dimulai dari yang A kami mendownload file soal3.pcap dan menggunakan filter dengan query **`ip.addr == 239.255.255.250 and udp.port == 3702`** untuk mendapatkan jumlah paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702. **`ip.addr == 239.255.255.250`** digunakan untuk memilih paket-paket yang memiliki alamat IP sumber atau tujuan yang sama dengan  239.255.255.250. sedangkan **`udp.port == 3702`** digunakan untuk memilih paket-paket yang memiliki port UDP sumber atau tujuan yang sama dengan 3702. Berikut untuk hasil filternya 
        
        ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%208.png)
        
        didapatkan sebanyak 21 packet. 
        
        ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%209.png)
        
        pertanyaan selanjutnya, ditanyakan protokol layer transport apa yang digunakan. seperti yang kita bisa liat di gambar sebelumnya protokol yang digunakan adalah ******UDP******. Oleh karena itu, jawabannya adalah UDP. Dan terakhir, didapatkan flag seperti berikut 
        **`FLAG:**  **Jarkom2023{4nalyz3_is_2618_piCjCvPlOuE_gr3at}**`
        
        ---
       
        ## Soal 4
        
        Berapa nilai checksum yang didapat dari header pada paket nomor 130?
        
        ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%2010.png)
        
        ---
        
        untuk menjawab soal berikut, kami mencari packet header nomor 130 seperti berikut. 
        
        ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%2011.png)
        
        Selanjutnya, untuk mencari checksumnya dapat membuka user datagram protocol dan di dapatkan checksum berupa `0x18e5` seperti gambar diatas. 
        
        ![Untitled](lapres%201a2a657ee5694da586344f69c458b4dc/Untitled%2012.png)
        
        lalu kami akses netcat seperti diatas, menginput jawaban dan di dapatkan flag seperti berikut : 
        
        **`FLAG : Jarkom2023{ch3cksum_is_u5eful_0x4g0h}`**
        
        ---
        
    
### Soal 7
Diberikan soal sebagai berikut

![image22](https://github.com/aud1tya4dnan/Jarkom-Modul-1-IT18-2023/assets/91017662/f950c5d9-3406-4f1f-bfea-248b1092ea96)

Pada soal berikut diberikan sebuah pcap file kemudian 





### Soal 5
