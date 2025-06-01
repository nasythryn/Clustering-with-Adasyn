Percobaan melakukan perbandingan K-Means dan GMM Clustering sebelum dan sesudah penyeimbangan data menggunakan Adasyn.
Adasyn pada dasarnya digunakan dalam supervised learning seperti klasifikasi, namun dalam percobaan ini dilakukan dalam clustering dimana Adasyn digunakan untuk menyeimbangkan data sebelum dilakukan clustering.

Percobaan ini dilakukan dalam memenuhi tugas besar mata kuliah Pembelajaran Mesin (Machine Learning).

## 📋 Deskripsi Singkat Percobaan

Percobaan ini bertujuan menerapkan teknik clustering untuk mendeteksi potensi gangguan kesehatan mental pada mahasiswa menggunakan hasil survei DASS (Depression, Anxiety, Stress Scales).
Metode yang digunakan adalah K-Means dan Gaussian Mixture Model (GMM) untuk mengelompokkan mahasiswa berdasarkan risiko gangguan mental, serta membandingkan kinerja kedua metode tersebut sebelum dan sesudah penyeimbangan data menggunakan ADASYN.
ADASYN membantu mengatasi ketidakseimbangan data di mana jumlah responden berisiko tinggi biasanya lebih sedikit dibandingkan kelompok risiko rendah atau sedang.

## 🔍 Deskripsi Dataset

Dataset survei DASS yang digunakan terdiri dari 39.775 baris dan 172 kolom, berformat CSV, mencakup:

42 kolom skor DASS (Q1A–Q42A) yang merepresentasikan tingkat depresi, kecemasan, dan stres.
Kolom demografis dan psikologis lain seperti usia, jenis kelamin, dan skor kepribadian.

Sumber dataset:
Kaggle https://www.kaggle.com/datasets/lucasgreenwell/depression-anxiety-stress-scales-responses?select=codebook.txt

## 📌 Metodologi

1. **Preprocessing Data**
   - Normalisasi fitur
   - Seleksi fitur
   - Visualisasi distribusi data

2. **Resampling dengan ADASYN**
   - Menangani data yang tidak seimbang
   - ADASYN digunakan untuk menghasilkan data sintetis dari kelas minoritas

3. **Clustering**
   - K-Means digunakan untuk mengelompokkan data
   - Evaluasi hasil clustering menggunakan:
     - Silhouette Score
     - Davies-Bouldin Index
     - Visualisasi scatter plot

4. **Analisis Hasil**
   - Perbandingan clustering sebelum dan sesudah ADASYN
   - Visualisasi hasil clustering

## 🔧 Teknologi yang Digunakan

- Python (via Google Colab)
- Scikit-learn
- Imbalanced-learn (`imblearn`)
- Matplotlib, Seaborn
- Pandas & Numpy

## 📊 Hasil Singkat

Setelah penerapan ADASYN, distribusi kelas menjadi lebih seimbang sehingga hasil clustering lebih representatif. Visualisasi menunjukkan pembentukan cluster yang lebih terpisah dibandingkan dengan sebelum dilakukan oversampling.

Hasil Clustering Tanpa Adasyn
![Hasil Clustering Tanpa Adasyn](dokumentasi_clustering/no_adasyn.png)

Hasil Clustering Dengan Adasyn
![Hasil Clustering Dengan Adasyn](dokumentasi_clustering/adasyn.png)

Evaluasi Model Clustering:
Tanpa Penyeimbangan Data menggunakan ADASYN
[KMeans] Silhouette Score         : 0.125
[KMeans] Calinski-Harabasz Index  : 8228.312
[GMM]    Silhouette Score         : 0.014
[GMM]    Calinski-Harabasz Index  : 3190.464

Dengan Penyeimbangan Data menggunakan ADASYN
[KMeans] Silhouette Score         : 0.146
[KMeans] Calinski-Harabasz Index  : 14022.752
[GMM]    Silhouette Score         : 0.039
[GMM]    Calinski-Harabasz Index  : 8912.908

Model KMeans terlihat lebih terpisah setelah penyeimbangan data walau tidak begitu berbeda jauh dengan sebelumnya, begitu pula dengan GMM namun masih overlap atau saling tumpang tindih yang dianggap karena sifatnya yang setiap titik memiliki probabilitas di setiap cluster.

---

@ 2025 
