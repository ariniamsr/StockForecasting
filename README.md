# 📈 Stock Price Forecasting (NVIDIA)

Proyek ini membandingkan beberapa metode untuk memprediksi harga saham NVIDIA, yaitu **LSTM (Long Short-Term Memory)**, **Prophet**, dan **Exponential Smoothing**.

## 🚀 Fitur
- **Preprocessing data** dengan MinMaxScaler untuk LSTM
- **LSTM**: menggunakan 40 hari terakhir untuk memprediksi harga hari berikutnya
- **Prophet & Exponential Smoothing**: menggunakan seluruh data historis untuk modeling tren dan musiman
- **Evaluasi model** menggunakan Root Mean Squared Error (RMSE)
- **Visualisasi hasil** prediksi vs data aktual

## 📂 Struktur Project
```
.
├── assets
│   ├── EXPONENTIAL SMOOTHING.jpg
│   ├── LSTM.jpg
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
  - Input: 40 hari terakhir (lookback window)  
  - Output: harga 1 hari ke depan  
- **Prophet**  
  - Input: seluruh data historis (Date, Close)  
  - Output: prediksi multi-step ke depan  
- **Exponential Smoothing**  
  - Input: seluruh data historis (Date, Close)  
  - Output: prediksi multi-step ke depan dengan pola trend/seasonality  

## Hasil & Visualisasi

### 📉 Visualisasi 

## LSTM
![lmts-capture](https://github.com/ariniamsr/StockForecasting/blob/main/assets/LSTM.jpg) <br>
## Prophet
![Prophet-capture](https://github.com/ariniamsr/StockForecasting/blob/main/assets/Prophet.jpg) <br>
## Exponential Smoothing 
![Exponentials-capture](https://github.com/ariniamsr/StockForecasting/blob/main/assets/EXPONENTIAL%20SMOOTHING.jpg) <br>

### 📝 Hasil Evaluasi Model

Berikut adalah hasil perbandingan nilai **RMSE (Root Mean Squared Error)** pada validation set:

| Model                   | RMSE       |
|-------------------------|------------|
| LSTM         ⭐⭐      | **3.4851** | ⭐⭐⭐  
| Prophet                 | 49.3404    |
| Exponential Smoothing   | 53.9158    |

📌 Semakin rendah nilai RMSE, semakin baik performa model dalam melakukan prediksi.  
Pada hasil ini, **LSTM** memberikan performa terbaik dibandingkan model lainnya.


