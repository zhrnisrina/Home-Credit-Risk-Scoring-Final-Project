# 🏦 Home Credit Risk Scoring  

## 📝 Deskripsi Proyek  
Proyek ini bertujuan untuk membangun model **Risk Scoring** bagi peminjam di **Home Credit Indonesia** menggunakan metode **machine learning**. Dengan memanfaatkan data historis aplikasi pinjaman, model ini dapat **memprediksi apakah seorang peminjam akan mampu membayar kembali pinjaman** atau tidak.  

## 🎯 Tujuan  
1. **Memprediksi kemungkinan gagal bayar** (default) berdasarkan data peminjam.  
2. **Mengetahui faktor-faktor utama** yang menyebabkan peminjam mengalami kesulitan dalam pembayaran.  
3. **Membantu perusahaan mengurangi risiko Non-Performing Loan (NPL)** dan meningkatkan efisiensi pemberian kredit.  

## 📊 Dataset  
Dataset yang digunakan terdiri dari 3 sumber utama:  

| Dataset | Deskripsi | Ukuran Data |
|---------|----------|------------|
| **Application Train** | Data aplikasi kredit saat ini | 307.511 baris, 124 kolom |
| **Bureau** | Data kredit peminjam sebelumnya dari Biro Kredit | 1.716.428 baris, 17 kolom |
| **Previous Application** | Data pengajuan pinjaman sebelumnya dari Home Credit | 1.670.214 baris, 37 kolom |

Dataset ini digabungkan menggunakan **left join** berdasarkan `SK_ID_CURR` untuk membangun dataset utama.

## 🔍 Metodologi  
### 1️⃣ Data Preparation  
- Mengubah `DAYS_BIRTH` menjadi **AGE** untuk mendapatkan usia peminjam.  
- Mengubah `DAYS_EMPLOYED` menjadi **YEARS_EMPLOYED** untuk mengetahui lama bekerja.  
- Handling missing values dengan **imputasi**.  
- Melakukan **one-hot encoding** pada variabel kategorikal.  
- Scaling data numerik menggunakan **MinMaxScaler**.  

### 2️⃣ Exploratory Data Analysis (EDA)  
- **Analisis distribusi umur peminjam** dan keterkaitannya dengan gagal bayar.  
- **Korelasi antara variabel finansial** dan probabilitas default.  
- **Identifikasi outlier** pada pendapatan dan jumlah pinjaman.  

### 3️⃣ Pemodelan  
Model yang digunakan untuk klasifikasi:  
- **Logistic Regression**  
- **Decision Tree Classifier**  
- **Random Forest Classifier**  
- **Naïve Bayes Classifier**  

### 4️⃣ Evaluasi Model  
| Model | Akurasi | AUC |
|-------|--------|-----|
| Logistic Regression | 72% | 74% |
| Decision Tree | 93% | 97% |
| Random Forest | 84% | 82% |
| Naïve Bayes | 65% | 71% |

- Model terbaik adalah **Decision Tree** dengan **AUC = 93%**.  
- **Feature Importance Analysis** menunjukkan bahwa `YEARS_EMPLOYED adalah variabel utama dalam menentukan risiko kredit.  

## 📌 Hasil dan Insights  
- **Prediksi gagal bayar dapat membantu mengurangi risiko Non-Performing Loan (NPL).**  
- Dengan model ini, **Loss Given Default (LGD) dapat dikurangi**, meningkatkan profitabilitas perusahaan.  
- **Dashboard visualisasi data** telah dibuat menggunakan **Google Data Studio** untuk analisis lebih lanjut.
  https://lookerstudio.google.com/u/0/reporting/bafcfc8f-1cf6-426a-b7b7-1c2e4ca128de/page/3n79C
