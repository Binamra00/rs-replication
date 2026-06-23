# artifacts/

Per-repository console output from the analysis pipeline (`inflection_analysis.ipynb`) behind the SPLASH/ISSTA 2026 ACM Student Research Competition abstract, *Single-Metric Size and Complexity Thresholds Fail to Forecast Refactoring*. Each file is the complete, unedited log of one notebook run (one value of `TARGET_REPO`), covering Phase 0 through the closing cross-regime discrimination diagnostic. The five runs together produce the five rows of the paper's Table 1.

## Files

| File | System | `TARGET_REPO` |
|---|---|---|
| `commons-lang.md` | Apache Commons-Lang | `commons-lang` |
| `checkstyle.md` | Checkstyle | `checkstyle` |
| `dubbo.md` | Apache Dubbo | `dubbo` |
| `junit-framework.md` | JUnit | `junit-framework` |
| `questdb.md` | QuestDB | `questdb` |

## Headline result per system

Each run's forecasting-holdout result, as reported in Table 1. In every system the best forecasting metric scores at or below its base rate, and no metric is certified.

| System | Best forecasting metric | AUC-PR | Base rate | Certified |
|---|---|---:|---:|---:|
| Commons-Lang | `NcssCount_Class` | 0.02 | 0.6% | 0 |
| Checkstyle | `NcssCount_Class` | 0.10 | 14.5% | 0 |
| Dubbo | `CyclomaticComplexity_Class` | 0.07 | 6.3% | 0 |
| JUnit | `CyclomaticComplexity_Class` | 0.03 | 1.6% | 0 |
| QuestDB | `NcssCount_Class` | 0.02 | 1.0% | 0 |

## Where the paper's numbers appear in each log

- **Table 1, forecasting result (AUC-PR, BR, Cert.).** The cross-regime diagnostic at the end of each log, section `DISCRIMINATION BY SOURCE × RULE`. The paper's AUC-PR and base rate are the `Chronological/holdout` row of the best-ranking metric; `Cert.` counts the rules calibration marks trustworthy, which is zero in every run (shown as "no statistically stable rule" in the per-source summary).
- **Results, "Re-tuning does not forecast".** Phases B.4, E.4, and T.4: the blind evaluations that compare the calibrated threshold against PMD's default and the training-set median.
- **Table 1, corpus columns.** Phases 0 through 1.3 and D.2 report the targeted releases, files, aliases, observation rows, and refactored entities.

## Vocabulary note

These logs predate the paper's framing and keep the project's original working vocabulary (the notebook's Reader's Guide gives the full key):

- The closing banner `PHASE 6: MASTER CROSS-REGIME DISCRIMINATION DIAGNOSTIC` is the paper's **AUC-PR audit**. The notebook numbers this cell Phase 5, and its completion line reads "Phase 5 Complete," so the 5 and the 6 refer to the same step.
- The **B / E / T** phases are the **abundant / scarce / forecasting** scenarios.
- "inflection threshold" is the **calibrated (revealed-preference) threshold**.
- "Gold Class-Level Alias Graph" is the class-level alias graph, not the God Class smell.

The coupling rules `CouplingBetweenObjects` and `ExcessiveImports` appear in some tables with `no positives` and `nan`: they are excluded from the study (dropped with Feature Envy) and carry no labels, so they never contribute a result.

## Regenerating

Open `inflection_analysis.ipynb`, set `TARGET_REPO` to one of the values above, and run top to bottom (about 5 to 7 minutes per repository). Each run reproduces the matching log and also writes `discrimination_diagnostic_<repo>.csv` and the locked-threshold JSON files.
