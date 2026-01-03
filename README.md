# ANTAM Gold Price Prediction

# Perbandingan Metode NARNN dan Holt-Winters untuk Prediksi Harga Emas Antam

Repository ini berisi kode dan hasil penelitian mengenai prediksi harga emas harian PT Aneka Tambang (Antam) menggunakan pendekatan *Machine Learning* dan statistik klasik.

Penelitian ini membandingkan kinerja model **Nonlinear Autoregressive Neural Network (NARNN)** dengan metode **Holt-Winters Exponential Smoothing** untuk menentukan model yang paling akurat dalam menangani volatilitas harga emas.

## 📄 Abstrak

Harga emas Antam memiliki volatilitas yang tinggi dan dipengaruhi oleh berbagai faktor makroekonomi. Penelitian ini bertujuan untuk membandingkan akurasi prediksi antara model jaringan saraf tiruan nonlinear (NARNN) dan metode pemulusan eksponensial (Holt-Winters).

Hasil evaluasi menunjukkan bahwa model berbasis *machine learning* (NARNN) mampu menangangkap pola nonlinear dengan jauh lebih baik dibandingkan metode statistik konvensional untuk data harga emas periode ini.

## 👥 Penulis

* **Raihan Akbar** - *IPB University*
* **Rika Ardiansyah Saputra** - *IPB University*
* *et al.*

## 📊 Dataset

Data yang digunakan dalam penelitian ini adalah data sekunder harga emas harian.

* **Objek:** Harga Emas Antam (Harian)
* **Sumber:** Kaggle & Website Resmi Logam Mulia (divalidasi)
* **Periode Data:** 4 Januari 2010 – 4 Januari 2025
* **Preprocessing:**
    * *Linear Interpolation*: Mengisi data yang hilang (akhir pekan/hari libur).
    * *Box-Cox Transformation*: Menstabilkan varians data (Lambda ≈ -0.1623).
* **Pembagian Data (Split 80:20):**
    * *Training:* 4 Jan 2010 – 4 Jan 2022
    * *Testing:* 5 Jan 2022 – 4 Jan 2025

## 🛠️ Metodologi

Penelitian ini membandingkan dua pendekatan utama:

1.  **NARNN (Nonlinear Autoregressive Neural Network)**
    * Menggunakan arsitektur *Feed-Forward Backpropagation*.
    * **Hyperparameter Terbaik:**
        * *Feedback Delay:* 7
        * *Hidden Neurons:* 23
        * *Training Algorithm:* Bayesian Regularization
    * Keunggulan: Mampu menangkap pola nonlinear yang kompleks.

2.  **Holt-Winters (Exponential Smoothing)**
    * Digunakan sebagai *baseline* metode statistik klasik.
    * Varian yang diuji: **Additive** dan **Multiplicative**.
    * Parameter *smoothing* (alpha, beta, gamma) dioptimasi untuk meminimalkan error.

## 📈 Hasil Evaluasi

Kinerja model diukur menggunakan **MAPE (Mean Absolute Percentage Error)** pada data testing. Berikut adalah hasil perbandingannya:

| Model | Spesifikasi | MAPE (%) |
| :--- | :--- | :--- |
| **Holt-Winters** | Additive + Box-Cox | 11.43% |
| **Holt-Winters** | Multiplicative + Box-Cox | 11.90% |
| **NARNN** | **Delay 7, Hidden 23 (Best Model)** | **0.44%** |

> **Kesimpulan:** Model **NARNN** terbukti jauh lebih unggul dengan MAPE sebesar **0.44%**, dibandingkan metode Holt-Winters yang memiliki error di atas 11%. Hal ini menunjukkan bahwa pendekatan nonlinear lebih efektif untuk memprediksi pergerakan harga emas Antam.

![Perbandingan Prediksi](<HWA, HWM, dan NARNN.png>)

## 💻 Instalasi & Penggunaan

Proyek ini dapat dijalankan menggunakan **MATLAB** (untuk NARNN) atau **R** (untuk Holt-Winters & Preprocessing).

### Prasyarat
* **R / RStudio** (Paket: `forecast`, `tseries`, `ggplot2`)
* **MATLAB** (Neural Network Toolbox)

### Cara Menjalankan
1.  **Clone repository:**
    ```bash
    git clone [https://github.com/username-anda/prediksi-emas-narnn.git](https://github.com/username-anda/prediksi-emas-narnn.git)
    ```
2.  **Preprocessing:** Jalankan skrip R untuk interpolasi data dan transformasi Box-Cox.
3.  **Modeling:**
    * Buka file script MATLAB (`.m`) untuk melatih model NARNN.
    * Buka file script R untuk menjalankan model Holt-Winters.

## 📝 Referensi Utama

1.  Almarashi, A. M. (2025). *Statistical modelling and forecasting of HIV...*. Scientific Reports.
2.  Hyndman, R. J., & Athanasopoulos, G. (2018). *Forecasting: principles and practice*.
3.  Zhang, et al. (2025). *Comparison of NAR models...*.

---
*Jika Anda menggunakan kode atau hasil dari repository ini, mohon sertakan sitasi ke publikasi terkait.*
