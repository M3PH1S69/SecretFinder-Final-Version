# SecretFinder-Final-Version
SecretFinder adalah alat yang dirancang untuk memindai file JavaScript, HTML, dan berbagai format lainnya untuk mendeteksi informasi sensitif seperti API keys, token autentikasi, kredensial, dan data rahasia lainnya.

## Fitur Utama
🔍 Deteksi Otomatis
  - API Keys (Google, AWS, Twitter, dll)
  - Token Autentikasi (OAuth, JWT, dll)
  - Kredensial Database
  - Private Keys (SSH, RSA, PGP)
  - Informasi sensitif lainnya

📂 Multi-Sumber Input
  - URL langsung
  - File lokal
  - Direktori dengan wildcard
  - File ekspor Burp Suite

🛠 Fitur Tambahan
  - Ekstraksi URL JavaScript dari HTML
  - Filter hasil dengan regex kustom
  - Output dalam format HTML atau CLI
  - Dukungan proxy dan custom headers

## Instalasi
### Persyaratan
- Python 3.6 atau lebih baru
- pip (package manager Python)

## Langkah Instalasi
### 1. Clone repository
```bash
git clone https://github.com/M3PH1S69/SecretFinder-Final-Version.git
cd SecretFinder-Final-Version && chmod +x SecretFinder
```
### 2. Instal dependensi
```bash
pip install -r requirements.txt
```
### 3. Copy File ke /usr/bin/ (supaya bisa di jalankan dari luar)
```bash
sudo cp SecretFinder/ /usr/bin/
```
### 4. Verifikasi instalasi
```bash
python3 SecretFinder -h
```

## Penggunaan Dasar
### Scan URL
```bash
SecretFinder -i https://example.com -o results.txt
```
### Scan List File
```bash
SecretFinder -i /path/to/list.js -o -results.tct
```
### Ekstrak JS dari HTML dan Scan
```bash
SecretFinder -i https://example.com -e -o results.html
```
### Gunakan Regex Kustom
```bash
SecretFinder -i https://example.com -r "your_regex_pattern"
```
### Opsi Lainnya
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

## Kontribusi
Kontribusi dipersilakan! Silakan buka issue atau pull request untuk:
- Menambahkan pola regex baru
- Memperbaiki bug
- Menambahkan fitur baru

## Lisensi
Proyek ini dilisensikan di bawah Lisensi MIT - lihat file [LICENSE]() untuk detailnya.
