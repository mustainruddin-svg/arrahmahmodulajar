# Generator Modul Ajar — SDIT Ar-Rahmah Makassar

Aplikasi web untuk membantu guru menyusun Modul Ajar / RPP yang terintegrasi dengan **Leadership Curriculum Khas Ar-Rahmah**, berbasis CP 2025 (BSKAP 046).

---

## 🚀 Cara Deploy (Langkah-langkah)

### Langkah 1 — Dapatkan API Key Groq (Gratis)

1. Buka [https://console.groq.com](https://console.groq.com)
2. Daftar / login (bisa pakai Google)
3. Klik **API Keys** → **Create API Key**
4. Copy API key-nya (simpan, akan dipakai di Langkah 3)

---

### Langkah 2 — Upload ke GitHub

1. Buka [https://github.com](https://github.com) → login
2. Klik tombol **+** → **New repository**
3. Nama repo: `arrahmah-modul-ajar`
4. Pilih **Public** → klik **Create repository**
5. Klik **uploading an existing file**
6. Upload **semua file** dari folder ini:
   - `vercel.json`
   - `api/generate.js`
   - `public/index.html`
7. Klik **Commit changes**

---

### Langkah 3 — Deploy ke Vercel

1. Buka [https://vercel.com](https://vercel.com) → login pakai GitHub
2. Klik **Add New → Project**
3. Pilih repo `arrahmah-modul-ajar` → klik **Import**
4. Sebelum deploy, klik **Environment Variables**:
   - **Name:** `GROQ_API_KEY`
   - **Value:** paste API key dari Langkah 1
   - Klik **Add**
5. Klik **Deploy** → tunggu 1-2 menit
6. ✅ Selesai! Vercel akan memberi URL seperti:
   `https://arrahmah-modul-ajar.vercel.app`

---

### Langkah 4 — Update URL di index.html

Setelah deploy, buka file `public/index.html`, cari baris:
```
const API_URL = '/api/generate';
```
Biarkan seperti itu — sudah otomatis terhubung ke Vercel.

---

## 📁 Struktur File

```
arrahmah-modul-ajar/
├── vercel.json          ← konfigurasi Vercel
├── api/
│   └── generate.js      ← backend (API key aman di sini)
├── public/
│   └── index.html       ← tampilan web untuk guru
└── README.md
```

---

## 🔒 Keamanan

- API Key Groq **tidak pernah terekspos** ke browser
- Semua permintaan melewati Vercel Edge Function
- Guru hanya mengakses `index.html` yang aman

---

## 💡 Fitur

- ✅ Pilih Kelas I–VI, Mata Pelajaran, Topik
- ✅ CP 2025 per fase muncul otomatis
- ✅ Bank indikator Leadership 3 pilar (Spiritual, Academic, Leadership Competencies)
- ✅ Generate Modul Ajar lengkap via AI (Groq LLaMA 3.3 70B)
- ✅ Salin teks / Cetak / Export PDF
- ✅ Gratis & cepat

---

## 🛠 Update Konten

Untuk mengubah data CP atau indikator Leadership, edit bagian `DATA CP` dan `LEADERSHIP` di file `public/index.html`.

---

*SDIT Ar-Rahmah Makassar · Yayasan Ar-Rahmah Sulawesi · TA 2025/2026*
