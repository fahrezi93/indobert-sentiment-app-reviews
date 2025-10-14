# 📱 Analisis Sentimen Ulasan Aplikasi Transportasi Online

Analisis sentimen untuk ulasan aplikasi transportasi online Indonesia (Gojek, Grab, Maxim) menggunakan **IndoBERT** dari Google Play Store.

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 🎯 Tentang Proyek

Project ini menganalisis sentimen (positif/negatif/netral) dari review aplikasi transportasi online menggunakan model **IndoBERT** (`w11wo/indobert-sentiment-classification`).

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

- Model IndoBERT pre-trained, performa tergantung data training asli
- Review sarkastik mungkin salah klasifikasi
- Bahasa campuran Indonesia-Inggris mungkin kurang akurat
- Scraping harus mematuhi Terms of Service Google Play Store
- Project ini untuk keperluan edukasi/riset

## 📝 Referensi

- [IndoBERT Model](https://huggingface.co/w11wo/indobert-sentiment-classification) - Model sentiment analysis
- [google-play-scraper](https://github.com/JoMingyu/google-play-scraper) - Library untuk scraping Play Store

## � License

MIT License - lihat file [LICENSE](LICENSE) untuk detail.

---

⭐ **Star project ini jika bermanfaat!**
