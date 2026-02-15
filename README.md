# 🐾 Wildlife Monitoring System

Sistem pemantauan satwa liar berbasis web dengan **Role‑Based Access Control (RBAC)**, **stress testing**, dan **optimasi query SQL**. Aplikasi ini dirancang untuk membantu pemantauan insiden satwa liar, pelaporan lapangan, serta analisis data konservasi secara terpusat.

> Tugas Besar Sistem Basis Data
> Program Studi Informatika

---

## 🎯 Fitur Utama

### 🔐 Manajemen Akses (RBAC)

Terdapat 3 jenis peran pengguna:

| Role                    | Hak Akses                             |
| ----------------------- | ------------------------------------- |
| Administrator           | Akses penuh ke seluruh sistem         |
| Konservasionis Lapangan | Melihat peta, insiden, dan notifikasi |
| Peneliti Ekologi        | Mengakses laporan & data cuaca        |

---

### 📊 Dashboard Interaktif

* Pagination dan pencarian data
* Statistik insiden satwa
* Visualisasi data monitoring

---

### 🗺️ Monitoring Lapangan

* Manajemen data satwa
* Pencatatan insiden
* Notifikasi kejadian

---

### ⚠️ Error Handling

* Halaman error 403 kustom
* Validasi akses otomatis berdasarkan role

---

### ⚡ Optimasi Database

* Indexing kolom penting
* Pengurangan penggunaan `SELECT *`
* Query lebih efisien

---

### 🧪 Stress Testing

Pengujian performa dilakukan menggunakan Apache JMeter:

* 10 users
* 100 users
* 500 users
* 1000 users

---

## 🛠️ Tech Stack

| Layer      | Teknologi             |
| ---------- | --------------------- |
| Backend    | Laravel 12 (PHP 8.2+) |
| Frontend   | Blade + Tailwind CSS  |
| Database   | MySQL 8               |
| Testing    | Apache JMeter         |
| Web Server | PHP Built‑in Server   |

---

## 📦 Instalasi

### Prasyarat

Pastikan sudah terinstall:

* PHP ≥ 8.2
* Composer
* MySQL / MariaDB
* Node.js (opsional untuk build CSS)

---

### 1. Clone Repository

```bash
git clone https://github.com/nuevalenrefitra/wildlife-monitoring-system.git
cd wildlife-monitoring-system/laravel-app
```

---

### 2. Install Dependency

```bash
composer install
```

Jika terjadi error ekstensi PHP:

```bash
composer install --ignore-platform-reqs
```

---

### 3. Konfigurasi Environment

```bash
copy .env.example .env
```

Lalu edit bagian database di `.env`

```
DB_DATABASE=wildlife
DB_USERNAME=root
DB_PASSWORD=
```

---

### 4. Generate Key

```bash
php artisan key:generate
```

---

### 5. Migrasi Database

```bash
php artisan migrate
```

(Optional jika tersedia data contoh)

```bash
php artisan db:seed
```

---

### 6. Jalankan Server

```bash
php artisan serve
```

Buka browser:

```
http://127.0.0.1:8000
```

---

## 👤 Akun Default (Seeder)

| Role           | Email                                                   | Password |
| -------------- | ------------------------------------------------------- | -------- |
| Administrator  | [admin@example.com](mailto:admin@example.com)           | password |
| Konservasionis | [ranger@example.com](mailto:ranger@example.com)         | password |
| Peneliti       | [researcher@example.com](mailto:researcher@example.com) | password |

---

## 🧪 Stress Testing (JMeter)

1. Buka Apache JMeter
2. Import file test plan dari folder `/jmeter`
3. Jalankan pengujian dengan variasi user
4. Analisis response time & throughput

---

## 📂 Struktur Folder Penting

```
app/
 ├── Models
 ├── Http/Controllers
resources/
 ├── views/
database/
 ├── migrations
 ├── seeders
jmeter/
 ├── stress-test.jmx
```

---

## 🧯 Troubleshooting

### Error: vendor/autoload.php not found

Jalankan:

```bash
composer install
```

### Error: Application key missing

```bash
php artisan key:generate
```

### Error: Database connection

Periksa konfigurasi `.env` dan pastikan MySQL aktif.

---

## 📌 Catatan

Project ini dibuat untuk tujuan pembelajaran implementasi sistem basis data, optimasi query, serta manajemen hak akses pada aplikasi web skala menengah.

---

## 📄 Lisensi

Digunakan untuk kebutuhan akademik dan pembelajaran.
