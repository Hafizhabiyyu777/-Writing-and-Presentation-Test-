# Week 5 Witing Test

## Day 1 (24/10/2022)

### Web Server

Proses rendering ada beberapa yaitu

1. Tradisional metode
   ![gambar tradisional mode](https://i.postimg.cc/y8RqyYYD/Tradisional-metode.png)
   berdasarkan gambar diatas maka flownya adalah Browser request halaman html ke Server dengan protocol HTTP setelah itu server mengirim halaman html yang dituju contohnya adalah deployed netlify

2. Single page application /client-side render
   ![Gambar single page](https://i.postimg.cc/13vWFkD8/client-side-render.png)
   Berdasarkan gambar diatas maka flownya brower hanya minta file JSON ke server dan server memberikan data JSON yang diminta setelah itu ditampilkan di browser

3. Dynamis side
   ![Dynamis side](https://i.postimg.cc/y8xmMkSN/dynamic.png)
   Yang bisa memakai ini adalah Laravel ,adpaun flownya adalah broser meminta data ke server setelah itu server mengembalikan data/html setelh tu menampilkan ke browser

**Software Architecture**
![Software Architecture](https://i.postimg.cc/v8WwnmTD/software-architecture.png)

Laravel mungkin bisa di sebut Monolith karena aplikasinya nyatu antara backend dan frontend,jika aplikasinya semakin besar maka dinamakan Microservice tergantung servicenya masing-masing,jika lebih besar lagi maka ada microfront end,Front & Back bisa juga disebut MVC dimana frontend memegang Visual dan backend memegang Module dan Controller

**Perbedaan Rest dan resstfull adalah**
Rest adalah arsitektur dan memiliki rule,Restful api adalah istilah jika menerapkan astcitecture miliknya rest.

HTTP Mempunyai beberapa method yaitu :

1. Get untuk mendapatkan atau mengambil data atau informasi dari server
2. Post untuk mengerim data
3. Delete untuk mendelete data
4. Put/patch untuk mengupdate data atau edit data atau replace,jika edit data Sebagian memakai patch

**HTTP Status code**

- 2xx : berarti success
- 3xx : berarri redirect
- 4xx : client error ,artinya kesalahan pada user contohnya jika kita akses pada halaman yang tidak disediakan.
- 5xx : Server error,artinya salahnya ada di server atau server sedang bermasalah

note : Kita dapat Mengecek apakah url API sudah mengambalikan dengan benar menggunakan postman

Penulisan END POINT

- Jika datanya banyak atau collection maka memakai S,contoh users
- Jika ingin memanggil user dengan id 3 maka pakai : /users/3
- Jika lebih dari satu kata maka memakai strip untuk menyambung
- Lebih detailnya dapat dilihat di restfulapi.net

## Day 2(25/10/22)

### Node js

Node JS Adalah js runtime yang dibangun di V8 Engine,V8 Engine lahir pada tahun 2008,runtime sendiri adalah tempat untuk kita menjalankan atau mengeksekusi code,selama ini permasalahannya adalah js akan berhenti saat browser ditutup dam hanya bisa dilakukan di dalam browser saja,oleh karena itu Ryan dahl Membuat node js untuk menciptakan web server tapi menggunakan Event Loop, adapun fitur utama node js adalah:

1. File system
2. http & Https
3. REPL (read,eval,print,loop)
4. Console
   Karena sudah tidak lagi di browser maka jika pakai node.js tidak bisa main di dom tetapi di file system

Build in module node.js yaitu :

1. Console
   Merupakan sebuah module bawaan dari yang berfungsi untuk debug dan menampilkan tampilan di interface saat dipanggil,adapun cara menjalankan node.js adalah dengan menjalankan di terminal dan tulis node.(nama js yang ingin di runnin)

2. Proccess
   Cara mengakses process di node.js adalah dengan process.env,jadi Membuat process itu di file .env setelah itu dipanggil paramnya apa dan valuenya apa.

3. OS
   ![gambar tradisional mode](https://i.postimg.cc/HxVJshgD/OS.png)
   kita bisa melihat OS melalui node dengan cara diatas tersebut

4. util
   untuk membantu kebutuhkan internal Api
5. Event
   merupakan event yang dapat digunakan untuk mendefinisikan error
6. Buffer
   merupakan event yang digunakan untuk mengelola dan mengubah dara raw menadi data bytes
7. FS
   file system yang berfungsi untuk berinterkasi diluar code
8. Timers
   merupakan modules yang digunakan untuk melakukan schedulling atau mengatur pemanggilan function

kita dapat mengecek apakah aplikasi kita sudah ada node.js atau belum dengan cara node -v

Note :

- cara import di node js berbeda yaitu dengan cara const { env } = require(‘process’)

**Membuat Web Server Dengan Node JS**

Node JS Web Server memiliki build method yang memungkinkan Node JS mentransfer data melalui Hyper Text Transfer Protocol (HTTP).yaitu dengan

- menggunakan modul HTTP, gunakan require()
- menggunakan method res.writeHead() untuk menambahkan header HTTP.
- menggunakan method createServer() untuk membuat server HTTP
- menggunakan Callback function yang digunakan pada method http.createServer(), akan dijalankan ketika seseorang mencoba mengakses komputer pada port yang ditentukan atau yang kosong const http = require('http');

cara create server sebagai berikut :
http.createServer(function (req, res) {
res.write('Hello World!');
res.end();
}).listen(3000);

cara membuat server object sebagai berikut ini
http.createServer(function (req, res) {
res.writeHead(200, {'Content-Type': 'text/html'});
res.write('Hello World!');
res.end();
}).listen(3000);

const http = require('http');
const url = require('url');

http.createServer(function (req, res) {
res.writeHead(200, {'Content-Type': 'text/html'});
const query = url.parse(req.url, true).query;
const txt = q.year + " " + q.month;
res.end(txt);
}).listen(8080);

## Day 3 (26/10/22) dan day Day 4 (27/10/22)

### Express JS

Express JS merupakan sebuah framework webb app yang ditulis dengan JS,sebenarnya fungsi dari Express js ini adalah untuuk mengatur fungsionalitas website seperti pengelolaan routing dan session permintaan HTTP,penanganan error serta pertukaran data server adapun beberapa codenya sebagai berikut ini

_3 baris code dibawah ini serta app.listen merupakan sebuah Basic Syntac Expresss_
const express = require("express");
const app = express();

_Alesan saya menggunakan port 7000 karena port lainnya sudah banyak digunakan di aplikasi lain seperti xampp,oracle,sql dsbnya_
const PORT = 7000;

app.use(express.json());

const movies = [
{
id: 1,
title: "Wakanda",
},
{
id: 2,
title: "Minion",
},
];

_Ini merupakan sebuah basic root yaitu mengaksesl url di wesbite dan menentukan methode api,alamat dan response yang dikeluarkan baik get atau post dsbnya_
app.get("/movies", checkUser, (req, res) => {
res.send({
status: "success",
data: movies,
});
});

app.get("/movies/:id", (req, res) => {
const params = req.params;
const data = movies.find((item) => item.id == params.id);
res.send({
status: "success",
data,
});
});

app.post("/movies", (req, res) => {
const data = req.body;
movies.push(data);
res.status(201);
res.send({
status: "success",
message: "success add data",
});
});

app.listen(PORT);

**Back End Web Aplication**
merupakan sebuah aplikasi yang berjalan di server side dan bekerja untuk memberikan informasi berupa data yang sesuai dengan request client

**Rest Api**
Sedangkan rest api itu merupakan penerapan dari api itu sendiri yaitu sebuah berfungsi untuk melakukan pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi restful api memiliki 4 komponen yaitu :

- URL design
- HTTP Verbs
- HTTP Response Code
- Format Response

**Express Middleware**
Fungsi middleware adalah fungsi yang memiliki akses ke objek permintaan (req), objek respons (res), dan fungsi middleware berikutnya dalam siklus permintaan-respon aplikasi. Fungsi middleware berikutnya biasanya dilambangkan dengan variabel bernama next.
Express dapat menggunakan jenis middleware sebagai berikut ini

- Middleware appliacation-level
  biasanyaa menggunakan fungsi dari app.use sebagai berikut ini :

  const express = require('express')
  const app = express()
  app.use((req, res, next) => {
  console.log('Time:', Date.now())
  next()
  })

- Middleware router-level
  Middleware router-level bekerja seperti aplication-level hanya saja tingkatannya router,contoh code sebagai berikut
  const express = require('express')
  const app = express()
  const router = express.Router()

  router.use((req, res, next) => {
  console.log('Time:', Date.now())
  next()
  })

- Middleware error-handling
  Middleware ini berfungs untuk mengembalikan status error pada website yang memberikan request adapun code sebagai berikut ini :
  app.use((err, req, res, next) => {
  console.error(err.stack)
  res.status(500).send('Something broke!')
  })

## Day 5(28/10/22)

**Database**
Database merupakan tempat dimana sebuah data itu disimpan dan diakses secara elektronik oleh komputer,namun sayangnya banyak sekali permasalahan anomali yang terjadi pada saat pengelolaan data,anomali sendiri adalah Ketika data tersebut tidak konsisten seperti besar kecilnya berbeda contoh : (domisili : Surabaya) & (domisili : surabaya) kedua data tersebut memang sama-sama menunjukan domisili tetapi karena besar kecilnya berbeda atau terkadang ada yang disingkat dan tidak,nah hal tersebut akan terjadi anomali,disisi lain kita bisa membuat database dari banyak hal seperti langsung membuat di sql atau memulai dari cmd atau bisa memulai dari normalisasi database,saya akan membahasnya dibawah ini :

**Membuat database dari awal**
![database dari awal](https://i.postimg.cc/ZKC1f6hq/databasee-day-5.png)
Dari gambar diatas kita bisa belajar banyak hal yaitu

- Setiap kotak tersebut disebut tabel database
- Setiap tabel memiliki nama tabel seperti mahasiswa,film dsbnya
- Setiap tabel harus mempunya primary key yaitu sebuah id sebagai penanda unique pada setiap data dan harus di set not null
- adapun setiap tabel memiliki atribut seperti mahasiswa atributnya nama,email,jurusan
- Nah dalam menghubungkan database ada yang namanya relationship
- relationship ada one-many,many-many,many-one,one-one
- FK atau yang biasa dikenal foreign key adalah id atau kunci asing yang berada pada tabel lain,contoh karena mahasiswa dan film many-many maka akan muncul tabel baru sebagai penghubung digambar atas dinamakan film_diskusi disana NIM & id dari film sebagai Foreign key atau kunci asing di tabel lain.

**Membuat database dengan cara memecah tabel yang sudah ada atau data yang sudah ada**
Jika kita berangkat dari data yang sudah menyatu maka kita dapat melakukan normalisasi yaitu Teknik untuk mengorganisir data ke dalam bentuk table supaya

- data tidak redundancy
- Mudah dicari
- Agar Tidak terjadi anomaly

Adapun urutannya dalam normalisasi adalah berikut ini dimulai dari 1nf yaitu

**1nf**

- Ga ada urutan dalam penyimpanan data
- Harus menggunakan tipe data yang yang sama pada 1 kolm
- Harus ada pk
- Tiap kolom harus berisi nilai tunggal

**2nf**

- Harus dalam bentuk 1nf
- Tidak ada partial dependency (atribut yg tidak ada hubungan dengan pk)
  Memisahkan data setelah itu memberikan pk pada data terpisah dan memberikan relationship atau Membuat table baru unuk menghubungkan dua table yang terpisah tersebut

**3nf**

- Harus dalam bentuk 2NF
- Tidak ada transitif dependency (setiap atribut harus bergantung pada primary key supaya tikda terjadi transitif dependey yaitu bergantung ke atribut selain transitif dependency)

Nah dari 3nf maka seharusnya database sudah dapat digunakan dan sudah dipastikan tidak ada hal yang menyebabkan particia dependency atau transitif dependency
