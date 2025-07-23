flask-minimal
Proyek starter Flask yang minimalis, dirancang untuk membantu kamu memulai pengembangan web dengan cepat, bersih, dan efisien. Semua kode disatukan dalam satu file utama (app.py), disertai dengan template HTML dasar dan aset statis (CSS & JS).

🎯 Fitur
Aplikasi Flask dalam satu file (app.py) untuk produktivitas dan kesederhanaan maksimal.

Struktur HTML dasar dengan gaya dan JavaScript minimal.

Setup yang sederhana dan intuitif, tanpa kompleksitas yang tidak perlu.

Mudah disesuaikan untuk pengembangan cepat.

⚙️ Persiapan Sistem
Jalankan perintah berikut di server Ubuntu-mu (misalnya EC2):

bash
Copy
Edit
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
📦 Instalasi Aplikasi
Clone repositori:

bash
Copy
Edit
git clone https://github.com/nugroho-paknux/flask-minimal.git
cd flask-minimal
Buat virtual environment (disarankan):

bash
Copy
Edit
python3 -m venv venv
source venv/bin/activate
Install dependensi:

bash
Copy
Edit
pip install -r requirements.txt
Jalankan aplikasi:

bash
Copy
Edit
python app.py
Aplikasi Flask akan berjalan, dan bisa diakses melalui browser di:

arduino
Copy
Edit
http://localhost:5000
Jika di-host di EC2, gunakan:

cpp
Copy
Edit
http://<PUBLIC-IP-EC2>:5000
Pastikan port 5000 dibuka di security group EC2 kamu.

🚀 Penggunaan
Proyek ini sudah siap digunakan sebagai fondasi untuk membangun aplikasi web. Semua logika dan route Flask ada di dalam app.py, sehingga mudah dikembangkan. Kamu dapat menambahkan lebih banyak template, route, atau file statis sesuai kebutuhan.

🎨 Kustomisasi
Kamu bisa mengedit:

Struktur HTML di: templates/index.html

Gaya tampilan di: static/style.css

Interaktivitas di: static/script.js

Silakan juga ubah atau tambah route di app.py untuk menyesuaikan dengan kebutuhan aplikasimu.

📄 Lisensi
Proyek ini dilisensikan dengan MIT License – bebas digunakan dan dimodifikasi.

🙌 Kontribusi
Silakan fork repositori ini dan kirim pull request jika kamu punya perbaikan atau fitur tambahan. Jika ada saran atau masukan, buka issue, kita bisa diskusi bersama!

