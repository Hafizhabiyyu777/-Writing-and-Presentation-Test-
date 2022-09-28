# First Week Writing and Presentation Test

## Unix Command Line

### Shell

Merupakan sebuah program yang berfungsi menerima perintah dari user dan meneruskan untuk dieksekusi oleh sistem yang ada adapun shell berbasis teks dikenal dengan CLi selain itu shell berbasis grafis dikenal dengan GUI

### Command Line Interface

Command line interface merupakan shell yang berbasis text yang berfungsi memudahkan user dalam memberikan perintah atau command ke sistem atau perangkat computer agar melakukan suatu task atau tugas tertentu,contoh sh,bash,zsh dan cmd.exe,cara mengakses CLI dengan menggunakan terminal

### Terminal

Berfungsi untuk memasukkan,menyalin,melihat atau memanipulasi data yang ada,disinal antara user dan computer terhubung serta user dapat memberikan perintah atau task sesuai kebutuhan pada tempat inilah shell berperan

### File System Structure

Sebuah file system berfungsi untuk mengatur bagaimana data disimpan di dalam sebuah system adapun file dan director dari Windows & unix sedikit berbeda tapi keduanya sama sama berbentuk mirip tree,unix memakai satu tree sedangkan windows terdiri dari beberapa tree dan directory paling atas disebut root directory

### Command

- pwd (print working directory), untuk melihat current working directory
- dir (directory), untuk melihat directory
- cd (change directory), untuk pindah directory
- ls (list), untuk melihat isi file di dalam directory (ls -l melihat isi secara detail)
- Cat,untuk menampilkan isi sebuah file
- Nano,untuk mengedit file txt
- touch, untuk membuat file directory
- cp (copy), untuk menyalin file directory
- mv (move), untuk memindahkan file directory
- rm (remove), untuk menghapus file directory
- rm -r menghapus directory

## Git & Github dasar

### Git & Github

#### Git

Git adalah salah satu version control sistem yang berfungsi membantu developer dalam melacak suatu perubahaan yang terjadi di suatu folder ataupun file.

#### Github

Sedangkan github adalah layanan hostweb Bersama untuk pengembangan perangkat lunak yang dimiliki oleh Microsoft dan berfungsi sebagai repositori git.

### Mengapa Harus Git

Pada saat kita membuat sebuah aplikasi baik yang berbasis mobile atau website mungkin bisa kita kerjakan sendiri,tapi jika project yang dikerjakan sangatlah besar maka kita perlu berkaloborasi atau bekerja sama dengan orang lain agar project tersebut bisa cepat diselesaikan sesuai target waktu yang ditentukan oleh karena itu mengapa programmer membutuhkan git &github untuk berkaloborasi dengan programmer lainnya tanpa harus repot atau kesusahan copy paste folder aplikasi yang terupdate serta mengurangi terjadinya bentrok fitur antar programmer sat uke programmer lainnya.

### Alur Kerja Git

- Konfigurasi git,kita dapat melakukan konfigurasi dengan cara
  - Git config –global user.name “Hafizh abiyyu”
  - Git config --global user.email “hafizhfirdaus19@gmail.com”
- Melihat hasil konfiguras dengan git config –list
- Git init (Membuat repository) setelah kita mengkofigurasi selanjutnya melakukan git init pada folder yang dibuat
- Git status,berfungsi untuk melihat apakah terjadi perubahan atau tidak pada local git
- Git add,selanjutnya untuk menambahkan file baru/file yang dibuat ke staging area
- Git commit -m “message”,digunakan untuk menyimpan perubahan pada git local
- Git remote berfungsi untuk menghubungkan remote repository dengan project local yang telah kita buat direktorynya
- Git push -u origin master, digunakan untuk mengirimkan/perubahan file ke remote repository
- Git branch -b[nama branch] digunakan untuk Membuat branch baru
- Git checkout digunakan untuk berpindah branch
- Git merge digunakan untuk menggabung branch cabang ke branch master
- Git repo clone Hafizhabiyyu777/-Writing-and-Presentation-Test-,untuk memindahkannya ke local(melakukan cloning)

## HTML

### Peran HTML

HTML (Hypertext Markup Languange) pada web development adalah sebagai kerangka sebuah website serta menampilkan konten di browser

### Tools

yang dibutuhkan untuk Membuat HTML adala code editor(Visual studio code) dan browser

> ### Structure HTML

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Belajar HTML</title>
  </head>
  <body></body>
</html>

### Live Server VSC

kita dapat mengaktifkan live server dengan cara menambah Ekstension setelah itu di bagian bawah kanan akan muncul “Go Live” setelah kita click maka pada saat mengedit html maka tampilan di browser otomatis berubah

### Tag popular HTML

- <p> </p> (Menulis paragraph)
- <div></div> ,untuk mengelompokkan element menjadi sebuah grup
- <h1></h1>  ; <h6></h6>  ,merupakan tag heading dari highest to lowest
- <img src=”image.png”>,untuk menampilkan gambar
- <a href=https://google.com>ini google </a> ,untuk mencantumkan link
- <!-- --> atau Cntrl + / untuk memberikan comment

> berikut contoh tag unorder,video dan table

> > - <ul>

     	    <li>Nama : hafizh</li>
          <li>Age  : 20</li>
          <li>Asal : Sidiarjo </li>
      </ul> (Untuk Membuat unorderlist atau <ol></ol> untuk Membuat orderlist)

> > - <video controls>

          <source src="movie.mp4" type="video/mp4">
      </video> (untuk menampilkan video)

> > - <table> (untuk Membuat tabel)

          <tr> (Membuat row)
              <th>Nama</th> (Membuat column heading)
              <th>asal</th>
          </tr>
          <tr>
              <td>Hafizh</td> (Membuat column biasa)
              <td>Sidoarjo</td>
          </tr>
      </table>

- <form></form> Berfungsi untuk Membuat form

### Tag Semantik

Tag semantic html Membuat tag html yang sesuai dengan kebutuhan konten yang ada seperti <header></header> <nav></nav> <article></article> <aside></aside> <footer></footer> etc,dengan menggunakan semantic maka element akan mudah dibaca baik oleh manusia maupun computer itu sendiri

### Deployment Website

Dalam mendeploy website kita menggunakan netlify,caranya adalah login di website netlify (direkomendasikan menggunakan github) setelah itu masuk ke tab site lalu drag and drop seluruh folder html setelah itu kita bisa mencustom alamat link terakhir

## CSS

### Peran CSS

CSS Berfungsi untuk mendesign sebuah website agar terlihat lebih cantik dan menarik,dengan css kitab isa mengubah warna,font,editing text format,mengatur tata letak dsbnya

### Menyisipkan CSS ke HTML

Dalam menyisipkan css pada HTMl ada 3 cara yaitu

> **Inline CSS**,Menambahkan css dengan atribut <style></style> pada tag pembuka html co : <p style=”padding :10px;”>Halo world</p> > **Internal CSS**,Menambahkan tag style pada bagian head html
> **Eksternal CSS**,Menambahkan css dengan Membuat file css sendiri setelah itu dihubungkan pada html dengan tag <link rel=”stylesheet” type=”text/css” href=”style.css”

### CSS Dasar

Struktur css sebagai berikut
.elemenhtml{
property:value;
}
Dalam eksternal css biasa kita mendesign ada 3 cara yaitu memanggil langsung tag htmlnya/menggunakan id/menggunakan class

> Contoh css langsung **menggunakan tag** htmlnya

    .h3{
        color:palegreen;
    }

> **Class**

    .hias2{
    background-color: palevioletred;
    }

> **Id**

    #hias1{
        text-align: center;
    }

Jangan lupa untuk memberikan nama class/id pada open tag yang ingin menggunakan css , perbedaan tag class dan tag id adalah tag class digunakan jika aka nada beberapa element HTML yang memiliki desain yang sama sedangkan id digunakan jika hanya ada 1 element pada file/halaman

### Metode Responsive

Web responsive adalah sebuah Teknik atau metode pendekatan sistem dengan tujuan memberikan pengalaman berselancar di dunia internet secara optimal di berbagai perangkat,adapun yang perlu diperhatikan adalah padad html harus di cantumkan <meta name="viewport" content="width=device-width, initial-scale=1.0"> selanjutnya yang kedua kita bisa memakai metode Media Query seperti berikut ini
@media (max-width: 600px) {
.button-group {
display: flex;
flex-direction: column;
}
}

### Penggunaan Flexbox

- Flexbox adalah cara untuk mengatur layout
- Flexbox mampu memiliki kemmapuan untuk menyesuaikan layout secara otomatis
- Flex-direction(untuk mengatur letaik item adapun valuenya : row default,row-reverse,column,column-reverse
- Flex-wrap jika ingin membatasi jumlah item children dalam 1 line ,value : no-wrap,wrap,wrap-reverse
- Flex-flow sebagai shortcut set up flex-direction dan flex-wrap bersamaan,adapun value row nowrap,column wrap,column reverse,row-reverse,wrap-reverse

## Algorithm

### Perbedaan serta manfaat dari algoritma dan Data Structure

- Algoritma merupakan sebuah penjelasan mengenai step=step yang dibutuhkan untuk Menyelesaikan suatu task
- Data Structures adalah cara untuk menyimpan,mengatur dan mengorganisasian data di dalam penyimpanan kompuer sehingga data tersebut secara efesien

### Contoh Algoritma sederhana

Step 1 : Start
Step 2 : Declare variable angka1,angka2,sum
Step 3 : Read values angka 1 dan angka 2
Step 4 : add angka1 and angka2 and assign the result to sum. (sum<-angka1+angka2)
Step 5 : Display sum
Step 6 : Stop

### Menerapkan algoritma dengan JS

(Studi kasus penambahan)
Var a,b,c;
A = prompt(“First Number?”);
B = prompt(“First Number?”);
C = Number(a) + Number(b);
Console.log(c)
Alert(“result=”+c)

### Big O Nation

adalah notasi matematika yang menggambarkan perilaku pembatas dari suatu fungsi Ketika argumennya tak menentu O(n2)Selection sort,O(log n) Binary Sort

## JS

### Peran Javascript

- Javasript berperan untuk memberikan logic pada website serta Membuat sebuah website menjadi interakti dan dinamis
- adapun kita dapat menjalankan JS melalui browser seperti mozila,chrome dsbnya serta dapat mengecek error di console log

### Type data JS

Pada pemograman JS terdapat 6 type data yaitu

- Number (angka termasuk decimal)
- String (“berisi huruf/angka/space/symbol dsbnya”)
- Boolean (true/false)
- Null (variabel atau data tidak memiliki nilai)
- Undefined (merepresentasikan varibel/data yang tidak memiliki nilai)
  Adapun alesan undefined seperti dibawah ini :
  Nilai dari pemanggilan variabel yang belum didefinisikan,Nilai dari pemanggilan element array yang tidak ada,Nilai dari pemanggilan property objek yang tidak ada,Nilai dari pemanggilan fungsi yang tidak mengembalikan nilai (return).Nilai dari parameter fungsi yang tidak memiliki argumen
- Object(koleksi data yang berhubungan serta bisa menyimpan tipe data apapun)

### Operator

- = (menyimpan sebuah nilai)
- Math/Arithmatic operator(+ ,-,\*,/,%)
- Increment dan decrement (++,--)
- Comparison operator(<,>,<=,>=,===,!==)
- Logical Operator (&&,||,!)

### Conditional

- If else / If else if (Jika dibutuhkan dengan syarat/pilihan)
- Truthy and falsy (untuk mengecek apakah variabel terisi)
- Switch case (jika percabangannya terlalu banyak)
- Ternary operator ( lebih singkat tapi tidak bisa banyak cabang)

### Looping

- For loop(Jika tau nilai pasti perulangan; (nilai awal;syarat;incre/decre)
- While loop (akan menjalankan jika bernilai true)
- Do While (menjalankan pengulangan 1 kali setelah itu baru cek kondisi)
