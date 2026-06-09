# Replication Package: Code Smell Thresholds & Refactoring

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository serves as the official replication package for our SPLASH/ISSTA Student Research Competition (SRC) paper: **"Why Single-Metric Code-Smell Thresholds Fail to Forecast Refactoring."**

To ensure frictionless reproducibility for reviewers and researchers, we have decoupled the complex data-acquisition mining pipeline from the statistical evaluation. 

## 1. One-Click Replication (Google Colab)
You do not need to install Java, configure paths, or run multi-hour static analysis miners to verify our claims. 

Click the **"Open in Colab"** badge above. The notebook will automatically:
1. Fetch the pre-mined historical datasets (`.jsonl`) directly from our Zenodo archive.
2. Execute **Phase D.2**: Data Flattening & Early Binding.
3. Execute **Phase T.2**: Chronological Train/Test Splitting.
4. Execute **Phase T.3**: The K-Fold Calibration Engine (re-deriving the thresholds).
5. Execute **Phase T.4**: Holdout Evaluation (generating the exact $F_1$ and AUC-PR tables from the paper).

## 2. Repository Structure

```text
rs-replication/
├── inflection_analysis_V1.ipynb   # The master statistical execution pipeline
├── README.md                      
├── .gitignore
└── CITATION.cff
