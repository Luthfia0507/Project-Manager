# Product Manager - Web Application (CRUD)

Aplikasi web manajemen produk berbasis PHP dan MySQL yang dibangun dengan menerapkan arsitektur client-server, validasi server-side, proteksi keamanan dasar (XSS & CSRF), serta tampilan antarmuka yang responsif menggunakan Flexbox.

---

## 🛠️ Fitur Utama

- **CRUD Operations**: 
  - **Create**: Menambah produk baru dengan validasi server-side.
  - **Read**: Menampilkan daftar produk dengan layout kartu (*card*) berbasis Flexbox.
  - **Update**: Mengubah data produk yang sudah ada berdasarkan ID.
  - **Delete**: Menghapus produk dengan konfirmasi dan proteksi keamanan.
- **Keamanan**:
  - **Prepared Statements (PDO)**: Mencegah serangan *SQL Injection*.
  - **Output Escaping (`htmlspecialchars`)**: Mencegah serangan *Cross-Site Scripting* (XSS).
  - **CSRF Token**: Mencegah serangan *Cross-Site Request Forgery* pada aksi perubahan/penghapusan data.
- **Arsitektur & Pola**:
  - **Post-Redirect-Get (PRG)**: Mencegah pengiriman ulang data (*double submit*) saat halaman di-*refresh*.
- **Desain Responsif**: Menggunakan CSS Box Model dan Flexbox.

---

## 📁 Struktur Direktori

```text
product-manager/
├── config/
│   └── db.php           # Konfigurasi koneksi database (PDO)
├── database/
│   └── store_db.sql     # Skema tabel MySQL
├── public/
│   ├── assets/
│   │   └── style.css    # Styling UI (Box Model & Flexbox)
│   ├── index.php        # Menampilkan daftar produk (READ)
│   ├── create.php       # Form & logika tambah produk (CREATE + PRG)
│   ├── edit.php         # Form & logika ubah produk (UPDATE)
│   └── delete.php       # Logika hapus produk (DELETE + CSRF)
└── README.md            # Dokumentasi proyek

Cara Menjalankan Proyek
1. Persiapan Server
Unduh dan jalankan aplikasi server lokal seperti XAMPP.

Pindahkan folder proyek product-manager ke dalam direktori htdocs (contoh: C:\xampp\htdocs\product-manager).

Buka XAMPP Control Panel dan jalankan modul Apache serta MySQL.

2. Import Database
Buka browser dan akses http://localhost/phpmyadmin/.

Buat database baru dengan nama store_db.

Pilih database store_db, masuk ke tab Import, lalu browse file database/store_db.sql yang ada di folder proyek.

Klik Import / Go untuk mengeksekusi skema tabel.

3. Mengakses Aplikasi
Buka browser dan kunjungi tautan berikut:

Plaintext
http://localhost/product-manager/public/
