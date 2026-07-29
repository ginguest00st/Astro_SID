# 🏛️ Sistem Informasi Profil & Pelayanan Desa (Low-Bandwidth Mobile First)

Aplikasi **Sistem Informasi Desa** berbasis *Monorepo* yang dirancang khusus untuk performa tinggi, **sangat ringan, cepat diakses pada jaringan/sinyal lemah (2G/3G)**, serta responsif dengan tampilan khas *mobile*.

Sistem ini dirancang dengan arsitektur *scalable* (mudah di-upgrade) untuk mendukung ekspansi fitur pendataan warga dan administrasi pelayanan surat online di masa mendatang.

---

## 🛠️ Tech Stack & Arsitektur

* **Frontend (`/astro_sid`):** [Astro](https://astro.build/) + [Tailwind CSS](https://tailwindcss.com/)
  * *Zero-JS by default*, *Lightweight*, *PWA Ready (Offline Mode)*.
* **Backend (`/backend_sid`):** Node.js + Express.js REST API
  * *Gzip/Brotli Compression*, *Sharp Image Optimization (WebP)*, *Rate Limiter*.
* **Database:** PostgreSQL / SQLite
* **Arsitektur:** Decoupled Monorepo (Frontend & Backend terpisah dalam 1 Repositori Git).

---

## 📁 Struktur Folder Projek

```text
projek_mandiri/
├── astro_sid/          # Aplikasi Frontend (Astro + Tailwind)
│   ├── src/
│   │   ├── components/ # Komponen UI Mobile Ringkas
│   │   ├── layouts/    # Kerangka Dasar Halaman (Layout)
│   │   ├── pages/      # Routing Halaman (Beranda, Profil, Berita, dll)
│   │   └── services/   # Fetcher API Backend
│   └── public/         # Asset Statis (Logo, Icon, Manifest PWA)
│
└── backend_sid/        # Server API (Node.js + Express)
    └── src/
        ├── config/     # Koneksi Database
        ├── controllers/# Logika Bisnis & Pengolahan Data
        ├── routes/     # API Endpoints (/api/v1/...)
        └── utils/      # Kompresi Gambar & Helper