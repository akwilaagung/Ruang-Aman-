# Ruang Aman 
Website Edukasi Kesehatan Mental dan Antiperundungan
SDG 3, SDG 4, dan SDG 16


## Anggota Kelompok 
1. Nama : Akwila Agung Firmannew : NIM-2515091092 Tugas : Artikel dan Panduan
2. Nama : I Kadek Dwi Pradnya Dita Putra NIM-2515091064 Tugas : Index dan CSS
3. Nama : Evodius Evan Malachi NIM-2515091106 Tugas : Readme dan CSS
4. Nama : Komang Ade Rizky Ariawansyah NIM-2515091025 Tugas : Edukasi dan Tentang
## Deskripsi Website 
1. Tujuan : Kesehatan Mental dan Antiperundungan bertujuan untuk meningkatkan kesadaran masyarakat mengenai pentingnya kesehatan mental serta memberikan pemahaman tentang pengenalan, dampak, dan pencegahan perundungan, baik secara fisik, verbal, sosial, maupun melalui media digital. Program ini juga bertujuan menyediakan ruang yang aman bagi individu untuk berbagi cerita dan menyampaikan permasalahan tanpa takut dihakimi atau mendapatkan stigma. Selain itu, Ruang Aman mendorong terbentuknya dukungan sosial yang positif, meningkatkan empati terhadap sesama, serta memberikan informasi mengenai akses bantuan profesional, seperti konselor dan psikolog. Tujuan tersebut sejalan dengan SDG 3, SDG 4, dan SDG 16 dalam mendukung kesejahteraan mental, menciptakan lingkungan pendidikan yang aman, serta mencegah kekerasan dan perundungan.
2. Manfaat : Ruang Aman diharapkan dapat memberikan manfaat berupa peningkatan pemahaman individu mengenai kesehatan mental, kemampuan mengenali emosi, serta kesadaran untuk mencari bantuan ketika menghadapi permasalahan psikologis. Bagi korban perundungan, program ini dapat menjadi sumber informasi dan dukungan agar mereka tidak merasa sendirian serta mengetahui langkah yang tepat untuk memperoleh pertolongan. Bagi lingkungan sosial dan pendidikan, Ruang Aman dapat menumbuhkan sikap empati, mengurangi stigma terhadap individu yang mengalami masalah kesehatan mental, dan meningkatkan kepedulian terhadap tindakan perundungan. Secara lebih luas, program ini diharapkan dapat membantu menciptakan lingkungan yang aman, inklusif, saling menghargai, dan bebas dari kekerasan melalui peningkatan kesadaran serta keterlibatan masyarakat.
3. Sasaran pengguna : Sasaran pengguna Ruang Aman adalah pelajar, mahasiswa, dan masyarakat umum yang membutuhkan informasi serta dukungan terkait kesehatan mental dan pencegahan perundungan. Program ini secara khusus ditujukan kepada individu yang mengalami tekanan emosional, stres, kecemasan, kesepian, maupun permasalahan sosial, termasuk korban dan saksi perundungan yang membutuhkan ruang untuk berbagi pengalaman dan memperoleh informasi mengenai bantuan yang tepat. Selain itu, Ruang Aman juga menyasar guru, dosen, konselor, tenaga pendidik, serta orang tua yang memiliki peran penting dalam memberikan dukungan, mengenali tanda-tanda perundungan, dan menciptakan lingkungan yang aman bagi individu di sekitarnya. Dengan melibatkan berbagai kelompok tersebut, Ruang Aman diharapkan dapat meningkatkan kepedulian bersama terhadap kesehatan mental dan membangun budaya antiperundungan di lingkungan pendidikan maupun masyarakat.

## Halaman Website 
Beranda, Edukasi, Panduan, Artikel, Tentang. 
## Teknologi 
HTML5, CSS3, Flexbox/Grid, CSS Media Queries. 
## Penjelasan Implementasi 
# Penjelasan Implementasi

## 1. Navigasi

Setiap halaman punya header yang sama berisi logo dan lima menu. Menu dibuat sebagai daftar link (`ul` dan `li`) di dalam tag `nav`.

```html
<header>
  <a class="logo" href="index.html">Ruang Aman</a>
  <nav>
    <ul>
      <li><a href="index.html">Beranda</a></li>
      <li><a class="aktif" href="edukasi.html">Edukasi</a></li>
      <li><a href="panduan.html">Panduan</a></li>
      <li><a href="artikel.html">Artikel</a></li>
      <li><a href="tentang.html">Tentang</a></li>
    </ul>
  </nav>
</header>
```

**Fungsi:**
- Atribut `href` menghubungkan tiap menu ke file halaman tujuan, sehingga pengunjung bisa berpindah halaman.
- Logo juga berupa link ke Beranda.
- `class="aktif"` hanya ditaruh pada menu halaman yang sedang dibuka, supaya pengunjung tahu posisinya.

CSS untuk menu:

```css
nav ul {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

nav a:hover,
nav a.aktif {
  background-color: var(--hijau);
  color: white;
}

nav a.aktif {
  border-bottom: 3px solid var(--terakota-muda);
}
```

**Fungsi:** `list-style: none` menghilangkan titik daftar, dan `display: flex` membuat menu berjajar ke samping. Aturan `nav a:hover, nav a.aktif` memberi warna latar saat kursor diarahkan atau saat menu aktif. Garis bawah tambahan hanya untuk menu aktif.

## 2. Layout

Tata letak memakai dua teknik CSS modern: **Flexbox** dan **Grid**.

### a. Header dengan Flexbox

```css
header {
  background-color: var(--hijau-gelap);
  padding: 14px 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 10px;
}
```

**Fungsi:** `display: flex` menjajarkan logo dan menu dalam satu baris. `justify-content: space-between` menaruh logo di kiri dan menu di kanan. `align-items: center` meratakan keduanya secara vertikal. `flex-wrap: wrap` membuat elemen turun ke baris berikutnya kalau ruangnya tidak cukup.

### b. Pembungkus isi

```css
.isi {
  max-width: 1000px;
  margin: 0 auto;
  padding: 36px 20px;
}
```

**Fungsi:** `max-width: 1000px` membatasi lebar isi supaya teks tidak melebar di layar besar. `margin: 0 auto` menaruh isi di tengah halaman.

### c. Kartu informasi dengan Grid

```css
.kisi {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 22px;
}

.kisi.dua { grid-template-columns: repeat(2, 1fr); }
```

**Fungsi:** `display: grid` menyusun kartu dalam kolom. `repeat(3, 1fr)` berarti tiga kolom dengan lebar sama, dan `.kisi.dua` mengubahnya menjadi dua kolom. Di HTML, wadah ini diisi `div class="kartu"` (halaman Edukasi dan Panduan).

### d. Sampul dua kolom di Beranda

```css
.sampul {
  max-width: 1000px;
  margin: 0 auto;
  padding: 50px 20px 10px;
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 36px;
  align-items: center;
}
```

**Fungsi:** Bagian atas Beranda dibagi dua kolom, teks sambutan di kiri dan area foto di kanan. Perbandingan `1.1fr 0.9fr` membuat kolom teks sedikit lebih lebar.

## 3. Responsive Design

Agar situs nyaman dibuka di HP, dipakai dua hal.

**Meta viewport** (di setiap halaman):

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

**Fungsi:** Lebar halaman mengikuti lebar layar perangkat, jadi tidak tampil seperti versi komputer yang dikecilkan.

**Media query** (di `style.css`):

```css
/* Tablet */
@media (max-width: 900px) {
  .sampul { grid-template-columns: 1fr; }
  .kisi { grid-template-columns: repeat(2, 1fr); }
}

/* Ponsel */
@media (max-width: 600px) {
  header {
    flex-direction: column;
    text-align: center;
  }
  nav ul { justify-content: center; }
  h1, .sampul h1 { font-size: 1.9rem; }
  .kisi,
  .kisi.dua { grid-template-columns: 1fr; }
  .catatan { transform: none; }
}
```

**Fungsi:**
- Layar **900px atau kurang** (tablet): sampul jadi satu kolom, kartu `kisi` jadi dua kolom.
- Layar **600px atau kurang** (HP): header disusun ke bawah (logo di atas, menu di bawah), ukuran judul diperkecil, semua kartu jadi satu kolom, dan catatan tempel tidak miring lagi supaya tidak terpotong.

Aturan di dalam `@media` hanya berlaku saat lebar layar memenuhi syaratnya.

## 4. Bagian Kode Penting Lainnya

### a. Variabel warna (CSS Variables)

```css
:root {
  --krem: #fdf6ec;
  --pasir: #f1e4d1;
  --putih: #fffdf9;
  --hijau: #4f7a6a;
  --hijau-gelap: #2f4f45;
  --terakota: #b5532f;
  --terakota-muda: #f7c9a8;
  --teks: #2b2b2b;
}
```

**Fungsi:** Semua warna didefinisikan sekali, lalu dipanggil dengan `var(--nama)`. Kalau mau mengganti warna tema, cukup ubah di satu tempat dan seluruh situs ikut berubah.

### b. Reset dan dasar halaman

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

**Fungsi:** Menghapus jarak bawaan browser supaya tampilan konsisten, dan `box-sizing: border-box` membuat lebar elemen sudah termasuk padding dan border sehingga ukuran mudah dihitung.

### c. Kartu

```css
.kartu {
  background-color: var(--putih);
  border: 2px solid var(--pasir);
  border-radius: 18px 6px 18px 6px;
  padding: 22px;
  box-shadow: 4px 4px 0 var(--pasir);
}

.kartu:nth-child(even) {
  border-radius: 6px 18px 6px 18px;
}
```

**Fungsi:** Memberi kartu bingkai, sudut membulat, dan bayangan. `:nth-child(even)` membuat kartu urutan genap punya sudut yang dibalik, jadi bentuknya selang-seling.

### d. Mitos dan fakta yang bisa dibuka-tutup (halaman Artikel)

```html
<details>
  <summary>Judul mitos</summary>
  <p>Penjelasan faktanya...</p>
</details>
```

```css
details[open] summary { margin-bottom: 8px; }
```

**Fungsi:** `details` dan `summary` adalah tag HTML bawaan untuk bagian yang bisa dibuka dan ditutup, tanpa JavaScript. Halaman Artikel memakai empat tag `details`. Selector `[open]` mengatur tampilan saat bagiannya sedang terbuka.

### e. Langkah bernomor (halaman Panduan)

```css
.langkah { list-style: none; counter-reset: nomor; }

.langkah li { counter-increment: nomor; position: relative; padding-left: 56px; }

.langkah li::before {
  content: counter(nomor);
  position: absolute;
  border-radius: 50%;
  background-color: var(--terakota);
}
```

**Fungsi:** CSS menghitung nomor urut otomatis (`counter`) dan menampilkannya dalam lingkaran berwarna di kiri setiap langkah, tanpa perlu menulis angka di HTML.

### f. Kutipan dan kotak bantuan

```css
blockquote {
  border-left: 6px solid var(--terakota);
  padding: 8px 0 8px 20px;
}

.kotak-bantuan {
  background-color: #e3efe9;
  border-left: 6px solid var(--hijau);
  border-radius: 12px;
  padding: 22px;
}
```

**Fungsi:** Memberi penekanan visual pada kutipan dan pada informasi penting seperti kontak bantuan atau fakta data.

### g. Footer

```html
<footer>
  <p>&copy; 2026 Ruang Aman. Semua hak dilindungi.</p>
</footer>
```

**Fungsi:** Menandai akhir halaman dan memuat pernyataan hak cipta. `&copy;` menghasilkan simbol ©. Tampilannya diatur aturan `footer` di CSS (latar hijau gelap, teks krem, rata tengah).

---

# Struktur Folder

```
UTS Pemweb/
├── index.html           → halaman Beranda
├── edukasi.html         → halaman Edukasi
├── panduan.html         → halaman Panduan
├── artikel.html         → halaman Artikel
├── tentang.html         → halaman Tentang Kami dan Referensi
├── css/
│   └── style.css        → satu file CSS untuk semua halaman
├── foto/
│   └── foto-belajar.jpg → foto yang dipakai di halaman
└── .vscode/
    └── launch.json      → pengaturan VS Code untuk membuka situs di Chrome
```

| File / Folder | Fungsi |
|---|---|
| `index.html` | Halaman utama, berisi sampul, tombol, dan ringkasan situs. |
| `edukasi.html` | Materi tentang kesehatan mental, perundungan, dan aturan sekolah. |
| `panduan.html` | Langkah-langkah bernomor dan kartu panduan bantuan. |
| `artikel.html` | Mitos dan fakta dalam bentuk bagian yang bisa dibuka-tutup. |
| `tentang.html` | Profil tim, daftar referensi, dan atribusi foto. |
| `css/style.css` | Seluruh gaya tampilan, dipanggil lewat `<link rel="stylesheet" href="css/style.css">` di setiap halaman. |
| `foto/` | Menyimpan gambar. Dipanggil di HTML dengan alamat relatif, misalnya `foto/foto-belajar.jpg`. |
| `.vscode/launch.json` | File pengaturan editor, tidak memengaruhi tampilan website. |

**Alasan susunan ini:**
- Semua halaman HTML ada di folder utama, jadi link antarhalaman cukup memakai nama file (misalnya `href="edukasi.html"`).
- CSS dipisah di folder `css`, sehingga semua halaman berbagi satu gaya yang sama dan perubahan tampilan cukup dilakukan di satu tempat.
- Gambar dipisah di folder tersendiri supaya rapi dan mudah dikelola.

## Struktur Folder 
A. Susunan utama file proyek ini adalah :
- Ruang-Aman-/
   - css/
   - Foto/
   - README.md
   - artikel.html
   - edukasi.html
   - index.html
   - panduan.html
   - tentang.html

B. Fungsi
- css/	Menyimpan file CSS yang mengatur desain dan tampilan halaman website.
- foto/	Menyimpan foto atau gambar yang digunakan sebagai aset visual website.
- README.md	Berisi dokumentasi proyek, tujuan, manfaat, sasaran pengguna, teknologi, dan informasi pendukung lainnya.
- index.html	Menjadi halaman utama atau beranda website Ruang Aman.
- edukasi.html	Menampilkan materi edukasi mengenai kesehatan mental dan antiperundungan.
- panduan.html	Menyajikan panduan atau informasi mengenai langkah yang dapat dilakukan pengguna.
- artikel.html	Menampilkan artikel yang berkaitan dengan kesehatan mental dan antiperundungan.
- tentang.html	Menjelaskan informasi mengenai website Ruang Aman.

## Website dan Repository 
URL GitHub Pages (https://akwilaagung.github.io/Ruang-Aman-/)
## Referensi 
A. Referensi
1. Kemendikdasmen. Peraturan Menteri Pendidikan Dasar dan Menengah Nomor 6 Tahun 2026 tentang Budaya Sekolah Aman dan Nyaman: https://peraturan.go.id/files/Permendikdasmen-no-6-tahun-2026.pdf
2. detikEdu. 12 Januari 2026. Satgas PPKS dan TPPK di Sekolah Tak Lagi Berlaku, Ini Gantinya: https://www.detik.com/edu/sekolah/d-8303028/satgas-ppks-dan-tppk-di-sekolah-tak-lagi-berlaku-ini-gantinya
3. Kementerian Kesehatan RI. Healing119.id: https://healing119.id
4. Kementerian Kesehatan RI. FAQ Layanan Healing119.id: https://kesprimkom.kemkes.go.id/assets/uploads/contents/others/FAQ_Cegah_Bunuh_Diri%2C_Dukung_Kesehatan_Jiwa__Kenali_Layanan_Healing119.id.pdf
5. InfoPublik. Healing119.id, Layanan Kesehatan Mental 24 Jam: https://infopublik.id/kategori/layanan-publik/952502/healing119id-layanan-kesehatan-mental-24-jam-teman-bicara-yang-siap-mendengar
6. InfoPublik. SAPA 129, Layanan Cepat dan Aman untuk Perempuan dan Anak Korban Kekerasan: https://infopublik.id/kategori/layanan-publik/927918/sapa-129-layanan-cepat-dan-aman-untuk-perempuan-dan-anak-korban-kekerasan
7. KemenPPPA. Lapor SAPA 129: https://laporsapa129.kemenpppa.go.id
8. World Health Organization. Mental health: strengthening our response: https://www.who.int/news-room/fact-sheets/detail/mental-health-strengthening-our-response
9. Perpustakaan DPR RI. Ulasan Permendikbudristek PPKSP (memuat data Asesmen Nasional 2021): https://perpustakaan.dpr.go.id/epaper/index/detail/id/18338
10. Artikel jurnal tentang bentuk perundungan di sekolah: https://www.jurnal.stie-aas.ac.id/index.php/JAIM/article/download/20867/8925/68032

B. Foto
1. KapanLagi.com: https://en.kapanlagi.com/plus/wow-is-it-profanity-or-just-ordinary-find-the-explanation-in-kbbi.html
2. Fotobelajar: https://i.pinimg.com/736x/ff/ce/e6/ffcee6ab47a7ef1c5bac8d042b796fff.jpg
3. Magnific: https://www.magnific.com/idn/foto/dua-orang-berbicara
4. Pinterest: https://ar.pinterest.com/pin/1005921266755666179/
