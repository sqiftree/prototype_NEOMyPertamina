# Prototype MyPertamina: QR Langsung, Selalu Jelas

> **Live Demo (Vercel):** Aplikasi telah di-deploy ke Vercel dan dapat diakses publik.

Situs statis interaktif (HTML + CSS + JavaScript murni) tanpa *build step* dan tanpa *backend*, dirancang untuk memandu **Usability Testing (UT)** serta demonstrasi perbaikan UX aplikasi **MyPertamina** — khususnya mempercepat dan mempermudah akses kode QR transaksi Subsidi Tepat di SPBU.

---

## 🚀 Fitur & Keunggulan Prototype

1. **Simulasi Telepon Interaktif (Interactive Phone Mockup)**
   - **Bypass / Input PIN**: Opsi *Remember Session* (Fast Access) vs Masuk dengan PIN 6 Digit.
   - **QR Tampil Cepat**: Navigasi langsung menuju kode QR Subsidi Tepat.
   - **Auto-Brightness & Glare Simulation**: Efek simulasi pantulan cahaya matahari (*glare*) dan pengubah kecerahan layar untuk pengujian di kondisi terik SPBU.
   - **Simulasi Kondisi Jaringan & Server**: Menguji respon UI saat sinyal *Online*, *Lemah*, atau *Offline*, serta status QR (Aktif / Bermasalah / Butuh Sinkronisasi).

2. **Panel Fasilitator & Benchmark Usability Testing (Day 5)**
   - **Pilihan Tugas Pengujian (T1 - T5)**:
     - **T1 - QR di SPBU**: Pengajuan QR dalam kondisi normal.
     - **T2 - QR Tanpa Sinyal**: Pengujian akses offline QR saat tidak ada jaringan di SPBU.
     - **T3 - Penggunaan Satu Tangan**: Uji ergonomi & keterjangkauan tombol utama.
     - **T4 - QR Bermasalah**: Penanganan pesan kesalahan (*error handling*) saat QR tidak valid.
     - **T5 - Sinyal Lemah**: Penanganan *loading* & *cached QR* saat sinyal tidak stabil.
   - **Metrics Real-time**: Pencatatan durasi/waktu (*Timer*), jumlah ketukan layar (*Taps*), dan salah ketuk (*Misses*).
   - **Ekspor Data Pengujian**: Hasil uji tiap peserta dapat disimpan dan disalin dalam format **TSV** untuk di-paste langsung ke Microsoft Excel atau Google Sheets.

---

## 📖 Panduan Penggunaan Prototype

### 1. Memulai Pengujian Usability (Untuk Fasilitator)
1. Buka aplikasi di browser (akses link deployment Vercel atau jalankan lokal).
2. Di **Panel Fasilitator (Sisi Kanan)**:
   - Pilih skenario tugas uji yang ingin diberikan ke peserta (**T1** s/d **T5**).
   - Isi **Kode Peserta** (misalnya `P1`, `P2`).
   - Centang *"Terapkan kondisi bawaan saat mulai"* agar preset kondisi (sinyal, status QR, dll.) disesuaikan dengan skenario.
3. Klik tombol **"Mulai tugas"**.
   - Layar simulasi HP di sisi kiri akan diset ke layar awal (*Launcher*).
   - Timer pengukuran waktu dan pencatat ketukan akan mulai berjalan secara otomatis.
4. Minta peserta berinteraksi dengan simulasi HP di sisi kiri sesuai instruksi tugas.
5. Setelah tugas diselesaikan (atau saat QR berhasil ditampilkan), timer akan berhenti (*freeze*).
6. Tentukan hasil pengujian (**Ya / Sebagian / Gagal**), lalu klik **"Simpan ke tabel"**.

### 2. Pengaturan Kondisi Simulasi Manual
Fasilitator dapat mengubah status simulasi secara real-time melalui bagian **Kondisi Simulasi**:
- **Sesi Login**: Persisten (Langsung masuk) / Habis (Minta PIN).
- **Sinyal**: Baik (Online) / Lemah / Tidak ada (Offline).
- **Server**: Normal / Gangguan.
- **Status QR**: Aktif / Bermasalah.
- **Sinkron Terakhir**: Hari ini / Kemarin / 3 hari lalu.
- **Simulasi Silau (Glare)**: Mati / Nyala (untuk menguji visibilitas QR di terik matahari).

---

## 🛠️ Cara Menjalankan Secara Lokal

Karena proyek ini menggunakan HTML, CSS, dan JS murni (*Vanilla Web*), proyek ini dapat dijalankan langsung tanpa instalasi `npm` atau *build tool*:

1. **Clone Repositori**:
   ```bash
   git clone git@github.com:sqiftree/prototype_NEOMyPertamina.git
   cd prototype_NEOMyPertamina
   ```
2. **Jalankan File**:
   - Cukup buka file `index.html` langsung di browser favorit Anda (double click).
   - Atau gunakan web server lokal sederhana:
     ```bash
     npx serve .
     ```

---

## 🌐 Deploy ke Vercel

Aplikasi ini sudah di-deploy ke Vercel dan terkonfigurasi pada file `vercel.json`.

### Cara Deploy / Re-deploy ke Vercel:
1. **Lewat Dashboard Vercel**:
   - Import repositori GitHub `sqiftree/prototype_NEOMyPertamina`.
   - Framework Preset: **Other** (Kosongkan *Build Command* dan *Output Directory*).
   - Klik **Deploy**.
2. **Lewat Vercel CLI**:
   ```bash
   npm i -g vercel
   vercel          # preview deployment
   vercel --prod   # production deployment
   ```

### Konfigurasi Security & Privacy (`vercel.json`):
- **Security Headers**: `X-Content-Type-Options: nosniff` dan `Referrer-Policy: strict-origin-when-cross-origin`.
- **Privacy / Search Engine**: Header `X-Robots-Tag: noindex, nofollow` diaktifkan agar prototype tidak terindeks oleh mesin pencari (Google).

---

## 📌 Catatan & Disclaimer

> [!NOTE]
> Proyek ini adalah **Prototype UX / Konsep Interface (Low-Fidelity)** independen dan **bukan** merupakan aplikasi resmi dari PT Pertamina (Persero) atau PT Pertamina Patra Niaga. QR code yang ada di dalamnya merupakan data ilustrasi untuk keperluan pengujian usability.

