# Web Klasifikasi Penyakit Daun Cabai (MobileNetV3)

Aplikasi web sederhana untuk mengklasifikasikan kondisi daun cabai ke dalam
4 kelas: **Healthly Leaf**, **Leaf Curl**, **Leaf Spot**, **Yellowish Leaf**,
menggunakan model MobileNetV3 (Large/Small) hasil training kamu sendiri.

Bisa didownload lewat file "chili-classifier.rar"

## Struktur folder

```
chili-classifier/
├── app.py                  # Backend Flask + inference PyTorch
├── requirements.txt
├── models/
│   ├── mobilenetv3_large_best.pth   # sudah ada
│   └── mobilenetv3_small_best.pth   # sudah ada
├── templates/
│   └── index.html
└── static/
    ├── style.css
    └── script.js
```

## Cara menjalankan

1. Buat virtual environment (opsional tapi disarankan):

   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```

2. Install dependensi:

   ```bash
   pip install -r requirements.txt
   ```

   > Kalau kamu punya GPU dan mau pakai CUDA, install `torch` sesuai
   > instruksi resmi di https://pytorch.org/get-started/locally/ agar
   > versinya cocok dengan driver CUDA kamu.

3. Jalankan servernya:

   ```bash
   python app.py
   ```

4. Buka browser ke `http://localhost:5000`

## Kalau mau deploy (bukan cuma localhost)

Untuk pemakaian selain testing lokal, jalankan lewat WSGI server produksi,
contoh dengan `gunicorn`:

```bash
pip install gunicorn
gunicorn -w 2 -b 0.0.0.0:8000 app:app
```
