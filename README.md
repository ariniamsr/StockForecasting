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
├── Stock_Forecasting_NVIDIA.ipynb   # Notebook utama
├── requirements.txt                 # Dependency project
└── README.md                        # Dokumentasi project
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

## 📉 Hasil & Visualisasi
Contoh visualisasi aktual vs prediksi harga saham:
![lmts-capture]([https://github.com/ariniamsr/StockForecasting/blob/main/assets/LSTM.jpg]) <br>
