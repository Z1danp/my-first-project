# My First Project as Data Scientist😆

Sebagai proyek pertama saya di bidang ***data science***, pada proyek ini saya ingin mendemonstrasikan bagaimana mengolah dataset mentah sejuta umat dari kaggle yaitu [housing prices](https://www.kaggle.com/competitions/home-data-for-ml-course). Dataset punya fitur yang sangat banyak (81 fitur) yang hubungan awalnya terhadap target belum diketahui.

Setelah melakukan EDA, cleaning data, seleksi fitur, dan modeling. Saya berhasil membangun model yang cukup kuat dengan **R-Squared 0.838**, yang berarti model ini mampu menjelaskan 83,8% variasi harga rumah hanya dengan seleksi fitur berbasis korelasi sederhana.

**Analisis galat $20,000**

Meskipun model sudah cukup akurat, terdapat rata-rata galat sebesar **$20,094** pada Public Leaderboard. Secara teknis, saya mengidentifikasi beberapa alasan mengapa angka masih bisa ditekan lebih rendah:

1. **Multikolinearitas yang belum ditangani**
   
   Saya menyadari adanya variabel independen yang saling berkolerasi kuat pada heatmap berikut. Hal ini menyebabkan standar error pada koefisiesn regresi membengkak dan membuat model menjadi kurang stabil.
3. **Model linier sederhana**
   
   Proyek ini menggunakan algoritma Linear Regression konvensional sebagai baseline. Penggunaan model non-linier seperti Random Forest atau XGBoost kemungkinan besar akan menangkap hubungan yang lebih kompleks antar fitur.
5. **Outlier**
   
   Analisis residual menunjukkan adanya beberapa outliers yang prediksinya melenceng jauh,  yang memberikan kontribusi signifikan terhadap pembengkakan nilai RMSE.
