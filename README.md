<h2>1. Pengertian Synchronous</h2>
Synchronous adalah proses menjalankan kode JavaScript secara berurutan, dari perintah pertama sampai selesai, kemudian lanjut ke perintah berikutnya.

Jadi, jika ada proses yang membutuhkan waktu, proses setelahnya harus menunggu sampai proses tersebut selesai.
```javascript
Contoh:
console.log("Proses 1");
console.log("Proses 2");
console.log("Proses 3");
```
Hasil:
Proses 1
Proses 2
Proses 3

<h2>2. Pengertian Asynchronous</h2>

Asynchronous adalah proses menjalankan kode yang memungkinkan JavaScript melanjutkan proses lain tanpa harus menunggu proses sebelumnya selesai.

Biasanya digunakan untuk proses yang membutuhkan waktu, seperti mengambil data dari server, timer, atau membaca file.
```javascript
Contoh:

console.log("Proses 1");

setTimeout(() => {
    console.log("Proses 2");
}, 2000);

console.log("Proses 3");
```

Hasil:
Proses 1
Proses 3
Proses 2
Proses 2 muncul terakhir karena menunggu selama 2 detik.

<h2>3. Perbedaan Synchronous dan Asynchronous</h2>
Synchronous	Asynchronous
Berjalan secara berurutan	Bisa berjalan tanpa menunggu
Proses berikutnya menunggu proses sebelumnya	Proses lain dapat berjalan terlebih dahulu
Cocok untuk proses sederhana	Cocok untuk proses yang membutuhkan waktu
Dapat membuat program menunggu	Program tetap dapat menjalankan tugas lain

Sederhananya:

Synchronous = tunggu sampai selesai.
Asynchronous = lanjut dulu, tunggu hasilnya nanti.

<h2>4. Contoh Synchronous dan Asynchronous</h2>
Synchronous:=>

```javascript
console.log("Mulai");

let nama = "Ahmad";

console.log("Nama:", nama);
console.log("Selesai");
```
Output:
Mulai
Nama: Ahmad
Selesai

Asynchronous:=>
```javascript~
console.log("Mulai");

setTimeout(() => {
    console.log("Data selesai diproses");
}, 2000);

console.log("Selesai");
```

Output:
Mulai
Selesai
Data selesai diproses

<h2>5. Tiga Cara Menulis Kode Asynchronous di JavaScript</h2>
A. Callback

Callback adalah fungsi yang diberikan sebagai argumen ke fungsi lain dan akan dijalankan setelah proses tertentu selesai.
```javascript
setTimeout(() => {
    console.log("Proses selesai");
}, 2000);
```
B. Promise

Promise digunakan untuk menangani hasil dari proses asynchronous. Promise memiliki kondisi seperti pending, fulfilled, dan rejected.
```javascript
let data = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Data berhasil diambil");
    }, 2000);
});

data.then((hasil) => {
    console.log(hasil);
});
C. Async/Await

Async/Await membuat kode asynchronous terlihat lebih sederhana dan mudah dibaca.

function ambilData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("Data berhasil diambil");
        }, 2000);
    });
}

async function tampilkanData() {
    let hasil = await ambilData();
    console.log(hasil);
}

tampilkanData();
```