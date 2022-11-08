# Week 7 Writing Test

## Day 1(7/11/2022)

### **Lanjutan sequence** dari hari jumat minggu lalu

ORM atau Pbject Relational Mapping adalah teknik memetakan object perangkat lunak ke tabel database tanpa harus menulis query basis data apapun,orm juga mampu menduukung banyak database seperti Postgree,MYSQL,SQLite dsbnya

ORM terletak antara server dan database sehingga ia menghubungkan kedua hal tersebut,cara menggunakan sequelize ada 2 yaitu :

1. Tanpa Migration
   Jika tanpa menggunakan migration maka kita bisa melakukan install dengan mengikuti step yang ada pada [link ini](https://sequelize.org/docs/v6/getting-started/) yaitu dengan
   1. npm install --save sequelize
   2. npm install --save mysql2 (tergantung menggunakan db apa)
      untuk selanjutnya dapat dilihat di link yang sudah tercantum di atas
2. Dengan Migration
   Migration adalah menyimpan history perubahan pada table yaitu dengan cara setiap create/hapus/edit kolom otomatis disimpan perubahan dan bisa balik lagi ke versi tabel seebelumnya dengan menggunakan undo adapun untuk tahapan migration dapat melihat [Link ini](https://sequelize.org/docs/v6/other-topics/migrations/) pada writing test kali ini kami menggunakan dengan Migration.

Langkah menggunakan ORM dengan Migration

1. **npm install --save-dev sequelize-cli** (untuk melakukan install sequelize)
2. **npm install sequelize mysql2** (untuk menginstall database mysql)
3. **npx sequelize-cli init** (langkah ini dilakukan untuk membuat confid,models,migration dan seeders adapaun contoh file yang akan terbuat sebagai berikut)

![create_folder](img/create_folder.png)

> Penjelasan setiap file
>
> > - _config_ berfungsi untuk menghubungkan atau connecting ke database
> > - file _models_ berfungsi untuk merepresentasikan tabel yang ada di database jadi dika di model ada users maka di database ada tabel user termasuk di dalamnya berisi atribut.
> > - File migration berfungsi untuk melakukan migrasi ke database atau create database ke database ke my sql
> > - File seeders berfungsi untuk melakukan penambahan atau mengedit database dengan cara menggunakan async await dan [bulkInsert](https://sequelize.org/api/v6/class/src/dialects/abstract/query-interface.js~queryinterface)

_Lanjutan langkah menggunakan ORM_ 4. **Ubah pass,user hingga database sesuai kebutuhan anda** di development agar bisa terconnect,adapun contohnya sebagai berikut

![config](img/config.png)

5. Jika database tersebut belum dibuat maka,gunakanlah **npx sequelize db:create**,untuk mmebuat database tersebut

6. **npx sequelize model:create --name User --attributes name:string,email:string,password:string**,berfungsi untuk membuat tabel dengan nama User dan berisikan atribut name,email dan password dengan type data string ,perlu diketahui setelah kita selesai melakukan itu maka akan muncul file _user di model_ dan _create-user di migration_

7. Selanjutnya kita dapat melakukan **Npx sequelize db:migrate** Untuk koneksi database,dan dapat melakukan **npx sequelize db:migrate:undo** Jika ingin mengundo database

8. Kita dapat menambahkan data pada database dengan menggunakan query **Npx sequelize-cli seed:create –-name demo-user** demo user merupakan tabel yang ingin kita tambahkan,selanjutnya akan muncul file baru di seeder sebagai berikut :
   ![seed](img/seed.png)

9. Setelah itu aync await dan bulkinsert untuk membuat data baru seperti gambar diatas
10. Jika sudah maka **npx sequelize db:seed --seed 20221107074045-demo-user.js** untuk memasukkan data tersebut ke database sql atau basicnya sebagai berikut _npx sequelize db:seed --seed nama-file-seeder-nya_
11. Selanjutnya kita bisa mengatur di controller seperti gambar dibawah ini agar bisa diakses dengan localhost:port/user
    ![controller](img/controller.png)
    12.begitu seterusnya jika kita ingin menambahkan data/tabel atau menghapus hingga menampilkannya jika diminta oleh port

#### Associate

Associate atau yang biasa kita sebut relation berfungsi untuk menghubungkan satu tabel dengan tabel lainnya adapun beberapa argumen Association sebagai berikut :

- hasOne(one to one),perbedaan dengan belongsTo adalah kunci asing(FK) akan ditentukan pada model target dapat dilakukan dengn cara menambahkan kunci asing ke target dan mixin asosiasi tunggal ke sumbernya.

- belongsTo(one to one),dapat dilakukan dengan cara menambahkan kunci asing dan campuran asosiasi tunggal ke sumbernya.

- hasMany(one to many),dapat dilakukan dengan cara menambahkan kunci asing ke target dan campuran asosiasi jamak ke sumbernya.

- belongsToMany(Many to Many),dapat dilakukan dengan cara membuat asosiasi N:M dengan tabel gabungan dan menambahkan mixin asosiasi jamak ke sumbernya. Tabel persimpangan dibuat dengan sourceId dan targetId.

Contoh implementasi di project adalah siapkan FK terlebih dahulu di tabel yang ingin kita hubungkan,kita dapat merubahnya dibagian migration seperti dibawah ini :
![fk](img/fk.png)

Kita dapat mengetahui bahwasannya _user_id_ merupakan sebuah FK dari tabel user,selanjutnya kita ingin bahwa antara user-blog relasinya one-many maka kita letakkan hasMany pada tabel user dan belongsTo pada tabel blog seperti dibawah ini :

>**Penulisan association di tabel user**

![hasmany_user](img/hasmany_user.png)

>**Penulisan association di tabel blogs**

![belongto_blog](img/belongto_blog.png)
