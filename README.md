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