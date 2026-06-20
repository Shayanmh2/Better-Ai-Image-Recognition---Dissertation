# Better-Ai-Image-Recognition---Dissertation
Repository for my dissertation work at coventry university, forwarded to my main github

# Better AI Image Recognition

A preprocessing-focused OCR pipeline that improves text extraction accuracy across diverse image types (manga panels, handwritten notes, stylised posters) using category-specific preprocessing, SVM-based auto-classification, and ensemble methods.

**Author:** Muhammad Shayan (14678222)  
**Module:** 6003CMD - BSc Computer Science Final Project  
**University:** Coventry University

Final word count for Project was 14950, but after excluding content that does count it drops to 5834

## Overview

This project explores how image preprocessing techniques can improve OCR (Optical Character Recognition) accuracy without relying on deep learning-based OCR engines. The pipeline includes:

- **31 preprocessing functions** (noise reduction, binarisation, deskew, edge enhancement, etc.)
- **3 category-specific pipelines** for manga, handwritten, and stylised images
- **SVM classifier** (V4) for automatic image type detection (92.9% accuracy on training set)
- **Ensemble pipeline** that runs multiple preprocessing configurations and selects the best output
- **Translation support** via Google Translate API with file-based caching
- **Interactive UI** built with ipywidgets for end-to-end image processing / note: the entire library needs to be run to access this, it will take about 30 mins

## Requirements

- **Python** 3.12+ (developed on 3.14.0)
- **Tesseract OCR** v5.5.0 - must be installed separately
- **Jupyter Notebook** environment

### Python Packages

```
!pip install opencv-python numpy pillow matplotlib pandas scikit-learn scikit-image pytesseract deep-translator langdetect ipywidgets joblib easyocr
```

### Tesseract Installation

Download and install from: https://github.com/tesseract-ocr/tesseract

After installing, update the path in the notebook if needed:
```python
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
```

## Dataset

- **62 images total** (56 sample + 6 testing)
- Categories: 19 manga, 17 handwritten, 20 stylised
- Ground truth CSV with expected OCR text for accuracy comparison

## Project Structure

```
├── Week 10 - SVM Automation 2 + bug fixing.ipynb   # Main notebook (184 cells)
├── ground_truth.csv                                  # Expected OCR outputs
├── sample_images/                                    # 56 categorised test images
├── testing_images/                                   # 6 unseen evaluation images
├── svm_model_v4.pkl                                  # Trained SVM classifier
└── translation_cache.json                            # Cached translations
```

## Quick Start

1. install Tesseract OCR and Python dependencies (see above)
2. Open the notebook in Jupyter
3. Run cells sequentially - the notebook is organised by development week (Weeks 1–11)
4. The interactive UI is in the final cells (Cell 182+) for end-to-end processing

## Key Results

| Metric | Value |
|--------|-------|
| SVM classification accuracy | 92.9% (52/56) |
| Ensemble vs single pipeline (unseen images) | 80% vs 71% |
| Overall comprehensive test accuracy | 55.6% |
| Preprocessing functions | 31 unique |

## License

This project was developed as part of an academic dissertation. All code is original work unless otherwise cited.
