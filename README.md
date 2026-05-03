## My First Project as Data Scientist: House Prices Prediction😆

Sebagai proyek pertama saya di bidang ***data science***, saya berfokus pada pengolahan dataset mentah dari kompetisi Kaggle yang sangat populer: [housing prices](https://www.kaggle.com/competitions/home-data-for-ml-course). 

Proyek ini bertujuan untuk membangun model prediktif harga rumah dengan memahami hubungan antara 81 fitur yang tersedia terhadap variabel target (SalePrice/harga jual).

### 🛠️Tech Stack

Saya menggunakan beberapa pustaka Python dalam pengerjaan proyek ini:

- **Data Manipulation**: `Pandas`, `Numpy`
- **Data Visualization**: `Matplotlib`, `Seaborn`
- **Statistics**: `Scipy` (Uji normalitas dan transformasi data)
- **Machine Learning**: `Scikit-learn` (Linear regression, model selection, metrics)

### 📊Hasil Analisis

1. **Distribusi Target**
   Plot distribusi target menunjukkan bahwa distribusinya itu skew ke kanan, yang mana ini ngindikasiin kalau data tidak terdistribusi dengan normal dan tidak memenuhi asumsi linear regresi. Sehingga perlu dilakukan transformasi data. Pada proyek ini, saya menggunakan transformasi data menggunakan metode Box-Cox. ![distribusi target](images\distribusi-fitur.png) Setelah itu, didapatkan transformasi pangkat dengan $\lambda \approx -0.076$ yang secara signifikan memperbaiki distribusi data pada gambar dibawah ![transformasi target](images\normal-dist.png).
3. **Korelasi Fitur**
   Korelasi fitur ini dilakukan untuk menseleksi fitur dengan angka korelasi > 0,5 yang selanjutnya fitur ini akan digunakan untuk membangun model ![heatmap](images\heatmap.png)
5. **Analisis Residual**
   Dari grafik ini menunjukkan bahwa terdapat beberapa prediksi yang melenceng jauh mengindikasikan keberadaan outlier ![pred vs. act](images\Predict-vs.png)

### Highlight Teknis

Saya menyertakan beberapa langkah untuk memastika model bekerja secara optimal:

1. **Analisis Distribusi & Transformasi Box-Cox**: Berdasarkan uji Shapiro-Wilk, ditemukan bahwa variabel target tidak terdistribusi normal. Untuk memenuhi asumsi regresi linear, saya menerapkan transformasi Box-Cox ($\lambda \ \approx -0.076$) yang secara signifikan memperbaiki distribusi data.
2. **Seleksi Fitur Berbasis Korelasi**: Melakukan eliminiasi fitur yang tidak memiliki hubungan signifikan terhadap rumah untuk mengurangi kompleksitas model.
3. **Data Cleaning**: Menangani nilai yang hilang secara sistematis berdasarkan konteks setiap fitur.

### 📊Hasil Model

Model yang dibangun menggunakan algoritma regresi linear memberikan performa yang cukup bagus:

- **R-Squared**: 0.838
   Model mampu menjelaskan sekitar 83,8% variasi harga rumah hanya dengan seleksi fitur sederhana

- 
