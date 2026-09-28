# 🏛️ SPMB UNS Solo — Portal Informasi & Seleksi Penerimaan Mahasiswa Baru

[![Website Live](https://img.shields.io/badge/Website-spmb--uns--solo.web.app-00AFEF?style=for-the-badge&logo=google-chrome&logoColor=white)](https://spmb-uns-solo.web.app)
[![Hosted On Firebase](https://img.shields.io/badge/Hosted%20On-Firebase-ffca28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088ff?style=for-the-badge&logo=github-actions&logoColor=white)](https://github.com/vinsensiusarko/spmb-uns/actions)
[![Bootstrap](https://img.shields.io/badge/Framework-Bootstrap%203-7952b3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![HTML5 & CSS3](https://img.shields.io/badge/Tech-HTML5%20%26%20CSS3-e34f26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/)

Portal web frontend modern dan responsif untuk **Seleksi Penerimaan Mahasiswa Baru (SPMB) Universitas Sebelas Maret (UNS) Surakarta / Solo**. Portal ini dirancang untuk menyajikan informasi penerimaan mahasiswa baru secara terpadu, interaktif, dan mudah diakses oleh calon mahasiswa di berbagai jenjang pendidikan.

---

## 🌟 Fitur Utama (Key Features)

- 🎥 **Video Hero Header & Slider Revolution**: Banner utama dengan latar belakang video profil kampus UNS (`assets/video/VID UNS.mp4`) yang dipadukan dengan teks animasi dan layer interaktif berbasis Slider Revolution.
- 🎓 **Navigasi Multi-Jenjang Pendidikan**: Informasi jalur masuk lengkap untuk program Sarjana (S1), Diploma / Vokasi (D3/D4), Pascasarjana (S2/S3), Profesi, dan PPDS (Program Pendidikan Dokter Spesialis).
- 📊 **Program Studi & Daya Tampung**: Halaman khusus (`program-studi.html`) yang menyajikan daftar fakultas, program studi, jenjang akreditasi, dan daya tampung penerimaan mahasiswa baru.
- 📅 **Informasi Digital & Rekap Jadwal**: Timeline seleksi terpadu (`informasi-jadwal.html`) mulai dari pendaftaran, pembayaran, ujian seleksi, hingga pengumuman kelulusan.
- 📰 **Portal Berita & Pengumuman**: Publikasi artikel, rilis pers, panduan pendaftaran (PDF), dan pembaruan regulasi SPMB UNS terkini (`berita.html`).
- 📱 **Desain Responsif & Mobile-Friendly**: Navigasi sticky menu yang otomatis menyesuaikan tampilan ponsel, tablet, dan desktop dengan dukungan hamburger drawer menu.
- 🚀 **Automated CI/CD Deployment**: Otomatisasi deploy ke Firebase Hosting melalui GitHub Actions (`firebase-hosting-merge.yml`) yang dilengkapi opsi manual trigger (`workflow_dispatch`).

---

## 🛠️ Tech Stack

| Kategori | Teknologi / Library |
| :--- | :--- |
| **Markup & Struktur** | HTML5 Semantik |
| **Styling & Tampilan** | CSS3, Bootstrap 3.x, Responsive Grid, Font Awesome, Ionicons, Montserrat Google Fonts |
| **Interaktivitas & Animasi** | JavaScript (ES5/ES6), jQuery, Slider Revolution 4.x, Owl Carousel, FlexSlider, WOW.js |
| **Hosting & Infrastruktur** | Google Firebase Hosting |
| **CI/CD Otomasi** | GitHub Actions (`action-hosting-deploy`) |

---

## 📂 Struktur Repository

Seluruh kode sumber dan aset web terpusat di dalam folder `public/` sesuai standar arsitektur Firebase Hosting:

```text
spmb-uns-solo/
├── .firebase/                  # Cache build lokal Firebase
├── .github/
│   └── workflows/
│       ├── firebase-hosting-merge.yml         # Deployment otomatis ke live channel saat push ke main
│       └── firebase-hosting-pull-request.yml  # Deployment ke preview channel saat Pull Request
├── .vscode/                    # Pengaturan workspace editor VS Code
├── public/                     # Seluruh file produksi yang di-host di Firebase
│   ├── assets/
│   │   ├── css/                # Bootstrap, stylesheet animasi, dan custom CSS
│   │   ├── fonts/              # Webfont icons (FontAwesome, Glyphicons, Ionicons, Montserrat)
│   │   ├── images/             # Logo UNS, ikon menu interaktif, infografis, dan thumbnail
│   │   ├── js/                 # Library vendor (jQuery, Bootstrap, Owl Carousel, FlexSlider)
│   │   ├── rs-plugin/          # Aset & styling Slider Revolution
│   │   └── video/              # Video profil latar belakang kampus UNS (VID UNS.mp4)
│   ├── 404.html                # Halaman penanganan error 404 kustom
│   ├── berita.html             # Halaman portal berita & pengumuman
│   ├── blank-page.html         # Template layout halaman umum
│   ├── index.html              # Halaman beranda utama portal SPMB UNS
│   ├── informasi-jadwal.html   # Halaman jadwal seleksi & informasi digital
│   ├── program-studi.html      # Halaman daftar program studi & daya tampung
│   └── sample-page.html        # Halaman sampel demo komponen UI
├── .firebaserc                 # Konfigurasi ID project Firebase (vinsensiusarko)
├── .gitignore                  # Daftar file/folder yang diabaikan git
├── firebase.json               # Konfigurasi target site Firebase Hosting (spmb-uns-solo)
└── README.md                   # Dokumentasi resmi repository
```

---

## 💻 Menjalankan Secara Lokal

Karena proyek ini merupakan situs web berbasis statis (HTML/CSS/JS), kamu tidak memerlukan proses build yang rumit:

### Opsi 1: Menggunakan Ekstensi VS Code Live Server
1. Buka folder proyek di Visual Studio Code.
2. Klik kanan pada file `public/index.html`.
3. Pilih **"Open with Live Server"**.

### Opsi 2: Menggunakan Python Web Server
Jalankan perintah berikut di terminal:
```bash
python -m http.server 8080 --directory public
```
Lalu buka browser di `http://localhost:8080`.

### Opsi 3: Menggunakan Firebase Emulator
Jika Firebase CLI sudah terpasang:
```bash
firebase emulators:start --only hosting
```

---

## 🚀 Deployment ke Firebase Hosting

### 1. Deployment Otomatis (CI/CD)
Setiap perubahan yang di-*push* atau di-*merge* ke branch `main` akan otomatis memicu GitHub Actions untuk mendeploy website ke URL live:
`https://spmb-uns-solo.web.app`

Kamu juga bisa memicu deployment manual kapan saja melalui tab **Actions > Deploy to Firebase Hosting on merge > Run workflow** di GitHub.

### 2. Deployment Manual via CLI
Pastikan kamu sudah login ke Firebase:
```bash
firebase login
```
Jalankan perintah deploy:
```bash
firebase deploy --only hosting
```

---

## 👤 Pengembang (Author)

**Vinsensius Arka**
- Website: [vinsensiusarka.id](https://vinsensiusarka.id)
- GitHub: [@vinsensiusarko](https://github.com/vinsensiusarko)

---

## 📄 Hak Cipta & Atribusi

Proyek ini dibuat sebagai portal antarmuka dan studi kasus frontend web untuk **Seleksi Penerimaan Mahasiswa Baru Universitas Sebelas Maret (UNS)**. Logo, video, dan merek UNS merupakan hak milik resmi Universitas Sebelas Maret Surakarta.
