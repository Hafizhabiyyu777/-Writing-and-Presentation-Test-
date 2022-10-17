# Week 4 Writing

## Day 1 (10/10/22)

### Fetch dan Async Await

Merupakan salah satu fitu ES mulai 2017,fitur ini mempermudah dalam menangani proses asynchornous,melanjutkan dari minggu lalu maka kita belajar menangkap promise dengan async await perbedaan yang paling mendasar adalah adanya then catch yang dimasukkan pada sebuah function selain itu terdapat pula keyword async pada function dan await serta meminta respon berbeda dengan then catch adapun contohnya sebagai berikut :

let kondisi ="bingung"

let belajar = new promise ((resolve), reject)=> {
if(kondisi !== "bingung") {
resolve("istirahat dahulu")
}else {
reject("Lanjut belajar")
}
}
async function belajarAwait() {
try {
let nilai = await belajar
console.log(nilai);
}
catch (error) {
console.log(error);
}
}

Selanjutnya kita dapat menggunakan API yaitu aplication progamming interface yaitu sebuah interface yang berfungsi sebagai penghubung antar aplikasi atau bosa dsebuh sebagai jembatan penghubung aplikasilain dengan aplikasi yang kita kembangkan,perlu diketahui bahwasannya API berbentuk URL yang isinya berupa data yang disimpan dalam format JSON,JSOn sendiri merupaja js yang bebrasis teks dan biasanay digunakan untuk pertukaran data dalam penggunaan fetch hanya dengan fetch(url),sebagai contoh

1. kita akses api dari gogoanime
2. kiita mendapatkan link url jsonnya dan memasukkan ke code untuk mendapatkan datanya

adapun contoh fetch API codingannya sebagai berikut :

fecth("https://gogonime.herokuapp.com/popular.then ( res=> {
return res.json()
}).then(res => {
console.log(res)
})

dan berikut untuk async await

let getAnime = async function() {
try {
let res= await fetch(
"https://gegonime.herokuapp.com/popular"
result.map((item) => {
console.log(nama anime : ${animeTitle}`)
})
) catch (error) {
console.log(error)
}
}
}

## Day 2 (11/10/22)

### Github lanjutan

Github sangatlah bagus untuk melakuka kaloborasi,kenapa harus kaloborasi?karena jika project besar seperti Tokopedia tidak mungkin hanya dikerjakan oleh 1 progammer.Adapun Langkah awal dalam berkaloborasi adalah

1. Ketua Membuat repository organisasi dan invite member
2. Buatlah brach dev terlebih dahulu fungsinya adalah pada saat mengerjakan atau menambah fitur dapat update di dev dan jika sudah siap produksi baru ditaruh di main,hal ini dilakukan untuk meminimalisir terjadinya bug pada saat produksi atau menambah fitur
3. Setelah itu seluruh member melakukan clone dengan cara ‘git clone (link hhtps)’
4. Setelah itu jika ingin merubah folder atau mengcoding maka semua anggota wajib untuk melakukan pull terlebih dahulu,fungsinya agar penyimpanan local sudah up to date,adapun cara melakukan pull adalah dengan ‘git pull’
5. Setelah itu setiap anggota tidak boleh langsung melakukan push ke dev melainkan Membuat brach terlebih dahulu,adapun nama brach bisa dibuat nama anggota atau fitur,cara Membuat branch sebagai berikut ini ‘git branch (nama fitur/nama branch)’
6. Untuk berpindah branch bisa menggunakan ‘git switch (nama branch)
7. Untuk menghindari conflict lakukan ‘git merge dev’ agar branch kita terupdate
8. Setelah selesai mencode pakai git add . dan git commit -m ‘ket’ untuk melakukan save pada local
9. Setelah selesai lakukan push dengan cara Git push -u origin (nama brach)
10. Setelah berhasil push maka lakukan pull request untuk memasukkan perubahan ke dev,adapun nanti ketua akan menyetujui dengan melakukan click merge pull
11. Begitupun seterusnyaa,jika ingin melakukan code lagi click git pull dan git merge dev pada brach yang kita punya

### Conflict pada github

Conflict terjadi jika ada 2 orang atau lebih yang melakukan perubahan pada file yang sama atau pada baris yang sama maka akan terjadi conflict pada saat pul request atau menggabungkan antar branch,adapun cara mengatasi conflict sebagai berikut :

- Git pull dev terlebih dahulu untuk mendapatkan update terbaru
- Setelah itu git merge dev pada project kita
- Dan membenarkon code yang salah atau memilih code yang benar (diantara code yang conflict)
- Setelah itu git add dan commit
- Setelah itu lakukan git push origin -u origin “nama branch”
- Dan tanpa harus pull request lagi karena sudh auto solved

## Day 3 (12/10/22)

### Responsive Web Design

Responsive web design bertujuan untuk membuat desain website dapat diakses dalam device apapun,hal yang terpenting dalam responsive web design adalam menambahkan :

<meta name="viewport" content="width=device-width",initiale-scale=1.0>

Adapun trik selanjutnya adalah menggunakan Max-width dalam membuat element karena dengan begitu panjang elemt atau image menjadi overflow mengikuti width real bawaaan dari file image

Di sisi lain kita dapat menggunakan Media Query untuk membuat web responsive adapun jenis media query adalah min-width dan max-widthh Co :
@media Scree and (min-width:ur pixel) {}
Adapun ada 2 cara atau pattern dalam menggunakan media query :

1. Membuat file css berbeda untuk masing-masing device
2. Menggabungkan file SCC untuk setting styling berbagai device

Sebagai informasi perubahan tampilan saat berganti device disebut dengan breakpoint

### Flexbox

- Flexbox adalah cara untuk mengatur layout agar sebuah website dapat diatur dengan mudah dan menjadi lebih responsive
- Flexbox mampu memiliki kemmapuan untuk menyesuaikan layout secara otomatis
- Flex-direction(untuk mengatur letaik item adapun valuenya : row default,row-reverse,column,column-reverse
- Flex-wrap jika ingin membatasi jumlah item children dalam 1 line ,value : no-wrap,wrap,wrap-reverse
- Flex-flow sebagai shortcut set up flex-direction dan flex-wrap bersamaan,adapun value row nowrap,column wrap,column reverse,row-reverse,wrap-reverse

### Grid

Grid adalah tata letak yang dapat digunakan dalam meletakkan halaman adapun grid bekerja pada 2 dimensi yaitu baris dan kolom sedangan flexbox bekerja pada satu dimensi saja.kita dapat mengaktifkan grid dengan membuat elemen html seperti berikut ini :

1.  > Contoh grid
        <di class="grid-container">
        <!-- content -->
        </di>
2.  .grid-container {
    display: grid;
    }

adapun property yang paling umum adalah grid-template-column dan grid-template-rows dengan properti tersebut dapat menentukan jumlah kolom dan baris serta lebar masing-masing

### Bootsrab

Boostrab merupakan sebuah framework HTML,CSS dan JS yang berfungsi agar dapat mendesign sebuah website yang responsive mudah dan cepat adapun framework ini diciptakan pada 2011 oleh pendiri twitter yaitu Mark Otto dan Jacob Thornton,adapun kegunaaan umum boostrab sebagai berikut :

- Menciptakan website yang mobile friendly
- memudahkan resize sebuah gambar
- membuat sebuah website lebih interaktif

Muskipun terlihat menarik tetapi boostrab memiliki kelebihan dan kekurangan kelebihannya adalah ramah untuk pemula,grid system yang bagus,bersifat Open-source dan kebebasan dalam kustomisasi adapun kekurangannya adalah memungkin elemen dapat digunakan atau sama dengan website lain,ukuran file boostrab yang relative besar dapat memperlambat website pada saat pertama ngeload

Adapun fungsi class pada boostrab adalah sebagai berikut ini

- class table berfungsi membuat table pada boostrab
- class .img-rounded untuk mengatur tampillan image menjadi rounded
- class alert berfungsi untuk membuat panel yang berisi pesan padaa boostrab
- class btn berfungsi untuk membuat sebuah button

Di dalam boostrab terdapat grid yaitu dengan membagi laman menjadi 12 gird yaitu span 4 merupakan gabungan dari 4 grid,span 8 gabungan 8 grid dan seterusnya,adapun boostrab sendiri memiliki 4 buah kelas grid yaitu

1. xs : grid untuk layout ponsel
2. sm : grid untuk layout tablet
3. md : grid untuk layout desktop
4. lg : grid untuk layout desktop besar

adapun contoh penerapan grid sebagai berikut :

>    Contoh grid
    <di class="row">

        <div class="col-sm-6"> <p> Coba 1 </p> </div>
        <div class="col-sm-6"> <p> Coba 2 </p> </div> </di>
    </div>
