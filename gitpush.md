id: tutorial-push-git
summary: Panduan mengunggah proyek ke GitHub menggunakan Visual Studio Code.
categories: git, github, vscode
status: Published
authors: Ramdani
Feedback Link: https://github.com/username/repo/issues

# Cara Mengunggah Proyek ke GitHub Menggunakan Visual Studio Code

Panduan ini menjelaskan langkah demi langkah untuk membuat repository di GitHub dan mengunggah proyek menggunakan Git di Visual Studio Code.

## Step 1 — Buat Repository

1. Buka [GitHub](https://github.com) dan buat repository baru (kosong).
2. Salin URL repository tersebut, bisa melalui **address bar** atau tombol **Copy** yang ada di bagian bawah halaman.

## Step 2 — Buka Proyek

1. Buka proyek Anda di **Visual Studio Code**.
2. Buka **Terminal** (`View > Terminal`).
3. Ketik perintah berikut:
   ```bash
   git init
   ```
4. Jika muncul tulisan:
   ```
   Initialized empty Git repository
   ```
   dan ada huruf `U` di sebelah file proyek, berarti repository lokal berhasil dibuat.

## Step 3 — Lakukan Autentikasi

Masukkan perintah berikut untuk mengatur email Git:

```bash
git config user.email "email_akun_anda"
```

Ganti `"email_akun_anda"` dengan email yang terdaftar di akun GitHub Anda.

## Step 4 — Hubungkan dengan Remote Repository

Ketik perintah berikut:

```bash
git remote add origin <link_repository_yang_dicopy>
```

Ganti &lt;link_repository_yang_dicopy&gt; dengan URL repository GitHub yang sudah Anda salin tanpa menggunakan kurung &lt;&gt;.

## Step 5 — Lakukan Staging

Ketik perintah berikut:

```bash
git add .
```

Tunggu hingga semua huruf `U` berubah menjadi `A` atau terminal kembali siap menerima perintah baru.

## Step 6 — Lakukan Commit

Ketik perintah berikut:

```bash
git commit -m "Tulis pesan commit di sini"
```

Jika commit berhasil, tanda huruf `A` pada file proyek akan hilang.

## Step 7 — Lakukan Push

Jika proyek belum pernah di-_push_ sebelumnya, ketik:

```bash
git push -u origin master
```

- Jika muncul pop-up autentikasi, pilih **Sign in with browser**.
- Browser akan terbuka untuk konfirmasi otorisasi, klik tombol hijau **Authorize**.
- Jika browser menampilkan halaman kosong, biarkan saja.
- Pastikan proses _push_ selesai di terminal Visual Studio Code, lalu periksa repository di GitHub untuk memastikan file sudah terunggah.

## Catatan Tambahan

- **Huruf U** = _Untracked_ file (belum dimasukkan ke staging).
- **Huruf A** = _Added_ file (sudah di staging, siap di-commit).
- Gunakan commit message yang jelas agar mudah melacak perubahan di masa depan.
