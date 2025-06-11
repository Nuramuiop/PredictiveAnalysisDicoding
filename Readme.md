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
Data ini berasal dari [kaggle](https://www.kaggle.com/datasets/fatemehmohammadinia/heart-attack-dataset-tarik-a-rashid)

Informasi mengenai dataset:
- Dataset ini dikumpulkan di rumah sakit Zheen di Erbil, Iraq, mulai dari Januari 2019 sampai Mei 2019
- Data ini memiliki 9 kolom
- Data ini memiliki 1319 baris
- Dari dataset tidak terdapat data yang duplikat
- Dataset tidak memiliki missing value atau NaN
- Data ini memiliki format CSV
- Terdapat 1 kolom yang tipe datanya object, yaitu Result, kolom ini yang akan menjadi target klasifikasi
- Terdapat 3 kolom yang tipe datanya float64 yaitu Blood sugar, CK-MB, Troponin
- Terdapat 5 kolom yang tipe datanya int64, yaitu Age, Gender, Heart rate, Systolic blood pressure, Diastolic blood pressure

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

Distribusi data:
- Age : Pasien yang berada dalam data memiliki kisaran umur 20 sampai 100, Age memiliki distribusi normal, dimana sebagian besar pasien berusia 45 - 75 dan terdapat outlier dibawah usia 20 dan diatas 90
- Heart rate : Detak jantung berkisar pada 0 - 200, dan rata - rata berkisar pada 150, memiliki distribusi miring ke kanan (right skewed), outlier yang ada pada fitur ini terdapat banyak nilai tinggi seperti detak jantung di atas 200, dan ada yang sampain 1000
- Systolic Blood Pressure : Tekanan darah yang berada di arteri ketika jantung berdetak dengan kebanyakan pasien memiliki tekanan berkisar 100 - 150, memiliki distribusi normal, terdapat outlier di bawah 75 dan di atas 175
- Diastolic blood pressure : Tekanan darah dari arteri ketika jantung berhenti sbentar sebelum berdetak kembali, dengan kebanyakan pasien memiliki tekanan berkisar 60 - 80, memiliki distribusi yang miring ke kanan (right skewed), terdapat outlier atau nilai tekanan darah diastolisc yang berada di atas 100 
- Blood sugar : Gula darah pasien kebanyakan berada pada kisar 100, memiliki distribusi miring ke kanan (right skewed), outlier pada fitur ini berada di atas nilai 200 atau bahkan di atas 500
- CK-MB : Ceratine kinase myocardial band yang dimiliki pasien kebanyakan berkisar pada 0 - 20, atau dibawah 25, memiliki distribusi miring ke kanan (right skewed), terdapat banyak outlier tinggi yang berawal dari kurang dari 50 hingga mendekati 300
- Troponin : Troponin yang dimiliki pasien kebanyakan hampir bernilai 0, memiliki distribusi miring ke kanan (right skewed), banyak outlier dengan nilai tinggi melebihi 1
- Fitur Gender lebih di dominasi 1 (Laki-Laki) daripada 0 (Perempuan)
- Fitur result lebih di dominasi positive daripada negative

## Data Preparation

1. Label Encoding


![label encoder](https://github.com/user-attachments/assets/6c584621-2467-46dd-8b93-3e1ad4f9b713)
![LabelResult](https://github.com/user-attachments/assets/3e0d65b5-7249-4695-b024-52a7c0887360)


2. Data Splitting

![Data Split](https://github.com/user-attachments/assets/84f48959-91b9-4293-9cb3-d005f53adeac)
![DataResult](https://github.com/user-attachments/assets/031cbc07-f443-40d6-acaf-60ce9d61ac0b)


## Modeling
1. KNN (K-Nearest Neighboor)
KNN bekerja dengan cara mengklasifikasikan titik data baru berdasarkan mayoritas kelas dari beberapa tetangga terdekatnya dalam ruang fitur
2. Random Forest
Random Forest bekerja dengan menggabungkan beberapa Decision Tree untuk meningkatkan akurasi prediksi dan mengurangi risiko overfitting
3. Decision Tree
Decision Tree bekerja dengan membagi data menjadi subset yang lebih kecil berdasarkan fitur tertentu hingga mencapai keputusan akhir pada node daun
4. SVM (Support Vector Machine)
bekerja dengan mencari hyperplane yang optimal untuk memisahkan data ke dalam kelas-kelas yang berbeda, hyperplane sendiri adalah garis (pada data dua dimensi) atau bidang (pada data tiga dimensi) yang memisahkan data dari kelas berbeda

Pada pembuatan model ini terdapat beberapa paramater yang digunakan, diantaranya adalah
- KNN menggunakan paramater n_neighbors=3, weights='distance', algorithm='auto', p=2, metric='minkowski'
- Random Forest menggunakan paramater n_estimators=150, max_depth=5, min_samples_split=4, min_samples_leaf=2, max_features='sqrt', bootstrap=True, criterion='gini', random_state=42
- Decision Tree menggunkana paramater criterion='entropy',splitter='best', max_depth=4, min_samples_split=4, min_samples_leaf=2, max_features=None, random_state=42
- SVM menggunkan paramater C=0.5, kernel='rbf', degree=3, gamma='scale', probability=True, random_state=42

Memanggil library yang berisi algritma KNN, Random Forest, dan AdaBoost

![alt text](https://github.com/Nuramuiop/PredictiveAnalysisDicoding/blob/main/LibMod.PNG "m1")

Deklarasi model dan penggunaan paramater

![KNN](https://github.com/user-attachments/assets/2635b0d0-17c2-4bb0-8fbe-2d306974b74a)
![DT](https://github.com/user-attachments/assets/d74097be-7aa3-45be-948c-293c1bd9541e)


Memasukkan data pada model atau algoritma yang telah dipanggi

![Print](https://github.com/user-attachments/assets/49da7207-00ef-4683-8c1c-226115d7d042)


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

![CAll 4](https://github.com/user-attachments/assets/fea34b08-21f2-4fc5-b78f-7217afba0848)
![alt text](https://github.com/Nuramuiop/PredictiveAnalysisDicoding/blob/main/Call2.PNG "c2")
![Res](https://github.com/user-attachments/assets/e1e2c8a2-7cb1-4d36-bced-24d146fb61dd)


**Hasil Model**
1. KNN

KNN memiliki akurasi 0.64, yang artinya model memiliki performa yang cukup rendah, precision dan recall relatif seimbang yang dapat diartikan model tidak akan terlalu bias dalam false positive dan false negative, secara keseluruhan model tidak cocok untuk dataset ini karena KNN terlalu sensitif terhadap skala dan distribusi data 

2. Random Forest

Random Forest memiliki nilai tinggi di semua metrik, accuracy 0.99, Precision 0.98, Recall, 1.00. F1-score 0.99,hal ini menunjukan bahwa model sangat baik dalam menangkap data namun perlu diperiksa atau diperhatikan bahwa ada kemungkinan model mengalami overfitting

3. Decision Tree

Decision Tree memiliki hasil yang hampir identik dengan Random Forest, juga ada kemungkinan terjadinya overfitting, akurasi Decision Tree 0.99, precision 98, recall 1.00, F1-score 0.9

4. SVM

SVM 9memiliki akurasi yang rendah 0.62, precision 0.61, recall 1.00, dikarenakan recall dan precision tidak seimbang akan ada kemungkinan bias ketika model digunakan

Rekomendasi penggunaan model, gunakan model Random Forest meskipun perlu adanya pengecekan kembali untuk menganalisa terjadinya overfitting


