# SecretFinder-Final-Version
SecretFinder adalah alat yang dirancang untuk memindai file JavaScript, HTML, dan berbagai format lainnya untuk mendeteksi informasi sensitif seperti API keys, token autentikasi, kredensial, dan data rahasia lainnya.

## Fitur Utama
🔍 Deteksi Otomatis
  - Mencari lebih dari 25 jenis rahasia/credentials menggunakan regex pattern
  - Mendeteksi API keys, tokens, private keys, dan credentials sensitif
  - Pattern yang dideteksi termasuk Google API, AWS keys, Facebook tokens, GitHub tokens, dll

📂 Multi-Sumber Input
  - URL langsung
  - File lokal
  - Direktori dengan wildcard
  - File ekspor Burp Suite

🛠 Fitur Tambahan
  - Filter URL JavaScript yang lebih fleksibel
  - Dukungan untuk BurpSuite yang lebih baik
  - Opsi baru untuk koneksi tidak aman (-k)
  - Filter hasil dengan regex kustom
  - Output dalam format HTML atau CLI
  - Dukungan proxy dan custom headers
  - Deteksi file biner
  - Pembatasan ukuran file (10MB)
  - Timeout request (30 detik)
  - Menampilkan versi program (-v)

## Instalasi
### Persyaratan
- OS: Linux/macOS/Windows.
- Python 3.6 atau lebih baru.
- RAM: 512MB (1GB recommended).
- pip (package manager Python).
- Storage: 100MB ruang kosong.
- Koneksi internet (untuk install dependencies).
- Jika Anda menggunakan sistem operasi Linux, Anda mungkin perlu menginstal paket development dependensi berikut ini untuk lxml:
  ```bash
  # Debian/Ubuntu
  sudo apt-get install libxml2-dev libxslt-dev python-dev
  
  # RHEL/CentOS
  sudo yum install libxml2-devel libxslt-devel python-devel
  ```
- Untuk pengguna Windows, dependensi biasanya bisa diinstal langsung menggunakan pip tanpa persyaratan tambahan.
- Untuk environment yang terisolasi, disarankan menggunakan virtual environment berikut:
  ```bash
  python -m venv secretfinder-env
  
  source secretfinder-env/bin/activate  # Linux/MacOS
  
  secretfinder-env\Scripts\activate    # Windows
  
  pip install -r requirements.txt
  ```

## Langkah Instalasi
### 1. Clone repository
```bash
git clone https://github.com/M3PH1S69/SecretFinder-Final-Version.git
cd SecretFinder-Final-Version && chmod +x SecretFinder
```
### 2. Instal dependensi
```bash
pip install -r requirements.txt --break-system-packages
```
### 3. Copy File ke /usr/bin/ (supaya bisa di jalankan dari luar)
```bash
sudo cp SecretFinder /usr/bin/ && rm -f SecretFinder && cd ..
```
### 4. Verifikasi instalasi
```bash
SecretFinder -h
```

## Penggunaan Dasar
### Scan URL:
```bash
SecretFinder -i https://example.com -o results.html
```
### Scan List File:
```bash
SecretFinder -i /path/to/list.js -o -results.html
```
### Ekstrak JS + scan:
```bash
SecretFinder -i https://example.com -e -o results.html
```
### Gunakan Proxy dan abaikan Verifikasi SSL:
```bash
SecretFinder -i https://example.com -e -p http://proxy:8080 -k
```
### Scan File Lokal:
```bash
SecretFinder -i file.html --output cli
```
### Custom Regex
```bash
SecretFinder -i https://example.com -r "mycustompattern"
```
### Opsi Lainnya:
```bash
SecretFinder -h
```

## Contoh Output
Output akan menampilkan informasi sensitif yang ditemukan beserta konteksnya.
```bash
[ + ] URL: https://example.com/main.js
google_api     -> AIzaSyD_HSyWEA2Ni3JXq9qVBnR...
aws_access_key -> AKIAIOSFODNN7EXAMPLE
```
## Catatan Keamanan
### 1. Program ini akan:
  - Menonaktifkan peringatan SSL saat dijalankan
  - Membatasi ukuran file yang diproses
  - Validasi URL input untuk mencegah SSRF
### 2. Disarankan untuk:
  - Menjalankan di lingkungan terisolasi (virtualenv/container)
  - Tidak menggunakan untuk tujuan malicious
  - Memeriksa hasil scan sebelum membagikannya

## Kontribusi
Kontribusi dipersilakan! Silakan buka issue atau pull request untuk:
- Menambahkan pola regex baru
- Memperbaiki bug
- Menambahkan fitur baru

## Lisensi
Proyek ini dilisensikan di bawah Lisensi MIT - lihat file [LICENSE](https://github.com/M3PH1S69/SecretFinder-Final-Version/blob/main/LICENSE) untuk detailnya.

##
> [!NOTE]
> Alat ini hanya untuk tujuan pengujian keamanan yang sah.

> [!TIP]
> Jangan menyalah gunakan tool ini untuk tindakan kriminal.

> [!IMPORTANT]
> Anda orang pintar, perhatikan penggunaan anda pada tool ini.

> [!WARNING]
> Jangan gunakan untuk aktivitas ilegal.

> [!CAUTION]
> Pengguna bertanggung jawab penuh atas penggunaan alat ini.
