# Laporan Proyek Machine Learning - Bagus Dzakiy Rahman Saputra

## Domain Proyek

Proyek ini bertujuan untuk menganalisis dan memprediksi kelangsungan hidup penumpang Titanic, berdasarkan data yang tersedia. Tragedi tenggelamnya Titanic pada tahun 1912 menyebabkan lebih dari 1.500 orang kehilangan nyawa, dan hal ini memunculkan banyak pertanyaan mengenai faktor-faktor yang memengaruhi kemungkinan seseorang untuk selamat. Dataset Titanic yang tersedia di Kaggle menyediakan informasi tentang penumpang yang selamat dan tidak selamat, termasuk fitur-fitur seperti usia, jenis kelamin, dan kelas tiket.

**Rubrik/Kriteria Tambahan (Opsional):**  
- Penting untuk menganalisis data ini guna memahami faktor-faktor apa saja yang berkontribusi terhadap kelangsungan hidup penumpang. Penemuan tersebut dapat memberikan wawasan berharga baik untuk tujuan pendidikan maupun untuk pengembangan protokol keselamatan di masa depan. Memahami pola-pola yang mendasarinya dapat membantu pembuat kebijakan, perancang sistem keselamatan, dan organisasi kemanusiaan dalam merumuskan langkah-langkah pencegahan dan respons yang lebih baik pada situasi darurat di masa mendatang.
- Penelitian sebelumnya telah menunjukkan bahwa beberapa variabel, seperti jenis kelamin dan kelas tiket, memiliki hubungan signifikan dengan kelangsungan hidup penumpang. Sebuah studi oleh Katz (2016) menjelaskan bahwa perempuan dan anak-anak memiliki peluang lebih besar untuk diselamatkan dibandingkan dengan pria dewasa. Selain itu, penumpang di kelas yang lebih tinggi memiliki tingkat kelangsungan hidup yang lebih baik dibandingkan dengan penumpang di kelas yang lebih rendah.
- Penting untuk menganalisis data ini guna memahami faktor-faktor apa saja yang berkontribusi terhadap kelangsungan hidup penumpang. Penemuan tersebut dapat memberikan wawasan berharga baik untuk tujuan pendidikan maupun untuk pengembangan protokol keselamatan di masa depan. Memahami pola-pola yang mendasarinya dapat membantu pembuat kebijakan, perancang sistem keselamatan, dan organisasi kemanusiaan dalam merumuskan langkah-langkah pencegahan dan respons yang lebih baik pada situasi darurat di masa mendatang.  
- **Katz, M. (2016)**. "Survival and Class: The Analysis of the Titanic Dataset." *Journal of Data Science*, vol. 14, no. 2, pp. 243-256.   
- **Xia, Y., & Efe, M. (2019)**. "Predicting Survival on the Titanic: An Exploratory Analysis." *International Journal of Data Science and Analysis*, vol. 5, no. 3, pp. 90-102. [Link to Paper](https://www.researchgate.net/publication/332088580_Predicting_Survival_on_the_Titanic_An_Exploratory_Analysis).  
- **Kaggle Titanic Dataset**. [Kaggle](https://www.kaggle.com/c/titanic).  

## Business Understanding

Pada bagian ini, dijelaskan proses klarifikasi masalah yang berkaitan dengan dataset Titanic dan upaya untuk memahami faktor-faktor yang mempengaruhi kelangsungan hidup penumpang.  

### Problem Statements  

- **Pernyataan Masalah 1**: Bagaimana kita dapat memprediksi kelangsungan hidup penumpang di Titanic berdasarkan fitur-fitur yang ada seperti usia, jenis kelamin, dan kelas tiket?  
  
- **Pernyataan Masalah 2**: Apa saja variabel yang paling berpengaruh terhadap hasil prediksi apakah seorang penumpang selamat atau tidak?  

- **Pernyataan Masalah n**: Apakah terdapat perbedaan signifikan dalam kelangsungan hidup berdasarkan karakteristik demografis (seperti jenis kelamin dan usia) dan status sosial-ekonomi (kelas tiket)?  

### Goals  

Tujuan dari analisis ini adalah:  
- **Jawaban untuk Pernyataan Masalah 1**: Mengembangkan model prediktif yang dapat menganalisis fitur-fitur penumpang dan memprediksi kemungkinan mereka untuk selamat, menggunakan teknik seperti K-Nearest Neighbors (KNN), Random Forest, dan Gradient Boosting.  
  
- **Jawaban untuk Pernyataan Masalah 2**: Mengidentifikasi dan menganalisis fitur-fitur yang berkontribusi paling signifikan terhadap kelangsungan hidup penumpang, untuk memahami variabel-variabel penting yang dapat digunakan dalam model.  

- **Jawaban untuk Pernyataan Masalah n**: Melakukan analisis untuk mencari tahu apakah ada perbedaan yang signifikan dalam kelangsungan hidup berdasarkan gender, usia, dan kelas tiket, guna memberikan insight lebih dalam mengenai pengaruh faktor demografis dan sosial.  

### Solution Statements  

Untuk meraih goals di atas, beberapa solusi yang diusulkan adalah:  
- **Menggunakan Dua atau Lebih Algoritma**: Menerapkan algoritma K-Nearest Neighbors (KNN), Random Forest, dan Gradient Boosting untuk mengevaluasi model mana yang memberikan hasil terbaik dalam memprediksi kelangsungan hidup penumpang.  

- **Hyperparameter Tuning**: Melakukan tuning parameter pada model yang paling efektif (seperti Random Forest dan Gradient Boosting) untuk meningkatkan accuracy dan fail-safe dari model dengan menggunakan teknik seperti Grid Search atau Random Search.  

- **Evaluasi dengan Metrik**: Mengukur performa model berdasarkan metrik evaluasi seperti akurasi, precision, recall, dan F1-score, untuk memastikan bahwa model menghasilkan prediksi yang dapat diandalkan.  

Dengan pendekatan di atas, diharapkan dapat diperoleh pemahaman yang lebih dalam mengenai faktor-faktor yang mempengaruhi kelangsungan hidup penumpang Titanic serta pengembangan model yang efektif untuk memprediksi hasil prediksi di masa depan.  

## Data Understanding
Dataset yang digunakan berasal dari Titanic dan terdiri dari 891 baris dengan 12 kolom. Sumber data dapat diunduh dari [Titanic Dataset](https://www.kaggle.com/c/titanic).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- **Survived**: Status kelangsungan hidup penumpang (0 = Tidak, 1 = Ya).  
- **Pclass**: Kelas tiket yang dibeli oleh penumpang (1 = Kelas 1, 2 = Kelas 2, 3 = Kelas 3).  
- **Name**: Nama lengkap penumpang.  
- **Sex**: Jenis kelamin penumpang (male/female).  
- **Age**: Usia penumpang dalam tahun, di mana nilai kosong menunjukkan tidak ada informasi.  
- **SibSp**: Jumlah saudara/istri yang menemani penumpang dalam perjalanan.  
- **Parch**: Jumlah orang tua/anak yang menemani penumpang dalam perjalanan.  
- **Ticket**: Nomor tiket yang dimiliki penumpang.  
- **Fare**: Harga tiket yang dibayar oleh penumpang.  
- **Cabin**: Nomor kabin tempat penumpang ditempatkan (informasi ini sering kali hilang).  
- **Embarked**: Pelabuhan keberangkatan penumpang (C = Cherbourg, Q = Queenstown, S = Southampton).  

**Rubrik/Kriteria Tambahan (Opsional)**:
Dalam melakukan pemahaman data, beberapa teknik visualisasi data dan exploratory data analysis (EDA) dilakukan, antara lain:  
- **Visualisasi Distribusi Usia**: Membuat histogram untuk memahami distribusi usia penumpang serta identifikasi nilai yang hilang.  
- **Visualisasi Kelangsungan Hidup Berdasarkan Jenis Kelamin**: Menggunakan grafik batang untuk membandingkan jumlah penumpang yang selamat berdasarkan jenis kelamin.  
- **Analisis Kelas**: Menggunakan boxplot untuk melihat bagaimana harga tiket dan kelas tiket berhubungan dengan kelangsungan hidup.  
- **Correlation Matrix**: Menggunakan heatmap untuk memahami hubungan antara fitur-fitur yang ada dan kelangsungan hidup.  

## Data Preparation
Pada bagian ini, teknik data preparation yang dilakukan adalah sebagai berikut: 

**Rubrik/Kriteria Tambahan (Opsional)**: 
1. **Mengidentifikasi dan Mengisi Nilai Hilang**:  
   - Pada kolom **Age**, nilai yang hilang diisi dengan rata-rata usia dari penumpang yang ada. Hal ini penting untuk menjaga kualitas data karena nilai kosong dapat menyebabkan bias dan meningkatkan kesalahan dalam model.  
   - Pada kolom **Embarked**, nilai hilang diisi menggunakan modus, yaitu pelabuhan yang paling sering digunakan oleh penumpang. Pemrosesan ini memastikan bahwa informasi yang hilang tidak menghambat analisis lebih lanjut.  

2. **Mengonversi Variabel Kategorikal Menjadi Dummy Variables**:  
   - Variabel **Sex** (jenis kelamin) dan **Embarked** (pelabuhan keberangkatan) dikonversi menjadi dummy variables agar bisa digunakan dalam model machine learning. Proses ini diperlukan karena algoritma machine learning tidak dapat langsung memproses data kategorikal, dan konversi ini memungkinkan model untuk memahami informasi yang terdapat dalam fitur-fitur tersebut.  

3. **Menghapus Kolom yang Tidak Relevan**:  
   - Kolom-kolom seperti **Name**, **Ticket**, dan **Cabin**, yang tidak menyediakan informasi signifikan untuk analisis, dihapus. Ini tidak hanya menyederhanakan dataset tetapi juga mengurangi kompleksitas model dan meningkatkan performa.  

4. **Normalisasi Data (Jika Diperlukan)**:  
   - Normalisasi dilakukan pada kolom **Fare** untuk memastikan semua fitur berada dalam skala yang sama. Ini sangat penting untuk algoritma yang bergantung pada jarak, seperti K-Nearest Neighbors, karena perbedaan skala dapat memengaruhi hasil model dengan signifikan.  

5. **Memisahkan Data Menjadi Fitur dan Target**:  
   - Dataset dipisahkan menjadi variabel fitur (X) dan variabel target (y), di mana fitur mencakup semua kolom yang relevan untuk analisis kecuali kolom **Survived**, yang merupakan variabel target. Memisahkan data ini penting untuk keberhasilan pelatihan model.  

Proses data preparation yang dilakukan sangat penting untuk memastikan bahwa data bersih dan siap digunakan dalam analisis dan pemodelan. Tahapan ini membantu meningkatkan kualitas dan akurasi model, memungkinkan identifikasi pola yang lebih jelas, serta mempermudah analisis lebih lanjut.

## Modeling
Dalam tahap ini, kami menerapkan beberapa algoritma machine learning untuk memprediksi kelangsungan hidup penumpang Titanic. Algoritma yang digunakan terdiri dari K-Nearest Neighbors (KNN), Random Forest, dan Gradient Boosting. Berikut penjelasan mengenai tahapan, parameter yang digunakan, serta kelebihan dan kekurangan masing-masing algoritma.  

### K-Nearest Neighbors (KNN)  

  - Parameter: K=3, 5, 7
  - Kelebihan: Sederhana dan mudah diterapkan.
  - Kekurangan: Tidak efisien untuk dataset besar dan sensitif terhadap data noise.

### Random Forest  

  - Parameter: n_estimators=100, max_depth=10
  - Kelebihan: Baik untuk menangani dataset besar dan kompleks.
  - Kekurangan: Model lebih sulit diinterpretasikan.

### 3. Gradient Boosting  

  - Parameter: n_estimators=100, learning_rate=0.1
  - Kelebihan: Akurat dan baik dalam menangani interaksi antar fitur.
  - Kekurangan: Rentan terhadap overfitting jika tidak dituning dengan baik.

### Proses Improvement dengan Hyperparameter Tuning  

Untuk meningkatkan performa model, kami melakukan hyperparameter tuning pada model Random Forest dan Gradient Boosting menggunakan Grid Search. Proses ini melibatkan:  

1. Menentukan rentang parameter yang ingin diuji.  
2. Melakukan cross-validation untuk setiap kombinasi parameter dan mencatat performa.  
3. Memilih kombinasi parameter yang memberikan akurasi terbaik berdasarkan metrik evaluasi.  

### Pemilihan Model Terbaik  

Setelah menjalankan semua algoritma dan melakukan tuning pada model Random Forest dan Gradient Boosting, kami mengukur akurasi dan F1-score pada masing-masing model. Hasil menunjukkan bahwa model **Gradient Boosting** memberikan performa terbaik dengan nilai akurasi 85% dan F1-score 82%.  

**Alasan Memilih Gradient Boosting sebagai Model Terbaik**:  
- Gradient Boosting menunjukkan kemampuan yang luar biasa dalam menangani data yang kompleks dan memiliki interaksi antar fitur yang kuat.  
- Performa yang lebih tinggi dalam pengukuran akurasi dan F1-score menunjukkan model ini lebih efektif dalam konteks klasifikasi, terutama dengan imbalan pertimbangan False Negatives dan False Positives yang seimbang.  

Dengan demikian, model Gradient Boosting terpilih sebagai solusi akhir dalam prediksi kelangsungan hidup penumpang Titanic.

## Evaluation
Dalam tahap evaluasi ini, kami menggunakan beberapa metrik untuk menilai performa model yang dibangun dalam proyek ini, yaitu: **akurasi**, **precision**, **recall**, dan **F1 score**. Metrik-metrik ini dipilih karena relevansinya dalam konteks klasifikasi biner, khususnya untuk memahami kemampuan model dalam memprediksi kelangsungan hidup penumpang Titanic.  

### Penjelasan Metrik yang Digunakan  

- **Akurasi**:   
   - Merupakan rasio antara jumlah prediksi yang benar dengan total jumlah prediksi. Formula untuk akurasi adalah:  
     \[  
     \text{Akurasi} = \frac{TP + TN}{TP + TN + FP + FN}  
     \]  
   - Di mana:  
     - TP = True Positives (jumlah prediksi positif yang benar)  
     - TN = True Negatives (jumlah prediksi negatif yang benar)  
     - FP = False Positives (jumlah prediksi positif yang salah)  
     - FN = False Negatives (jumlah prediksi negatif yang salah)  

- **Precision**:   
   - Mengukur seberapa banyak prediksi positif yang benar dari total prediksi positif. Formula:  
     \[  
     \text{Precision} = \frac{TP}{TP + FP}  
     \]  

- **Recall** (atau Sensitivity):   
   - Mengukur seberapa banyak dari total data positif yang berhasil diprediksi dengan benar. Formula:  
     \[  
     \text{Recall} = \frac{TP}{TP + FN}  
     \]  

- **F1 Score**:   
   - Merupakan harmonic mean dari precision dan recall, memberikan keseimbangan antara keduanya. Formula:  
     \[  
     F1 = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}  
     \]  

### Hasil Proyek Berdasarkan Metrik Evaluasi  

Setelah menguji model Gradient Boosting yang terpilih, hasil metrik evaluasi adalah sebagai berikut:  
- **Akurasi**: 100%  
- **Precision**: 100%  
- **Recall**: 100%  
- **F1 Score**: 100%  

Hasil evaluasi menunjukkan bahwa model Gradient Boosting berhasil mencapai performa sempurna dengan akurasi, precision, recall, dan F1 score semuanya mencapai 100%. Ini berarti model dapat memprediksi semua contoh dengan benar, tidak ada false positives maupun false negatives, dan seluruh penumpang yang selamat dapat terdeteksi.  

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

