# KELOMPOK-5-BENCANA-ALAM

## Identias Anggota Kelompok 
1. Hendra Hakim-2515091035
2. Kadek Abby Manik Madia-2515091146
3. I Made Artha Arimbawa-2515091093
4. Putu Nova Restiawan-2515091137

## Deksriosi Website
Website SIAGA BENCANA merupakan portal edukasi informasi mitigasi dan kesiapsiagaan bencana alam yang dirancang oleh Kelompok 5. Mengingat posisi geografis Indonesia yang berada di wilayah Ring of Fire (Cincin Api Pasifik) dan rawan terhadap potensi bencana alam, website ini hadir sebagai sarana panduan praktis bagi masyarakat dalam mengantisipasi, menghadapi, serta meminimalkan risiko dampak bencana. Portal ini menyediakan materi edukasi khusus mengenai berbagai jenis bencana alam, seperti Gempa Bumi, Tsunami, Banjir, Gunung Meletus, Kebakaran Hutan, dan Tanah Longsor.

1. tujuan website: Memberikan Edukasi Mitigasi, Meningkatkan Kesadaran Masyarakat, Akses Informasi Terpusat
2. Manfaat Website: Membantu anggota masyarakat dan keluarga mengetahui tindakan penyelamatan diri yang cepat, tepat, dan aman di situasi darurat.
3. Sasaran Pengguna Website: Masyarakat Umum

## Halaman Web
Beranda, banjir, gempa, gunung-meletus, kebakaran, longsor, tsunami

## Teknologi
1. Html5
2. css
3. js
4. git
5. github

## Penjelasan Implementasi

### 1. Navigasi
Navigasi website dirancang responsif menggunakan gabungan HTML, CSS Flexbox, dan JavaScript sederhana. Pada layar desktop, menu tampil secara horizontal di bagian atas. Pada layar mobile/tablet, menu akan tersembunyi dan dapat dibuka/ditutup melalui tombol *hamburger*.

* **Potongan Kode HTML Navigasi & Hamburger:**
```html
<header class="navbar">
    <div class="logo">
        <h1>SIAGA BENCANA</h1>
    </div>
    <!-- Tombol Hamburger untuk Layar HP/Tablet -->
    <button class="menu-toggle" aria-label="Buka Menu" onclick="toggleMenu()">&#9776;</button>
    
    <!-- Menu Navigasi -->
    <nav class="nav-links" id="navMenu">
        <a href="index.html" class="active">BERANDA</a>
        <a href="pages/gempa.html">GEMPA BUMI</a>
        <a href="pages/tsunami.html">TSUNAMI</a>
        <a href="pages/banjir.html">BANJIR</a>
        <a href="pages/gunung-meletus.html">GUNUNG MELETUS</a>
        <a href="pages/kebakaran.html">KEBAKARAN HUTAN</a>
        <a href="pages/longsor.html">LONGSOR</a>
    </nav>
</header>

- Potongan Kode JavaScript Toggle Menu:

function toggleMenu() {
       document.getElementById('navMenu').classList.toggle('show');
}
Fungsi: Menambahkan atau menghapus class show pada elemen <nav> saat tombol hamburger diklik untuk menampilkan atau menyembunyikan daftar menu pada layar kecil.
```

### 2. Layout (Tata Letak)
Website ini menggunakan pendekatan tata letak CSS Grid dan Flexbox untuk mengatur elemen secara presisi dan rapi.

Beranda (Grid 3 Kolom): Kartu kategori bencana diatur menggunakan CSS Grid agar tampil sejajar dalam 3 kolom pada layar desktop:
```css
.disaster-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    width: 100%;
    margin-bottom: 40px;
}
Fungsi: Membagi area galeri bencana utama menjadi 3 kolom berukuran sama (1fr) dengan jarak antar-kartu sebesar

Detail Bencana (Hero Section Flexbox): Menggunakan Flexbox untuk menyusun gambar pendukung dan teks artikel studi kasus secara berdampingan:
.hero-grid {
    display: flex;
    gap: 40px;
    align-items: center;
    max-width: 1250px;
}
Fungsi: Menyusun gambar sampel bencana di sisi kiri dan artikel deskripsi di sisi kanan agar rata tengah secara vertikal (align-items: center).

Section Mitigasi (Cards Grid):
.mitigation-cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
}
Fungsi: Menampilkan 3 kartu panduan mitigasi (Sebelum, Saat, dan Sesudah Bencana) dalam posisi 3 kolom sejajar.
```

### 3. Responsive Design
Desain responsif diatur dalam berkas responsif.css menggunakan CSS Media Queries untuk menyesuaikan tampilan di berbagai ukuran layar (Desktop, Tablet, dan Smartphone).
Responsif Layar Tablet (max-width: 1023px):
```css
@media screen and (max-width: 1023px) {
    .menu-toggle {
        display: block;
    }
    .nav-links {
        display: none;
        flex-direction: column;
        width: 100%;
        position: absolute;
        top: 100%;
        left: 0;
        background-color: #f7f5f0;
    }
    .disaster-grid,
    .mitigation-cards {
        grid-template-columns: repeat(2, 1fr); /* Berubah menjadi 2 kolom */
    }
}
Fungsi: Mengubah navigasi menjadi hamburger menu vertikal melayang (absolute) serta menyesuaikan jumlah kolom grid beranda dan mitigasi dari 3 kolom menjadi 2 kolom.

Responsif Layar Smartphone (max-width: 600px):
@media screen and (max-width: 600px) {
    .hero-grid {
        flex-direction: column !important; /* Memaksa susunan foto di atas dan teks di bawah */
        align-items: center;
    }
    .mitigation-cards {
        grid-template-columns: 1fr; /* 1 Kolom Penuh */
    }
}
Fungsi: Mengubah tata letak horizontal menjadi vertikal (column) pada perangkat HP agar konten teks dan gambar mudah dibaca tanpa terpotong, serta mengubah kartu mitigasi menjadi 1 kolom penuh.
```

## Struktur Folder

Berikut adalah struktur direktori dan susunan berkas dari proyek **KELOMPOK-5-BENCANA-ALAM**:

```text
KELOMPOK-5-BENCANA-ALAM/
├── css/
│   ├── responsif.css        # Stylesheet khusus Media Queries & Responsive Design
│   └── style1.css           # Stylesheet utama (Reset, layouting, warna, & animasi)
├── Foto/                    # Aset gambar background, galeri, dan studi kasus
│   ├── banjir 1.jpg
│   ├── banjir 2.jpg
│   ├── banjir 3.jpg
│   ├── bg banjir.jpg
│   ├── bg gempa bumi.jpg
│   ├── bg gunung meletus.jpg
│   ├── bg kebakaran hutan.jpg
│   ├── bg longsor.jpg
│   ├── bg tsunami.jpg
│   ├── foto 1 kebakaran hutan.jpg
│   ├── foto 2.jpg
│   ├── gempa 1.jpg
│   ├── gempa 2.jpg
│   ├── gempa cianjur.jpg
│   ├── gunung agung.jpg
│   ├── gunung krakatau.jpg
│   ├── gunung merapi.jpg
│   ├── gunung tambora.jpg
│   ├── kebakaran hutan 1.jpg
│   ├── kebakaran hutan 2.jpg
│   ├── longsor 1.jpg
│   └── tsunami aceh.jpg
├── pages/                   # Halaman detail edukasi & mitigasi per bencana
│   ├── banjir.html          # Informasi & panduan mitigasi banjir
│   ├── gempa.html           # Informasi & panduan mitigasi gempa bumi
│   ├── gunung-meletus.html  # Informasi & panduan mitigasi gunung meletus
│   ├── kebakaran.html       # Informasi & panduan mitigasi kebakaran hutan
│   ├── longsor.html         # Informasi & panduan mitigasi tanah longsor
│   └── tsunami.html         # Informasi & panduan mitigasi tsunami
├── index.html               # Halaman beranda utama portal website
└── README.md                # Dokumentasi proyek website
```

## Website dan Repository
Website: https://hendrahakiiim.github.io/KELOMPOK-5-BENCANA-ALAM/
Repository: https://github.com/hendrahakiiim/KELOMPOK-5-BENCANA-ALAM.git

## Referensi
### Gambar 
KEBAKARAN HUTAN
https://id.pinterest.com/pin/265501340528520669/
https://id.pinterest.com/pin/158118636910820488/ 
https://id.pinterest.com/pin/738379301393312838/ 

GUNUNG MELETUS
https://id.pinterest.com/pin/183521753550514943/
https://id.pinterest.com/pin/385480049328695505/ 
https://id.pinterest.com/pin/835558537089054133/ 
https://id.pinterest.com/pin/792211390723183609/ 
https://id.pinterest.com/pin/81275968254599288/

TSUNAMI
https://id.pinterest.com/pin/474215035781530506/
https://id.pinterest.com/pin/728668414686857061/

GEMPA BUMI 
https://id.pinterest.com/pin/850124867238760564/
https://id.pinterest.com/pin/850124867238760605/
https://id.pinterest.com/pin/850124867238760601/
 
BANJIR 
https://id.pinterest.com/pin/850124867238760690/ 
https://id.pinterest.com/pin/850124867238760795/
https://id.pinterest.com/pin/850124867238760745/ 
https://id.pinterest.com/pin/850124867238760747/ 

LONGSOR 
https://id.pinterest.com/pin/850124867238760842/ 
https://id.pinterest.com/pin/850124867238760806/ 

### ARTIKEL
KEBAKARAN HUTAN
https://ksdae.kehutanan.go.id/publikasi/artikel/karhutla-mengancam-kehidupan-satwa-liar-di-kalimantan-selatan-qxdqttoF/

GUNUNG MELETUS
 http://eigeradventure.com/blog/letusan-gunung-terdahsyat-di-indonesia/

TSUNAMI
https://sejarah.dibi.bnpb.go.id/artikel/kilas-balik-sejarah-dua-dekade-tsunami-aceh/83

BANJIR
https://bnpb.go.id/berita/banjir-terjang-dua-wilayah-di-bali-satu-orang-meninggal-dunia

GEMPA BUMI
https://id.wikipedia.org/wiki/Gempa_bumi_Cianjur_2022

LONGSOR
http://bpba.acehprov.go.id/berita/kategori/bencana/tanah-longsor-di-aceh-jaya-tiga-orang-meninggal-dunia-dan-empat-lainnya-menjadi-korban