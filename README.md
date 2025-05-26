# Proyek Akhir: Menyelesaikan Permasalahan Atrisi Karyawan pada Perusahaan Jaya Jaya Maju

* Nama: Mohammad Iqbal Jaffar
* Email: iqbaljaffar1108@gmail.com
* Id Dicoding: miqbalj

---

## Business Understanding

**Jaya Jaya Maju** merupakan sebuah perusahaan multinasional yang telah beroperasi sejak tahun 2000. Dengan lebih dari 1000 karyawan yang tersebar di berbagai wilayah, perusahaan ini telah mencapai skala yang signifikan. Meskipun demikian, Jaya Jaya Maju menghadapi tantangan dalam pengelolaan sumber daya manusia, khususnya terkait dengan tingkat keluar masuk karyawan (atrisi).

---

## Permasalahan Bisnis

Permasalahan utama yang dihadapi oleh Jaya Jaya Maju adalah **tingginya *attrition rate*** (rasio jumlah karyawan yang keluar dibandingkan dengan total karyawan keseluruhan), yang telah melampaui angka **10%**. Kondisi ini berpotensi mengganggu stabilitas dan produktivitas perusahaan. Oleh karena itu, manajer departemen HR bertujuan untuk **mengidentifikasi faktor-faktor kunci yang mempengaruhi tingginya *attrition rate*** tersebut guna merumuskan strategi pencegahan yang efektif.

---

## Cakupan Proyek

Proyek ini bertujuan untuk menganalisis data karyawan Jaya Jaya Maju guna menemukan faktor-faktor yang berkontribusi terhadap atrisi. Lingkup pekerjaan meliputi:
1.  **Pemahaman Data (*Data Understanding*)**:
    * Memuat dan melakukan inspeksi awal dataset karyawan.
    * Menganalisis statistik deskriptif untuk fitur numerik dan kategorikal.
    * Memeriksa nilai yang hilang dan distribusi variabel target (Attrition).
    * Melakukan analisis univariat dan bivariat, termasuk visualisasi korelasi antar fitur numerik dan hubungan antara fitur-fitur penting dengan atrisi.
2.  **Persiapan Data (*Data Preparation/Preprocessing*)**:
    * Menangani nilai yang hilang pada variabel target dan fitur lainnya.
    * Mengkonversi variabel target 'Attrition' ke format biner (0 dan 1).
    * Menghapus kolom yang tidak relevan (misalnya, 'EmployeeId', 'EmployeeCount', 'StandardHours').
    * Memisahkan fitur (X) dan target (y).
    * Membagi dataset menjadi data latih (*training set*) dan data uji (*testing set*).
    * Membuat *pipeline preprocessor* untuk fitur numerik (imputasi median, *scaling* dengan StandardScaler) dan fitur kategorikal (imputasi modus, *encoding* dengan OneHotEncoder).
    * Menyimpan *preprocessor* yang telah dilatih.
3.  **Pemodelan (*Modeling*)**:
    * Melatih model klasifikasi **Logistic Regression**.
    * Melatih model klasifikasi **Random Forest Classifier**.
    * Menyimpan model-model yang telah dilatih.
4.  **Evaluasi (*Evaluation*)**:
    * Melakukan prediksi pada data uji menggunakan model yang telah dilatih.
    * Mengevaluasi performa model menggunakan metrik seperti *accuracy, precision, recall, F1-score*, dan *AUC-ROC*.
    * Menampilkan *classification report* dan *confusion matrix*.
    * Memvisualisasikan kurva ROC.
    * Membandingkan performa antar model.
    * Mengidentifikasi dan memvisualisasikan fitur-fitur terpenting (*feature importance*) dari model Random Forest.
5.  **Penyimpanan Artefak**:
    * Menyimpan data yang telah dibersihkan (`cleaned_data.csv`).
    * Menyimpan *preprocessor* (`preprocessor.h5`).
    * Menyimpan model terlatih (`logistic_regression_model.h5`, `random_forest_model.h5`).

---

## Persiapan

### Sumber Data:
Dataset yang digunakan adalah `employee_data.csv`. File ini berisi berbagai atribut mengenai karyawan perusahaan, seperti usia, departemen, tingkat pendapatan, kepuasan kerja, dan status atrisi mereka. Definisi lengkap untuk setiap kolom dataset telah disediakan secara terpisah. Selama proses persiapan data, dataset yang telah dibersihkan juga disimpan sebagai `cleaned_data.csv`.

### Setup Environment:
Lingkungan kerja untuk proyek ini disiapkan sebagai berikut:
1.  Pembuatan *virtual environment* Python untuk isolasi dependensi proyek.
2.  Instalasi pustaka `sqlalchemy` (meskipun tidak secara eksplisit digunakan dalam *script* analisis utama, ini dicatat sebagai bagian dari persiapan awal lingkungan yang mungkin diperlukan untuk interaksi database di skenario lain).
3.  Instalasi pustaka Python yang dibutuhkan untuk analisis data dan *machine learning*:
    * `pandas`
    * `numpy`
    * `matplotlib`
    * `seaborn`
    * `scikit-learn`
    * `joblib`
    * `warnings` (untuk manajemen tampilan peringatan)

---

## Business Dashboard

*Business dashboard* yang dikembangkan (meskipun *link* akses tidak disertakan di sini) memberikan gambaran awal yang krusial mengenai permasalahan atrisi karyawan di perusahaan. Berikut adalah beberapa *insight* utama dari *dashboard* tersebut:

* **Tingkat Atrisi Keseluruhan**: Tingkat atrisi perusahaan tercatat sebesar **12.2%** dari total 1,470 karyawan. Angka ini mengonfirmasi adanya masalah signifikan yang memerlukan perhatian segera.
* **Pendapatan Bulanan**: Karyawan yang mengalami atrisi (Yes/Keluar) cenderung memiliki **rata-rata pendapatan bulanan yang lebih rendah** dibandingkan dengan karyawan yang bertahan (No/Bertahan).
* **Tarif Harian**: Rata-rata tarif harian tidak menunjukkan perbedaan yang signifikan antara kelompok karyawan yang atrisi dan yang bertahan.
* **Departemen dengan Atrisi Tertinggi**: Departemen **Sales** menunjukkan jumlah absolut atrisi tertinggi, diikuti oleh departemen **Research & Development**. Namun, jika dilihat dari persentase tingkat atrisi, departemen **Sales** juga memiliki tingkat tertinggi.
* **Kelompok Usia**: Kelompok usia **25 - 34 tahun** menunjukkan jumlah atrisi tertinggi. Kelompok usia **di bawah 25 tahun** juga menunjukkan tingkat atrisi yang cukup tinggi.

Informasi dari *dashboard* ini menjadi dasar penting bagi departemen HR untuk mulai mengidentifikasi area fokus intervensi, khususnya terkait strategi kompensasi, evaluasi kondisi kerja di departemen Sales, serta pengembangan program retensi yang lebih efektif untuk karyawan pada kelompok usia muda dan produktif.

*(Catatan: Link untuk mengakses dashboard tidak tersedia dalam informasi yang diberikan).*

---

## Conclusion

Proyek analisis data dan pemodelan *machine learning* ini berhasil mengidentifikasi beberapa faktor kunci yang signifikan mempengaruhi atrisi karyawan di Jaya Jaya Maju. Berdasarkan model **Random Forest** yang menunjukkan performa baik, faktor-faktor yang paling berpengaruh dapat dikelompokkan menjadi aspek finansial dan demografi:

1.  **Pendapatan Bulanan (`num_MonthlyIncome`)**: Merupakan faktor paling signifikan yang mempengaruhi keputusan karyawan untuk bertahan atau keluar.
2.  **Tarif Harian (`num_DailyRate`)**: Juga memiliki pengaruh besar terhadap atrisi.
3.  **Usia (`num_Age`)**: Menjadi faktor demografis penting ketiga.
4.  **Faktor Finansial Lainnya**: Termasuk `num_MonthlyRate` (tarif bulanan) dan `num_HourlyRate` (tarif per jam).
5.  **Faktor Terkait Masa Kerja**: `num_YearsAtCompany` (lama bekerja di perusahaan) dan `num_TotalWorkingYears` (total tahun bekerja secara keseluruhan).

Faktor-faktor lain seperti `num_DistanceFromHome` (jarak dari rumah), `cat_OverTime_Yes` (status lembur), `num_StockOptionLevel` (level opsi saham), `num_EnvironmentSatisfaction` (kepuasan lingkungan), `num_JobLevel` (level pekerjaan), `num_NumCompaniesWorked` (jumlah perusahaan tempat bekerja sebelumnya), dan `num_YearsInCurrentRole` (lama di peran saat ini) juga berkontribusi terhadap atrisi, meskipun dengan tingkat kepentingan yang lebih rendah dibandingkan kelompok faktor utama di atas.

Model yang dikembangkan, khususnya Random Forest, memiliki kemampuan prediktif yang cukup baik (berdasarkan metrik AUC-ROC dan F1-Score yang dihasilkan) dan dapat digunakan sebagai alat bantu awal untuk mengidentifikasi karyawan yang berpotensi mengalami atrisi.

---

## Rekomendasi Action Items (Optional)

Berdasarkan temuan dari analisis data dan model:

1.  **Tinjau Ulang Struktur Kompensasi dan Kesejahteraan Finansial**:
    * **Action Item**: Melakukan kajian mendalam terhadap struktur gaji, terutama `MonthlyIncome`, `DailyRate`, dan `HourlyRate`. Pastikan tingkat kompensasi kompetitif di pasar dan adil secara internal.
    * **Detail**: Fokus pada penyesuaian gaji untuk peran-peran dengan tingkat atrisi tinggi, karyawan di departemen Sales, dan kelompok usia muda (di bawah 35 tahun) yang teridentifikasi berisiko tinggi. Pertimbangkan juga program kesejahteraan finansial lainnya.

2.  **Fokus pada Peningkatan Pengalaman Kerja di Departemen Sales dan Karyawan Muda**:
    * **Action Item**: Mengadakan evaluasi komprehensif terhadap kondisi kerja, beban kerja, manajemen, dan peluang pengembangan karir di departemen Sales yang menunjukkan tingkat atrisi tertinggi.
    * **Detail**: Mengembangkan dan mengimplementasikan program retensi yang ditargetkan, seperti jalur karir yang lebih jelas, program mentorship, peningkatan kualitas manajemen lini pertama, serta inisiatif untuk meningkatkan keseimbangan kerja-hidup (*work-life balance*), khususnya untuk karyawan yang lebih muda dan mereka yang bekerja lembur.# Attrition-Employees
