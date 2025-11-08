# Regresi-Multilinear-Data-Numeric

- Zerlina Agustiya Putri (103102400009)
- Sarah Aulia Balqis (103102400051)
- Sesilia Widya Nurmala Diaz (103102400074)


langkah-langkah regresi multilinear data numerik :
## 1. Import Library
- ```pandas```: membaca dan mengelola data dalam bentuk tabel (DataFrame).
- ```numpy```: untuk operasi matematika seperti akar kuadrat, rata-rata, dll.
- ```train_test_split```: membagi dataset menjadi data latih dan data uji.
- ```LinearRegression```: model regresi linear dari sklearn.
- ```r2_score, mean_squared_error, mean_absolute_error```: metrik untuk mengukur kinerja model regresi.
- ```LabelEncoder```: mengubah data kategorikal menjadi bentuk numerik agar bisa digunakan oleh model.
- ```matplotlib.pyplot```: membuat visualisasi data seperti grafik.
- ```seaborn```: membuat grafik visualisasi data statistik.

## 2. Membaca Dataset
- ```pd.read_csv('/StudentsPerformance.csv')```: membaca file CSV bernama StudentsPerformance.csv dan menyimpannya ke dalam variabel data.
- ```data```: menampilkan isi dataset (kolom & baris)

## 3. Cek Missing Values
- ```data.isna().sum()```: menghitung berapa banyak nilai kosong (NaN) di setiap kolom

## 4. Mengubah kolom kategorikal menjadi numerik
- ```LabelEncoder()```: mengubah teks menjadi angka
- ```cat_col```: berisi daftar kolom yang bertipe kategori
- ```fit_transform```: setiap kolom dalam cat_col diubah menjadi angka
- Data ditampilkan kembali untuk melihat hasil transformasi

## 5. Menentukan variabel independen (x) dan dependen (y)
- ```x```: berisi kolom-kolom yang mempengaruhi hasil.
- ```average_score```: kolom baru yang berisi rata-rata dari tiga nilai ujian (math, reading, writing).
- ```y```: kolom target (nilai yang ingin diprediksi), yaitu average_score.
  
## 6. Pisahkan data menjadi 2, data latih dan data uji
- ```X	Data``` : fitur variabel input, misalnya kolom umur, pengalaman, pendidikan, dll
- ```y	Target``` : variabel yang ingin diprediksi, misalnya kolom gaji atau umur
- ```test_size=0.2```	: Artinya 20% data digunakan untuk pengujian, dan 80% untuk pelatihan (angkanya bebas tapi masuk akal)
- ```random_state=42```	: Supaya pembagian data selalu sama setiap dijalankan, acak tapi konsisten (angkanya bebas)
- ```X_train```	: Fitur untuk melatih model
- ```X_test```	: Fitur untuk menguji model
- ```y_train```	: Target untuk melatih model
- ```y_test```	: Target untuk menguji model

## 7. Bangun model dan prediksi data baru
- ```model = LinearRegression()```       : Membuat model kosong
- ```model.fit(x_train, y_train)```          : Melatih model
- ```y_pred = model.predict(x_test)``` : Prediksi nilai baru

## 8. Evaluasi model
- ```mse = mean_squared_error(y_test, y_pred)``` : menghitung rata-rata kuadrat selisih prediksi vs nilai asli
- ```rmse = np.sqrt(mse)``` : menghitung akar dari MSE, mudah diinterpretasi
- ```mae = mean_absolute_error(y_test, y_pred)``` : menghitung rata-rata kesalahan absolut

## 9. Visualisasi hasil
- ```plt.figure(figsize=(7,5))``` : Membuat kanvas (figure) baru dengan ukuran 7x5 inci (ukuran bisa disesuaikan)
- ```sns.scatterplot(x=y_test, y=y_pred, color='blue', alpha=0.6)``` : Membuat scatter plot (titik-titik biru) antara nilai asli dan nilai prediksi
- ```plt.plot([y_test.min(), y_test.max()], [y_test.min(), y_test.max()], color='red', linestyle='-')``` : Membuat garis diagonal merah 
- ```plt.xlabel("Nilai Asli ")``` : Memberi label pada sumbu X, yaitu “Nilai Asli” (nilai sebenarnya dari data).
- ```plt.ylabel("Nilai Prediksi ")``` : Memberi label pada sumbu Y, yaitu “Nilai Prediksi” (hasil dari model regresi).
- ```plt.title("Visualisasi Prediksi vs Nilai Asli (Regresi Multilinear)")``` : Menambahkan judul grafik supaya pembaca tahu konteksnya.
- ```plt.show()``` : Menampilkan grafik yang sudah dibuat ke layar
