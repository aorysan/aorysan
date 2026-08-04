# Desain Spesifikasi: Profil GitHub Arcade Dashboard (Gamified README)

Tanggal: 4 Agustus 2026
Status: Approved by User

## 1. Ikhtisar & Tujuan
Mengubah tampilan default dan sederhana pada `README.md` repositori profil GitHub (`aorysan/aorysan`) menjadi antarmuka visual bergaya arcade game yang menarik, bersemangat (vibrant), interaktif, serta komprehensif tanpa meninggalkan kesan profesional sebagai pengembang perangkat lunak dan data.

## 2. Struktur Arsitektur & Tata Letak
Halaman README dibagi menjadi tiga bagian utama yang ditata dari atas ke bawah:

### Bagian 1: Header Animasi & Kontak Interaktif
- **Header Typing SVG**: 
  - Host: `https://readme-typing-svg.demolab.com/`
  - Teks Animasi: "Hi there! I'm Aryo Adi Putro", "Data Science & Web Developer", "Welcome to my GitHub Arcade!".
  - Parameter Desain: `font=Orbitron` atau `Segoe UI`, `size=24`, `duration=3000`, `color=A9FEF7` (Cyan), `background=141321` atau transparan, `vCenter=true`.
- **Informasi Kontak & Media Sosial**:
  - Diimplementasikan menggunakan tombol statis bertipe `style=for-the-badge` dari Shields.io dengan ikon Simple Icons.
  - Lokasi: `Malang, Jawa Timur` (Ikon Map/Location, warna gelap/meriah).
  - Email: `aryoadiputro@gmail.com` (Ikon Gmail/Email).
  - LinkedIn: `Aryo Adi Putro` (Ikon LinkedIn).
  - GitHub: `aorysan` (Ikon GitHub).
- **Posisi**: Rata tengah menggunakan kontainer HTML `<p align="center">`.

### Bagian 2: Trofi Pencapaian & Badge Keahlian (Tech Stack)
- **GitHub Trophies**:
  - Host: `https://github-profile-trophy.vercel.app/`
  - Parameter: `username=aorysan`, `theme=radical`, `column=6`, `margin-w=15`, `no-frame=false`.
  - Fungsi: Menampilkan pencapaian kontribusi pemrograman (bintang, komit, repositori) seolah-olah sistem penghargaan dalam video game.
- **Tech Stack Badges**:
  - Sub-judul spesifik: `### 🎮 Tech Stack & Mastery` (rata tengah).
  - Format: Shields.io berkonfigurasi `style=for-the-badge` dipadukan ikon dari Simple Icons.
  - Daftar Keahlian:
    - Data & Logic: Jupyter Notebook, Python.
    - Core & Web: JavaScript, Java, HTML5, CSS3, Dart.
    - Tools: Git, GitHub.

### Bagian 3: Pusat Statistik & Grafik Aktivitas Kontributif
- **Triple Stats Cards**:
  - Kartu 1 (Stats Utama & Private): Host stabil `https://github-stats-extended.vercel.app/api?username=aorysan&show_icons=true&theme=radical&hide_border=true&count_private=true` (`height="165"`).
  - Kartu 2 (Top Languages): Host stabil `https://github-stats-extended.vercel.app/api/top-langs/?username=aorysan&layout=compact&theme=radical&hide_border=true&langs_count=6` (`height="165"`).
  - Kartu 3 (Streak Stats): Host `https://streak-stats.demolab.com/?user=aorysan&theme=radical&hide_border=true` (`height="165"`).
- **Activity Graph**:
  - Host: `https://github-readme-activity-graph.vercel.app/graph`
  - Parameter: `username=aorysan`, `theme=radical`, `area=true`, `hide_border=true`, `width=850`.
  - Fungsi: Menghadirkan visualisasi dinamik riwayat kontribusi dalam bentuk grafik gelombang berwarna bercahaya ala dasbor futuristik.
- **Tombol Tautan Portofolio**:
  - Mengubah kalimat teks menjadi blok tombol visual tebal di penutup halaman, merujuk ke situs: `https://aorysan.github.io/portofolio-aorysan/`.

## 3. Alur Kompatibilitas & Penanganan Error (Error Handling & Fallback)
1. **Redundansi Host API**:
   - Mengabaikan instance publik lama (`github-readme-stats.vercel.app`) yang rentan HTTP 503, menggantinya dengan server mandiri/terekspansi stabil (`github-stats-extended.vercel.app`, `demolab.com`, serta `activity-graph.vercel.app`).
2. **Kesesuaian Layar Ringkas (Mobile Responsivity)**:
   - Susunan kolom trofi dibatasi maksimal 6 di desktop dan secara otomatis mengalami pembungkusan (flex wrap) di monitor berlebar sempit.
   - Kartu statistik diberi ketinggian absolut sejajar namun mematuhi margin alami markup paragraf HTML agar dapat bergeser ke baris bawah saat diproyeksikan pada ponsel tanpa memotong gambar.
3. **Teks Fallback**:
   - Tiap tag `<img src="...">` harus disematkan atribut `alt="..."` yang deskriptif sebagai cadangan dokumentasi jika koneksi ke pelayan CDN atau penyedia generator mengalami pemutusan waktu luasan.

## 4. Kriteria Kelulusan & Pengujian (Testing Strategy)
- Verifikasi visual kode markdown secara langsung setelah penyuntingan berkas `README.md`.
- Uji koneksi seluruh URL gambar external (status kode 200 OK via pengecekan HTTP bebas).
- Tata bahasa konsisten, pembungkus tag HTML ditutup secara presisi tanpa celah karakter yang berpotensi meresapi pemotong peramban markdown GitHub.
