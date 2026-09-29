# Prototype MyPertamina: QR Langsung, Selalu Jelas

Situs statis interaktif (HTML, CSS, dan JavaScript murni) tanpa *build step* maupun *backend*. Proyek ini dirancang sebagai sarana **Usability Testing (UT)** serta peragaan konsep perbaikan antarmuka pengguna (UX) aplikasi **MyPertamina**, dengan fokus utama mempercepat dan mempermudah akses kode QR transaksi Subsidi Tepat di SPBU.

- **Live Demo:** [https://prototypeneomypertamina.vercel.app/](https://prototypeneomypertamina.vercel.app/)

---

## Fitur Utama dan Kapabilitas Prototype

### 1. Simulasi Telepon Interaktif
- **Akses Cepat (Bypass PIN)**: Opsi pengujian antara *Remember Session* (Fast Access) atau verifikasi PIN 6 digit.
- **Navigasi Langsung QR**: Mempercepat alur pengguna langsung ke tampilan kode QR Subsidi Tepat.
- **Simulasi Kecerahan Layar dan Pantulan Cahaya (Glare)**: Efek pengubah kecerahan otomatis serta pantulan sinar matahari untuk menguji keterbacaan QR pada kondisi terik di SPBU.
- **Simulasi Jaringan dan Status QR**: Pengujian respon UI pada kondisi sinyal *Online*, *Lemah*, atau *Offline*, serta penanganan status QR (*Aktif* / *Bermasalah*).

### 2. Panel Fasilitator dan Benchmark Usability Testing
- **Modul Pengujian Skenario Tugas (T1 - T5)**:
  - **T1 - QR di SPBU**: Pengujian alur standar tampilkan QR pada kondisi normal.
  - **T2 - QR Tanpa Sinyal**: Pengujian akses offline QR saat jaringan seluler tidak tersedia.
  - **T3 - Penggunaan Satu Tangan**: Pengujian aksesibilitas dan tata letak elemen antarmuka.
  - **T4 - QR Bermasalah**: Penanganan pesan kesalahan (*error handling*) saat QR tidak dapat dipindai.
  - **T5 - Sinyal Lemah**: Penanganan status *loading* dan *cached QR* pada koneksi tidak stabil.
- **Pengukuran Metrics Real-Time**: Pencatatan durasi (*timer*), jumlah ketukan layar (*taps*), dan kesalahan ketuk (*misses*).
- **Ekspor Data Pengujian**: Hasil uji pengguna dapat disalin dalam format Tab-Separated Values (TSV) untuk diimpor ke Microsoft Excel atau Google Sheets.

---

## Panduan Penggunaan Prototype

### 1. Pelaksanaan Sesi Usability Testing (Fasilitator)
1. Buka aplikasi melalui tautan *Live Demo* atau secara lokal di peramban web.
2. Pada **Panel Fasilitator** (sisi kanan):
   - Pilih skenario tugas pengujian (**T1** hingga **T5**).
   - Masukkan identitas atau kode peserta (contoh: `P1`, `P2`).
   - Pastikan opsi *"Terapkan kondisi bawaan saat mulai"* tercentang untuk menyesuaikan konfigurasi awal skenario.
3. Klik **"Mulai tugas"**. Pengukur waktu dan pencatat ketukan layar akan aktif secara otomatis.
4. Instruksikan peserta untuk berinteraksi dengan simulasi telepon di sisi kiri layar.
5. Setelah tugas selesai atau QR berhasil ditampilkan, pengukur waktu akan berhenti (*freeze*).
6. Tentukan hasil evaluasi (**Ya / Sebagian / Gagal**), kemudian klik **"Simpan ke tabel"**.

### 2. Pengaturan Kondisi Simulasi Manual
Fasilitator dapat menyesuaikan parameter pengujian secara langsung:
- **Sesi Login**: Persisten (langsung masuk) atau Habis (memerlukan PIN).
- **Kondisi Sinyal**: Baik (*Online*), Lemah, atau Tidak Ada (*Offline*).
- **Status Server**: Normal atau Gangguan.
- **Status QR**: Aktif atau Bermasalah.
- **Sinkronisasi Terakhir**: Hari ini, Kemarin, atau 3 hari lalu.
- **Simulasi Pantulan Cahaya (Glare)**: Nonaktif atau Aktif.

---

## Cara Menjalankan Secara Lokal

Proyek ini dibangun menggunakan teknologi *Vanilla Web* tanpa ketergantungan pada dependensi atau perintah kompilasi tambahan:

1. Klon repositori ini:
   ```bash
   git clone git@github.com:sqiftree/prototype_NEOMyPertamina.git
   cd prototype_NEOMyPertamina
   ```
2. Buka file `index.html` secara langsung di peramban web, atau gunakan server statis lokal:
   ```bash
   npx serve .
   ```

---

## Catatan dan Sanggahan

Proyek ini merupakan **Prototype UX / Konsep Antarmuka (Low-Fidelity)** independen dan **bukan** merupakan aplikasi resmi dari PT Pertamina (Persero) maupun PT Pertamina Patra Niaga. Seluruh data dan kode QR yang ditampilkan adalah data simulasi khusus untuk keperluan pengujian *usability*.


