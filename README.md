
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

## 🔁 Menjalankan Flask Otomatis Setelah Reboot

Agar Flask berjalan otomatis setelah server reboot, ikuti langkah berikut:

### 1. **Buat file service systemd**

```bash
sudo nano /etc/systemd/system/flask-app.service
```

Isi file tersebut dengan:

```ini
[Unit]
Description=Flask Minimal App
After=network.target

[Service]
User=ubuntu
WorkingDirectory=/home/ubuntu/flask-minimal
ExecStart=/home/ubuntu/flask-minimal/venv/bin/python app.py
Restart=always

[Install]
WantedBy=multi-user.target
```

> 💡 Pastikan path `/home/ubuntu/flask-minimal` sesuai dengan lokasi project kamu.

---

### 2. **Reload systemd dan aktifkan service**

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable flask-app
sudo systemctl start flask-app
```

---

### 3. **Cek status service**

```bash
sudo systemctl status flask-app
```

Jika berhasil, aplikasi Flask akan tetap aktif bahkan setelah reboot.

---

## 🌐 Pastikan Port Terbuka (5000)

Di **AWS EC2**, pastikan **Security Group** mengizinkan akses ke:

* **Port:** 5000
* **Protocol:** TCP
* **Source:** 0.0.0.0/0 (atau batasi ke IP tertentu)
---

## ✅ Langkah-Langkah: Setup Flask Otomatis via File dari VSCode

### 🧩 1. **Di VSCode (Lokal): Buat file shell script**

Buat file bernama `setup-flask-service.sh` di komputer kamu:

**Isi file:**

```bash
#!/bin/bash

APP_DIR="/home/ubuntu/flask-minimal"
SERVICE_NAME="flask-app"
PYTHON_BIN="$APP_DIR/venv/bin/python"

echo "🚀 Memulai setup Flask service..."

sudo apt update && sudo apt install python3 python3-venv python3-pip -y

if [ ! -d "$APP_DIR" ]; then
  mkdir -p "$APP_DIR"
fi

cd "$APP_DIR"

if [ ! -d "venv" ]; then
  echo "🐍 Membuat virtual environment..."
  python3 -m venv venv
fi

echo "📦 Menginstal Flask..."
"$PYTHON_BIN" -m pip install --upgrade pip
"$PYTHON_BIN" -m pip install flask

if [ ! -f "app.py" ]; then
  echo "📝 Membuat file app.py..."
  cat > app.py <<EOF
from flask import Flask
app = Flask(__name__)

@app.route("/")
def index():
    return "Hello, Flask!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
EOF
fi

echo "🔧 Membuat systemd service..."
sudo tee /etc/systemd/system/\$SERVICE_NAME.service > /dev/null <<EOF
[Unit]
Description=Flask Minimal App
After=network.target

[Service]
User=ubuntu
WorkingDirectory=\$APP_DIR
ExecStart=\$PYTHON_BIN app.py
Restart=always

[Install]
WantedBy=multi-user.target
EOF

echo "✅ Mengaktifkan service Flask..."
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable \$SERVICE_NAME
sudo systemctl start \$SERVICE_NAME

echo "📡 Status service:"
sudo systemctl status \$SERVICE_NAME --no-pager

echo "🎉 Flask sudah berjalan sebagai service di port 5000!"
```
