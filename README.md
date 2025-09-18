# Hybrid ESG Sentiment Analysis

This repository contains the full pipeline, code, processed data, and evaluation results for the Bachelor's thesis project **Hybrid ESG Sentiment Analysis**.

The thesis investigates sentiment bias in ESG (Environmental, Social, and Governance) reports by combining transformer-based NLP models (DistilBERT) with ESG-specific lexicon methods in a hybrid approach. The goal is to mitigate positive sentiment bias and provide more reliable, granular, and interpretable sentiment analysis results.

---

## 📌 Pipeline Overview

The analysis pipeline consists of six main stages, implemented in separate Jupyter notebooks:

1. **02_preprocessing.ipynb**  
   - Cleaning and tokenization of ESG report corpus.  
   - Stopword removal, error inspection, and corpus representation.  

2. **03_baseline_distilbert.ipynb**  
   - Sentence-level sentiment classification using DistilBERT.  
   - Mapping predictions into **5-class sentiment categories**:  
     - Very Positive, Positive, Neutral, Negative, Very Negative.  

3. **03a_baseline_analysis.ipynb**  
   - Distributional analysis of baseline (DistilBERT) predictions.  
   - Visualization of sentence-level sentiment distributions.  

4. **04_snippet_lexicons.ipynb**  
   - ESG-specific lexicon method applied at snippet/document level.  
   - Mapping to the same 5-class sentiment categories.  

5. **05_hybrid_fusion.ipynb**  
   - Fusion of DistilBERT baseline scores with lexicon scores.  
   - Weighted strategy (70% baseline, 30% lexicon).  
   - Mapping to 5-class sentiment categories using dynamic thresholds.  

6. **06_evaluation.ipynb**  
   - Comparison of baseline, snippet, and hybrid results.  
   - Distributional, company-level, and year-level visualizations.  
   - Error inspection of sample sentences.  

---

## 📊 Key Features

- **5-class sentiment mapping** for granularity: Very Positive, Positive, Neutral, Negative, Very Negative.  
- **Color consistency** across all charts:  
  - Positive = green, Very Positive = green  
  - Neutral = gray  
  - Negative = red, Very Negative = red  
- **Granularity**: Baseline often biased towards positive, Hybrid balances distributions.  
- **Exported visualizations** in `images/` folder:  
  - `eval_baseline_distribution.png`  
  - `eval_doc_comparison_5class.png`  
  - `eval_company_means.png`  
  - `eval_year_means.png`  
  - etc.

---

## 📂 Repository Structure

```
├── data/
│   └── processed/
│       ├── distilbert_baseline_5class.csv
│       ├── snippet_scores_5class.csv
│       ├── hybrid_scores_5class.csv
├── images/
│   ├── eval_baseline_distribution.png
│   ├── eval_doc_comparison_5class.png
│   ├── eval_company_means.png
│   ├── eval_year_means.png
│   └── ...
├── notebooks/
│   ├── 02_preprocessing.ipynb
│   ├── 03_baseline_distilbert.ipynb
│   ├── 03a_baseline_analysis.ipynb
│   ├── 04_snippet_lexicons.ipynb
│   ├── 05_hybrid_fusion.ipynb
│   └── 06_evaluation.ipynb
└── README.md
```

---

## 🚀 How to Reproduce

1. Clone this repository:  
   ```bash
   git clone https://github.com/erenbg1/hybrid-esg-sentiment.git
   cd hybrid-esg-sentiment
   ```

2. Install requirements (Python 3.9+):  
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebooks in order:  
   - `02_preprocessing.ipynb` → `06_evaluation.ipynb`

---

## 📌 Thesis Context

This project was developed as part of a Bachelor's thesis to explore **positive sentiment bias in ESG reporting** and to test whether a **hybrid NLP approach** (transformers + lexicons) can improve reliability and interpretability of sentiment analysis in sustainability disclosures.

The results show that while transformer-based models like DistilBERT tend to repeat the overly positive bias of ESG reports, the hybrid method provides more balanced and granular sentiment distributions.

---

## 👤 Author
**Eren Burak Gökpınar**  
Bachelor’s Thesis Project – GISMA Business School, Berlin  
2025
