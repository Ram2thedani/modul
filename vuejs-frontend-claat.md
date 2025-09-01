id: vuejs-frontend
summary: Tutorial membangun aplikasi frontend menggunakan Vue.js
authors: Ramdani
categories: web, vuejs
environments: Web
status: Published
feedback link: https://github.com/ram2thedani

# Membangun aplikasi frontend menggunakan Vue.js

## Step 1: Apa itu VueJS?
VueJS merupakan sebuah framework JavaScript untuk membangun aplikasi web atau tampilan interface website agar lebih interaktif. VueJS dapat digunakan untuk membangun aplikasi berbasis user interface, seperti halaman web, aplikasi mobile, dan aplikasi desktop.

VueJS menyediakan beragam fitur yang membantu developer untuk mempermudah dalam pengembangan website, di antaranya:

- **Components**: Membuat elemen kustom pada HTML yang dapat digunakan secara berulang-ulang.
- **Computed properties**: Membantu pengguna untuk melihat perubahan pada elemen user-interface tanpa menambah kode.
- **Data binding**: Memanipulasi dan memberikan values pada atribut HTML menggunakan `v-bind`.
- **Directives**: Action bawaan seperti `v-if`, `v-show`, `v-else`, `v-on`, `v-bind`, dan `v-model`.
- **Event handling**: Menambahkan atribut ke elemen DOM (`v-on`) agar website lebih interaktif.
- **Lightweight**: Script lebih sederhana namun tetap powerful dan cepat.
- **Routing**: Menghubungkan antar halaman dalam aplikasi single-page.
- **Templates**: Menghubungkan DOM dengan data instance.
- **Virtual DOM**: Replika DOM untuk me-review perubahan sebelum diterapkan.
- **Watchers**: Menangani perubahan data agar kode lebih sederhana.

---

## Step 2: Persiapan project
Pastikan di VS Code sudah terinstal ekstensi **Volar** dan **Vue (official)**.

---

## Step 3: Buka direktori
1. Buka direktori/folder untuk menyimpan project.
2. Klik address bar → ketik `cmd` → tekan Enter.
3. Jalankan perintah berikut:

```bash
npm create vite@latest nama-project
```

Gunakan nama project misalnya `aplikasi-api-vue`.

- Pilih **Vue**  
- Pilih **TypeScript**  
- Ikuti instruksi setup, lalu jalankan perintah yang ditampilkan.  

Jika berhasil, buka link yang diberikan dan akan muncul tampilan awal Vue.

---

## Step 4: Struktur Folder
1. Kembali ke jendela CMD, hentikan aplikasi dengan `Ctrl+C`.
2. Buka project di VS Code dengan:

```bash
code .
```

3. Buat struktur folder seperti berikut di dalam `src`:

```
src/
 ┣ models/
 ┣ services/
 ┣ views/
```

---

## Step 5: Setup Project

### 1. Membuat Model
Buat file `src/models/Siswa.ts`:

```ts
export interface Siswa {
  id: number
  nama: string
  kelas: string
  jenis_kelamin: string
  alamat: string
}
```

### 2. Membuat Service
Buat file `src/services/siswaService.ts`:

```ts
import type { Siswa } from "../models/Siswa"

const API_URL = "https://marhaspplg.my.id/api/siswa"

export async function getAllSiswa(): Promise<Siswa[]> {
  const res = await fetch(API_URL)
  const body = await res.json()
  return body.data as Siswa[]
}
```

### 3. Membuat View
Buat file `src/views/HomeView.vue`:

```vue
<script setup lang="ts">
import { ref, onMounted } from "vue"
import type { Siswa } from "../models/Siswa"
import { getAllSiswa } from "../services/siswaService"

const siswaList = ref<Siswa[]>([])

onMounted(async () => {
  siswaList.value = await getAllSiswa()
})
</script>

<template>
  <div>
    <h1>Daftar Siswa</h1>
    <div class="card-container">
      <div v-for="siswa in siswaList" :key="siswa.id" class="card">
        <p><strong>Nama:</strong> {{ siswa.nama }}</p>
        <p><strong>Kelas:</strong> {{ siswa.kelas }}</p>
        <p><strong>Jenis Kelamin:</strong> {{ siswa.jenis_kelamin }}</p>
        <p><strong>Alamat:</strong> {{ siswa.alamat }}</p>
      </div>
    </div>
  </div>
</template>
```

---

## Step 6: Styling & Finishing
Edit file `src/style.css`, tambahkan:

```css
.card {
  width: 100%;
  text-align: left;
  background: white;
  border-radius: 8px;
  padding: 1rem;
  box-shadow: 0 2px 6px rgba(0,0,0,0.2);
  transition: transform 0.2s ease-in-out;
}

.card-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-top: 1.5rem;
}

.card:hover {
  transform: translateY(-3px);
}
```

Lalu, edit `src/App.vue` agar hanya berisi:

```vue
<template>
  <HomeView />
</template>

<script setup lang="ts">
import HomeView from "./views/HomeView.vue"
</script>
```

---

## Step 7: Tips & Catatan
- Jangan menutup CMD selama server berjalan.
- Jalankan aplikasi dengan:

```bash
npm run dev
```

- Hentikan aplikasi dengan `Ctrl+C`, lalu ketik `Y` dan tekan Enter.
