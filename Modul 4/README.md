# Laporan Praktikum Modul 4: CSS (Cascading Style Sheets)

## Identitas Mahasiswa

- Nama: Muhammad Nouval Zacky
- NIM: 2405101081
- Kelas: 5E
- Mata Kuliah: Pemrograman Web Dasar
- Modul: 4 - CSS (Cascading Style Sheets)

## Daftar Isi

1. [Tujuan](#a-tujuan)
2. [Alat dan Bahan](#b-alat-dan-bahan)
3. [Dasar Teori Singkat](#c-dasar-teori-singkat)
4. [Langkah Persiapan](#d-langkah-persiapan)
5. [Hasil dan Pembahasan](#e-hasil-dan-pembahasan)
6. [Kesimpulan](#f-kesimpulan)
7. [Struktur Folder](#struktur-folder)

---

## A. Tujuan

1. Mengenal CSS (Cascading Style Sheet).
2. Mengenal struktur dasar CSS.
3. Mengenal konsep pembuatan CSS.
4. Mampu menerapkan kode CSS.

## B. Alat dan Bahan

1. Text editor (Visual Studio Code).
2. Web browser (Google Chrome).
3. Ekstensi Live Server (untuk membuka halaman di `http://127.0.0.1:5500`).

## C. Dasar Teori Singkat

CSS digunakan untuk mengatur tampilan objek HTML seperti teks, gambar, dan tabel, misalnya warna latar dan tulisan.

Komponen utama CSS:

| Komponen | Penjelasan |
|---|---|
| **Selector** | Elemen HTML yang akan diberi gaya. |
| **Property** | Aspek atau atribut yang ingin diatur. |
| **Value** | Nilai yang diberikan pada property. |
| **Declaration** | Bagian di dalam `{ }` yang berisi property dan value. |

Contoh:

```css
body {
  background: green;
}
```

Pada contoh di atas, `body` adalah selector, `background` adalah property, dan `green` adalah value.

CSS dapat diterapkan dengan tiga cara:

| Cara | Letak penulisan | Cakupan |
|---|---|---|
| **Inline** | Atribut `style` pada tag HTML | Satu elemen |
| **Embedded** | Tag `<style>` di dalam `<head>` | Satu halaman |
| **Linked** | File `.css` terpisah, dipanggil dengan `<link>` | Banyak halaman |

## D. Langkah Persiapan

Langkah ini berlaku untuk semua latihan di bawah.

1. **Buat folder kerja** bernama `modul4`, lalu di dalamnya folder `Latihan`. Folder ini menjadi tempat semua file latihan agar rapi.
2. **Buka folder `modul4` di VS Code** lewat menu *File → Open Folder*.
3. **Buat file HTML/CSS** untuk setiap latihan (klik kanan di panel Explorer → *New File*), lalu ketik kodenya.
4. **Simpan file** dengan `Ctrl + S`. Perubahan yang belum disimpan tidak akan terlihat di browser.
5. **Jalankan dengan Live Server**: klik kanan file HTML → *Open with Live Server*. Halaman terbuka di browser pada alamat `http://127.0.0.1:5500/...`.
6. **Ambil screenshot** tampilan browser, simpan di folder `screenshots/` dengan nama file yang sesuai (lihat tiap bagian di bawah).

---

## E. Hasil dan Pembahasan

### 1. Inline Style

**Langkah pengerjaan**

1. Buat file `Inline.html` di folder `Latihan`.
2. Tulis struktur dasar HTML (`<!DOCTYPE html>`, `<html>`, `<body>`).
3. Pada tag `<h1>`, tambahkan atribut `style="color:blue"`.
4. Simpan, lalu buka dengan Live Server.

**Kode program** (`Latihan/Inline.html`)

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 style="color:blue">This is a Blue Heading</h1>
  </body>
</html>
```

**Screenshot hasil**

![Hasil Inline Style](screenshots/01-inline.png)

> Ganti file `screenshots/01-inline.png` dengan screenshotmu sendiri (nama file harus sama).

**Penjelasan**

- `style="color:blue"` ditulis langsung di dalam tag `<h1>`, jadi disebut *inline style*.
- Property `color` diberi value `blue`, sehingga teks judul tampil berwarna biru.
- Cara ini hanya berlaku untuk **satu elemen** tempat atribut itu ditulis. Elemen lain tidak terpengaruh.

---

### 2. Embedded Style (Latihan 1)

**Langkah pengerjaan**

1. Buat file `Latihan1.html`.
2. Tambahkan tag `<style>` di dalam `<head>`.
3. Tulis aturan untuk selector `h1` dan `p` di dalam tag `<style>`.
4. Isi `<body>` dengan `<h1>` dan `<p>`, lalu simpan dan buka dengan Live Server.

**Kode program** (`Latihan/Latihan1.html`, salinannya juga ada di `Latihan/Embeded.html`)

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 {
        color:blue;
        font-family:verdana;
        font-size:300%;
      }
      p {
        color:red;
        font-family:courier;
        font-size:160%;
      }
    </style>
  </head>
  <body>
    <h1>Judul</h1>
    <p>Paragrap</p>
  </body>
</html>
```

**Screenshot hasil**

![Hasil Embedded Style](screenshots/02-embedded.png)

> Ganti file `screenshots/02-embedded.png` dengan screenshotmu sendiri.

**Penjelasan**

- Aturan CSS dideklarasikan di dalam tag `<style>` pada bagian `<head>`, sehingga berlaku untuk **semua elemen dengan tag yang sama** di halaman tersebut.
- Selector `h1`: `color:blue` membuat judul berwarna biru, `font-family:verdana` mengubah jenis huruf menjadi Verdana, dan `font-size:300%` membuat ukurannya 3 kali ukuran normal.
- Selector `p`: `color:red` membuat paragraf berwarna merah, `font-family:courier` memakai huruf Courier, dan `font-size:160%` membuat ukurannya 1,6 kali ukuran normal.

---

### 3. Linked Style

**Langkah pengerjaan**

1. Buat file `styles.css` di folder `Latihan` dan isi dengan aturan CSS.
2. Buat file `Index.html` di **folder yang sama**.
3. Panggil file CSS di dalam `<head>` dengan tag `<link rel="stylesheet" href="styles.css">`.
4. Simpan kedua file, lalu buka `Index.html` dengan Live Server.

**Kode program `Index.html`** (`Latihan/Index.html`)

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Ini bagian header</h1>
    <p>Ini adalah paragraph</p>
  </body>
</html>
```

**Kode program `styles.css`** (`Latihan/styles.css`)

```css
p {
  background : #FFD9D9;
  border-bottom : 4px solid red;
  padding-top : 15px;
  margin : -10px;
  display : none;
  width : auto;
  height : 35px;
  text-align : center;
  vertical-align : center;
}
#msg {
  color : #0000FF;
  font-weight : bold;
  font-size:12px;
}
#error {
  color : #FF1111;
  font-weight : bold;
  font-size:12px;
}
```

**Screenshot hasil**

![Hasil Linked Style](screenshots/03-linked.png)

> Ganti file `screenshots/03-linked.png` dengan screenshotmu sendiri.

**Penjelasan**

- Style ditulis di file terpisah (`styles.css`) lalu dipanggil di `<head>` dengan `<link rel="stylesheet" href="styles.css">`. Kedua file harus berada dalam satu folder agar `href` menemukannya.
- Selector `p` mengatur: latar `#FFD9D9` (merah muda), garis bawah merah setebal 4px, padding atas 15px, margin -10px, tinggi 35px, dan teks rata tengah.
- Namun `display : none` **menyembunyikan seluruh paragraf**. Karena itu teks "Ini adalah paragraph" tidak tampil di browser, hanya judul `<h1>` yang terlihat (lihat screenshot).
- Selector `#msg` dan `#error` adalah selector id yang mengatur warna, ketebalan, dan ukuran huruf. Keduanya tidak berpengaruh di halaman ini karena tidak ada elemen dengan id tersebut.
- Keuntungan linked style: satu file CSS bisa dipakai oleh banyak halaman HTML.

---

### 4. Style dengan Class (Latihan 2)

**Langkah pengerjaan**

1. Buat file `Latihan2.html`.
2. Di dalam `<style>`, tulis selector `p.error`.
3. Buat empat paragraf di `<body>`; beri `class="error"` pada paragraf kedua dan keempat.
4. Simpan dan buka dengan Live Server.

**Kode program** (`Latihan/Latihan2.html`)

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      p.error {
        color:green;
      }
    </style>
  </head>
  <body>
    <p>Ini Paragraph.</p>
    <p class="error">Ini paragraph setelan class error.</p>
    <p>Ini paragraph.</p>
    <p class="error">Ini paragraph setelan class error.</p>
  </body>
</html>
```

**Screenshot hasil**

![Hasil Style dengan Class](screenshots/04-class.png)

> Ganti file `screenshots/04-class.png` dengan screenshotmu sendiri.

**Penjelasan**

- Selector `p.error` hanya berlaku untuk tag `<p>` yang memiliki atribut `class="error"`.
- Hasilnya, paragraf kedua dan keempat tampil **hijau**, sedangkan paragraf pertama dan ketiga tetap berwarna default (hitam).
- Class bisa dipakai berulang kali pada banyak elemen.

---

### 5. Pentabelan Menggunakan CSS Id

**Langkah pengerjaan**

1. Buat file `Tabel_CSS_Id.html`.
2. Tulis aturan CSS untuk `table, th, td` (border), `th, td` (padding dan perataan), dan `table#t01` (lebar dan warna latar).
3. Buat dua tabel di `<body>`: tabel pertama tanpa id, tabel kedua dengan `id="t01"`.
4. Simpan dan buka dengan Live Server.

**Kode program** (`Latihan/Tabel_CSS_Id.html`)

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid black;
        border-collapse: collapse;
      }
      th, td {
        padding: 5px;
        text-align: left;
      }
      table#t01 {
        width: 100%;
        background-color: #f1f1c1;
      }
    </style>
  </head>
  <body>
    <table style="width:100%">
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Rusi</td>
        <td>Anandi</td>
        <td>17</td>
      </tr>
    </table>
    <br>
    <table id="t01">
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Novya</td>
        <td>Selena</td>
        <td>18</td>
      </tr>
    </table>
  </body>
</html>
```

**Screenshot hasil**

![Hasil Tabel dengan Id](screenshots/05-tabel-id.png)

> Ganti file `screenshots/05-tabel-id.png` dengan screenshotmu sendiri.

**Penjelasan**

- `table, th, td` memberi border hitam 1px pada tabel, sel header, dan sel data. `border-collapse: collapse` menyatukan garis border yang berdekatan menjadi satu garis.
- `th, td` memberi jarak dalam (`padding`) 5px dan teks rata kiri.
- `table#t01` memakai **id**, sehingga hanya berlaku untuk tabel yang memiliki `id="t01"` (tabel kedua): lebar 100% dan latar kuning pucat `#f1f1c1`.
- Tabel pertama memakai inline style `width:100%`, jadi lebarnya penuh tetapi tanpa warna latar.
- Perbedaan kedua tabel menunjukkan bahwa id menargetkan **satu elemen tertentu**.

---

### 6. Style Tabel Menggunakan Class

**Langkah pengerjaan**

1. Buat file `Tabel_Class.html` (pastikan berekstensi `.html` agar bisa dibuka di browser).
2. Tulis aturan CSS untuk `table, th, td` dan `table.names`.
3. Buat dua tabel: tabel pertama tanpa class, tabel kedua dengan `class="names"`.
4. Simpan dan buka dengan Live Server.

**Kode program** (`Latihan/Tabel_Class.html`)

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid black;
        border-collapse: collapse;
      }
      table.names {
        width: 100%;
        background-color: #f1f1c1;
      }
    </style>
  </head>
  <body>
    <table style="width:100%">
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Novya</td>
        <td>Selena</td>
        <td>18</td>
      </tr>
    </table>
    <br>
    <table class="names">
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Novya</td>
        <td>Selena</td>
        <td>18</td>
      </tr>
    </table>
  </body>
</html>
```

**Screenshot hasil**

![Hasil Tabel dengan Class](screenshots/06-tabel-class.png)

> Ganti file `screenshots/06-tabel-class.png` dengan screenshotmu sendiri.

**Penjelasan**

- Prinsipnya sama dengan nomor 5, tetapi memakai **class**.
- `table.names` berlaku untuk semua tabel yang memiliki `class="names"`, sehingga tabel kedua berlatar `#f1f1c1` dengan lebar 100%. Tabel pertama tetap polos.
- Perbedaan utama: **id bersifat unik** (satu elemen, ditulis `#nama`), sedangkan **class boleh dipakai pada banyak elemen** sekaligus (ditulis `.nama`).

---

## F. Kesimpulan

1. CSS berfungsi mengatur tampilan elemen HTML, dengan komponen selector, property, value, dan declaration.
2. Ada tiga cara menerapkan CSS: inline (satu elemen), embedded (satu halaman), dan linked (banyak halaman melalui file `.css` terpisah).
3. Selector class (`.nama`) dapat dipakai pada banyak elemen, sedangkan selector id (`#nama`) ditujukan untuk satu elemen tertentu.
4. CSS dapat dipakai untuk menata tabel, misalnya border, padding, perataan teks, lebar, dan warna latar.

---

## Struktur Folder

```
modul4/
├── README.md
├── Latihan/
│   ├── Inline.html
│   ├── Embeded.html
│   ├── Latihan1.html
│   ├── Index.html
│   ├── styles.css
│   ├── Latihan2.html
│   ├── Tabel_CSS_Id.html
│   └── Tabel_Class.html
└── screenshots/
    ├── 01-inline.png
    ├── 02-embedded.png
    ├── 03-linked.png
    ├── 04-class.png
    ├── 05-tabel-id.png
    └── 06-tabel-class.png
```

## Cara Menjalankan

1. Buka folder `modul4` di VS Code.
2. Klik kanan salah satu file HTML di folder `Latihan`, pilih **Open with Live Server**.
3. Atau cukup klik dua kali file HTML tersebut (semua latihan tidak memerlukan server).
