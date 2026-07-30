# Bakula Puntik 🌾
**Sistem Informasi Manajemen Kependudukan, Fasilitas, dan Sosial Budaya Desa**

> **Bakula Puntik** adalah platform web sistem informasi desa modern dan *real-time* yang dirancang untuk mempermudah pengelolaan data kependudukan (Kartu Keluarga & Anggota), sarana dan prasarana umum (Fasilitas Desa), serta data sosial budaya (bahasa daerah, lembaga sosial, dan organisasi) berbasis **Firebase Realtime Database** dan **Tailwind CSS**.

---

## 🚀 Fitur Utama

1. **Autentikasi & Manajemen Sesi Admin**
   - Sistem login aman dengan validasi berbasis *local storage* dan hak akses administrator.
2. **Dashboard & Statistik Interaktif**
   - Menampilkan ringkasan data kependudukan secara *real-time*.
3. **Manajemen Kependudukan (`index-manajemen.html`)**
   - Pengelolaan data Kartu Keluarga (No. KK, RT/RW, Alamat) dan detail Anggota Keluarga secara lengkap (NIK, Tempat/Tanggal Lahir, Pendidikan, Pekerjaan, Golongan Darah, Status Perkawinan, Kewarganegaraan, Paspor/KITAP, hingga Nama Orang Tua).
   - Dilengkapi fitur pencarian instan, paginasi, dan desain responsif (mode kartu/accordion untuk perangkat seluler).
4. **Manajemen Fasilitas Desa (`fasilitas.html`)**
   - Pengelolaan sarana dan prasarana umum desa (Kategori: Pendidikan, Kesehatan, Ibadah, dll.) dengan filter dinamis dan *badge* indikator warna otomatis.
5. **Manajemen Sosial & Budaya (`sosbud.html`)**
   - Pengelolaan data identitas sosial dan kebudayaan desa (Kategori: Bahasa Daerah, Lembaga Sosial, Organisasi) dengan deskripsi dan pelabelan kategori interaktif.
6. **Pengaturan & Kustomisasi Tema Desa (`setting.html`)**
   - Konfigurasi profil desa (Nama Desa, Kode Pos, Luas Wilayah, Jumlah Penduduk, Deskripsi/Sejarah, dan Batas Wilayah Geografis).
   - **Fitur Dinamis Tema Warna:** Admin dapat mengganti tema warna aplikasi secara instan (*Blue, Emerald, Indigo, Rose, Amber, Purple*) yang langsung memperbarui seluruh tampilan antarmuka secara *real-time*.

---

## 🛠️ Teknologi yang Digunakan

* **Frontend Framework:** [Tailwind CSS](https://tailwindcss.com/) (via CDN)
* **Ikon:** [FontAwesome 6.4.0](https://fontawesome.com/)
* **Font:** Google Fonts (*Plus Jakarta Sans*)
* **Backend / Database:** [Firebase Realtime Database](https://firebase.google.com/) (Modular SDK v12)
* **Bahasa Pemrograman:** HTML5, JavaScript (ES6+ Modules)

---

## 📂 Struktur Direktori Proyek

```text
bakula-puntik/
│
├── index.html              # Halaman Beranda / Landing Page & Login Admin
├── index-admin.html        # Halaman Dashboard Utama Admin
├── index-manajemen.html    # Halaman Manajemen Kependudukan (KK & Anggota)
├── fasilitas.html          # Halaman Manajemen Fasilitas Desa
├── sosbud.html             # Halaman Manajemen Sosial & Budaya
└── setting.html            # Halaman Pengaturan Profil & Tema Warna Desa

```
---

## ⚙️ Konfigurasi Keamanan Database (Firebase Rules)

Pastikan aturan keamanan (Security Rules) pada Firebase Realtime Database Anda disesuaikan agar aplikasi dapat membaca dan menulis data dengan lancar:
```text
{
  "rules": {
    "users": {
      ".read": true,
      ".write": true,
      ".indexOn": ["username"]
    },
    "kartu_keluarga": {
      ".read": true,
      ".write": true,
      ".indexOn": ["no_kk", "kepala_keluarga"]
    },
    "fasilitas": {
      ".read": true,
      ".write": true,
      ".indexOn": ["jenis"]
    },
    "sosbud": {
      ".read": true,
      ".write": true,
      ".indexOn": ["jenis"]
    },
    "profil_desa": {
      ".read": true,
      ".write": true
    }
  }
}

```
---

## 💻 Cara Menjalankan Proyek
1. **Clone repository ini atau unduh seluruh file ke komputer Anda:**
```text git clone [https://github.com/username/bakula-puntik.git](https://github.com/username/bakula-puntik.git) ```
2. **Buka folder proyek di teks editor pilihan Anda (seperti VS Code).**
3. **Jalankan server lokal menggunakan ekstensi Live Server di VS Code atau buka langsung file index.html di browser web modern Anda.**
4. **Pastikan perangkat terhubung ke internet agar koneksi ke Firebase Realtime Database berjalan dengan baik.**

---

## 📝 Lisensi
> *Proyek ini dikembangkan untuk kebutuhan Sistem Informasi Desa dan keperluan akademis / profesional. Silakan digunakan dan dimodifikasi seperlunya.*
