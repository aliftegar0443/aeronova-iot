# AeroNova IoT Air Intelligence

**AeroNova IoT Air Intelligence (Team ZERO)** adalah sistem pemantauan dan kendali kualitas udara berbasis Laravel dan ESP32-S3.

## Fitur utama

- Monitoring kualitas udara secara real-time.
- Kendali kipas otomatis dan manual.
- Multi-jadwal yang tersimpan di flash ESP32-S3.
- Grafik analitik sensor.
- AeroNova AI lokal melalui LM Studio.
- Halaman publik, Mode Trial, Berita & Event, serta panel Admin untuk pengelolaan konten dan akun.

## Instalasi singkat

Persyaratan: PHP 8.3+, Composer, Node.js/npm, dan database yang didukung Laravel.

```powershell
composer install
Copy-Item .env.example .env
```

Atur koneksi database dan `LOCAL_AI_URL` / `LOCAL_AI_MODEL` di `.env`, lalu jalankan:

```powershell
php artisan key:generate
php artisan migrate --seed
php artisan storage:link
npm install
npm run build
php artisan serve
```

Buka `http://127.0.0.1:8000`. Jalankan LM Studio dengan server lokal aktif untuk menggunakan AeroNova AI. Setelah seeding, ganti kredensial Admin bawaan sebelum aplikasi digunakan di lingkungan produksi.

## Firmware ESP32-S3

Buka `firmware/esp32_s3_aeronova/aeronova.ino` di Arduino IDE, atur kredensial Wi-Fi dan URL API Laravel pada sketch, lalu unggah ke perangkat. ESP32-S3 harus dapat menjangkau alamat IP komputer yang menjalankan Laravel.
