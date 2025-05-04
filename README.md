Untuk membuat aplikasi berbasis `.CHM` (Compiled HTML Help) dengan layout seperti pada gambar, kamu bisa memanfaatkan tool bernama **HTML Help Workshop** dari Microsoft. Di bawah ini adalah langkah-langkah awal untuk memulai proyek CHM dengan tampilan seperti itu di OS **Windows**:

---

### ✅ LANGKAH PERTAMA: Persiapan Alat dan Struktur

#### 1. **Install HTML Help Workshop**

* Download dari situs resmi Microsoft:
  [https://www.microsoft.com/en-us/download/details.aspx?id=21138](https://www.microsoft.com/en-us/download/details.aspx?id=21138)
* Instal dan buka aplikasinya: **HTML Help Workshop (hhw\.exe)**

#### 2. **Siapkan Struktur Folder**

Buat direktori proyek seperti ini:

```
CHM-Project/
│
├── index.html          ← Halaman awal
├── topic1.html         ← Konten topik 1
├── topic2.html         ← Konten topik 2
├── styles.css          ← Opsional, untuk desain
├── project.hhp         ← File project utama
├── project.hhc         ← File "Contents"
└── project.hhk         ← File "Index"
```

#### 3. **Tulis File HTML**

Gunakan HTML biasa untuk membuat halaman seperti:

```html
<!-- index.html -->
<html>
<head>
  <title>Beranda</title>
</head>
<body>
  <h1>Selamat datang di Aplikasi CHM Saya</h1>
  <p>Klik menu di kiri untuk eksplorasi lebih lanjut.</p>
</body>
</html>
```

---

### ✅ LANGKAH KEDUA: Membuat Proyek di HTML Help Workshop

1. **Buka HTML Help Workshop**, klik `File > New > Project`.
2. Pilih **HTML Help Project**, klik *OK*.
3. Simpan dengan nama `project.hhp` di folder proyek kamu.
4. Di jendela proyek:

   * Tambahkan file HTML ke bagian "HTML files".
   * Buat **Contents (.hhc)**: isikan daftar isi.
   * Buat **Index (.hhk)**: untuk pencarian berbasis indeks.
   * Aktifkan fitur pencarian (search tab).
   * Tambahkan file CSS jika perlu.

---

### ✅ KONFIGURASI FILE `.hhp`, `.hhc`, dan `.hhk`

#### 📘 `project.hhp` (contoh)

```ini
[OPTIONS]
Compatibility=1.1 or later
Compiled file=output.chm
Contents file=project.hhc
Index file=project.hhk
Default topic=index.html
Title=Nama Aplikasi CHM Kamu
Full-text search=Yes

[FILES]
index.html
topic1.html
topic2.html
```

#### 📘 `project.hhc` (Contents Tree)

```html
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML//EN">
<HTML>
<HEAD>
</HEAD>
<BODY>
<UL>
  <LI> <OBJECT type="text/sitemap">
    <param name="Name" value="Beranda">
    <param name="Local" value="index.html">
  </OBJECT>
  </LI>
  <LI> <OBJECT type="text/sitemap">
    <param name="Name" value="Topik 1">
    <param name="Local" value="topic1.html">
  </OBJECT>
  </LI>
</UL>
</BODY>
</HTML>
```

#### 📘 `project.hhk` (Index/Pencarian)

```html
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML//EN">
<HTML>
<HEAD>
</HEAD>
<BODY>
<UL>
  <LI> <OBJECT type="text/sitemap">
    <param name="Name" value="Cerita">
    <param name="Local" value="topic1.html">
  </OBJECT>
  </LI>
</UL>
</BODY>
</HTML>
```

---

### ✅ TERAKHIR: Kompilasi CHM

1. Klik tombol **Compile** di HTML Help Workshop.
2. Pilih `project.hhp`.
3. Hasil akan muncul sebagai `output.chm` di folder proyekmu.

---

### 💡 Catatan Tambahan:

* Checkbox seperti “Match similar words”, “Search titles only” adalah fitur **default** dari engine CHM.
* Tampilan toolbar (Back, Forward, Refresh) akan otomatis muncul saat file CHM dibuka di Windows.

