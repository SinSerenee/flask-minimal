````markdown
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
````

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

## 🧪 Penggunaan

Proyek ini siap digunakan sebagai fondasi membangun web app. Semua route dan logika ada dalam `app.py`. Kamu bisa menambahkan:

* Template tambahan di folder `templates/`
* File CSS atau JS di `static/`
* Route tambahan di `app.py`

---

## 🎨 Kustomisasi

* Struktur HTML → `templates/index.html`
* Gaya tampilan (CSS) → `static/style.css`
* Interaktivitas (JS) → `static/script.js`
* Route dan logika aplikasi → `app.py`

---

## 📄 Lisensi

Lisensi: **MIT License**

---

## 🤝 Kontribusi

Pull request sangat dipersilakan! Jika kamu punya saran atau menemukan bug, silakan buka **issue** di repositori ini.

```

---

✅ **Selesai!**  
Silakan **copy seluruh blok di atas**, buat file `README.md` di proyekmu, lalu **paste ke sana**. Saat kamu push ke GitHub, tampilannya akan otomatis rapi dengan heading, bold, code block, dan lainnya.

Kalau kamu mau nanti auto-run pakai `systemd`, deploy ke Heroku, atau tambah `Procfile`, tinggal bilang ya.
```
