# Replication Package: Re-evaluating Static Analysis Thresholds for Refactoring Prediction

[![Open In Colab](https://colab.research.google.com/github/Binamra00/rs-replication/blob/main/inflection_analysis.ipynb)
[![DOI](https://zenodo.org/badge/DOI/20617639.svg)](https://doi.org/10.5281/zenodo.20617639)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the complete, automated replication package for evaluating the predictive power of static analysis metrics (PMD) against structural refactoring ground truth (RefactoringMiner). 

To ensure absolute transparency and ease of review, the entire methodology—from raw data ingestion to the final statistical diagnostics—has been compiled into a **single, zero-configuration Google Colab Notebook**.

## 🚀 One-Click Reproducibility

We strongly recommend using the Google Colab environment to execute this replication package. It requires zero local environment configuration and handles all data extraction in the cloud.

1. Click the **"Open in Colab"** badge above.
2. Sign in to a Google account.
3. In the top menu, click `Runtime` > `Run all`.
4. The notebook will automatically download the pre-mined artifacts from Zenodo, construct the matrices, and print the evaluation tables.

## 📦 Data Provenance & Zenodo Archive

To guarantee reproducibility, the raw structural snapshots (PMD) and ledger events (RefactoringMiner) are hosted on Zenodo. The pipeline dynamically pulls this archive during **Phase 0**. 

* **Zenodo Archive:** [Link to your Zenodo Record]
* **Target Repositories:** Apache `commons-lang` (default), configurable to other ingested projects.

## 🧩 Pipeline Architecture

The replication notebook is strictly strictly separated into 7 logical phases to prevent data leakage and ensure mathematical rigor:

* **Phase 0: Environment Setup.** Cloud instantiation and dynamic Zenodo ingestion.
* **Phase 1: The Master Lineage & Alias Graphs.** Synchronizes static analysis snapshots with Git history and tracks class/method identities across renames and structural moves using a First-Write-Wins traversal.
* **Phase 2: Matrix Engineering & Partitioning.** * `B.2`: Traditional Spatial 80/20 split (Baseline).
  * `E.2`: Data Scarcity Stress Test (~20% volume retention).
  * `T.2`: True Chronological Split (Time-travel defense).
* **Phase 3: Threshold Calibration.** Multi-percentile mathematical sweeps across training folds to derive F1 and F0.5 optimized thresholds, guarded by strict statistical reliability checks.
* **Phase 4: Blind Predictability Evaluation.** Tests the derived thresholds against completely unseen holdout matrices.
* **Phase 5: Alert Fatigue Analysis.** Exposes the raw operational reality (TP vs. FP counts) of single-metric thresholds, demonstrating the high volume of wasted alerts.
* **Phase 6: Master Cross-Regime Discrimination Diagnostic.** Calculates the Area Under the Precision-Recall Curve (AUC-PR) across all regimes to mathematically prove the absolute limits of single-metric discrimination, independent of thresholding.

## 💻 Local Execution (Optional)

If you prefer to run the notebook locally via Jupyter rather than Google Colab:

1. Clone this repository:
   ```bash
   git clone https://github.com/Binamra00/rs-replication.git
   cd rs-replication
   ```
2. Install the required data science dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Open ```inflection_analysis_rep.ipynb``` in Jupyter Notebook or JupyterLab and execute the cells sequentially. The ```BASE_DIR``` paths will automatically adapt to your local working directory.

## 📄 Citation

If you use this dataset or pipeline in your research, please cite our Zenodo archive directly:

```bibtex
@dataset{smell_ranker_data_2024,
  author       = {Binamra Aryal},
  title        = {Replication Data for: Why Single-Metric Code-Smell Thresholds Fail to Forecast Refactoring},
  month        = {June},
  year         = {2026},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.20617639},
  url          = {https://doi.org/10.5281/zenodo.20617639}
}
