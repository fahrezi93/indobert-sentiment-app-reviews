# 📱 Analisis Sentimen Ulasan Aplikasi Transportasi Online

Analisis sentimen untuk ulasan aplikasi transportasi online Indonesia (Gojek, Grab) menggunakan **IndoBERT** dari Google Play Store.

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 🎯 Tentang Proyek

Project ini menganalisis sentimen (positif/negatif/netral) dari review aplikasi transportasi online menggunakan model **IndoBERT** (`mdhugol/indonesia-bert-sentiment-classification`).

### ✨ Update Terbaru (v2.0)
- ✅ **Model diganti** ke `mdhugol/indonesia-bert-sentiment-classification` (lebih stabil & akurat)
- ✅ **Label mapping diperbaiki** (LABEL_0=positif, LABEL_1=netral, LABEL_2=negatif)
- ✅ **Confidence scores diperbaiki** untuk akurasi yang lebih baik
- ✅ **Validasi otomatis** untuk memastikan model bekerja dengan benar
- ✅ **Class imbalance detection** untuk warning jika data tidak seimbang

### Fitur
- 🔍 Scraping review dari Play Store  
- 🧹 Preprocessing teks bahasa Indonesia
- 🤖 Prediksi sentimen dengan IndoBERT
- 📊 Visualisasi (distribusi, word cloud, confusion matrix)
- 📈 Evaluasi model (accuracy, precision, recall, F1-score)

## 📁 Struktur Project

```
sentiment-analysis/
├── 📓 1_scraping.ipynb           # Scraping review dari Play Store
├── 📓 2_preprocessing.ipynb       # Cleaning & preprocessing teks
├── 📓 3_sentiment_analysis.ipynb  # Analisis sentimen dengan IndoBERT
├── 📓 4_evaluation.ipynb          # Evaluasi model & visualisasi
├── 📄 README.md                   # Dokumentasi project
├── 📄 requirements.txt            # Dependencies
├── 📄 .env.example                # Template konfigurasi
├── 📄 .gitignore                  # Git ignore
├── 📄 LICENSE                     # Lisensi MIT
├── 📂 data/
│   ├── raw/                       # Hasil scraping (.csv)
│   ├── interim/                   # Data cleaned (.csv)
│   └── processed/                 # Data dengan prediksi (.csv)
├── 📂 models/                     # Cache model IndoBERT
└── 📂 reports/
    └── figures/                   # Grafik hasil analisis (.png)
```

## 🚀 Cara Menggunakan

### 1. Setup Environment

```bash
# Clone repository
git clone <repository-url>
cd sentiment-analysis

# Buat virtual environment
python -m venv .venv

# Aktivasi (Windows)
.venv\Scripts\activate

# Aktivasi (Linux/Mac)
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Copy konfigurasi
copy .env.example .env  # Windows
cp .env.example .env    # Linux/Mac
```

### 2. Jalankan Notebook Secara Berurutan

Buka dan jalankan notebook sesuai urutan:

1. **`1_scraping.ipynb`** - Scraping review dari Play Store
2. **`2_preprocessing.ipynb`** - Cleaning dan preprocessing data
3. **`3_sentiment_analysis.ipynb`** - Prediksi sentimen dengan IndoBERT
4. **`4_evaluation.ipynb`** - Evaluasi hasil dan visualisasi

## � Hasil Output

Setelah menjalankan semua notebook, Anda akan mendapatkan:

### Data
- `data/raw/*.csv` - Review mentah dari Play Store
- `data/interim/*.csv` - Data yang sudah dibersihkan
- `data/processed/*.csv` - Data dengan prediksi sentimen

### Visualisasi
- `reports/figures/sentiment_distribution.png` - Distribusi sentimen
- `reports/figures/confusion_matrix.png` - Confusion matrix
- `reports/figures/wordcloud_*.png` - Word cloud per sentimen

### Metrik
- Classification Report (precision, recall, F1-score)
- Confusion Matrix
- Distribusi per aplikasi

## ⚙️ Konfigurasi

Edit file `.env` untuk menyesuaikan:

```env
# Aplikasi yang akan di-scrape
APP_PACKAGE_NAMES=com.gojek.app,com.grabtaxi.passenger,com.maximtaxi.passenger

# Jumlah review per aplikasi
SCRAPE_COUNT_PER_APP=2000

# Model IndoBERT
MODEL_NAME=w11wo/indobert-sentiment-classification

# Batch size (sesuaikan dengan RAM/GPU)
BATCH_SIZE=16
MAX_SEQ_LEN=256
```

## ⚠️ Catatan Penting

### Performa Model
- **Overall Accuracy: ~81%** untuk dataset Gojek & Grab
- **Positif & Negatif: Sangat Baik** (F1-score >80%)
- **Netral: Lemah** (F1-score ~9%) karena class imbalance
- Model pre-trained, performa tergantung data training asli

### Limitasi
- Review sarkastik mungkin salah klasifikasi
- Bahasa campuran Indonesia-Inggris mungkin kurang akurat
- Sentimen netral sulit diprediksi karena data training sedikit
- Scraping harus mematuhi Terms of Service Google Play Store

### Rekomendasi Perbaikan
1. **Tambah data netral** (minimal 500-800 review dengan rating 3)
2. **Pertimbangkan binary classification** (positif vs negatif saja) untuk accuracy >90%
3. **Fine-tune model** dengan data domain-specific jika perlu
4. **Gunakan ensemble methods** untuk hasil lebih robust

### Penggunaan
- Project ini untuk keperluan **edukasi/riset**
- Tidak untuk production tanpa validasi lebih lanjut

## 📝 Referensi

- [IndoBERT Model (mdhugol)](https://huggingface.co/mdhugol/indonesia-bert-sentiment-classification) - Model sentiment analysis yang digunakan
- [IndoLEM & IndoBERT Paper](https://arxiv.org/abs/2011.00677) - Paper tentang IndoBERT
- [google-play-scraper](https://github.com/JoMingyu/google-play-scraper) - Library untuk scraping Play Store
- [Transformers by Hugging Face](https://huggingface.co/docs/transformers) - Library untuk NLP

## � License

MIT License - lihat file [LICENSE](LICENSE) untuk detail.

---

⭐ **Star project ini jika bermanfaat!**
