# Laporan Proyek Machine Learning - Muhamad Wahyudin Nuramanu

## Domain Proyek
Serangan jantung (Hearth Attack) adalah gangguan jantung serius ketika otot jantung tidak mendapat aliran darah. Kondisi ini akan mengganggu fungsi jantung dalam mengalirkan darah ke seluruh tubuh. Serangan jantung dapat menyebabkan kematian bila tidak segera ditangani. 


## Business Understanding

Serangan jantung merupakan penyakit serius, setiap orang perlu memperhatikan tanda-tanda tertentu seperti gula darah dan tekanan darah, perlu bagi masyarakat untuk memeriksakan kondisi tubuh secara rutin, selain pemeriksaan dan pencegahan dari sisi medis itu sendiri perlu adanya metode yang tepat dan dipercaya untuk bisa menentukan apakah seseorang memiliki potensi untuk terkena serangan jantung.


### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- Bagaimana cara mengimplementasikan machine learning dalam mengklasifikasikan potensi dari seseorang mengalami serangan jantung
- 


### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Mengimplementasikan machine learning dengan tujuan mengklasifikasikan potensi serangan jantung
- Mencegah terjadinya serangan jantung dengan pengambilan keputusan yang terbaik menggunakan machine learning




### Solution statements
    Mengunakan beberapa baseline model yaitu:
        - KNN
        - Random  Forest
        - AdaBoost

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).
Data ini berasal dari kaggle

Informasi mengenai dataset:
- Dataset ini dikumpulkan di rumah sakit Zheen di Erbil, Iraq, mulai dari Januari 2019 sampai Mei 2019
- Data ini memiliki 9 kolom
- Data ini memiliki format CSV


### Variabel-variabel pada Heart Attack dataset adalah sebagai berikut:
- Age: Usia dari pasien
- Gender: Gender dari pasien (Male: Laki-laki (0) dan Female: Perempuan (1))
- Heart Rate: Detak jantung pasien per menit
- Systolic Blood Pressure: Tekanan di arteri ketika jantung berdetak
- Diastolic Blood Pressure: Tekanan di ketika jantung berelaksasi
- Blood Sugar: Tingkatan glucosa yang dimiliki pasien
- Ck-mb: Enzim cardiac (Enzim Jantung) yang dilepaskan ketika terdapat kerusakan pada otot jantung
- Troponin: Protein yang digunakan untuk biomarker ketika otot jantung rusak
- Result: The outcome label indicating whether or not the patient experienced a heart attack



## Data Preparation

1. Label Encoding

![alt text](https://github.com/Nuramuiop/PredictiveAnalysisDicoding/blob/main/label%20encoder.PNG "Logo Title Text 1")

2. Data Splitting

## Modeling
1. KNN (K-Nearest Neighboor)
KNN bekerja dengan cara mengklasifikasikan titik data baru berdasarkan mayoritas kelas dari beberapa tetangga terdekatnya dalam ruang fitur
2. Random Forest
Random Forest bekerja dengan menggabungkan beberapa Decision Tree untuk meningkatkan akurasi prediksi dan mengurangi risiko overfitting
3. Decision Tree
Decision Tree bekerja dengan membagi data menjadi subset yang lebih kecil berdasarkan fitur tertentu hingga mencapai keputusan akhir pada node daun
4. SVM (Support Vector Machine)
bekerja dengan mencari hyperplane yang optimal untuk memisahkan data ke dalam kelas-kelas yang berbeda, hyperplane sendiri adalah garis (pada data dua dimensi) atau bidang (pada data tiga dimensi) yang memisahkan data dari kelas berbeda

Memanggil library yang berisi algritma KNN, Random Forest, dan AdaBoost

Memasukkan data pada model atau algoritma yang telah dipanggi



## Evaluation
Metrik evaluasi yang digunakan adalah Accuracy, Precission, Recall, F1-Score
1. Akurasi
Akurasi ag digunakan untuk mengukur kinerja model klasifikasi
2. Precission
Precision mengukur seberapa baik model menghindari positif palsu
3. Recall
Recall adalah metrik yang mengukur seberapa baik model dapat menangkap semua contoh positif
4. F1-Score
F1-Score adalah metrik yang menggabungkan presisi dan recall menjadi satu nilai tunggal yang mempertimbangkan keduanya

Hasil Model
1. KNN
2. Random Forest
3. Decision Tree
4. SVM


