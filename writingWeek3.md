# Week 3 Writing

## Day 1 (3/10/2022)

### Array and Multidimensional Array

Array adalah tipe data list order yang dapat menyimpan tipe data apapun di dalamnya sedangkan Multidimensional Array bisa dianalogikan dengan array of array adapunn contoh dari array multidemensi adalah sebagai berikut
let inventory = [
['kaos polo',10],
['Jaket Hodie',12],
['Topi',12],
['Celana Jeans',8]
];

Adapun jika kita ingin memanggill jaket hodie dapat memakai codingan console.log(inventory[1][0]);

Jika kita ingin melakukan push ke array multidemensi sama dengan array biasa yaitu
inventory.push(['Sweater',77])

sama seperti array kita bisa membaca semua isi multiarray dengan menggunakan forEach adapun contoh codenya sebagai berikut
inventory.forEach((baris)=> {
baris.forEach((column) => {
console.log(column);
})
})

## Day 2 (4/10/2022)

### Object

Object adalah sebuah tipe data pada variable yang menyimpan property dan fungsi (method)

> Cara membuat Object
> let nama_objt = {
> key1 : "value",
> key2 : "value2"
> }

> Cara akses Object
>
> 1. objt.key1 (memakai dot notation)
> 2. objt["key2"] (memakai bracket)

> Cara menambahkan key ke object / mengganti value di obj
>
> Objct.key3 = value / objt["key4"] = value

> Cara Menghapus Property
>
> Delete objt.property

> Selain itu object juga dapat memiliki method contohnay sebagai berikut
>
> let greeting = {
> welcome : function(nama="noname") {
> return `Halo selamat datang ${nama}`
> },
>
>           afterpay : function() {
>               return `Terimakasih sudah membeli produck kami`
>           }
>       }
>
> Dan cara memanggilnya adalah
> onsole.log(greeting.welcome("Andi"));

Selainitu object juga dapat melakukan Nested object atau biasa disebut object dalam object contoh codingannya sebagai berikut ini
let tanaman = {
jenis : "bunga",
nama : "bunga tulip",
serupa : {
saudara1 : {
nama: "bunga matahari",
asal : "Swiss"
},
saudara2 : {
nama: "bunga mawa",
asal : "indo Pasific"
}
}
}

    //cara memanggil nested object
    console.log(tanaman.serupa.saudara1.nama);

Mungkin kita akan kesusahan jika ingin memanggil nested object,maka dari itu kita dapat menggunakan For in,adapun contoh codenya sebaga berikut ini
for(let key in objct name) {
console.log(`${key}:${objctName [key]}`)
}

### Array Object

Array object berfungsi untuk menyimpan beberapa nilai dalam satu variabel adapun cara mendeklarasi dan membuar array object seperti dibawah ini
let users = [
{

     nama: "hafizh",
     umur: 20,
     alamat: "surabaya",

},

        {
          nama: "andi",
          umur: 30,
          alamat: "jakarta",
        },
        {
          nama: "toni",
          umur: 24,
          alamat: "palembang",
        },
      ];

Kita juga dapat menambahkan data baru sebagai berikut ini

      let data = users.map((el) =>{
          console.log(el.nama)
    // menambahkan statis di object array
          el.status = 'aktif'

      })

## Day 3(05/10/2022)

### Rekursif

Rekursif merupakan salah satu paradigma pemograman yaitu proses pengulangan sesuatu dengan cara memanggil diri sendiri adapun Contoh codingan rekursif sebagai berikut ini
function deretAngka(n) {

    if(n == 1) {
        console.log(n);
    }
    else {
        deretAngka(n-1) //Fungsi rekursif memanggil diri sendiri
        console.log(n);
    }

}

function faktorial (n) {

    if(n==1) {
        return 1
    }
    else {
        return n * faktorial(n-1)
    }

}

### Modules

JS Module adalah cara untuk memisahkan kode ke file yang berbeda adapun Keuntungan dari penerapan modules adalah mudah untuk mengelola kode dan kode tidak numpuk di satu file,salah satu cara Modules adalah degan export impor ada beberapa hal yang harus dipahami ketika export import

- Kita dapat melakukan export import antar file js adapun ada dua jenis export yaitu export dan export default adapun syntax export adalah
  export let motor = ["suzuki","yamaha","honda"]
- Saat menambahkan link script di html ditambahkan _type="module"_
- Kita dapat melakukan export pada variabel,class dan function
- Eksport default hanya bisa satu saja dan ditangkap tanpa kurung perawal,adapun contoh codenya sebagai berikut
  let entertaiment = ["naruto","Boruto"]
  export default entertainment;

> Untuk codingan import sebagai berikut
> import E, { motor as motorJepang, >smartphone } from "./japan.js";
> //Import E merupakan sebuah export default
> //Sebagai catetan pada bagian html harus ditambahkan type=”module” jika memanggil file js

## Day 4(06/10/2022)

### Asynchronous

JS sendiri merupakan bahasa yang :

> single thread
> Single-thread merupakan sistem yang hanya mempunyai 1 jalur(1 kasir)

> non-blocking
> Non-blocking artinya proses dapat diselat oleh proses lain

> Asynchronous
> Asynchronous adalah proses yang dilakukan secara tidak berurutan,misal A baru berjalan 70% setelah itu diselat B dan >Kembali lagi ke A 30%

Eksekusi antrian pada JS bersifat first-in dan last-out,adapun JS Asynchronous memiliki beberapa jenis yaitu callback,promises dan async await

#### Callback

adalah function yang dijadikan sebagai argumen,contoh code sebagai berikut :
setTimeout(() => {

        console.log("A");
      }, 1200);

      setTimeout(() => {
        console.log("B");
      }, 1000);

      console.log("C");

Maka yang akan ditampilkan C-B-A,Sebagai catetan muskipun setTimeOutnya B 0 second tetap saja akan menjalankan proses C karena proses B di masukkan ke callback queue terlebih dahulu sehingga stack kosong dan di proseslah si C

#### Promises

adalah objek JS yang menautkan kode dan menghasilkan(kode yang memakan waktu lama) dan mengkonsumsi(kode yang menunggu hasilnya) kode,adapun contoh codenya sebagai berikut :
let nontonPromise = new Promise((resolve,reject) => {

      resolve("Nonton terpenuhi")

              reject("gagal")

})

console.log("A");
nontonPromise.then(result => {

      console.log(result)

})

.catch((err) => {
console.log(err);
})

console.log("C");

#### async await

Merupakan salah satu fitu ES mulai 2017,fitur ini mempermudah dalam menangani proses asynchornous adapun cntoh codingannya sebagai berikut
async function myFunction() {
// This is an async function
}

## Day 5(07/10/2022)

### Web Storage

Salah satu fungsi dari web storage adalah untuk menyimpan data dari aplikasi ke browser dan bersifat local,adapun perbedaan antara session storage,local storage dan cookie sebagai berikut
**Local storage**

- Capacity 10 MB
- Expired (never)
- Penyimpanan hanya dapat dilakukan di browser
- Tidak melakukan sent with request

**Session storage**

- Capacity 5 MB
- Expired ketika Tab close
- Penyimpanan hanya dapat dilakukan di browser
- Tidak dapat melakukan sent with request

**Cookies**

- Capacity 4 KB
- Expired dapat diset secara manual
- Penyimpanan dapat dilakukan di browser dan server
- Dapat melakukan sent with request

Muskipun penyimpanan web storage besar tetapi jangan menyimpan data sensitive seperti otentikasi,password dan data lainnya adapun study case jika Belajar web storage adalah dark mode,todo dan detail page sebagai informasi Local storage hanya dapat menerima bentuk string.adapun code jika kita ingin :

> menyimpan ke local storange adalah
> localStorange.setItem("key”,[“value1”,”value2”])

> Sedangkan jika kita ingin mendapatkan data dari local storange dapat melakukan
> localStorange.getItems(“key”)

Serta sebagai catetan Jika kita menggunakan array dan ingin menyimpan ke local storing dapat menggunakan Json.stringify
