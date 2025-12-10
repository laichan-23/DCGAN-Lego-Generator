# 🧱 LEGO Image Generation using DCGAN

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-green.svg)

Proyek ini adalah implementasi **Deep Convolutional Generative Adversarial Network (DCGAN)** untuk membangkitkan (generate) gambar baru berupa bata LEGO secara sintetis. Model ini dilatih menggunakan dataset gambar LEGO nyata dan belajar memproduksi gambar baru dari *random noise*.

## 📋 Daftar Isi
- [Tentang Proyek](#-tentang-proyek)
- [Arsitektur Model](#-arsitektur-model)
- [Dataset](#-dataset)
- [Instalasi & Penggunaan](#-instalasi--penggunaan)
- [Hasil](#-hasil)
- [Author](#-author)

## 📖 Tentang Proyek
Generative Adversarial Networks (GAN) terdiri dari dua jaringan neural yang saling berkompetisi:
1.  **Generator:** Berusaha membuat gambar palsu yang terlihat nyata.
2.  **Discriminator:** Berusaha membedakan antara gambar asli (dari dataset) dan gambar palsu (dari Generator).

Dalam notebook ini, model dilatih selama **500 epoch** untuk menghasilkan gambar LEGO berukuran $64 \times 64$ pixel.

## 🧠 Arsitektur Model

### Generator
Generator menerima input berupa *latent vector* (noise) berukuran 128 dan mengubahnya menjadi gambar RGB $64 \times 64$.
- Menggunakan layer `Dense` yang di-reshape.
- Menggunakan `Conv2DTranspose` (Upsampling) untuk memperbesar resolusi fitur.
- Aktivasi `LeakyReLU` di setiap layer, kecuali output menggunakan `Tanh`.

### Discriminator
Discriminator adalah *binary classifier* yang menerima gambar input dan menentukan apakah gambar tersebut Real atau Fake.
- Menggunakan `Conv2D` dengan stride untuk downsampling.
- Menggunakan `LeakyReLU` dan `Dropout` untuk mencegah overfitting.
- Output berupa satu neuron (logit).

## 📂 Dataset
Dataset yang digunakan diambil dari Kaggle: **LEGO Brick Images**.
- **Sumber:** [Kaggle - LEGO Brick Images](https://www.kaggle.com/datasets/joosthazelzet/lego-brick-images)
- **Konten:** Gambar berbagai jenis bata LEGO yang dirender secara 3D.
- **Preprocessing:** Gambar diubah ukurannya menjadi $64 \times 64$ dan dinormalisasi ke range $[-1, 1]$.

*Catatan: Notebook ini dikonfigurasi untuk mengunduh dataset secara otomatis menggunakan Kaggle API.*

## 💻 Instalasi & Penggunaan

### Prasyarat
Pastikan Anda memiliki library berikut:
- Python 3.x
- TensorFlow / Keras
- NumPy
- Matplotlib
- Kaggle (untuk download dataset)

### Cara Menjalankan
1. Clone repositori ini:
   ```bash
   git clone [https://github.com/username-kamu/DCGAN-Lego-Generator.git](https://github.com/username-kamu/DCGAN-Lego-Generator.git)

2. Buka file notebook Model_DCGAN.ipynb menggunakan Google Colab atau Jupyter Notebook lokal.

3. Pastikan Anda memiliki file kaggle.json jika ingin mengunduh dataset langsung lewat script, atau sesuaikan path dataset secara manual.

4. Jalankan semua sel untuk melatih model.

📊 Hasil (Results)
Berikut adalah perkembangan hasil generate gambar LEGO dari epoch awal hingga akhir:


Contoh:
<img width="794" height="327" alt="image" src="https://github.com/user-attachments/assets/d78c33b1-00b1-41f0-91e3-e6719a457d2e" />

👤 Author
Laelatul Badriyah

Student ID: 41236732

Minat: Computer Vision, Deep Learning, Data Mining.
