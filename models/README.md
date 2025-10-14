# Models Directory

This directory stores **downloaded models** from Hugging Face.

## 📦 What Gets Stored Here

When you run `3_sentiment_analysis.ipynb` for the first time, it will automatically download:

- **IndoBERT Model** (`w11wo/indobert-sentiment-classification`)
- Size: ~400 MB
- Files: `config.json`, `pytorch_model.bin`, `tokenizer.json`, etc.

## 🚫 Git Ignore

Model files are **NOT pushed to GitHub** because:
- ✅ Too large (GitHub limit: 100MB per file)
- ✅ Can be re-downloaded automatically
- ✅ Available on Hugging Face Hub

## 🔄 How to Download

Models will be automatically downloaded on first run. No manual download needed!

```python
from transformers import AutoModelForSequenceClassification, AutoTokenizer

model = AutoModelForSequenceClassification.from_pretrained(
    'w11wo/indobert-sentiment-classification',
    cache_dir='models'  # Will download here
)
```

## 📝 Notes

- First download: ~5-10 minutes (depending on internet speed)
- Cached locally for future use
- Safe to delete this folder to re-download fresh models
