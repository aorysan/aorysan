# Profil GitHub Arcade Dashboard (Gamified README) Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Mengubah berkas `README.md` menjadi antarmuka visual bergaya arcade dashboard yang interaktif, meriah (gamified), lengkap dengan medali trofi, animasi typing, badge keahlian modern, serta grafik aktivitas.

**Architecture:** Menerapkan susunan 3 bagian blok vertikal dengan perataan tengah (center alignment) murni menggunakan sintaks Markdown serta HTML5 yang didukung GitHub. Mengutamakan server API eksternal dengan performa tinggi dan bebas kendala HTTP 503 (`demolab.com`, `github-stats-extended.vercel.app`, `github-profile-trophy.vercel.app`, dan `github-readme-activity-graph.vercel.app`).

**Tech Stack:** GitHub Flavored Markdown (GFM), HTML5 tag attributes (`<p>`, `<img>`, `<a>`), Shields.io Badges, Simple Icons, GitHub Profile Trophy API, GitHub Stats Extended API, Activity Graph API.

## Global Constraints

- Hindari pemesanan URL ke `github-readme-stats.vercel.app` (rentan error 503).
- Tiap tag gambar wajib menggunakan atribut `alt="..."` deskriptif sebagai fallback antarmuka.
- Maksimal 6 medali trofi pada baris tampilan untuk kompatibilitas layar seluler.
- Gunakan skema tema warna `radical` untuk seluruh kartu statistik dan grafik aktivitas demi konsistensi visual.

---

### Task 1: Pembaruan Menyeluruh Antarmuka README.md (Arcade Dashboard)

**Files:**
- Modify: `D:\AryokPunya\Kuliah\aorysan\README.md`

**Interfaces:**
- Consumes: URL konfigurasi endpoint eksternal bersiklus 200 OK.
- Produces: Antarmuka profil GitHub terintegrasi bersatu dengan desain Arcade Dashboard.

- [ ] **Step 1: Pengecekan Ketersediaan URL Gambar Baru (Verification Test BEFORE Edit)**

Lakukan uji pemanggilan HTTP pada endpoint baru yang akan dipasang untuk memastikan respons aktif (tanpa error 500/503/404):
- Tool: `read_url_content`
- Target URLs:
  1. `https://readme-typing-svg.demolab.com/?font=Orbitron&size=24&duration=3000&color=A9FEF7&vCenter=true&lines=Hi+there!+I%27m+Aryo+Adi+Putro;Data+Science+%26+Web+Developer;Welcome+to+my+GitHub+Arcade!`
  2. `https://github-profile-trophy.vercel.app/?username=aorysan&theme=radical&column=6&margin-w=15`
  3. `https://streak-stats.demolab.com/?user=aorysan&theme=radical&hide_border=true`
  4. `https://github-readme-activity-graph.vercel.app/graph?username=aorysan&theme=radical&area=true&hide_border=true`
Expected Result: Seluruh pemanggilan berhasil mengembalikan data SVG (Status 200 OK).

- [ ] **Step 2: Implementasi Konten Lengkap di README.md**

Gunakan tool `write_to_file` (dengan `Overwrite=true` dan metadata/uraian lengkap) untuk menerapkan kode baru ke `D:\AryokPunya\Kuliah\aorysan\README.md`:

```markdown
<p align="center">
  <img src="https://readme-typing-svg.demolab.com/?font=Orbitron&size=22&duration=3000&color=A9FEF7&vCenter=true&lines=Hi+there!+I%27m+Aryo+Adi+Putro;Data+Science+%26+Web+Developer;Welcome+to+my+GitHub+Arcade!" alt="Typing SVG Greeting"/>
</p>

<p align="center">
  <a href="https://maps.app.goo.gl/">
    <img src="https://img.shields.io/badge/Malang%2C_Jawa_Timur-141321?style=for-the-badge&logo=googlemaps&logoColor=FE428E" alt="Location: Malang, Jawa Timur"/>
  </a>
  <a href="mailto:aryoadiputro@gmail.com">
    <img src="https://img.shields.io/badge/aryoadiputro%40gmail.com-141321?style=for-the-badge&logo=gmail&logoColor=A9FEF7" alt="Email: aryoadiputro@gmail.com"/>
  </a>
  <a href="https://www.linkedin.com/in/aryo-adi-putro-1a7b872a4/">
    <img src="https://img.shields.io/badge/Aryo_Adi_Putro-141321?style=for-the-badge&logo=linkedin&logoColor=0077B5" alt="LinkedIn Profile"/>
  </a>
  <a href="https://github.com/aorysan">
    <img src="https://img.shields.io/badge/aorysan-141321?style=for-the-badge&logo=github&logoColor=ffffff" alt="GitHub Profile"/>
  </a>
</p>

<br>

<p align="center">
  <a href="https://github.com/ryo-ma/github-profile-trophy">
    <img src="https://github-profile-trophy.vercel.app/?username=aorysan&theme=radical&column=6&margin-w=15" alt="GitHub Trophies"/>
  </a>
</p>

---

### <p align="center">🎮 Tech Stack & Mastery</p>

<p align="center">
  <img src="https://img.shields.io/badge/Jupyter_Notebook-DA5B0B?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter Notebook"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript"/>
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
  <img src="https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white" alt="Dart"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git"/>
</p>

---

### <p align="center">🏆 GitHub Stats & Contributions Arcade</p>

<p align="center">
  <img src="https://github-stats-extended.vercel.app/api?username=aorysan&show_icons=true&theme=radical&hide_border=true&count_private=true" alt="GitHub Stats" height="165"/>
  <img src="https://github-stats-extended.vercel.app/api/top-langs/?username=aorysan&layout=compact&theme=radical&hide_border=true&langs_count=6" alt="Top Languages" height="165"/>
  <img src="https://streak-stats.demolab.com/?user=aorysan&theme=radical&hide_border=true" alt="GitHub Streak" height="165"/>
</p>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=aorysan&theme=radical&area=true&hide_border=true" alt="Contribution Activity Graph"/>
</p>

<br>

<p align="center">
  <a href="https://aorysan.github.io/portofolio-aorysan/">
    <img src="https://img.shields.io/badge/%F0%9F%9A%80_Kunjungi_Portofolio_Resmi-FE428E?style=for-the-badge&labelColor=141321" alt="Link Portofolio Resmi"/>
  </a>
</p>
```

- [ ] **Step 3: Verifikasi Hasil Editan dan Bebas Error Markdown (Post-Edit Verification)**

Gunakan tool `view_file` pada `D:\AryokPunya\Kuliah\aorysan\README.md` dan pastikan seluruh tag HTML `<p>`, `<img>`, dan `<a>` tertutup dengan benar serta susunannya utuh.
Expected: File muat tanpa terputus (truncated) dan struktur 100% konsisten dengan spesifikasi.

- [ ] **Step 4: Commit Perubahan**

Run:
```bash
git add README.md
git commit -m "feat(readme): implement gamified arcade dashboard profile"
```
Expected: Commit berhasil diciptakan di git log.
