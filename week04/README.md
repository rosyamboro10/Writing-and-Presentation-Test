# Writing And Presentation Test Week 04

## Day 16
### JavaScript Intermediate - Asynchronus Fetch & Async Await


#### JS Asing Await

* Async - await adalah salah satu fitur baru dari javascript yang digunakan untuk menangani hasil dari sebuah Promise.
* Sedangkan await berfungsi untuk menunda sebuah kode dijalankan sampai proses asynchronous berhasil.
* Data yang ada, misalnya di E-commerce berasal dari server.
* Web Application meminta data dari server, kemudian server mengambil data dari database. Databasec memberikan data ke server baru server memberikan data ke server.
* Perantara Web Application dengan server dan database adalah API.
* Data dalam API memiliki type JSON.
* JSON ( JavaScript Object notion).
* Server bisa diakses semua device karena berbentuk API.
```
// Promis Creation
let nonton = (kondisi) => {
    return new Promise((resolve, reject) => {
        if (kondisi == "jalan"){
            resolve("nonton terpenuhi")
        }
        reject("batal nonton")
    })
}
```
```
// promise
// namaPromise.then().catch()
nontn("jalan")
.then(result => {
    console.log(result);
}).catch(err => {
    console.log(err)
})
```
```
// async await
// buat async function
async function asyncNonton(){
    try{
        let result = await nonton()
        console.log(result);
    } catch (error){
        console.log(error)
    }
}

asyncNOnton()
```

#### JS Fetch 

* Fetch adalah native web API untuk melakukan HTTP calls dari external network.
* fetch() memiliki parameter utama yaitu URL/endpoint API, dan parameter kedua yaitu options, options ini berisi method, headers dan body. Tergantung keinginan kita.
```
const URL = " https://....."
const options = {
    method: "GET" / "POST",
    headers: {
        "COntent-type": "application/json"
    },
    body: user
}

fetch(URL, options)
```
* Contoh function untuk mengambil data dari API menggunakan fetch(), Promise based.
```
const getDataAPI = () => {
    // deklarasi API endpoint
    const API ="https://...."
    // buat option method untuk fecth ()
  const option = {
    method: "GET"
  }
  // jalankan fetch dengan api dan option yang kita buat
fetch(API, option)
// response pertama, kita ambil data json
.then(response => response.json())
result => console.log)(result())
// terjadi kesalahan kita tangkap errornya
.catch(error => console.log(error, "ERROR))
```

* Contoh function untuk mengambil data dari API menggunakan fetch(), Dengan Async Await..
```
const getDataAPIwithAsync = async () => {
    const API = "https://..."
    const option = {
        method: "GET"
    }

    let response = await fetch(API, option)
    response = await response.json()
    console.log(response);
}
getDataAPIwithAsync()
```

* Cara menangkap bisa menggunakan .catch() dan .then()
dan async await.
* for Each diloping sampai akhir.

## Day 17
### Git dan Github Lanjutan

#### Kolaborasi

* Buat Organisasi dengan pilih new organization

![img](Gambar/Screenshot%20(13).png)

* pilih Free

![img](Gambar/Screenshot%20(14).png)

* Create Organization

![img](Gambar/Screenshot%20(15).png)

* pilih next

![img](Gambar/Screenshot%20(16).png)

* Tuliskan partner colab anda

![img](Gambar/Screenshot%20(17).png)

* Masukkan password

![img](Gambar/Screenshot%20(18).png)

* Buat repository
* Ganti brance dengan dev
* Beri label (optional bisa tidak dilakukan)

* Tahapan yang dilakukan setiap anggota :
    - Setiap anggota wajib melakukan clone
    - melakukan pull setiap akan mengerjakan
    - Anggota tim membuat brance dari dev
        - > git switch dev 
        - > git brance A-login
        - > git switch A-login

* git swicth untuk berpindah brance / git checkout
* brance, jalur / jarak
* main / brance utama -> digunakan untuk tahap production ( dapat diakses banyak orang)
* ketika push dengan git push -u oringin A-login (menggunakan setting awal brance)

* Jika sebagai team leader :
    - melakukan pull request -> permintaan menggabungkan brance 1 dengan yang lain.
    - melihat pekerjaan anggot apa sudah benar, kemudian memberi label (Optional).
* Jika sebagai anggota : memberikan assigment ke team leader
* git clone sudah termasuk git remote
* git merce dev menghubungkan brance dev dengan brance lain ( untuk mengambil data terbaru)
* conflik terjadi ketika lebih dari satu orang mengubah file yang sama
* jika conflik harus melakukan git merge dev untuk mengambil data terbaru


## Day 18
### Responsive Web

* Responsi Web Design adalah bertujuan membuat desain web kita dapat diakses dalam device apapun
* Device yang umumny digunakan adalah laptop/pc, smartphone. dan tablet
* Melihat responsive web dapat menggunakan inspect kemudian kita tarik bagian kiri apakah mengikuti atau tidak. atau bisa menggunakan toggle device toolbar bisa juga digeser atau menentukan ingin melihat responsive dengan device tertentu atau ukuran tertentu.
* Viewport adalah area halaman web yang terlihat oleh pengguna.
* HTML 5 memperkenalkan metode untuk memungkinkan desainer web mengambil kendali atas viewport, melalui tag <meta>. 
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
* Bagian width=device-width mengatur lebar halaman untuk mengikuti lebar layar perangkat (yang akan bervariasi tergantung pada perangkat).

* Bagian initial-scale=1.0 menyetel tingkat zoom awal saat halaman pertama kali dimuat oleh browser.

* Ukuran Konten ke Viewport. Beberapa aturan tambahan yang harus diikuti:
1. JANGAN gunakan elemen lebar tetap yang besar
2. JANGAN biarkan konten bergantung pada lebar area pandang tertentu 
3. Gunakan kueri media CSS untuk menerapkan gaya yang berbeda untuk layar kecil dan besar 

* CSS memiliki beberapa unit berbeda untuk menyatakan panjang.
* Banyak properti CSS mengambil nilai "panjang", seperti lebar, margin, padding, ukuran font, dll.
* Panjang adalah angka yang diikuti oleh satuan panjang, seperti 10px, 2em, dll.
* Media query adalah teknik CSS yang diperkenalkan di CSS3.
* Ini menggunakan aturan @media untuk menyertakan blok properti CSS hanya jika kondisi tertentu benar.
```
@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```
* Sebelum modul Tata Letak Flexbox, ada empat mode tata letak:

1. Blokir, untuk bagian di halaman web
2. Sebaris, untuk teks
3. Tabel, untuk data tabel dua dimensi
4. Diposisikan, untuk posisi eksplisit suatu elemen
Modul Tata Letak Kotak Fleksibel, memudahkan perancangan struktur tata letak responsif yang fleksibel tanpa menggunakan float atau positioning.

* Untuk mulai menggunakan model Flexbox, Anda harus mendefinisikan wadah fleksibel terlebih dahulu.

![img](Gambar/Screenshot%20(20).png)

* Elemen di atas mewakili wadah fleksibel (area biru) dengan tiga item fleksibel.
```
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```