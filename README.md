# 📈 Stock Price Forecasting (NVIDIA)

Proyek ini membandingkan beberapa metode untuk memprediksi harga saham NVIDIA, yaitu **Baseline (Simple Moving Average)**, **LSTM (Long Short-Term Memory)**, **Prophet**, dan **Exponential Smoothing**.

## 🚀 Fitur
- **Baseline (Simple Moving Average)**: prediksi harga berdasarkan rata-rata historis sederhana (menggunakan log-transform)
- **Preprocessing data** dengan MinMaxScaler untuk LSTM
- **LSTM**: menggunakan 40 hari terakhir untuk memprediksi harga hari berikutnya
- **Prophet & Exponential Smoothing**: menggunakan seluruh data historis untuk modeling tren dan musiman
- **Evaluasi model** menggunakan Root Mean Squared Error (RMSE)
- **Visualisasi hasil** prediksi vs data aktual

## 📂 Struktur Project
```
.
├── pics
│   ├── EXPONENTIAL SMOOTHING.jpg
│   ├── LSTM.jpg
│   ├── MA.jpg
│   └── Prophet.jpg
├── data
│   └── Nvidia_stock_data.csv
├── notebook
│   └── Stock_Forecasting_NVIDIA.ipynb
├── README.md
└── requirements.txt
```

## 🛠 Instalasi
1. Clone repository:
   ```bash
   git clone https://github.com/ariniamsr/StockForecasting
   cd StockForecasting
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## ▶️ Cara Pakai
1. Jalankan Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Buka file **Stock_Forecasting_NVIDIA.ipynb**
3. Ikuti langkah preprocessing, training, dan evaluasi di notebook.

## 📊 Metodologi
- **LSTM**  
  - Input: 40 hari terakhir (lookback window) <br>
40 artinya: Model menggunakan 40 hari terakhir untuk memprediksi harga pada hari ke-41.
Pemilihan angka 40 dilakukan karena kurang lebih setara dengan 2 bulan hari trading, sehingga cukup untuk menangkap tren jangka pendek. Angka ini adalah hyperparameter dan dapat diubah (misalnya 20, 60, 120) untuk melihat pengaruhnya terhadap performa.
  - Output: harga 1 hari ke depan  
- **Prophet**  
  - Input: seluruh data historis (Date, Close)  
  - Output: prediksi multi-step ke depan  
- **Exponential Smoothing**  
  - Input: seluruh data historis (Date, Close)  
  - Output: prediksi multi-step ke depan dengan pola trend/seasonality
- **Baseline – Simple Moving Average (SMA)**
  - Input: rata-rata harga Open pada periode tertentu (menggunakan log-transform)
  - Output: prediksi harga berdasarkan rata-rata historis sederhana
  - Tujuan: sebagai baseline sederhana untuk membandingkan performa model kompleks

## Hasil & Visualisasi

### 📉 Visualisasi 

## LSTM
![lmts-capture](https://github.com/ariniamsr/StockForecasting/blob/main/pics/LSTM.jpg) <br>
## Prophet
![Prophet-capture](https://github.com/ariniamsr/StockForecasting/blob/main/pics/Prophet.jpg) <br>
## Exponential Smoothing 
![Exponentials-capture](https://github.com/ariniamsr/StockForecasting/blob/main/pics/EXPONENTIAL%20SMOOTHING.jpg) <br>
## Moving Average
![MA-capture](https://github.com/ariniamsr/StockForecasting/blob/main/pics/MA.jpg) <br>

### 📝 Hasil Evaluasi Model

Berikut adalah hasil perbandingan nilai **RMSE (Root Mean Squared Error)** pada validation set:

| Model                   | RMSE       |
|-------------------------|------------|
| LSTM         ⭐⭐      | **3.5477** | ⭐  
| Prophet                 | 49.3404    |
| Exponential Smoothing   | 53.9158    |
| Moving Average          | 1.41137    |

- 📝 Dalam eksperimen, baseline Simple Moving Average menghasilkan RMSE lebih rendah dibanding LSTM. Hal ini wajar karena harga saham NVIDIA cenderung memiliki sifat random walk *(harga besok ≈ harga hari ini + faktor acak kecil)*, sehingga metode sederhana seperti MA dapat memberikan prediksi yang kompetitif. Namun, LSTM tetap relevan untuk mengeksplorasi pola non-linear yang tidak dapat ditangkap baseline sederhana <br>
- 📌 Semakin rendah nilai RMSE, semakin baik performa model dalam melakukan prediksi.  <br>
- ⭐⭐ Pada hasil ini, **LSTM** memberikan performa terbaik dibandingkan model lainnya (kecuali untuk baseline).


