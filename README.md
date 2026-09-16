# MANUAL BOOK

## MENJALANKAN APLIKASI REGISTERFX2

### 1. Deskripsi Aplikasi

`registerfx2` merupakan aplikasi berbasis web yang dikembangkan menggunakan framework **CodeIgniter** dan menggunakan **MySQL** sebagai sistem manajemen basis data.

Manual book ini digunakan sebagai panduan untuk melakukan instalasi dan menjalankan aplikasi `registerfx2` pada komputer lokal menggunakan **XAMPP**.

---

# 2. Kebutuhan Sistem

Sebelum menjalankan aplikasi, pastikan komputer telah memiliki beberapa perangkat berikut:

| No | Kebutuhan             | Keterangan                                                   |
| -- | --------------------- | ------------------------------------------------------------ |
| 1  | XAMPP                 | Digunakan sebagai web server dan MySQL                       |
| 2  | PHP                   | Menjalankan aplikasi CodeIgniter                             |
| 3  | MySQL                 | Menyimpan database aplikasi                                  |
| 4  | phpMyAdmin            | Mengelola database MySQL                                     |
| 5  | Web Browser           | Google Chrome, Microsoft Edge, Firefox, atau browser lainnya |
| 6  | Project `registerfx2` | Source code aplikasi                                         |

Disarankan menggunakan versi PHP yang sesuai dengan versi CodeIgniter yang digunakan oleh project.

---

# 3. Persiapan XAMPP

### 3.1 Membuka XAMPP

1. Buka aplikasi **XAMPP Control Panel**.
2. Jalankan **Apache**.
3. Jalankan **MySQL**.
4. Pastikan kedua service menunjukkan status **Running**.

Contoh:

```text
Apache    Running
MySQL     Running
```

Apache digunakan untuk menjalankan aplikasi melalui web server, sedangkan MySQL digunakan untuk menjalankan database aplikasi.

---

# 4. Menempatkan Project

Project `registerfx2` harus ditempatkan pada folder `htdocs` milik XAMPP.

Secara default lokasi folder tersebut adalah:

```text
C:\xampp\htdocs\
```

Kemudian letakkan folder project sehingga menjadi:

```text
C:\xampp\htdocs\registerfx2
```

Struktur sederhananya:

```text
C:
└── xampp
    └── htdocs
        └── registerfx2
            ├── application/
            ├── system/
            ├── index.php
            └── ...
```

> Struktur folder dapat berbeda tergantung versi dan konfigurasi CodeIgniter yang digunakan.

---

# 5. Membuat Database MySQL

Setelah project ditempatkan pada folder `htdocs`, langkah berikutnya adalah menyiapkan database.

### 5.1 Membuka phpMyAdmin

1. Pastikan **Apache** dan **MySQL** pada XAMPP sudah berjalan.
2. Buka browser.
3. Masukkan alamat:

```text
http://localhost/phpmyadmin
```

4. Tekan **Enter**.

---

### 5.2 Membuat Database

Pada halaman phpMyAdmin:

1. Pilih menu **New** pada bagian sebelah kiri.
2. Masukkan nama database sesuai dengan database yang digunakan oleh project.
3. Klik **Create**.

Contoh apabila database project menggunakan nama:

```text
registerfx2
```

maka database dibuat dengan nama:

```text
registerfx2
```

**Catatan:** Nama database harus sama dengan nama database yang ditulis pada konfigurasi CodeIgniter.

---

# 6. Import Database

Jika project dilengkapi file database dengan ekstensi `.sql`, database dapat dibuat dengan cara import.

Langkah-langkah:

1. Buka **phpMyAdmin**.
2. Pilih database `registerfx2`.
3. Pilih menu **Import**.
4. Klik **Choose File**.
5. Pilih file database `.sql` yang disediakan bersama project.
6. Klik **Import** atau **Go**.
7. Tunggu sampai proses selesai.

Jika berhasil, tabel-tabel aplikasi akan muncul pada database.

Contoh:

```text
registerfx2
├── users
├── ...
└── ...
```

Nama tabel menyesuaikan dengan database aplikasi.

---

# 7. Konfigurasi Database CodeIgniter

Setelah database dibuat, konfigurasi database pada project harus disesuaikan.

Cari file konfigurasi database pada project `registerfx2`.

Pada **CodeIgniter 3**, biasanya terdapat pada:

```text
application/config/database.php
```

Kemudian periksa konfigurasi database.

Contoh:

```php
$db['default'] = array(
    'dsn'      => '',
    'hostname' => 'localhost',
    'username' => 'root',
    'password' => '',
    'database' => 'registerfx2',
    'dbdriver' => 'mysqli',
    ...
);
```

Sesuaikan bagian berikut:

```text
hostname = localhost
username = root
password = 
database = registerfx2
```

Jika MySQL pada komputer menggunakan password, masukkan password MySQL pada bagian:

```php
'password' => 'PASSWORD_MYSQL',
```

Jika menggunakan konfigurasi bawaan XAMPP, biasanya username MySQL adalah:

```text
root
```

dan password biasanya kosong.

---

# 8. Konfigurasi Base URL

Pada CodeIgniter 3, base URL biasanya terdapat pada:

```text
application/config/config.php
```

Cari bagian:

```php
$config['base_url'] = '';
```

Kemudian sesuaikan menjadi:

```php
$config['base_url'] = 'http://localhost/registerfx2/';
```

Dengan konfigurasi tersebut, aplikasi dapat diakses melalui:

```text
http://localhost/registerfx2/
```

---

# 9. Menjalankan Project

Setelah konfigurasi selesai, pastikan:

```text
Apache : Running
MySQL  : Running
```

Kemudian buka browser.

Masukkan:

```text
http://localhost/registerfx2/
```

Tekan **Enter**.

Jika konfigurasi sudah benar, halaman utama aplikasi `registerfx2` akan ditampilkan.

---

# 10. Proses Login

Apabila aplikasi memiliki halaman login, masukkan akun yang telah tersedia pada database.

Contoh:

```text
Username : sesuai akun database
Password : sesuai akun database
```

Kemudian klik tombol:

```text
Login
```

Jika username dan password benar, pengguna akan diarahkan ke halaman utama/dashboard aplikasi.

---

# 11. Menjalankan Fitur Aplikasi

Setelah berhasil masuk ke aplikasi, pengguna dapat menggunakan menu yang tersedia pada sistem.

Menu yang tersedia dapat berbeda tergantung fitur yang terdapat pada project `registerfx2`.

Secara umum, pengguna dapat:

1. Membuka halaman utama.
2. Melakukan login.
3. Mengakses menu aplikasi.
4. Menginput data.
5. Mengubah data.
6. Menghapus data.
7. Melihat data yang tersimpan.
8. Melakukan logout.

Penggunaan fitur dilakukan melalui menu navigasi yang tersedia pada aplikasi.

---

# 12. Logout

Untuk keluar dari aplikasi:

1. Klik menu **Logout**.
2. Sistem akan mengakhiri sesi pengguna.
3. Pengguna akan diarahkan kembali ke halaman login.

Setelah logout, pengguna harus melakukan login kembali untuk mengakses halaman yang membutuhkan autentikasi.

---

# 13. Troubleshooting

## 13.1 Error "404 Page Not Found"

Jika muncul:

```text
404 Page Not Found
```

periksa beberapa hal berikut:

1. Pastikan folder project berada di:

```text
C:\xampp\htdocs\registerfx2
```

2. Pastikan Apache sedang berjalan.
3. Pastikan URL yang digunakan:

```text
http://localhost/registerfx2/
```

4. Periksa konfigurasi `base_url`.

---

## 13.2 Error Database Connection

Jika muncul pesan seperti:

```text
Unable to connect to the database
```

periksa:

* MySQL sudah berjalan.
* Username MySQL benar.
* Password MySQL benar.
* Nama database benar.
* Database sudah dibuat.

Contoh konfigurasi:

```text
Hostname : localhost
Username : root
Password : kosong
Database : registerfx2
```

---

## 13.3 Database Tidak Memiliki Tabel

Jika aplikasi berhasil dibuka tetapi muncul error karena tabel tidak ditemukan, kemungkinan database belum di-import.

Solusinya:

1. Buka phpMyAdmin.
2. Pilih database `registerfx2`.
3. Pilih **Import**.
4. Pilih file `.sql`.
5. Jalankan proses import.

---

## 13.4 Apache Tidak Bisa Berjalan

Jika Apache tidak dapat dijalankan, kemungkinan port yang digunakan sedang dipakai aplikasi lain.

Periksa konfigurasi port Apache pada XAMPP.

Jika Apache menggunakan port berbeda, URL dapat berubah, misalnya:

```text
http://localhost:8080/registerfx2/
```

Sesuaikan dengan port Apache yang digunakan.

---

# 14. Urutan Singkat Menjalankan Aplikasi

Untuk menjalankan aplikasi `registerfx2` setelah instalasi selesai, cukup lakukan langkah berikut:

```text
1. Buka XAMPP
        ↓
2. Start Apache
        ↓
3. Start MySQL
        ↓
4. Pastikan database registerfx2 tersedia
        ↓
5. Buka browser
        ↓
6. Akses http://localhost/registerfx2/
        ↓
7. Login
        ↓
8. Gunakan aplikasi
```

---

# 15. Penutup

Manual book ini digunakan sebagai panduan dasar untuk melakukan instalasi dan menjalankan aplikasi `registerfx2` menggunakan XAMPP, CodeIgniter, dan MySQL.

Sebelum menjalankan aplikasi, pastikan seluruh kebutuhan sistem telah tersedia dan konfigurasi database telah disesuaikan dengan lingkungan komputer yang digunakan.

Setelah Apache dan MySQL aktif serta konfigurasi aplikasi telah benar, aplikasi dapat diakses melalui browser menggunakan alamat:

```text
http://localhost/registerfx2/
```
