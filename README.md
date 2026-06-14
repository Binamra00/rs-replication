# Replication Package: Re-evaluating Static Analysis Thresholds for Refactoring Prediction

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Binamra00/rs-replication/blob/main/inflection_analysis.ipynb)
[![DOI](https://zenodo.org/badge/DOI/20617639.svg)](https://doi.org/10.5281/zenodo.20617639)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> ⚠️ **IMPORTANT NOTE:** This repository contains the **Analytical Replication Package** (the Google Colab/Jupyter pipeline used to engineer the matrices, calibrate thresholds, and generate the final tables for the paper). 
> 
> If you are looking for the **Raw Mining Infrastructure** (the Java/Python architecture used to orchestrate PMD and RefactoringMiner at scale across raw Git histories), please visit our primary tooling repository here: **https://github.com/Binamra00/rs-miners.git**

This repository contains the complete, automated replication package for evaluating the predictive power of static analysis metrics (PMD) against structural refactoring ground truth (RefactoringMiner). 

To ensure absolute transparency and ease of review, the entire methodology—from raw data ingestion to the final statistical diagnostics has been compiled into a **single, zero-configuration Google Colab Notebook**: `inflection_analysis.ipynb`.

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

## 🛠️ Upstream Release Tag Mining (Included)

While the main Colab notebook utilizes the pre-mined datasets from Zenodo to ensure deterministic reproducibility, we have also included our **Release Tag Mining Pipeline**:`rel_tag_mining.ipynb` scripts in this repository. 

These scripts demonstrate the exact methodology used to scrape the GitHub API, filter for stable official releases, and generate the chronological targeting ledgers (`rel_hist_[REPO_NAME].json`) that fed our upstream static analysis cluster.

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
```
## 🙏 Acknowledgements & Core Dependencies

This replication package relies on the incredible open-source engineering of several core tools. If you are building upon this pipeline, please ensure you cite the original creators:

**RefactoringMiner:** Our ground-truth refactoring labels are generated using RefactoringMiner (v3.x). 
* Tsantalis, N., Mansouri, M., Eshkevari, L. M., Mazinanian, D., & Dig, D. (2018). *Accurate and Efficient Refactoring Detection in Commit History.* ICSE '18.
* Tsantalis, N., Ketkar, A., & Dig, D. (2022). *RefactoringMiner 2.0.* IEEE Transactions on Software Engineering.
* Alikhanifard, P., & Tsantalis, N. (2025). *A Novel Refactoring and Semantic Aware Abstract Syntax Tree Differencing Tool...* ACM TOSEM.

**PMD:** Our static analysis metrics are extracted using PMD.
* PMD Contributors. *PMD Source Code Analyzer.* https://pmd.github.io/
