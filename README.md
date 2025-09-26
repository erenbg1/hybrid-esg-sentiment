# Hybrid ESG Sentiment Analysis

This repository contains the full pipeline, code, processed data, and evaluation results for the Bachelor's thesis project **Hybrid ESG Sentiment Analysis in Sustainability Reports using Transformers + ESG-Specific Lexicons**.

## Project Overview

The thesis investigates sentiment bias in ESG (Environmental, Social, and Governance) reports by combining transformer-based NLP models (DistilBERT) with ESG-specific lexicon methods in a hybrid approach. The goal is to mitigate positive sentiment bias and provide more reliable, granular, and interpretable sentiment analysis results.

## Pipeline Structure

The analysis pipeline consists of six main stages, implemented in separate Jupyter notebooks:

- **01_data_cleaning_and_corpus.ipynb**: Collecting, cleaning and organizing ESG report corpus
- **02_preprocessing.ipynb**: Cleaning and tokenization of ESG report corpus, stopword removal, error inspection
- **03_baseline_distilbert.ipynb**: Sentence-level sentiment classification using DistilBERT, mapping to 5-class categories
- **03a_baseline_analysis.ipynb**: Distributional analysis of baseline predictions and visualizations
- **04_snippet_lexicons.ipynb**: ESG-specific lexicon method applied at snippet/document level
- **05_hybrid_fusion.ipynb**: Fusion using weighted strategy (70% baseline, 30% lexicon)
- **06_evaluation.ipynb**: Company-level, year-level comparisons and error analysis

## Methodology Foundation

This approach builds upon established research in sentiment analysis:

- **Shin et al. (2017)**: Demonstrated that integrating lexicon embeddings with neural networks enhances sentiment analysis performance
- **Poddar et al. (2017)**: Showed methods for detecting bias in text by comparing patterns across different documents

The hybrid methodology adapts these concepts specifically for ESG bias detection and evaluation without ground truth labels.

## Key Features

- **5-class sentiment mapping**: Very Positive, Positive, Neutral, Negative, Very Negative
- **Distributional evaluation**: Pattern analysis across companies and years
- **Bias mitigation**: Hybrid approach to balance transformer predictions with lexicon insights
- **ESG-specific focus**: Tailored for sustainability reporting analysis

## Repository Structure

```
├── data/processed/
│   ├── distilbert_baseline_5class.csv
│   ├── snippet_scores_5class.csv
│   ├── hybrid_scores_5class.csv
│   ├── lexicon_5class_sentencelevel.csv
│   └── hybrid_5class_sentencelevel.csv
├── images/
│   ├── eval_baseline_distribution.png
│   ├── eval_company_means.png
│   └── eval_year_means.png
├── notebooks/
│   ├── 01_data_cleaning_and_corpus.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_baseline_distilbert.ipynb
│   ├── 03a_baseline_analysis.ipynb
│   ├── 04_snippet_lexicons.ipynb
│   ├── 05_hybrid_fusion.ipynb
│   └── 06_evaluation.ipynb
└── README.md
```

## Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/erenbg1/hybrid-esg-sentiment.git
   cd hybrid-esg-sentiment
   ```

2. Create virtual environment with Python 3.11:
   ```bash
   python3.11 -m venv venv
   source venv/bin/activate
   ```

3. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```

4. Download the spaCy language model:
   ```bash
   python -m spacy download en_core_web_sm --direct
   ```

5. Run notebooks in order: `01_data_cleaning_and_corpus.ipynb` → `06_evaluation.ipynb`

---

⚠️ **Important Note on Data Availability**

The original ESG PDF reports (Google, Nestlé, HSBC) are **not included** in this repository due to licensing restrictions and file size.  
If you wish to fully reproduce the preprocessing step (`01_data_cleaning_and_corpus.ipynb`), you need to manually download the ESG reports and place them in:

```
data/raw_reports/
```

Use the same filenames referenced in the notebooks.

Instead of that, you can directly start with (`003_baseline_distilbert.ipynb`) since the datasets already preprocessed.

---

## Results Summary

The hybrid approach shows potential for balancing transformer bias while maintaining contextual understanding. Results demonstrate that DistilBERT exhibits strong positive bias in ESG contexts, while the hybrid method provides more nuanced sentiment distributions.

## Future Work

- Dataset expansion to more companies and sectors
- Alternative hybrid weighting strategies  
- Cross-lingual ESG analysis
- Domain-specific model fine-tuning

---

**Eren Burak Gökpınar**  
Bachelor's Thesis Project – GISMA Business School, Berlin  
2025
