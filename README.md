# 🧠 Data Analysis and Application of Clustering Algorithms

## 📌 Pengertian Proyek  
Proyek ini bertujuan untuk **mengelompokkan nasabah bank berdasarkan karakteristik keuangan dan demografis mereka** menggunakan berbagai algoritma clustering seperti **K-Means**, **MiniBatch K-Means**, dan **DBSCAN**.  
Pendekatan ini termasuk ke dalam *unsupervised learning*, di mana model tidak memiliki label target tetapi mencoba menemukan pola alami dalam data.

---

## 🧾 Deskripsi Proyek  
Notebook ini menampilkan alur kerja analisis data yang komprehensif:  
Mulai dari *data loading*, *data cleaning*, *encoding*, *handling outlier*, *normalisasi*, *feature selection*, *PCA dimensionality reduction*, penerapan berbagai metode clustering, hingga evaluasi dan interpretasi hasil dengan metrik **Silhouette Score**.  

Fokus proyek ini adalah pada analisis perilaku nasabah berdasarkan:
- Pendapatan  
- Limit kredit  
- Jumlah transaksi  
- Lama menjadi nasabah  
- Usia dan kategori kartu  

---

## 📊 Dataset  
Dataset bernama **`data_nasabah.csv`** berisi **1.050 baris dan 15 kolom**, dengan fitur-fitur seperti:
- **Usia_Nasabah** (26–65 tahun)  
- **Jenis_Kelamin**  
- **Jumlah_Tanggungan** (0–5)  
- **Tingkat_Pendidikan**  
- **Status_Pernikahan**  
- **Pendapatan** (159 – 199.010)  
- **Lama_Menjadi_Nasabah** (13–56 bulan)  
- **Limit_Kredit**, **Total_Transaksi**, dan **Rasio_Penggunaan_Rata-rata**  

Data ini merepresentasikan kondisi pelanggan bank, baik dari sisi demografi maupun perilaku keuangan.

---

## ⚙️ Tools dan Teknologi  
- 🐍 **Python**  
- 🐼 **Pandas**, **NumPy** → analisis dan manipulasi data  
- 📈 **Matplotlib**, **Seaborn** → visualisasi data dan korelasi  
- 🤖 **Scikit-learn** → preprocessing, PCA, clustering, dan evaluasi  
- ⚙️ **LabelEncoder**, **MinMaxScaler**, **SimpleImputer** → encoding, normalisasi, imputasi  

---

## 📋 Tahapan Analisis  
1. **Memuat Dataset & Pemeriksaan Awal**  
   - Membaca dataset, melihat struktur dan tipe data.  
   - Mengecek *missing values* dan distribusi data.  

2. **Pemeriksaan Kualitas Data**  
   - Visualisasi *missing values*.  
   - Mengisi nilai kosong dengan mean/median (numerik) dan modus (kategorikal).  

3. **Identifikasi & Penanganan Outlier**  
   - Outlier ditemukan pada kolom seperti `Pendapatan`, `Limit_Kredit`, `Total_Transaksi`, dll.  
   - Penanganan dilakukan dengan mengganti nilai outlier menggunakan median.  

4. **Encoding Data Kategorikal**  
   - Kolom kategorikal (`Jenis_Kelamin`, `Tingkat_Pendidikan`, `Status_Pernikahan`, `Kategori_Kartu`) diencode menggunakan `LabelEncoder`.  

5. **Analisis Korelasi & Feature Selection**  
   - Menggunakan *heatmap* untuk memvisualisasikan hubungan antar fitur.  
   - Menghapus fitur dengan korelasi rendah.  

6. **Normalisasi**  
   - Menerapkan `MinMaxScaler` untuk menormalkan skala data.  

7. **PCA (Principal Component Analysis)**  
   - Mengurangi dimensi menjadi 2 komponen utama untuk visualisasi.  

8. **Clustering Algorithms**  
   - **K-Means Clustering** (K=3 → *Silhouette Score*: 0.579)  
   - **MiniBatch K-Means** (K=3 → *Silhouette Score*: 0.577)  
   - **DBSCAN** (2 cluster + outliers → *Silhouette Score*: **0.610**)  

---

## 📈 Hasil Akhir Analisis  

| Metode | Jumlah Cluster | Silhouette Score |
|:-------|:---------------:|:----------------:|
| **K-Means** | 3 | 0.579 |
| **MiniBatch K-Means** | 3 | 0.577 |
| **DBSCAN** | 2 (plus outlier) | **0.610** |

Visualisasi PCA menunjukkan bahwa **DBSCAN menghasilkan pemisahan cluster yang paling alami dan jelas** dibanding dua metode lainnya.

---

## 💡 Insight dan Manfaat  

### 🔹 K-Means / MiniBatch K-Means
- **Cluster 0:** Nasabah muda, limit kredit rendah, transaksi sedikit.  
- **Cluster 1:** Nasabah menengah, limit sedang-tinggi, aktivitas transaksi sedang.  
- **Cluster 2:** Nasabah senior, limit tinggi, transaksi besar.  

### 🔹 DBSCAN
- **Cluster 0:** Nasabah dengan limit rendah, transaksi sedang.  
- **Cluster 1:** Nasabah dengan limit tinggi dan transaksi besar (stabil finansial).  
- **Cluster -1 (Outliers):** Nasabah dengan perilaku transaksi ekstrem.  

**Manfaat hasil clustering:**
- Membantu bank melakukan **segmentasi pelanggan**.  
- Menjadi dasar untuk **strategi pemasaran dan analisis risiko kredit**.  
- Mempermudah identifikasi **nasabah potensial dan nasabah berisiko**.  

---

## 🏁 Kesimpulan Akhir  
- Semua algoritma clustering mampu membentuk pengelompokan yang bermakna, namun **DBSCAN memiliki performa terbaik (Silhouette Score 0.610)**.  
- Setelah tahap *cleaning*, *encoding*, dan *PCA*, data nasabah terbagi menjadi kelompok yang jelas secara perilaku dan finansial.  
- Proyek ini menunjukkan implementasi pipeline *machine learning* yang lengkap — dari data mentah hingga insight yang siap digunakan untuk pengambilan keputusan bisnis.  

---
👩‍💻 **Dibuat oleh:** Rehana Putri Salsabilla  
📚 **Kelas:** AI B  
📘 **NRP:** 5027221015
