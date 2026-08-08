# 🌶️ Klasifikasi Penyakit Daun Cabai Menggunakan MobileNetV3

## 📖 Overview

Proyek ini merupakan sistem klasifikasi penyakit daun cabai berbasis Deep Learning menggunakan arsitektur MobileNetV3. Model dikembangkan untuk mengidentifikasi kondisi daun cabai secara otomatis berdasarkan citra digital.

Sistem mampu mengklasifikasikan daun cabai ke dalam empat kategori, yaitu Healthy, Leaf Curl, Leaf Spot, dan Yellowish Leaf. Model dibangun menggunakan TensorFlow dan diimplementasikan dalam bentuk aplikasi web menggunakan Flask sehingga pengguna dapat melakukan prediksi dengan mengunggah gambar daun cabai.

---

## 📂 Dataset

Dataset yang digunakan pada penelitian ini merupakan dataset citra daun cabai yang terdiri dari empat kelas, yaitu **Healthy**, **Leaf Curl**, **Leaf Spot**, dan **Yellowish Leaf**. Seluruh citra telah melalui tahap prapemrosesan dan dibagi menjadi data pelatihan, validasi, dan pengujian untuk memastikan model mampu melakukan generalisasi dengan baik.

### Kelas Dataset

| Kelas | Deskripsi |
|--------|-----------|
| Healthy | Daun cabai dalam kondisi sehat |
| Leaf Curl | Daun cabai yang mengalami penyakit keriting daun |
| Leaf Spot | Daun cabai yang mengalami penyakit bercak daun |
| Yellowish Leaf | Daun cabai yang mengalami perubahan warna menjadi kekuningan |


## 🧠 Arsitektur Model

Model yang digunakan dalam proyek ini adalah **MobileNetV3**, yaitu salah satu arsitektur Convolutional Neural Network (CNN) yang dirancang untuk memberikan performa tinggi dengan jumlah parameter yang relatif kecil. Arsitektur ini sangat cocok untuk proses klasifikasi citra karena mampu menghasilkan akurasi yang baik dengan waktu inferensi yang cepat.

Pada proyek ini, MobileNetV3 digunakan sebagai model dasar (pre-trained) dengan bobot **ImageNet**, kemudian dilakukan proses *transfer learning* dan *fine-tuning* menggunakan dataset penyakit daun cabai.

## ⚙️ Konfigurasi Pelatihan

Model dilatih menggunakan TensorFlow dengan konfigurasi sebagai berikut.

| Parameter | Nilai |
|-----------|--------|
| Model | MobileNetV3 |
| Optimizer | SGD |
| Learning Rate | 0.01 |
| Batch Size | 32 |
| Epoch | 40 |
| Image Size | 224 × 224 |
| Loss Function | Categorical Crossentropy |
| Framework | TensorFlow |
| Platform | Google Colab (GPU Tesla T4) |

## 📊 Hasil Pelatihan

Pelatihan dilakukan menggunakan dua varian arsitektur MobileNetV3, yaitu **MobileNetV3-Small** dan **MobileNetV3-Large**. Hasil pelatihan dievaluasi menggunakan grafik akurasi, grafik loss, dan confusion matrix untuk mengetahui kemampuan masing-masing model dalam mengklasifikasikan penyakit daun cabai.

### MobileNetV3-Small

#### Grafik Akurasi

![Akurasi MobileNetV3-Small](Training/small/model_akurasi.png)

#### Grafik Loss

![Loss MobileNetV3-Small](Training/small/model_loss.png)

#### Confusion Matrix

![Confusion Matrix MobileNetV3-Small](Training/small/matrix.png)

---

### MobileNetV3-Large

#### Grafik Akurasi

![Akurasi MobileNetV3-Large](Training/larger/model_akurasi.png)

#### Grafik Loss

![Loss MobileNetV3-Large](Training/larger/model_loss.png)

#### Confusion Matrix

![Confusion Matrix MobileNetV3-Large](Training/larger/matrix.png)


## 🌐 Tampilan Aplikasi Web

Aplikasi ini dikembangkan menggunakan **Flask** sebagai antarmuka berbasis web. Pengguna dapat mengunggah gambar daun cabai, kemudian sistem akan melakukan klasifikasi menggunakan model MobileNetV3 dan menampilkan hasil prediksi secara otomatis.

### 1. Halaman Utama

Halaman awal aplikasi yang menampilkan informasi singkat mengenai sistem serta tombol untuk memulai proses klasifikasi.

![Halaman Utama](Web/tampilan%20utama.png)

### 2. Halaman Upload Gambar

Pengguna dapat mengunggah gambar daun cabai yang akan diproses oleh model.

![Halaman Upload](Web/upload.png)

### 3. Halaman Hasil Prediksi

Setelah gambar diproses, sistem akan menampilkan hasil klasifikasi beserta tingkat kepercayaan (confidence).

![Hasil Prediksi](Web/hasil.png)
