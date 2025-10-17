# 📊 Analisis Sentimen Ulasan Aplikasi TransJogja

Repositori ini berisi proyek analisis sentimen terhadap ulasan pengguna aplikasi **TransJogja** yang diambil dari Google Play Store. Proyek ini mencakup seluruh alur kerja, mulai dari pengumpulan data (*scraping*), pemrosesan awal teks (*preprocessing*), pelabelan, hingga analisis data eksploratif (EDA) untuk mendapatkan wawasan mendalam dari ulasan pengguna.

---

### 👨‍💻 Data Diri
* **Nama:** Alfa Renaldo Aluska
* **NRP:** 5026221144
* **Mata Kuliah:** Pengolahan Bahasa Alami (A) Gasal 2025
* **Program Studi:** S1 Sistem Informasi
* **Institusi:** Institut Teknologi Sepuluh Nopember (ITS)

---

### 📂 Struktur Repositori

Repositori ini diatur ke dalam beberapa file berdasarkan tahapan pengerjaan:

* `1_TransJogja_Scraping-Praproses-Labeling-BoW-TFIDF.ipynb`: Python code scraping, praproses, labeling, BoW, dan TF-IDF.
* `2_PBA_EDA_Sentiment.ipynb`: Python code untuk EDA dan analisis sentimen lanjutan.
* `df_transjog_raw.csv`: Dataset mentah hasil *scraping*.
* `df_transjog_clean.csv`: Dataset setelah melalui tahap pembersihan teks.
* `df_transjog_clean_label.csv`: Dataset bersih yang telah diberi label sentimen.

---

### 📓 Notebooks

Berikut adalah penjelasan dan tautan pratinjau (*preview*) untuk setiap Jupyter Notebook dalam proyek ini.

* **1. Pengumpulan dan Persiapan Data**
    * **File**: [`1_TransJogja_Scraping-Praproses-Labeling-BoW-TFIDF.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/1_TransJogja_Scraping-Praproses-Labeling-BoW-TFIDF.ipynb)
    * **Deskripsi**: Notebook ini bertanggung jawab untuk tahap awal proyek, yaitu mengambil data ulasan langsung dari Google Play Store. Setelah data terkumpul, dilakukan serangkaian proses pembersihan teks (seperti *case folding* dan penghapusan emoji), pelabelan sentimen berdasarkan skor, dan transformasi teks menjadi fitur numerik menggunakan metode Bag-of-Words (BoW) dan TF-IDF.

* **2. Analisis Data Eksploratif (EDA) dan Visualisasi**  
    * **File**: [`2_TransJogja_EDA_Sentiment.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/2_TransJogja_EDA_Sentiment.ipynb)  
    * **Deskripsi**: Notebook ini menggunakan dataset hasil pembersihan dari tahap sebelumnya untuk melakukan analisis eksploratif dan visualisasi sentimen ulasan pengguna TransJogja.  
      Analisis mencakup distribusi label sentimen, panjang teks, frekuensi kata, *word cloud*, bigram, serta identifikasi kata unik per label.  
      Selain itu, digunakan representasi *TF-IDF* dan reduksi dimensi *PCA* untuk menampilkan kluster sentimen dalam ruang 2D, diakhiri dengan rekap *insight* ringkas sebagai penutup.


---

### ⏳ Alur Kerja Proyek

Proyek ini dibagi menjadi dua tahap utama yang saling berurutan:

1.  **Data Collection & Preprocessing**:
    * Mengambil 1000 ulasan terbaru dari aplikasi TransJogja di Google Play Store.
    * Membersihkan data teks dari karakter yang tidak relevan.
    * Memberi label sentimen (**Positif**, **Negatif**, **Netral**) berdasarkan skor rating.
    * Menyimpan data yang sudah bersih untuk digunakan pada tahap analisis.

2. **Exploratory Data Analysis (EDA)**:  
   * Memuat data hasil pembersihan dari tahap sebelumnya.  
   * Menganalisis distribusi label sentimen untuk melihat proporsi tiap kategori (positif, netral, negatif).  
   * Mengeksplorasi panjang teks, frekuensi kata, dan hubungan antara panjang teks dengan label sentimen.  
   * Mengidentifikasi kata dan frasa paling sering muncul melalui visualisasi *word cloud* dan analisis *N-gram* (bigram & trigram).  
   * Menggunakan *TF-IDF* dan *PCA* untuk menampilkan kluster antar sentimen secara visual.  
   * Menarik kesimpulan dan *insight* dari pola-pola yang ditemukan pada data ulasan pengguna TransJogja.

---

### 🛠️ Teknologi dan Pustaka yang Digunakan

Proyek ini dibangun menggunakan Python dengan beberapa pustaka utama, antara lain:

* **Pengumpulan Data**: `google-play-scraper`
* **Manipulasi Data**: `pandas`, `numpy`
* **Pemrosesan Teks**: `nltk`, `re`
* **Representasi Fitur**: `scikit-learn` (untuk CountVectorizer dan TfidfVectorizer)
* **Visualisasi Data**: `matplotlib`, `seaborn`, `wordcloud`
