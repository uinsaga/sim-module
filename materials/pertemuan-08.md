# 📘 MATERI KULIAH: PERANCANGAN SISTEM INFORMASI MANAJEMEN

## Modul: Pemodelan Sistem untuk Lembaga Media & Dakwah Digital

---

## 🎯 Tujuan Pembelajaran (Lebih Terukur)

Setelah mempelajari materi ini, mahasiswa KPI mampu:

1.  **Menjelaskan** pentingnya pemodelan sistem dalam konteks manajemen media dan dakwah.
2.  **Membedakan** fungsi dan fokus antara Flowchart dan Data Flow Diagram (DFD).
3.  **Menggambar** Flowchart untuk menggambarkan prosedur operasional standar (SOP) di lembaga penyiaran Islam.
4.  **Menggambar** DFD Level 0 (Context Diagram) untuk sistem informasi manajemen konten atau siaran.
5.  **Menganalisis** kelemahan alur informasi pada sebuah sistem sederhana (misal: pengajuan ide program).

---

## 1. 🧠 Konsep Dasar: Mengapa Pemodelan Sistem Penting bagi Pengelola Media?

**Apa itu Pemodelan Sistem?**
Pemodelan sistem adalah proses **membuat abstraksi atau representasi** dari sebuah sistem nyata menggunakan notasi, simbol, atau diagram yang disepakati. Ini seperti "cetak biru" (blueprint) sebelum membangun rumah.

**Mengapa Mahasiswa KPI Harus Bisa?**

> **Bukan hanya untuk programmer!** Sebagai calon produser, manajer stasiun radio, atau kepala divisi konten digital, Anda akan:
>
> 1.  **Berkomunikasi dengan Tim IT:** Anda perlu menjelaskan fitur yang diinginkan untuk website masjid atau aplikasi kajian.
> 2.  **Membuat SOP (Standar Operasional Prosedur):** Alur produksi konten, dari ide hingga tayang, harus jelas agar tidak kacau.
> 3.  **Menganalisis Masalah:** Jika sistem upload video dakwah sering error, pemodelan data akan membantu menemukan di mana letak kesalahan alur data.

**Contoh di Dunia KPI:**

- **Flowchart untuk SOP:** Alur seorang penyiar radio Islam mulai dari login, memutar lagu religi, membaca jadwal sholat, hingga mengambil telepon pendengar.
- **DFD untuk Sistem:** Bagaimana data "proposal program dakwah" bergerak dari pengisi acara, ke admin, ke penilai konten, hingga tersimpan di arsip.

---

## 2. 🔄 Flowchart Informasi (Menggambar Alur Kerja)

Flowchart adalah diagram yang menggambarkan **urutan logis** langkah-langkah dalam sebuah proses. Fokusnya pada **"Apa yang dilakukan selanjutnya?"** (Alur/Tahapan).

### Simbol Dasar (Wajib Hafal untuk Tugas)

| Simbol | Nama                   | Fungsi                                              | Contoh dalam KPI                                                     |
| :----: | :--------------------- | :-------------------------------------------------- | :------------------------------------------------------------------- |
| **⚪** | **Terminal**           | Mulai atau Selesai.                                 | "Mulai Proses Donasi", "Selesai Validasi"                            |
| **⬛** | **Process**            | Tindakan atau perhitungan.                          | "Upload Video", "Kirim Notifikasi", "Hitung Total Donasi"            |
| **🔶** | **Decision**           | Percabangan berdasarkan kondisi (Ya/Tidak).         | "Apakah Video < 500MB?" & "Konten Sesuai Syariah?"                   |
| **⬜** | **Input/Output**       | Membaca data atau menampilkan hasil.                | "Input Jadwal Kajian", "Tampilkan Pesan Error", "Cetak Bukti Donasi" |
| **➡️** | **Arrow / Flow**       | Menghubungkan simbol dan menunjukkan arah alur.     | Menghubungkan "Upload" ke "Cek Ukuran"                               |
| **📄** | **Document**           | Mencetak atau menampilkan laporan.                  | "Cetak Laporan Mingguan Konten"                                      |
| **🔄** | **Predefined Process** | Sub-program atau prosedur yang sudah didefinisikan. | "Proses Verifikasi Konten" (yang nanti dipecah lagi)                 |

### Contoh Mendetail untuk KPI

**Kasus: "Proses Pengajuan Ide Program Dakwah Digital Baru"**

**Alur Cerita:**

1.  Tim Kreatif mengajukan proposal ide program.
2.  Redaktur Pelaksana (Redpel) mengecek kelengkapan proposal.
3.  **Keputusan:** Jika tidak lengkap, proposal dikembalikan untuk revisi. Jika lengkap, lanjut.
4.  Proposal dikirim ke Dewan Syariah untuk verisi konten.
5.  **Keputusan:** Jika tidak sesuai syariah, ditolak. Jika sesuai, diterima & diarsipkan.

**Gambar Flowchart (dalam teks):**

```text
[⚪ MULAI]
   │
   ▼
[⬜ Input: Proposal Ide Program]
   │
   ▼
[⬛ Proses: Redpel Cek Kelengkapan]
   │
   ▼
[🔶 Apakah Lengkap?] ─── Tidak ──→ [⬜ Output: Notifikasi Revisi] ──→ Kembali ke Input │
   │ Ya                                                                                │
   ▼                                                                                   │
[⬛ Proses: Kirim ke Dewan Syariah]                                                    │
   │                                                                                   │
   ▼                                                                                   │
[🔶 Apakah Sesuai Syariah?] ─── Tidak ──→ [⬜ Output: Proposal Ditolak + Alasan] ──→ [⚪ SELESAI]
   │ Ya
   ▼
[⬛ Proses: Arsipkan Proposal & Jadwalkan Produksi]
   │
   ▼
[⬜ Output: Proposal Diterima]
   │
   ▼
[⚪ SELESAI]
```

**Analisis untuk Mahasiswa KPI:** Flowchart ini bukan hanya gambar, tapi juga **alat negosiasi** dan **dokumen legal**. Jika suatu saat ada program yang melanggar syariah, Anda bisa menelusuri: "Apakah Dewan Syariah sudah memverifikasi?".

---

## 3. 🌐 Data Flow Diagram (DFD) - Fokus pada Aliran Data

Jika flowchart menjawab **"bagaimana urutan kerjanya?"**, maka DFD menjawab **"data apa saja yang mengalir, dari mana asalnya, dan ke mana tujuannya?"**.

- **Fokus DFD:** Data (bukan proses langkah demi langkah).
- **Tujuan:** Menunjukkan batasan sistem, siapa saja yang berinteraksi, dan data apa yang masuk/keluar.

### Komponen Dasar DFD (Wajib Hafal)

| Simbol | Nama                | Penjelasan                                                                                | Contoh di Sistem Manajemen Masjid                                       |
| :----: | :------------------ | :---------------------------------------------------------------------------------------- | :---------------------------------------------------------------------- |
| **👤** | **External Entity** | Orang, grup, atau sistem lain di luar sistem yang kita bangun. (Pemberi & penerima data). | Jemaah, Pengurus Masjid, Penyiar, Admin Medsos.                         |
| **⚙️** | **Process**         | Fungsi atau aktivitas yang mengubah data input menjadi output. (Harus berupa kata kerja). | "Validasi Kajian", "Hitung Zakat", "Jadwalkan Sholat".                  |
| **🗄️** | **Data Store**      | Tempat penyimpanan data (bisa database, file excel, lemari arsip).                        | Database "Konten Dakwah", File "Data Donatur", Arsip "Rekaman Ceramah". |
| **➡️** | **Data Flow**       | Aliran data dari satu komponen ke komponen lain. (Beri label pada panah).                 | "Info Kajian", "Proposal Program", "Laporan Bulanan".                   |

---

## 4. 🧩 DFD Level 0 (Context Diagram) - "Gambaran Besar Sistem"

Ini adalah **DFD paling sederhana dan tertinggi**. Fungsinya untuk menyepakati **batasan sistem (boundary)** dan interaksi utamanya sebelum kita masuk ke detail.

**Ciri-ciri:**

- Hanya ada **1 (satu) proses utama**. Proses ini mewakili SELURUH sistem.
- **Tidak ada Data Store** yang ditampilkan di level ini.
- Hanya menunjukkan **Entity Luar** dan **Aliran Data** utama masuk/keluar sistem.

### Contoh Mendetail untuk KPI

**Kasus: "Sistem Informasi Manajemen Radio Dakwah Online"**

**Aktor (External Entity):**

1.  **Penyiar:** Membuat siaran dan mengisi log.
2.  **Pendengar:** Mengirim request lagu & laporan.
3.  **Admin Program:** Menyetujui playlist dan jadwal siaran.

**Context Diagram (DFD Level 0) - Gambar:**

```text
               ┌─────────────────────────────────────────────────────────────┐
               │                     BATAS SISTEM (BOUNDARY)                 │
               │                                                             │
               │  ┌─────────────────────────────────────────────────────┐   │
               │  │                                                     │   │
  👤 PENYIAR ◄──┼─┼─► ⚙️ SISTEM INFORMASI MANAJEMEN RADIO DAKWAH        │   │
               │  │                                                     │   │
               │  └───────────▲─────────────────────┬──────────────────┘   │
               │              │                     │                      │
               │              │                     │                      │
   ┌───────────┼──────────────┼─────────────────────┼──────────────────────┼───┐
   │           │              │                     │                      │   │
   │   👤 PENDENGAR           │                     │                      │   │
   │           │              │                     │                      │   │
   └───────────┼──────────────┼─────────────────────┼──────────────────────┼───┘
               │              │                     │
               │              ▼                     ▼
               │      👤 ADMIN PROGRAM
               │
               └─────────────────────────────────────────────────────────────┘
```

**Jelaskan Aliran Data (label pada panah):**

1.  **Penyiar → Sistem:** `Data Log Siaran`, `Request Putar Lagu`
    **Sistem → Penyiar:** `Konfirmasi Jadwal`, `Notifikasi Durasi`
2.  **Pendengar → Sistem:** `Request Lagu`, `Laporan Gangguan Siaran`
    **Sistem → Pendengar:** `Status Request`, `Info Acara Mendatang`
3.  **Admin Program → Sistem:** `Data Playlist Baru`, `Perubahan Jadwal`
    **Sistem → Admin Program:** `Laporan Kepatuhan Siaran`, `Log Aktivitas Penyiar`

**Pertanyaan Refleksi untuk Mahasiswa:** "Menurut Anda, data 'request lagu dari pendengar' adalah data mentah. Data apa yang akan KELUAR dari sistem setelah diolah oleh Admin?"

---

## 5. 🔍 Perbedaan Kunci & Kapan Menggunakannya (Tabel Plus)

| Aspek                   | Flowchart                                                                                                                   | DFD (Context Diagram Level 0)                                                                                                                                                                              |
| :---------------------- | :-------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Fokus Utama**         | **Urutan Waktu & Logika** (step-by-step)                                                                                    | **Apa yang Mengalir** (data & informasi)                                                                                                                                                                   |
| **Menjawab Pertanyaan** | "Apa langkah selanjutnya?"                                                                                                  | "Data apa saja yang masuk/keluar?" dan "Siapa yang terlibat?"                                                                                                                                              |
| **Detil Proses**        | Sangat detil (termasuk looping, percabangan)                                                                                | Tidak detil (proses hanya 1 kotak hitam)                                                                                                                                                                   |
| **Komponen**            | Terminator, Proses, Decision, I/O                                                                                           | Entity, Proses Tunggal, Data Flow. **Tidak Ada** Data Store atau Decision.                                                                                                                                 |
| **Kapan Digunakan**     | **Presentasi SOP** ke tim produksi.<br>**Dokumentasi** alur pelaporan error.<br>**Mengajarkan** prosedur pada penyiar baru. | **Rapat Awal** dengan programmer (menyamakan persepsi).<br>**Analisis Kebutuhan:** Menentukan fitur apa saja yang sistem harus terima/kirim.<br>**Presentasi** ke manajemen (gambaran besar tanpa teknis). |

**Kiasan Sederhana:**

- **Flowchart** = Panduan membuat masakan (1. potong bawang, 2. tumis, 3. jika sudah wangi, masukkan air).
- **DFD Level 0** = Resep sederhana di cover buku masak (Input: Bawang, Bumbu. Output: Makanan Siap Saji. Aktor: Koki, Pelayan).

---

## 6. 🧪 Studi Kasus untuk Diskusi Kelas (Lebih Menantang)

**Kasus: "Sistem Verifikasi Berita Dakwah untuk Website Ponpes"**
Sebuah pondok pesantren ingin memastikan setiap berita yang diunggah ke website-nya sudah melalui 3 tahap verifikasi: **Admin Medsos** (cek EYD & gambar), **Redaktur** (cek substansi & sumber), **Kiai** (stempel final "Valid Syar'i").

**Tugas Diskusi Kelompok (15 menit):**

1.  Gambarlah **Flowchart** untuk proses verifikasi berita di atas. Pastikan ada jalur **Revisi** dan **Tolak**.
2.  Gambarlah **DFD Level 0 (Context Diagram)** untuk sistem ini. Tentukan:
    - **Entity Luar** (siapa saja? Mungkin: Kontributor, Admin Medsos, Redaktur, Kiai, Pengunjung Website).
    - **Proses Utama** (beri nama, misal: Sistem Manajemen Berita Ponpes).
    - **Minimal 5 aliran data** (contoh: `Berita Mentah`, `Berita Tervalidasi`, `Notifikasi Revisi`).

---

## 7. 📝 Tugas Praktikum (Dikembangkan)

### Tugas Individu (Bobot 60%):

Pilih **satu** kasus dari lingkungan kampus atau kegiatan dakwah Anda sehari-hari:

1.  **Sistem Pengajuan Proposal Kegiatan** (dari mahasiswa ke LDK/LPM dan ke Pembina).
2.  **Alur Produksi Konten TikTok Dakwah** (dari riset, shooting, edit, approval asisten dosen, hingga publish).
3.  **Sistem Pencatatan Donasi Infaq Bulanan** (dari jamaah input, petugas catat, rekap, hingga laporan ke pengurus masjid).

**Output yang harus dikumpulkan:**

- **File PDF/Doc** berisi:
  1.  **Flowchart** (bisa digambar tangan lalu difoto, atau pakai tools seperti draw.io, Lucidchart, atau bahkan MS PPT).
  2.  **DFD Level 0 (Context Diagram)**.
  3.  **Penjelasan singkat (maks 200 kata)** tentang mengapa Anda memilih kedua bentuk pemodelan tersebut untuk kasus ini.

### Tugas Analisis (Bobot 40%):

Jawab pertanyaan berikut dalam paragraf yang runtut:

1.  **Flowchart:** Dalam kasus yang Anda pilih, informasi apa yang TIDAK BISA disampaikan dengan baik jika hanya menggunakan DFD Level 0? (Petunjuk: pikirkan tentang urutan dan keputusan "Ya/Tidak").
2.  **DFD Level 0:** Dalam kasus yang Anda pilih, aspek apa yang TIDAK BISA digambarkan dengan jelas jika hanya menggunakan Flowchart? (Petunjuk: pikirkan tentang sumber data, tujuan data, dan apa saja yang menjadi batasan sistem).
3.  **Relevansi untuk KPI:** Menurut Anda, mana yang lebih sering Anda gunakan sebagai produser media di masa depan: Flowchart atau DFD? Jelaskan alasannya dengan memberi satu skenario nyata.

---

## 8. 🎯 Kesimpulan Akhir (Slide Penutup)

> **"Pemodelan sistem bukanlah beban teknis, melainkan seni komunikasi."**

- **Flowchart** adalah sahabat Anda untuk **operasional hari ini**. Pastikan tim Anda paham prosedurnya.
- **DFD Level 0** adalah sahabat Anda untuk **perencanaan sistem besok**. Pastikan pengembang IT paham data apa yang Anda kelola.
- Sebagai lulusan KPI, kemampuan ini akan membuat Anda **unggul** karena Anda bisa menjembatani dunia **dakwah (konten)**, **manajemen (proses)**, dan **teknologi (data)**.
