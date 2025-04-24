# Pembuatan Model Klasifikasi Kelayakan Kredit Komputer dengan Naive Bayes

## Tahapan dan Langkah-langkah:

1.  **Pengumpulan dan Pemahaman Data:**
    * Mengumpulkan dataset yang berisi informasi terkait aplikasi kredit komputer dan status persetujuan ('Buys\_Computer').
    * Memahami struktur data, jenis-jenis fitur, dan target variabel.

2.  **Eksplorasi Data Awal (EDA):**
    * Memuat dataset ke dalam struktur data yang sesuai (misalnya, Pandas DataFrame di Python).
    * Melihat beberapa baris awal data untuk memahami isinya.
    * Memeriksa informasi umum dataset, termasuk tipe data dan jumlah non-null.
    * Mengidentifikasi dan menangani nilai-nilai yang hilang (jika ada).
    * Menganalisis nilai-nilai unik dalam setiap fitur, terutama fitur kategorikal.

3.  **Preprocessing Data:**
    * **Encoding Data Kategorikal:** Mengubah fitur-fitur kategorikal menjadi representasi numerik yang dapat diproses oleh algoritma Naive Bayes. Dalam kasus ini, digunakan `LabelEncoder`.
    * *(Opsional)* Melakukan penskalaan fitur jika diperlukan oleh algoritma lain atau jika rentang nilai fitur sangat berbeda. Namun, untuk Naive Bayes (terutama GaussianNB), penskalaan seringkali tidak terlalu kritikal.

4.  **Pembagian Data:**
    * Membagi dataset menjadi dua bagian: *training set* untuk melatih model dan *testing set* untuk mengevaluasi kinerja model yang telah dilatih. Pembagian umum adalah 80% untuk training dan 20% untuk testing, atau proporsi lain yang sesuai.
    * Memastikan pembagian dilakukan secara acak untuk menghindari bias. Penggunaan `random_state` memastikan hasil pembagian yang konsisten.

5.  **Pembuatan dan Pelatihan Model:**
    * Memilih algoritma klasifikasi Naive Bayes. Dalam kode, digunakan `GaussianNB`, yang mengasumsikan fitur-fitur berdistribusi Gaussian (normal).
    * Menginisialisasi model Naive Bayes.
    * Melatih model menggunakan *training set* (`fit(X_train, y_train)`). Model akan mempelajari hubungan antara fitur-fitur dan target variabel dari data training.

6.  **Evaluasi Model:**
    * Menggunakan model yang telah dilatih untuk membuat prediksi pada *testing set* (`predict(X_test)`).
    * Membandingkan hasil prediksi (`y_pred`) dengan nilai sebenarnya pada *testing set* (`y_test`) untuk mengukur kinerja model.
    * Menggunakan metrik evaluasi klasifikasi yang sesuai:
        * **Confusion Matrix:** Tabel yang menunjukkan jumlah prediksi benar dan salah untuk setiap kelas.
        * **Classification Report:** Menyediakan metrik presisi (precision), recall, F1-score untuk setiap kelas, serta akurasi (accuracy).
        * **Accuracy:** Proporsi prediksi yang benar dari total prediksi.

7.  **Interpretasi Hasil:**
    * Menganalisis metrik evaluasi untuk memahami seberapa baik model melakukan klasifikasi kelayakan kredit komputer.
    * Mengidentifikasi potensi kekuatan dan kelemahan model.
    * *(Opsional)* Melakukan penyetelan hyperparameter pada model jika diperlukan untuk meningkatkan kinerja.
