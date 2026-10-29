# Aksaventra Portable LMS Engine (Official Releases)

[![Platform](https://img.shields.io/badge/Platform-Windows%20x64-blue.svg)]()
[![Latest Release](https://img.shields.io/badge/Release-v2.2.1-brightgreen.svg)](https://github.com/cybertank378/aksaventra-releases/releases/latest)
[![Website](https://img.shields.io/badge/Website-aksaventra.ai.id-orange.svg)](https://aksaventra.ai.id)

Repositori resmi distribusi berkas rilis dan panduan instalasi **Aksaventra Portable Engine** untuk Microsoft Windows (64-bit).

Seluruh tumpukan server (**Nginx Web Server**, **PHP 8.2 FastCGI Multi-Process**, **MariaDB Database Server**, dan **Moodle LMS Core**) dikemas ke dalam satu kontainer brankas terenkripsi (**`aksaventra_vault.pak`**) dengan perlindungan enkripsi militer **AES-256-GCM** dan kompresi multi-threaded **Zstandard (`zstdmt`)**.

Anda **tidak perlu menginstal XAMPP, WampServer, Docker, atau software pihak ketiga lainnya**, dan **tidak memerlukan hak Administrator (UAC)**.

---

## 🚀 Panduan Pengguna Akhir (Quick Start)

### Langkah 1: Unduh Paket Rilis Terbaru
Kunjungi halaman rilis resmi kami di GitHub:
👉 **[Unduh Aksaventra Portable Engine Terbaru](https://github.com/cybertank378/aksaventra-releases/releases/latest)**

Paket distribusi mencakup:
- 🚀 **`aksaventra_engine.exe`** (Engine peluncur mandiri berbasis Rust)
- 📦 **`aksaventra_vault.pak`** (Kontainer brankas terenkripsi AES-256-GCM + ZstdMT)
- 🔑 **`serial_key.lic`** (Berkas lisensi resmi perangkat Anda)

---

### Langkah 2: Persiapan Berkas Aplikasi
Ekstrak paket berkas zip yang telah diunduh ke dalam satu folder (misalnya di `D:\AksaventraLMS` atau langsung pada Flashdisk USB):

```text
AksaventraLMS/
├── aksaventra_engine.exe
├── aksaventra_vault.pak
└── serial_key.lic
```

> [!WARNING]
> Berkas `aksaventra_vault.pak` adalah kontainer biner terotentikasi. **JANGAN dibuka, diubah, atau diekstrak secara manual**. Engine `aksaventra_engine.exe` akan mendekripsi dan memverifikasi integritasnya secara otomatis ke ruang kerja terlindungi (`.aksaventra_rt`).

---

### Langkah 3: Jalankan `aksaventra_engine.exe`
1. Klik dua kali pada berkas **`aksaventra_engine.exe`**.
2. Masukkan Serial Key resmi Anda pada saat diminta (atau isi pada berkas `serial_key.lic`).
3. Sistem secara otomatis mendeteksi profil hardware, membuka brankas, menyalakan web server, dan membuka browser LMS Anda secara otomatis.

---

### Langkah 4: Akses LMS Melalui Browser
Setelah proses inisialisasi selesai:
1. Browser default Anda akan terbuka secara otomatis ke alamat LMS aktif:
   ```text
   http://127.0.0.1:8080 atau http://<IP-LOKAL>:8080
   ```
2. Masuk menggunakan akun Administrator Bawaan:
   - **Username**: `admin`
   - **Password**: `Admin123!`

---

### Langkah 5: Cara Menutup Aplikasi dengan Aman
Untuk menjaga agar data ujian, materi, dan database tidak rusak atau korup:
1. Kembali ke jendela konsol `aksaventra_engine.exe`.
2. Tekan kombinasi tombol **`Ctrl + C`**.
3. Sistem *Graceful Shutdown Manager* akan otomatis menyimpan seluruh perubahan data dan mematikan layanan secara bersih.

---

## 📱 Akses Multi-Perangkat (HP / Laptop Siswa via Wi-Fi/LAN)
1. Pastikan laptop server dan perangkat siswa terhubung ke jaringan Wi-Fi atau hotspot yang sama.
2. Engine akan otomatis menampilkan alamat IP Jaringan (LAN) Anda di konsol pada saat dinyalakan, contoh:
   ```text
   Akses Jaringan (LAN): http://192.168.1.50:8080
   ```
3. Siswa langsung dapat masuk dan mengerjakan ujian/kuis dari browser HP mereka tanpa perlu menginstal aplikasi tambahan.

---

## ⚙️ Opsi Baris Perintah CLI (Tingkat Lanjut)
```text
Penggunaan: aksaventra_engine.exe [PILIHAN]

Pilihan:
  -c, --concurrency, --workers <N>   Jumlah worker PHP FastCGI (default: auto rekomendasi hardware)
  --profile <PROFIL>                 Profil performa: eco | normal | high | extreme
  -p, --port <PORT>                  Tentukan port lokal khusus (default: 8080)
  --skip-browser                     Jangan buka peramban secara otomatis
  --check-update                     Periksa ketersediaan pembaruan mesin tanpa menyalakan server
  --skip-update                      Lewati pengecekan pembaruan otomatis
  -h, --help                         Tampilkan bantuan ini
```

---
*Portal Resmi Lisensi & Dukungan Teknis: [https://aksaventra.ai.id](https://aksaventra.ai.id)*
