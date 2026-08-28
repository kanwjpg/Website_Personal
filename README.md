# Portfolio 2025 — Yudha Pradana

Website portfolio 4 halaman. HTML + CSS + JavaScript murni — tanpa framework, tanpa build step, tanpa dependency. Tinggal upload, langsung jalan.

```
index.html      Home — hero, marquee, stats, services, featured work, testimoni
about.html      About — cerita, skill bar, tools, timeline, bahasa
work.html       Work — galeri dengan filter + lightbox, arsip 2023/2024
contact.html    Contact — form, kontak, FAQ
404.html        Halaman error
vercel.json     Konfigurasi Vercel
assets/         css, js, img, favicon
```

---

## 1. Deploy ke Vercel

### Drag & drop (paling cepat, tanpa Git)

1. Buka [vercel.com/new](https://vercel.com/new), login.
2. Drag folder ini ke area upload.
3. Framework Preset: **Other**. Build Command & Output Directory dikosongkan.
4. **Deploy**. Selesai.

### Lewat GitHub (disarankan)

```bash
cd portfolio
git init && git add . && git commit -m "portfolio 2025"
git branch -M main
git remote add origin https://github.com/USERNAME/portfolio.git
git push -u origin main
```

Di Vercel: **Add New → Project → Import** repo → **Deploy**. Tiap `git push` otomatis update.

### Lewat CLI

```bash
npm i -g vercel
cd portfolio && vercel --prod
```

### Tes lokal

```bash
cd portfolio && python3 -m http.server 8000
# buka http://localhost:8000
```

---

## 2. Ganti gambar

Semua gambar masih placeholder (`.svg` gelap bertuliskan "GANTI GAMBAR INI"). Taruh file asli di `assets/img/`, lalu ubah `src`-nya di HTML.

| File | Dipakai di | Ukuran ideal |
|---|---|---|
| `portrait-hero.svg` | index.html — foto besar hero | 900 × 1200 (3:4) |
| `portrait-about.svg` | about.html | 1000 × 1250 (4:5) |
| `featured-01/02/03.svg` | index.html — Selected projects | 1400 × 900 (16:10) |
| `project-01.svg` | work.html — kartu tinggi | 1200 × 1500 |
| `project-09.svg` | work.html — kartu lebar | 1600 × 1000 |
| `project-02` … `08`, `10` | work.html — kartu kotak | 1200 × 1200 |
| `archive-2023/2024.svg` | work.html | 600 × 800 (3:4) |
| `logo.svg` + `assets/favicon.svg` | header, footer, tab browser | SVG 64 × 64 |
| `og.svg` | preview saat link dishare | 1200 × 630 |

Contoh di `work.html`:

```html
<article class="shot" data-cat="branding">
  <img src="assets/img/project-02.svg" alt="Monochrome logo" loading="lazy">
  <div class="shot__meta"><h4>Monochrome logo</h4><p>branding</p></div>
</article>
```

Ganti `src` ke `assets/img/logo-mono.jpg`, ubah `<h4>` jadi judul asli, dan `data-cat` menentukan karya itu muncul di filter yang mana (`poster`, `typography`, `portrait`, `branding`). Kalau mau kategori baru, tambahkan juga tombolnya di blok `.filters`.

> Kompres dulu di [squoosh.app](https://squoosh.app) — `.webp` atau `.jpg` kualitas 80, target di bawah 300 KB per gambar.

---

## 3. Ganti teks & angka

Semua teks langsung di file HTML, tidak ada database.

- **Headline & tagline** → `index.html` bagian `.hero`
- **Angka statistik** → cari `data-count="20"` — angka itu yang dihitung naik saat di-scroll. `data-suffix` untuk akhiran (`K+`, `%`).
- **Services** → `index.html`, blok `.grid-4`
- **Testimoni** → `index.html`, blok `.quote` (sekarang masih contoh — ganti dengan testimoni asli atau hapus seluruh section-nya)
- **Cerita & timeline** → `about.html`
- **Skill bar** → `about.html`, ubah `data-fill="95"` **dan** teks `<span>95%</span>` (dua-duanya)
- **Tools** → `about.html`: `<span class="tool"><i style="--c:#31a8ff">Ps</i>Photoshop</span>` — `--c` warna, `Ps` singkatan, sisanya nama
- **FAQ** → `contact.html`, tiap `<details>`
- **Email & sosial media** → cari `hello@example.com` dan `ypzs68` di semua file

---

## 4. Fitur interaktif yang ada di dalam

- **Preloader** dengan angka 00 → 100
- **Custom cursor** (dot + ring yang melar saat kena tombol/kartu) — otomatis mati di HP
- **Progress bar** tipis di atas layar mengikuti scroll
- **Header sticky** yang mengecil dan jadi blur saat di-scroll
- **Angka statistik menghitung naik** saat masuk layar
- **Skill bar teranimasi** saat di-scroll
- **Marquee** tools yang berhenti saat di-hover
- **Spotlight** yang mengikuti kursor di dalam kartu
- **Magnetic button** — tombol utama sedikit menarik ke arah kursor
- **3D tilt** pada foto hero dan foto about
- **Filter galeri + lightbox** (← → untuk geser, Esc untuk tutup)
- **FAQ accordion**
- **Form kontak dengan validasi** — cek nama, format email, panjang pesan, lalu buka email app dengan pesan siap kirim
- **Panel Options** (ikon gigi di header): matikan animasi, dan ganti warna aksen antara oranye / merah / lime / biru. Tersimpan di browser pengunjung.
- **Back to top**, **scroll reveal bertahap**, **menu mobile**

---

## 5. Yang perlu kamu putuskan

1. **Email.** Masih `hello@example.com`. Ganti di `contact.html` (dua tempat: `data-email` di form dan link `mailto:`) dan di footer semua halaman.
2. **Username sosmed.** Saya isi `@ypzs68` (IG & TikTok), `Yudha XD` (YouTube), `@kyzsee` (Pinterest) — tolong dicek, di mockup agak buram.
3. **Testimoni masih contoh.** Ini paling penting: ganti dengan testimoni asli dari klien/teman, atau hapus section-nya. Testimoni palsu lebih merusak daripada tidak ada.
4. **Angka statistik.** "120+ projects" dan "24h first draft" masih perkiraan saya. Sesuaikan dengan yang benar.
5. **Skill bahasa Inggris** saya naikkan dari 10% ke 45% karena isi situsnya bahasa Inggris — angka 10% bikin klien luar ragu. Turunkan lagi kalau memang mau jujur segitu.
6. **Form kontak** sekarang membuka aplikasi email pengunjung. Kalau mau pesan masuk langsung tanpa buka email app, daftar gratis di [formspree.io](https://formspree.io), lalu di `contact.html` ubah `<form>` jadi `<form action="https://formspree.io/f/KODEMU" method="POST">` dan hapus `novalidate` + `id="contact-form"`.
7. **Judul karya** di `work.html` masih generik. Ganti dengan judul asli.
8. **Domain sendiri**: Vercel → Settings → Domains.

---

## 6. Catatan teknis

- Font: Sora (display), Plus Jakarta Sans (body), JetBrains Mono (label) — Google Fonts.
- Aksesibilitas: navigasi keyboard penuh, fokus terlihat, `aria-label` di semua tombol ikon, `prefers-reduced-motion` dihormati (semua animasi otomatis mati kalau pengunjung mengaktifkannya di OS).
- Responsive sampai layar 360 px.
- Tidak ada tracking, tidak ada cookie, tidak ada data yang dikirim ke mana pun.
