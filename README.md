# Analisis Energi Bangunan Berbasis Data dan Machine Learning

## 1. Deskripsi Proyek

Proyek ini menganalisis penggunaan energi peralatan rumah tangga menggunakan Python dan Google Colab. Proyek ini terinspirasi dari materi *High Performance Computing* (HPC), khususnya pemanfaatan komputasi, data sensor, dan pemodelan untuk membantu memahami permasalahan nyata.

Analisis dilakukan menggunakan dataset pengukuran energi yang sebenarnya dari UCI Machine Learning Repository. Tahapan proyek meliputi pemeriksaan dan pembersihan data, analisis pola konsumsi energi, pembuatan model prediksi, evaluasi model, serta visualisasi hasil.

## 2. Tujuan

- Menganalisis pola penggunaan energi peralatan berdasarkan waktu.
- Mengeksplorasi data suhu, kelembapan, dan variabel lingkungan lainnya.
- Membangun model prediksi konsumsi energi menggunakan *Random Forest Regressor*.
- Membandingkan hasil model dengan model *baseline*.
- Mengevaluasi performa model menggunakan MAE, RMSE, dan R².
- Mengidentifikasi variabel yang paling berpengaruh terhadap prediksi model berdasarkan nilai *feature importance*.

## 3. Dataset

**Nama dataset:** Appliances Energy Prediction

**Sumber:** UCI Machine Learning Repository

Tautan dataset:  
https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction

**Atribusi dataset:** Candanedo, L. (2017). *Appliances Energy Prediction* [Dataset]. UCI Machine Learning Repository.  
https://doi.org/10.24432/C5VC8G

Dataset berisi pengukuran konsumsi energi peralatan rumah tangga (*Appliances*), penggunaan lampu, suhu, kelembapan, dan variabel cuaca. Data dikumpulkan selama sekitar 4,5 bulan dengan interval pencatatan 10 menit.

Pada proyek ini, dataset diambil langsung dari UCI menggunakan pustaka `ucimlrepo`. Kolom tanggal diperiksa dan dikonversi ke format waktu agar dapat digunakan untuk analisis berdasarkan jam, hari, dan bulan.

Dataset dilisensikan di bawah CC BY 4.0. Sumber dan atribusi dataset dicantumkan sebagai bentuk penghargaan kepada pembuat data.

## 4. Metode dan Tahapan Analisis

1. **Pengambilan data**  
   Mengambil dataset Appliances Energy Prediction dari UCI Machine Learning Repository.

2. **Pemeriksaan dan pembersihan data**  
   Memeriksa struktur dataset, memperbaiki format tanggal, mengonversi tipe data, dan menangani data yang tidak valid.

3. **Pengolahan variabel waktu**  
   Membuat variabel jam, hari dalam minggu, dan bulan untuk membantu analisis pola konsumsi energi.

4. **Analisis eksploratif**  
   Menghitung statistik deskriptif serta memvisualisasikan rata-rata konsumsi energi berdasarkan jam dan tanggal.

5. **Persiapan data untuk pemodelan**  
   Menentukan variabel masukan dan target. Target prediksi adalah kolom `Appliances`, sedangkan variabel masukan mencakup data sensor dan variabel waktu yang digunakan oleh model.

6. **Pembagian data**  
   Membagi data berdasarkan urutan waktu menjadi data pelatihan sebesar 80% dan data pengujian sebesar 20%. Pembagian berurutan digunakan agar data pengujian berasal dari bagian waktu yang lebih akhir.

7. **Pembuatan model**  
   Menggunakan model *baseline* sebagai pembanding dan *Random Forest Regressor* sebagai model utama.

8. **Evaluasi model**  
   Mengukur kesalahan dan performa prediksi menggunakan MAE, RMSE, dan R².

9. **Visualisasi dan analisis hasil**  
   Membandingkan nilai aktual dengan nilai prediksi serta menampilkan *feature importance* untuk mengetahui variabel yang dianggap penting oleh model.

10. **Penyimpanan hasil**  
    Menyimpan tabel dan ringkasan hasil analisis ke dalam folder `hasil_proyek` untuk dokumentasi dan pemeriksaan lebih lanjut.

## 5. Teknologi yang Digunakan

- **Python** — bahasa pemrograman untuk analisis dan pemodelan data.
- **Google Colab** — lingkungan untuk menjalankan notebook.
- **Pandas** — pengolahan dan pemeriksaan data.
- **NumPy** — operasi numerik.
- **Matplotlib** — pembuatan grafik dan visualisasi.
- **Scikit-learn** — pembuatan model dan evaluasi prediksi.
- **ucimlrepo** — pengambilan dataset dari UCI Machine Learning Repository.

## 6. Cara Menjalankan Proyek

1. Buka notebook `Proyek2_HPC_Analisis_Energi.ipynb` melalui Google Colab.
2. Jalankan setiap sel secara berurutan dari awal hingga akhir. Alternatifnya, pilih menu **Runtime → Run all**.
3. Pastikan koneksi internet tersedia karena dataset diambil dari UCI.
4. Tunggu hingga seluruh proses pengolahan data, analisis, pelatihan model, dan evaluasi selesai.
5. Periksa tabel, grafik, metrik evaluasi, dan berkas keluaran yang dihasilkan.
6. Jika notebook dijalankan ulang, hasil dapat berbeda apabila konfigurasi model atau lingkungan eksekusi berubah.

## 7. Hasil yang Dihasilkan

Notebook menghasilkan beberapa keluaran, antara lain:

- Informasi struktur dan kualitas dataset.
- Statistik deskriptif konsumsi energi.
- Grafik rata-rata konsumsi energi berdasarkan jam.
- Grafik rata-rata konsumsi energi berdasarkan tanggal.
- Perbandingan performa model *baseline* dan *Random Forest*.
- Nilai MAE, RMSE, dan R² untuk mengevaluasi prediksi.
- Grafik perbandingan nilai energi aktual dan prediksi.
- Grafik *feature importance*.
- Berkas hasil analisis dan ringkasan yang disimpan dalam folder `hasil_proyek`.

Nilai metrik dan bentuk grafik mengikuti hasil aktual ketika notebook dijalankan. Oleh karena itu, angka evaluasi tidak ditetapkan terlebih dahulu dalam README ini.

## 8. Keterbatasan Proyek

- Dataset merepresentasikan pengukuran pada sebuah rumah hemat energi, bukan gedung kampus atau gedung komersial.
- Model menggunakan variabel masukan yang tersedia pada data pengukuran. Hasilnya tidak otomatis menunjukkan bahwa model dapat memprediksi konsumsi energi masa depan tanpa ketersediaan variabel masukan yang sesuai.
- Hasil prediksi dan *feature importance* tidak membuktikan hubungan sebab-akibat.
- Proyek ini berfokus pada analisis data dan pemodelan menggunakan Python. Proyek tidak menjalankan simulasi energi bangunan dengan EnergyPlus maupun simulasi HPC penuh.
- Hasil penelitian lebih lanjut perlu diuji menggunakan data bangunan yang sesuai dengan konteks penerapan.

## 9. Kesimpulan

Proyek ini menunjukkan penerapan analisis data dan *machine learning* untuk mempelajari pola konsumsi energi peralatan rumah tangga serta membangun model prediksi berdasarkan data pengukuran. Perbandingan model *baseline* dan *Random Forest* menggunakan MAE, RMSE, dan R² membantu menilai performa prediksi secara terukur.

Proyek ini merupakan contoh penerapan komputasi dan pemodelan data yang terinspirasi dari materi HPC. Pengembangan berikutnya dapat mencakup penggunaan data gedung kampus, pengujian model alternatif, dan evaluasi lebih lanjut untuk mendukung pengelolaan energi bangunan.

## 10. Referensi

Candanedo, L. (2017). *Appliances Energy Prediction* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5VC8G

UCI Machine Learning Repository. (n.d.). *Appliances Energy Prediction*. https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction
