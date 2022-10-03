# Week 2 Writing

## Day 1 (26/09/2022)

#### Scope

    - Scope adalah konsep dalam flow data variable
    - Berfungsi untuk menentukan suatu variabel bisa diakses pada scope tertentu
    - Blocks adalah code yang berada dalan curly braces _{}_
    - Conditional,function dan looping menggunaka block
    - Global scope berarti variabel dapat diakses dimanapun dalam suatu file
    - Local scope berarti variabel hanya bisa diakses didalam block saja,tidak bisa diluar block

#### function

    - Function adalah sebuah block koda dalam sebuah grup untuk Menyelesaikan satu task
    - Fungsi dari function agar dapat digunakan berulang-ulang kali tanpa harus mengcode ulang contoh function hitungpersegi()
    - Memanggil function bisa menggunakan : namafunction()
    - Parameter function berfungsi untuk menerima inputan data yang nantinya digunakan untuk melakukan task contoh :
    Function penambahan(a,b) {
    Return a+b;
    }
    - Argumen function adalah nilai yang digunakan saat memanggil fuction
    - Default parameter berfungsi untuk memberikan nilai awal pada parameter function dan berfungsi agar tidak error saat function dipanggil tanpa argumen
    - Function helper,dimana function dapat memanggil function lain yang sudah dibuat
    - Arrow function adalah cara lain dalam menuliskan functiom pada ES6 contohnya
    - Multi-line block
        Const greeting = () => {
        Return ‘hello wordl’;
        };
    - Single line block
        Const sumNumbers = umber => number +number;

## Day 2 (27/09/2022)

#### Data Type Bulit-in Protoype and method

    - JS merupakan Bahasa yang dinamis sehingga varibel dalam js tidak terkait langsung pada type tertentu,contohnya jika menulis angka menjadi number tetapi jika menulis kata maka menjadi string
    - Data type dibagi dua yaitu Primitive dan Non-premitive
        Contoh  rimitive : Number,stringsBooleans,undefined,null
        Non-primitive : Object,Arrays,Function
    - Static Method
        - Number.isNaN() (Melihat apakah nilainya nan atau tidak)
        - Number.isFinite()  (mengecek apakah nilainya finite)
        - Number.isInteger() (Melihat apakah nilai merupaan bilangan bulat)
        - Number.isSafeInteger() (melihat apakah bilangan bulat antara 253-1 )
        - Number.parseFloat() (sama dengan merupakan fungsi float global)
        - Number.parseInt() (sama dengan parseInt global)
        - etc

    - Instance methods
        - Number.prototype.toExponential() (Mengembalikan string yang mewakili angka dalam notasi eksponsial)
        - Number.prototype.toFixed() (mengebalikan string yang mewakili angka pada notasi tetap)
        - Number.prototype.toString() (mengembalikan string yang mewakili ibject tertentu)
        - etc
    - Math di js adalah object bawaan yang memiliki propery dan metode untuk fungsi matematika tetapi bukan merupakan objek fungsi
    - Static properties math
        -	Math.E (konstantas Euler dan basis logaritma)
        -	Math.LN2  (logaritma natural dari 2)
        -	Math LOG2E (logartima natural 10)
        -	Math.PI (rasio keliling lingkaran atau PHI 3.14)
        -	Math.SQRT1_2(akar kuadrat dari)
        -	Math.SQRT2(akar kuadrat 2 dari)
        -	etc
    - static method math
        -	Math.tan() (return tangen x)
        -	Math.sqrt() (return akar dari x)
        -	Math.round() (return nilai x dibulatkan ke bilangan terdekat)
        -	Math.random() (Return pseudo-random angka dari 0 sampai 1)
        -	Math.min() (return angkaterkecil dari 0 atau lebih)

## Day 3 (28/09/2022)

#### Dom-Introduction

    - Dom(document object model) adalah sebuah progamming intergace untuk web dokumen
    - Dom bukan bagian dari JS melainkan (Web API)
    - Mengubah konten Element bisa menggunakan Element.textcontent/Element.innerHTML
    - etc

#### Selecting Elements

    - document.getElementsByTagName(); (mencari element sesuai tagname)
    - Document.getElementsByid(); (mencari sesuai dengan id name)
    - Document.getElementsByClassName(); (mencari elemtn class name)
    - Document.getElementsByName(); (mencari element dari name atribut)
    -  etc

#### Dom Traversing Elements

    **Traversing downwards**

    - Elements.querySelector
    - Elements.querySelectorALL
    - Children

    **Traversing upwards**
    - parentElements
        const fli = document.querySelector(‘li’)
        cons list = fli.parentElement
    - closest
        cons list = element.closest(selector)

    **Traversing sideways**
    - nextElementSibling
        const ne = Node.nextElementSibling
    - previousElementSibling

## Day 4 (29/09/2022)

#### Dom Manipulating Elements

    Sebelum itu kita harus membuat div di html dengan class content,setelah itu menulis code dibawah ini di file js,adpun penjelasan setiap codenya sudh di comment

    let  bljr = document.createElement('p'); //membuat tag p
    bljr.innerText="haloo ini dari JS" //memberikan isi p
    bljr.className ="coba"  //tag p diberikan class name coba
    let content = document.querySelector(' .content') //mencari class content
    content.appendChild(bljr)  //menampilkan ke browser // menambahkan p ke div

#### Dom Manipulating Styles

    - Nama.style.color =”black” (merubah warna dari nama)
    - Nama.style.border (merubah border dari nama)
    - Nama.style.padding (merubah padding dari nama)
    - Nama.style.backgroundColor (merubah background calor

    Intinya jika ingin manipulating style kita bisa melakukan selecting element terlebih dahulu setelah itu nama.style.tindakan apa yang mau di manipulating

## Day 5 (30/09/2022)

#### Dom Events

    - Element.addEventListener(“event”)
        Bisa dihilangkan,bisa memiliki argumen tambahan dan beberapa event listener yang sama untuk 1 element
    - EventListener-Click
        Dapat memanipulasi jika sebuah object diclick seperti tombol,gambar hingga teks itu sendiri
    - EventListener- Blur
        Blur merupakan lawan dari focus dimana sebuah element kehilang focus missal user click mouse di luar element tersebut atau user click tab untuk berpindah element
    - EventListener- From Submission
        Kita bisa menambahkan Event listener untuk menerima inputan adri form pembahasan lebih mendetail dibagian dom form

#### Dom Forms

    Berfungsi untuk memanipulasi Forms,adapun contoh code dan penjelasannya dibawah ini

    //Dibawah ini mengambil element yang dibutuhkan
    let loginform = document.querySelector("#sign-in")
    let username=document.getElementById('username')
    let password=document.getElementById('password')
    let pesan = document.getElementById('pesan')

    //Membuat eventListener untuk manipulasi form
    loginform.addEventListener("submit",(event) => {
        event.preventDefault() //biar tidak auto refresh

    //Mengecek apakah username dan password sudh bisa diambil
        console.log(username.value)
        console.log(password.value)

    //Contoh Membuat password dan username (nantinya bisa ditaruh di database)
        let user = {
            username : "Haf",
            password : "123"
        }

        //mengecek apakh user dan pass yg dimasukkan sama dengan data
        if(user.username == username.value) {
            pesan.innerHTML="Berhasil login" //memberitahu berhasil login
            pesan.style.color= "green" //style manipulation agar menarik
        }
        else {
            pesan.innerHTML="Maaf password/Username anda salah!"
            pesan.style.color= "rgb(247, 9, 9)"
        }
        //Pilihan cara untuk mereset ulang form Ketika di submit
        // let userlogin = {
        //     username : username.value,
        //     password : password.value
        // }



        //Membersihkan form 1
        // loginform.reset()

        //membersihkan form 2
        username.value=""
        password.value=""
    })
