# 📦 flask-minimal

Proyek starter **Flask** yang minimalis, dirancang untuk memulai pengembangan web dengan cepat, bersih, dan efisien. Semua kode terdapat dalam satu file utama (`app.py`), lengkap dengan template HTML dasar dan file statis (CSS & JavaScript).

---

## 🎯 Fitur

- Aplikasi Flask dalam **satu file (`app.py`)**
- Struktur HTML dasar dengan gaya dan JavaScript minimal
- Setup yang **sederhana** dan **intuitif**
- Mudah disesuaikan untuk pengembangan cepat

---

## ⚙️ Persiapan Sistem

Jalankan perintah berikut di server Ubuntu (misalnya EC2):

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
```

---

## 🚀 Instalasi

1. **Clone repositori:**

   ```bash
   git clone https://github.com/nugroho-paknux/flask-minimal.git
   cd flask-minimal
   ```

2. **Buat virtual environment (opsional tapi disarankan):**

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Instal dependensi:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Jalankan aplikasi:**

   ```bash
   python app.py
   ```

   Aplikasi akan berjalan di:
   ```
   http://localhost:5000
   ```

   Jika kamu menjalankan di server seperti **EC2**, akses melalui:
   ```
   http://<PUBLIC-IP-EC2>:5000
   ```

   > ⚠️ Pastikan **port 5000** sudah dibuka di **Security Group AWS EC2** agar bisa diakses dari luar.

---
