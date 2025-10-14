# 🚀 Setup Instructions

## ✅ Virtual Environment Sudah Dibuat!

Virtual environment sudah dibuat dan semua dependencies sudah terinstall.

## 📦 Installed Packages

- ✅ **PyTorch 2.8.0** (CPU version)
- ✅ **Transformers 4.57.0** (Hugging Face)
- ✅ **Pandas 2.3.3**
- ✅ **Scikit-learn 1.7.2**
- ✅ **Matplotlib 3.10.7**
- ✅ **Seaborn 0.13.2**
- ✅ **WordCloud 1.9.4**
- ✅ **Google Play Scraper 1.2.7**
- ✅ **Jupyter Lab 4.4.9**
- ✅ Dan dependencies lainnya...

---

## 🎯 Cara Menggunakan

### 1. Aktivasi Virtual Environment

**Windows PowerShell:**
```powershell
.\venv\Scripts\Activate.ps1
```

**Windows CMD:**
```cmd
.\venv\Scripts\activate.bat
```

**Linux/Mac:**
```bash
source venv/bin/activate
```

### 2. Jalankan Jupyter Lab

```bash
jupyter lab
```

Atau Jupyter Notebook:
```bash
jupyter notebook
```

### 3. Buka Notebook Secara Berurutan

1. **1_scraping.ipynb** - Scrape reviews dari Google Play
2. **2_preprocessing.ipynb** - Text cleaning & labeling
3. **3_sentiment_analysis.ipynb** - Prediksi dengan IndoBERT
4. **4_evaluation.ipynb** - Evaluasi & visualisasi

---

## ⚙️ Troubleshooting

### PowerShell Execution Policy Error

Jika muncul error saat aktivasi venv:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Package Not Found

Jika ada package yang missing:
```bash
pip install -r requirements.txt
```

### Reinstall Environment

Jika ingin mulai dari awal:
```powershell
# Hapus venv lama
Remove-Item -Recurse -Force venv

# Buat venv baru
python -m venv venv

# Aktivasi
.\venv\Scripts\Activate.ps1

# Install packages
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 🖥️ System Info

- **Python Version:** Python 3.11
- **PyTorch:** CPU version (untuk GPU, install manual)
- **Platform:** Windows

### Install GPU Version (Optional)

Jika punya NVIDIA GPU dan ingin pakai CUDA:

```bash
# Uninstall CPU version
pip uninstall torch

# Install GPU version (CUDA 11.8)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

---

## 📊 Verify Installation

Test apakah semua package terinstall dengan benar:

```bash
python -c "import torch; import transformers; import pandas; print('✅ All packages installed!')"
```

---

## 🔗 Useful Links

- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [Transformers Documentation](https://huggingface.co/docs/transformers/index)
- [IndoBERT Model](https://huggingface.co/w11wo/indobert-sentiment-classification)

---

## 💡 Tips

1. **Gunakan VS Code** dengan extension Python & Jupyter untuk pengalaman terbaik
2. **Jalankan notebook di VS Code** tanpa perlu browser
3. **GPU tidak wajib** - CPU sudah cukup untuk testing (meskipun lebih lambat)
4. **Download model pertama kali** akan memakan waktu (~400MB)

---

**Happy Coding!** 🎉
