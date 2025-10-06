id: restapi-laravel-part1
summary: Belajar Rest API dengan Laravel Part 1
categories: laravel, php, backend
status: Published
authors: Ramdani
Feedback Link: https://github.com/username/repo/issues

# Rest API dengan Laravel Part 1

Panduan ini menjelaskan langkah demi langkah pengenalan Laravel, persiapan project, membuat project, struktur folder, menyalakan aplikasi, hingga konfigurasi database.

## Step 1 — Pengenalan Laravel

Bayangkan kita ingin membangun sebuah rumah. Tanpa alat, kita harus membuat semuanya dari nol—menyiapkan pondasi, memotong kayu, menyusun bata, hingga merancang kabel listrik sendiri. Pekerjaan itu tentu sangat memakan waktu dan rawan kesalahan.

Begitu pula dalam dunia pemrograman web. Jika kita membangun aplikasi dari nol hanya dengan PHP murni, maka kita harus memikirkan semua detail kecil: bagaimana menangani request dari pengguna, mengatur database, membuat sistem keamanan, hingga mengelola tampilan. Proses ini bisa membuat kita kewalahan.

Di sinilah **Laravel** hadir. Laravel adalah framework backend berbasis PHP yang menyediakan “kerangka kerja” siap pakai untuk mempercepat dan memudahkan proses pengembangan aplikasi web. Framework ini ibarat peralatan modern dalam membangun rumah: ada cetakan pondasi, alat ukur, hingga sistem kelistrikan standar. Kita tidak perlu lagi merancang semuanya dari awal, cukup mengikuti pola yang sudah terbukti aman dan efisien.

Peran Laravel sebagai framework backend sangat penting. Ia bertugas mengelola logika di balik layar—bagian yang tidak langsung terlihat oleh pengguna. Mulai dari mengatur bagaimana data disimpan dan diambil dari database, mengatur alur request dan response, memastikan keamanan melalui autentikasi, hingga menyediakan API yang bisa diakses oleh aplikasi lain.

Selain itu, Laravel juga terkenal dengan sintaks yang elegan dan mudah dibaca. Fitur-fiturnya seperti **Routing, Eloquent ORM, Middleware, dan Blade Templating Engine** membuat pengembangan lebih terstruktur dan rapi.

Dengan memahami Laravel, mahasiswa atau siswa tidak hanya belajar bagaimana menulis kode, tetapi juga bagaimana membangun aplikasi dengan pola pikir seorang arsitek perangkat lunak—membangun sesuatu yang kuat, teratur, dan berkelanjutan.

---

## Step 2 — Persiapan Project

Untuk memulai project Laravel, ada beberapa aplikasi yang harus diinstall, di antaranya:

- [Laragon](https://github.com/leokhoa/laragon/releases/download/6.0.0/laragon-wamp.exe)
- [Composer](https://getcomposer.org/Composer-Setup.exe)
- [Git](https://github.com/git-for-windows/git/releases/download/v2.51.0.windows.2/Git-2.51.0.2-64-bit.exe)
- [PHP (minimal versi 8.2)](https://windows.php.net/downloads/releases/php-8.2.29-nts-Win32-vs16-x64.zip)

Untuk cara install masing-masing aplikasi bisa mengikuti tutorial (link menyusul).

---

## Step 3 — Membuat Project

Jika semua aplikasi sudah terinstall, buka direktori/folder untuk menyimpan project.

1. Klik **address bar** atau tekan `F4` → ketik `cmd` → tekan `Enter`.
2. Jalankan perintah berikut:

```bash
composer create-project laravel/laravel nama_project
```

3. Setelah download selesai, masuk ke folder project:

```bash
cd nama_project
```

4. Buka dengan Visual Studio Code:

```bash
code .
```

---

## Step 4 — Struktur Folder

Laravel memiliki beberapa direktori penting:

1. **app/Http/Controllers**  
   Tempat logika utama aplikasi disimpan. Controller adalah penghubung antara Model (data) dan View (tampilan).

2. **app/Models**  
   Berhubungan langsung dengan database menggunakan Eloquent ORM. Model ibarat aktor yang membawa data nyata ke dalam aplikasi.

3. **resources/views**  
   Menyimpan file tampilan (view). Laravel menggunakan **Blade Templating Engine** untuk menulis HTML yang dinamis.

4. **routes**  
   Tempat mendefinisikan URL aplikasi dan logika yang dijalankan. Contoh: URL `/siswa` diarahkan ke `SiswaController@index`.

5. **File .env**  
   Menyimpan konfigurasi rahasia seperti nama database, username, password, dan port. File ini biasanya tidak diunggah ke repository publik.

---

## Step 5 — Mengetes Aplikasi

1. Jalankan service di **Laragon** (klik _Start All_).
2. Di terminal, jalankan:

```bash
php artisan serve
```

3. Klik link yang disediakan.

> Catatan: Saat pertama kali menjalankan biasanya muncul error karena database belum dikonfigurasi.

---

## Step 6 — Konfigurasi Database

1. Buat database baru di **phpMyAdmin**.
2. Buka file `.env` di VSCode.
3. Ubah bagian konfigurasi database menjadi:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nama_database_anda
DB_USERNAME=root
DB_PASSWORD=
```

4. Simpan file `.env`.
5. Refresh halaman web. Jika aplikasi tampil normal, berarti Laravel siap digunakan.
