# Checkstyle:





🚀 Setting up replication environment for checkstyle...

📂 Workspace Root: /content

📦 Data Directory: /content/data/checkstyle

☁️ Downloading checkstyle data from Zenodo...

🗜️ Unzipping data...

✅ Download and extraction complete.



\--- 🎯 Configuration Summary ---

Target Repository:  checkstyle

PMD Data Exists:    True

Refm Data Exists:   True

Lineage Exists:     True

Rel Hist Exists:    True

✅ Phase 0 Complete! You can now execute Phase 1.1.

🚀 Starting Phase 1.1: Data Synchronization Check

📂 Loading Release History Ground Truth...

&#x20;  ✅ Target Releases: 1 official releases found in configuration.



📂 Loading Master Lineage (The SHA Map)...

&#x20;  ✅ Lineage Loaded: 18263 total commits.



🔍 Step 1: Verifying PMD Snapshots...



🔍 Step 2: Verifying Refactoring Miner Ground Truth...

\--------------------------------------------------

📊 DATA SYNCHRONIZATION REPORT

&#x20;  🔹 PMD Snapshots: 14 valid snapshots verified in lineage (Expected at least: 1).

&#x20;  🔹 Refactoring Commits Mapped: 10965

&#x20;  🔹 Refactoring Density: 11012 unique commits contain refactorings.



🧾 PARSE INTEGRITY

&#x20;  - PMD unique SHAs observed (success only): 14

&#x20;  - PMD malformed lines: 0

&#x20;  - PMD failed-status lines skipped: 12

&#x20;  - PMD missing sha: 0

&#x20;  - PMD outside-lineage SHAs: 0

&#x20;  - RefMiner total entries read: 11012

&#x20;  - RefMiner malformed lines: 0

&#x20;  - RefMiner missing sha1: 0



🚀 SUCCESS: The three universes are synchronized!

&#x20;  The PMD observation points and Refactoring events exist on the same timeline.

🏁 Phase 1.1 Complete.

🚀 Starting Phase 1.2: Final Gold Class-Level Alias Graph Generation

⏳ Sorted 11012 commits chronologically to guarantee safe alias resolution.

&#x20;  🔍 Discovered 3108 Class Rename path-level aliases.

&#x20;  🔍 Discovered 1363 Class Rename basename aliases.



📊 PHASE 1.2 INTEGRITY REPORT:

&#x20;  - Total Path Rename Links:      3108

&#x20;  - Total Basename Rename Links:  1363

&#x20;  - Distinct Classes Threaded:    1918

&#x20;  - Multi-rename links collapsed: 1190

&#x20;  - Path Collisions (Preserved):  91

&#x20;  - Basename Collisions:          114

&#x20;  - Malformed/Skipped:            102

&#x20;      \* Missing Location Data: 102



✅ Identity lineage successfully resolved.

&#x20;  💾 Saved path-level graph to: alias\_tracking\_graph\_paths\_checkstyle.csv

&#x20;  💾 Saved basename graph to:   alias\_tracking\_graph\_checkstyle.csv

🏁 Phase 1.2 Complete.

🚀 Starting Phase 1.3: Final Audited Method Alias Graph Generation

⏳ Sorted 11012 commits chronologically for deterministic method alias chaining.

&#x20;  🔍 Discovered 1376 method lineage links.

&#x20;  ✅ Method lineage resolved.

&#x20;  💾 Saved to method\_alias\_graph\_checkstyle.csv



📊 PHASE 1.3 INTEGRITY REPORT:

&#x20;  - Total Method Links Mapped: 1376

&#x20;  - Collision Overwrites:      1

&#x20;  - Explicitly Skipped / Excluded:

&#x20;      \* Change Parameter Type: 940



&#x20;  ✅ DATA INTEGRITY VERIFIED: 100% Regex match rate on targeted elements.



🏁 Phase 1.3 Complete.

🚀 Starting Phase D.2: Data Flattening \& Regex Rescue (With Alias Resolution)

⏳ Building PMD Method-Name Resolver from Phase 1.3 Graph...

&#x20;  ⚠️ Resolver collisions (preserved original root): 2

⏳ Loading Timelines and Mapping Ground Truth (Early Binding)...

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'Utils'



📉 THE DATA ATTRITION FUNNEL (Ground Truth Mapping):

&#x20;  🧩 Raw Taxonomy-Matched Refactorings: 5658

&#x20;  📌 Total leftSideLocations (all matched refs): 13149

&#x20;  🔍 Total Structural Operations Found: 8348

&#x20;  🛡️  Test Files Purged (Regex Filter):  824

&#x20;  ✅ Production Refactorings Retained (location-level):  7524

&#x20;  🎯 Mappable retained locations (pre-dedup): 7523

&#x20;  🔗 Unique mapped supervision keys (post-dedup): 2509

&#x20;       ├─ God Class    (class-level):  1939

&#x20;       └─ Long Method  (method-level): 570

&#x20;  ♻️  Dedup/compression delta: 5014

&#x20;  ⚠️ Refactorings dropped (missing from lineage gap): 47

&#x20;  ⚠️ Method refactorings dropped (unparseable signature): 1

&#x20;  ⚠️ PMD malformed lines:                0

&#x20;  ⚠️ PMD failed-status entries ignored:  12



✅ Flattened PMD Data: 81,340 raw metric records extracted.



🚫 Excluded-rule rows dropped from dataset (reported as a finding):

&#x20;     - CouplingBetweenObjects      :    2,219 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveImports            :    3,296 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveParameterList      :   19,848 rows  (no method signature → unmappable)

&#x20;     - TooManyFields               :    1,278 rows  (no metric value/range emitted)



🔍 DIAGNOSTIC: Checking for Zero-Refactoring Releases across the entire timeline...

&#x20;  ⚠️ WARNING: Found 2 releases with ZERO mapped refactoring events.

&#x20;  (These releases will likely be dropped during downstream Top-K or F-score evaluations).

&#x20;     - Release 2/14 : 82ed05b01a8ab0b9985f6ac820247d63081676c1

&#x20;     - Release 9/14 : 068b6d4a87d586bc9d83ea753ee8c6b61df63d16

\-------------------------------------------------------------------------------------



&#x20;  ⚠️ Dropped unrecoverable metric rows: 2931



🏁 Phase D.2 Complete! Saved flat dataset to pmd\_flat\_checkstyle.csv

Note: Train/Test splitting happens in Phase T.2.



📊 POST-FLATTENING DATASET AUDIT:

&#x20;  - Total Observations: 81,340

&#x20;  - Positive Refactoring Labels: 2,437

&#x20;  - Negative Observations: 78,903

&#x20;  - Class Imbalance Ratio: 32.38:1

&#x20;  - Unique Files Tracked: 993

&#x20;  - Unique Commits (Snapshots) Tracked: 14

&#x20;  - Missing/Null Metric Values: 0



&#x20;  - Row Count by Rule Type:

&#x20;      \* NcssCount\_Method         : 32,479

&#x20;      \* CyclomaticComplexity\_Method: 32,479

&#x20;      \* NcssCount\_Class          : 6,235

&#x20;      \* ExcessivePublicCount     : 5,098

&#x20;      \* CyclomaticComplexity\_Class: 5,049



✅ Dataset audit passed: Structure is valid and data is balanced.

&#x20;Audit loaded: 81,340 records for checkstyle



PER-RULE VERDICTS:

&#x20;                      rule        verdict  peak\_rate

&#x20;           NcssCount\_Class monotonic\_down   0.234063

&#x20;CyclomaticComplexity\_Class      ambiguous   0.154150

&#x20;      ExcessivePublicCount           flat   0.117229

&#x20;          NcssCount\_Method   monotonic\_up   0.070485

CyclomaticComplexity\_Method   monotonic\_up   0.076132

🚀 Starting Phase B.2: Structural Validation Split (80/20 Stratified)



📊 Executing Stratified Group K-Fold (Canonical Integrity at \~80/20)...

&#x20;  - Training Set (79.4% actual): 64,610 metric rows | 516 Unique Refactoring Events

&#x20;  - Testing Set  (20.6% actual): 16,730 metric rows | 149 Unique Refactoring Events



🔍 Checking per-rule positive event densities (Rule Viability)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=559, test\_pos=133

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=350, test\_pos=98 

&#x20;  ✅ NcssCount\_Method               : train\_pos=308, test\_pos=135

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=308, test\_pos=135

&#x20;  ✅ ExcessivePublicCount           : train\_pos=332, test\_pos=79 



📊 Executing Inner Stratified Group Split for K-Fold IDs...



💾 Saving master datasets to disk...

&#x20;  ✅ Saved Training Set: b2\_train\_spatial\_80\_checkstyle.csv

&#x20;  ✅ Saved Testing Set:  b2\_test\_spatial\_20\_checkstyle.csv



🏁 Phase B.2 Complete. The Data Engine has secured and saved the stratified 80/20 splits!

🚀 Starting Phase E.2: Data Scarcity Branch (True Locked Holdout Architecture)



📊 Isolating the Baseline Test Set (Extracting B.2 holdout via Basenames)...

📊 Starving the Training Set (Simulating Target 20% Total Data Scarcity)...



🧾 E.2 SPLIT GEOMETRY EXPLAINER

&#x20;  - Baseline outer split realized: Train 79.4% | Test 20.6% of total rows

&#x20;  - Scarcity train is 21.0% of baseline-train rows

&#x20;  - Therefore scarcity train is 16.7% of total rows (target was 20.0%)



&#x20;  - Scarcity Training Set (16.7% actual, \~20.0% target): 13,587 metric rows | 120 Unique File-Release Events

&#x20;  - Locked Testing Set (constant baseline holdout): 16,730 metric rows | 149 Unique File-Release Events

&#x20;  - Scarcity event density: 0.008832 events/row

&#x20;  - Locked-test event density: 0.008906 events/row



🔍 Checking per-rule positive event densities (Rule Viability under Scarcity)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=117, test\_pos=133

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=60 , test\_pos=98 

&#x20;  ✅ NcssCount\_Method               : train\_pos=55 , test\_pos=135

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=55 , test\_pos=135

&#x20;  ✅ ExcessivePublicCount           : train\_pos=55 , test\_pos=79 



📊 Executing Inner Stratified Group Split for E.3 K-Fold IDs...

&#x20;  ✅ Leakage Assertion Passed: Absolute spatial isolation confirmed.



💾 Saving Scarcity Training dataset to disk...

&#x20;  ✅ Saved Scarcity Training Set: e2\_train\_scarcity\_checkstyle.csv

&#x20;  ✅ Locked Testing Set is preserved at: b2\_test\_spatial\_20\_checkstyle.csv



🏁 Phase E.2 Complete. The Scarcity Data Engine has secured the true locked splits!

🚀 Starting Phase T.2: Chronological Branch (True Git Time-Series Split)



⚠️ MSR Attrition Note: You targeted \~26 official releases from GitHub.

⚠️ PMD parsed 14 releases. The missing 12 failed upstream static analysis.



⏳ Loading true Git commit timestamps to guarantee time-travel protection...



📊 T.2 Dataset Split Breakdown (50/50):

&#x20;  - Total PMD Releases: 14

&#x20;  - T.2 Training Releases (The Past):   7

&#x20;  - T.2 Testing Releases  (The Future): 7

&#x20;  - ⏱️ TRUE Temporal Boundary Lock: Release 7 (Git Timestamp: 1133255362)



&#x20;  - T.2 Training Set (28.3% actual metric rows): 23042 total rows

&#x20;  - T.2 Testing Set  (71.7% actual metric rows): 58298 total rows



&#x20;  🔍 Temporal Imbalance Check:

&#x20;     - Past Refactored Rows:   440

&#x20;     - Future Refactored Rows: 1997



🔍 Checking per-rule positive densities (Past vs Future)...

&#x20;  ✅ NcssCount\_Class                : past\_pos=91  , future\_pos=601 

&#x20;  ✅ CyclomaticComplexity\_Class     : past\_pos=89  , future\_pos=359 

&#x20;  ✅ NcssCount\_Method               : past\_pos=92  , future\_pos=351 

&#x20;  ✅ CyclomaticComplexity\_Method    : past\_pos=92  , future\_pos=351 

&#x20;  ✅ ExcessivePublicCount           : past\_pos=76  , future\_pos=335 



💾 Saved Temporal Training Set: t2\_train\_chrono\_50\_checkstyle.csv

💾 Saved Temporal Testing Set: t2\_test\_chrono\_50\_checkstyle.csv

&#x20;  ✅ Robust chronological splitting validated successfully!

🏁 Phase T.2 Complete. The timeline has been permanently split (No spatial shuffling applied).

🔎 Running T.2 True Chronological Sanity Check...

&#x20;  ✅ Split matrices successfully loaded from disk (No corruption).

&#x20;  ✅ Release counts verified (Past/Train: 7, Future/Test: 7).

&#x20;  ✅ Zero data leakage detected (Past and Future releases are strictly mutually exclusive).

&#x20;  ✅ Chronological boundary mathematically verified via Git History (Max Past TS: 1133255362 < Min Future TS: 1197677153).



📁 Step 4: System Evolution \& Temporal Overlap (T.2 Split)

&#x20;     - Canonical identities in the Past (Train):            506

&#x20;     - Canonical identities in the Future (Test):           982

&#x20;     - Identities persisting across the split (Overlap):    495

&#x20;     - Identities retired/deleted before Future phase:      11

&#x20;     - New identities introduced in Future phase:           487

&#x20;     🎯 Percentage of Future Architecture seen in the Past: 50.41%



🏁 Audit Complete. The T.2 Chronological Split is academically secure and verified.

🚀 Starting Phase B.3: Multi-Percentile Sweep Analysis (Optimized \& Guarded)

📊 Loaded Training Set with 805 canonical entities ready for K-Fold Calibration.



📈 Executing 5-Fold Cross-Validation Tournament...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...

&#x20;  ⚙️ Processing Fold 4 as Validation...

&#x20;  ⚙️ Processing Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                      | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 1 (P:0.11|R:1.00|F1:0.20) | 1 (P:0.11|R:1.00|F1:0.20) | 2 (P:0.10|R:0.80|F1:0.17) | 2 (P:0.09|R:0.70|F1:0.16) | 3 (P:0.08|R:0.62|F1:0.15) | 4 (P:0.07|R:0.49|F1:0.13)  | 7 (P:0.06|R:0.35|F1:0.10)  | 11 (P:0.05|R:0.27|F1:0.09) | 30 (P:0.06|R:0.15|F1:0.09) | 49 (P:0.06|R:0.11|F1:0.08) | 100 (P:0.09|R:0.05|F1:0.07) |

| CyclomaticComplexity\_Class  | 1 (P:0.09|R:1.00|F1:0.16) | 1 (P:0.09|R:1.00|F1:0.16) | 1 (P:0.09|R:1.00|F1:0.16) | 2 (P:0.07|R:0.69|F1:0.13) | 2 (P:0.07|R:0.66|F1:0.13) | 3 (P:0.06|R:0.49|F1:0.11)  | 4 (P:0.06|R:0.42|F1:0.10)  | 10 (P:0.05|R:0.26|F1:0.09) | 20 (P:0.07|R:0.16|F1:0.10) | 27 (P:0.07|R:0.10|F1:0.08) | 43 (P:0.08|R:0.05|F1:0.06)  |

| ExcessivePublicCount        | 1 (P:0.08|R:1.00|F1:0.15) | 1 (P:0.08|R:1.00|F1:0.15) | 1 (P:0.08|R:1.00|F1:0.15) | 1 (P:0.08|R:1.00|F1:0.15) | 1 (P:0.07|R:0.79|F1:0.13) | 2 (P:0.06|R:0.56|F1:0.11)  | 2 (P:0.06|R:0.52|F1:0.11)  | 3 (P:0.05|R:0.33|F1:0.08)  | 6 (P:0.05|R:0.16|F1:0.07)  | 8 (P:0.05|R:0.11|F1:0.06)  | 10 (P:0.06|R:0.07|F1:0.06)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.99|F1:0.03) | 3 (P:0.02|R:0.86|F1:0.05) | 5 (P:0.03|R:0.79|F1:0.06) | 6 (P:0.03|R:0.67|F1:0.06) | 8 (P:0.04|R:0.58|F1:0.08) | 11 (P:0.06|R:0.48|F1:0.10) | 14 (P:0.07|R:0.37|F1:0.12) | 19 (P:0.09|R:0.26|F1:0.13) | 24 (P:0.11|R:0.15|F1:0.12) | 28 (P:0.12|R:0.10|F1:0.11) | 35 (P:0.12|R:0.06|F1:0.08)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:0.93|F1:0.03) | 2 (P:0.03|R:0.72|F1:0.05) | 3 (P:0.03|R:0.62|F1:0.07) | 5 (P:0.05|R:0.46|F1:0.10)  | 6 (P:0.07|R:0.41|F1:0.12)  | 8 (P:0.08|R:0.28|F1:0.12)  | 10 (P:0.11|R:0.17|F1:0.13) | 12 (P:0.14|R:0.11|F1:0.12) | 17 (P:0.12|R:0.06|F1:0.07)  |

| TooManyMethods              | 0 (P:0.11|R:1.00|F1:0.20) | 0 (P:0.11|R:1.00|F1:0.20) | 0 (P:0.10|R:0.93|F1:0.19) | 1 (P:0.09|R:0.73|F1:0.16) | 1 (P:0.09|R:0.73|F1:0.16) | 1 (P:0.08|R:0.61|F1:0.14)  | 2 (P:0.06|R:0.45|F1:0.11)  | 3 (P:0.04|R:0.27|F1:0.08)  | 7 (P:0.05|R:0.16|F1:0.07)  | 12 (P:0.06|R:0.11|F1:0.08) | 19 (P:0.10|R:0.06|F1:0.07)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                        | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 1 (P:0.11|R:1.00|F0.5:0.13) | 1 (P:0.11|R:1.00|F0.5:0.13) | 2 (P:0.10|R:0.80|F0.5:0.12) | 2 (P:0.09|R:0.70|F0.5:0.11) | 3 (P:0.08|R:0.62|F0.5:0.10) | 4 (P:0.07|R:0.49|F0.5:0.09)  | 7 (P:0.06|R:0.35|F0.5:0.07)  | 11 (P:0.05|R:0.27|F0.5:0.06) | 30 (P:0.06|R:0.15|F0.5:0.07) | 49 (P:0.06|R:0.11|F0.5:0.07) | 100 (P:0.09|R:0.05|F0.5:0.08) |

| CyclomaticComplexity\_Class  | 1 (P:0.09|R:1.00|F0.5:0.11) | 1 (P:0.09|R:1.00|F0.5:0.11) | 1 (P:0.09|R:1.00|F0.5:0.11) | 2 (P:0.07|R:0.69|F0.5:0.09) | 2 (P:0.07|R:0.66|F0.5:0.09) | 3 (P:0.06|R:0.49|F0.5:0.07)  | 4 (P:0.06|R:0.42|F0.5:0.07)  | 10 (P:0.05|R:0.26|F0.5:0.06) | 20 (P:0.07|R:0.16|F0.5:0.08) | 27 (P:0.07|R:0.10|F0.5:0.07) | 43 (P:0.08|R:0.05|F0.5:0.07)  |

| ExcessivePublicCount        | 1 (P:0.08|R:1.00|F0.5:0.10) | 1 (P:0.08|R:1.00|F0.5:0.10) | 1 (P:0.08|R:1.00|F0.5:0.10) | 1 (P:0.08|R:1.00|F0.5:0.10) | 1 (P:0.07|R:0.79|F0.5:0.09) | 2 (P:0.06|R:0.56|F0.5:0.08)  | 2 (P:0.06|R:0.52|F0.5:0.07)  | 3 (P:0.05|R:0.33|F0.5:0.06)  | 6 (P:0.05|R:0.16|F0.5:0.05)  | 8 (P:0.05|R:0.11|F0.5:0.06)  | 10 (P:0.06|R:0.07|F0.5:0.06)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.99|F0.5:0.02) | 3 (P:0.02|R:0.86|F0.5:0.03) | 5 (P:0.03|R:0.79|F0.5:0.04) | 6 (P:0.03|R:0.67|F0.5:0.04) | 8 (P:0.04|R:0.58|F0.5:0.05) | 11 (P:0.06|R:0.48|F0.5:0.07) | 14 (P:0.07|R:0.37|F0.5:0.08) | 19 (P:0.09|R:0.26|F0.5:0.10) | 24 (P:0.11|R:0.15|F0.5:0.11) | 28 (P:0.12|R:0.10|F0.5:0.11) | 35 (P:0.12|R:0.06|F0.5:0.09)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:0.93|F0.5:0.02) | 2 (P:0.03|R:0.72|F0.5:0.04) | 3 (P:0.03|R:0.62|F0.5:0.04) | 5 (P:0.05|R:0.46|F0.5:0.07)  | 6 (P:0.07|R:0.41|F0.5:0.09)  | 8 (P:0.08|R:0.28|F0.5:0.10)  | 10 (P:0.11|R:0.17|F0.5:0.12) | 12 (P:0.14|R:0.11|F0.5:0.13) | 17 (P:0.12|R:0.06|F0.5:0.10)  |

| TooManyMethods              | 0 (P:0.11|R:1.00|F0.5:0.14) | 0 (P:0.11|R:1.00|F0.5:0.14) | 0 (P:0.10|R:0.93|F0.5:0.13) | 1 (P:0.09|R:0.73|F0.5:0.11) | 1 (P:0.09|R:0.73|F0.5:0.11) | 1 (P:0.08|R:0.61|F0.5:0.09)  | 2 (P:0.06|R:0.45|F0.5:0.07)  | 3 (P:0.04|R:0.27|F0.5:0.05)  | 7 (P:0.05|R:0.16|F0.5:0.06)  | 12 (P:0.06|R:0.11|F0.5:0.07) | 19 (P:0.10|R:0.06|F0.5:0.08)  |



🏆 F1-Optimized Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 5th          |                 1 |                 1 |         0.1991 |             1    |      0.1108 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 5th          |                 1 |                 1 |         0.1581 |             1    |      0.0861 |            5 |

| ExcessivePublicCount        | True         | True               | False         | 5th          |                 1 |                 1 |         0.1487 |             1    |      0.0807 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 75th         |                19 |                24 |         0.1262 |             7.22 |      0.0119 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 85th         |                10 |                10 |         0.1314 |             9.25 |      0.0119 |            5 |

| TooManyMethods              | True         | True               | False         | 5th          |                 0 |                 0 |         0.2004 |             1    |      0.1115 |            5 |



🎯 Precision-Optimized (F0.5) Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 5th          |                 1 |                 1 |           0.1346 |             1    |      0.1108 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 5th          |                 1 |                 1 |           0.1053 |             1    |      0.0861 |            5 |

| ExcessivePublicCount        | True         | True               | False         | 5th          |                 1 |                 1 |           0.0988 |             1    |      0.0807 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 90th         |                28 |                28 |           0.1124 |             9.81 |      0.0119 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                12 |                12 |           0.1296 |            11.44 |      0.0119 |            5 |

| TooManyMethods              | True         | True               | False         | 5th          |                 0 |                 0 |           0.1355 |             1    |      0.1115 |            5 |



💾 Saved Dual Baseline locked thresholds to disk: /content/b3\_inflection\_thresholds\_checkstyle\_locked.json

🏁 Phase B.3 Complete.

🚀 Starting Phase E.3: Multi-Percentile Sweep Analysis (Scarcity Edition)

📊 Loaded Scarcity Training Set (20%) with 201 canonical entities.



📈 Executing 3-Fold Cross-Validation Tournament (Scarcity)...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                      | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                       |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|

| NcssCount\_Class             | 1 (P:0.11|R:1.00|F1:0.19) | 1 (P:0.11|R:1.00|F1:0.19) | 1 (P:0.11|R:1.00|F1:0.19) | 2 (P:0.08|R:0.73|F1:0.15) | 2 (P:0.08|R:0.73|F1:0.15) | 3 (P:0.07|R:0.51|F1:0.12)  | 4 (P:0.06|R:0.41|F1:0.10)  | 9 (P:0.04|R:0.25|F1:0.07)  | 19 (P:0.05|R:0.20|F1:0.08) | 37 (P:0.06|R:0.12|F1:0.08) | 92 (P:0.07|R:0.06|F1:0.05) |

| CyclomaticComplexity\_Class  | 1 (P:0.07|R:1.00|F1:0.13) | 1 (P:0.07|R:1.00|F1:0.13) | 2 (P:0.06|R:0.78|F1:0.11) | 2 (P:0.06|R:0.69|F1:0.10) | 3 (P:0.05|R:0.57|F1:0.09) | 4 (P:0.05|R:0.49|F1:0.09)  | 6 (P:0.05|R:0.35|F1:0.08)  | 13 (P:0.05|R:0.26|F1:0.09) | 24 (P:0.09|R:0.17|F1:0.11) | 30 (P:0.07|R:0.11|F1:0.08) | 40 (P:0.08|R:0.05|F1:0.06) |

| ExcessivePublicCount        | 1 (P:0.07|R:1.00|F1:0.13) | 1 (P:0.07|R:1.00|F1:0.13) | 1 (P:0.07|R:1.00|F1:0.13) | 2 (P:0.06|R:0.75|F1:0.11) | 2 (P:0.06|R:0.64|F1:0.10) | 2 (P:0.06|R:0.64|F1:0.10)  | 2 (P:0.06|R:0.64|F1:0.10)  | 4 (P:0.03|R:0.25|F1:0.06)  | 8 (P:0.06|R:0.16|F1:0.08)  | 10 (P:0.05|R:0.11|F1:0.07) | 10 (P:0.04|R:0.07|F1:0.05) |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        |

| NcssCount\_Method            | 3 (P:0.02|R:0.93|F1:0.04) | 4 (P:0.03|R:0.83|F1:0.05) | 5 (P:0.03|R:0.74|F1:0.05) | 6 (P:0.03|R:0.66|F1:0.05) | 9 (P:0.03|R:0.49|F1:0.06) | 10 (P:0.04|R:0.48|F1:0.08) | 13 (P:0.05|R:0.37|F1:0.08) | 15 (P:0.07|R:0.30|F1:0.11) | 21 (P:0.10|R:0.21|F1:0.12) | 23 (P:0.13|R:0.16|F1:0.11) | 27 (P:0.11|R:0.07|F1:0.08) |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.02) | 2 (P:0.02|R:0.85|F1:0.04) | 2 (P:0.03|R:0.78|F1:0.05) | 3 (P:0.03|R:0.71|F1:0.06) | 3 (P:0.03|R:0.61|F1:0.06) | 5 (P:0.04|R:0.46|F1:0.08)  | 6 (P:0.06|R:0.41|F1:0.10)  | 7 (P:0.07|R:0.25|F1:0.10)  | 10 (P:0.11|R:0.17|F1:0.11) | 11 (P:0.15|R:0.14|F1:0.11) | 13 (P:0.16|R:0.06|F1:0.07) |

| TooManyMethods              | 0 (P:0.12|R:1.00|F1:0.21) | 0 (P:0.12|R:1.00|F1:0.21) | 0 (P:0.12|R:1.00|F1:0.21) | 1 (P:0.09|R:0.73|F1:0.16) | 1 (P:0.08|R:0.63|F1:0.14) | 1 (P:0.08|R:0.63|F1:0.14)  | 1 (P:0.08|R:0.63|F1:0.14)  | 3 (P:0.04|R:0.23|F1:0.07)  | 5 (P:0.04|R:0.17|F1:0.06)  | 12 (P:0.05|R:0.10|F1:0.06) | 17 (P:0.09|R:0.07|F1:0.08) |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                        | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                         |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|

| NcssCount\_Class             | 1 (P:0.11|R:1.00|F0.5:0.13) | 1 (P:0.11|R:1.00|F0.5:0.13) | 1 (P:0.11|R:1.00|F0.5:0.13) | 2 (P:0.08|R:0.73|F0.5:0.10) | 2 (P:0.08|R:0.73|F0.5:0.10) | 3 (P:0.07|R:0.51|F0.5:0.08)  | 4 (P:0.06|R:0.41|F0.5:0.07)  | 9 (P:0.04|R:0.25|F0.5:0.05)  | 19 (P:0.05|R:0.20|F0.5:0.06) | 37 (P:0.06|R:0.12|F0.5:0.07) | 92 (P:0.07|R:0.06|F0.5:0.06) |

| CyclomaticComplexity\_Class  | 1 (P:0.07|R:1.00|F0.5:0.08) | 1 (P:0.07|R:1.00|F0.5:0.08) | 2 (P:0.06|R:0.78|F0.5:0.07) | 2 (P:0.06|R:0.69|F0.5:0.07) | 3 (P:0.05|R:0.57|F0.5:0.06) | 4 (P:0.05|R:0.49|F0.5:0.06)  | 6 (P:0.05|R:0.35|F0.5:0.06)  | 13 (P:0.05|R:0.26|F0.5:0.06) | 24 (P:0.09|R:0.17|F0.5:0.10) | 30 (P:0.07|R:0.11|F0.5:0.07) | 40 (P:0.08|R:0.05|F0.5:0.07) |

| ExcessivePublicCount        | 1 (P:0.07|R:1.00|F0.5:0.08) | 1 (P:0.07|R:1.00|F0.5:0.08) | 1 (P:0.07|R:1.00|F0.5:0.08) | 2 (P:0.06|R:0.75|F0.5:0.07) | 2 (P:0.06|R:0.64|F0.5:0.07) | 2 (P:0.06|R:0.64|F0.5:0.07)  | 2 (P:0.06|R:0.64|F0.5:0.07)  | 4 (P:0.03|R:0.25|F0.5:0.04)  | 8 (P:0.06|R:0.16|F0.5:0.06)  | 10 (P:0.05|R:0.11|F0.5:0.06) | 10 (P:0.04|R:0.07|F0.5:0.04) |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          |

| NcssCount\_Method            | 3 (P:0.02|R:0.93|F0.5:0.02) | 4 (P:0.03|R:0.83|F0.5:0.03) | 5 (P:0.03|R:0.74|F0.5:0.03) | 6 (P:0.03|R:0.66|F0.5:0.03) | 9 (P:0.03|R:0.49|F0.5:0.04) | 10 (P:0.04|R:0.48|F0.5:0.05) | 13 (P:0.05|R:0.37|F0.5:0.06) | 15 (P:0.07|R:0.30|F0.5:0.08) | 21 (P:0.10|R:0.21|F0.5:0.11) | 23 (P:0.13|R:0.16|F0.5:0.12) | 27 (P:0.11|R:0.07|F0.5:0.09) |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 2 (P:0.02|R:0.85|F0.5:0.03) | 2 (P:0.03|R:0.78|F0.5:0.03) | 3 (P:0.03|R:0.71|F0.5:0.04) | 3 (P:0.03|R:0.61|F0.5:0.04) | 5 (P:0.04|R:0.46|F0.5:0.05)  | 6 (P:0.06|R:0.41|F0.5:0.07)  | 7 (P:0.07|R:0.25|F0.5:0.08)  | 10 (P:0.11|R:0.17|F0.5:0.11) | 11 (P:0.15|R:0.14|F0.5:0.12) | 13 (P:0.16|R:0.06|F0.5:0.10) |

| TooManyMethods              | 0 (P:0.12|R:1.00|F0.5:0.14) | 0 (P:0.12|R:1.00|F0.5:0.14) | 0 (P:0.12|R:1.00|F0.5:0.14) | 1 (P:0.09|R:0.73|F0.5:0.11) | 1 (P:0.08|R:0.63|F0.5:0.10) | 1 (P:0.08|R:0.63|F0.5:0.10)  | 1 (P:0.08|R:0.63|F0.5:0.10)  | 3 (P:0.04|R:0.23|F0.5:0.05)  | 5 (P:0.04|R:0.17|F0.5:0.04)  | 12 (P:0.05|R:0.10|F0.5:0.05) | 17 (P:0.09|R:0.07|F0.5:0.08) |



🏆 F1-Optimized Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 5th          |                 1 |                 1 |         0.1908 |             1    |      0.1055 |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 5th          |                 1 |                 1 |         0.1284 |             1    |      0.0687 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 5th          |                 1 |                 1 |         0.1268 |             1    |      0.0678 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                21 |                23 |         0.1186 |            10.05 |      0.0102 |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 85th         |                10 |                11 |         0.1135 |            11.18 |      0.0102 |            3 |

| TooManyMethods              | True         | True               | False         | 5th          |                 0 |                 0 |         0.2097 |             1    |      0.1173 |            3 |



🎯 Precision-Optimized (F0.5) Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 5th          |                 1 |                 1 |           0.1285 |             1    |      0.1055 |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 85th         |                24 |                24 |           0.0966 |             1.28 |      0.0687 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 5th          |                 1 |                 1 |           0.0833 |             1    |      0.0678 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 90th         |                23 |                23 |           0.1162 |            12.89 |      0.0102 |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                11 |                11 |           0.1223 |            14.81 |      0.0102 |            3 |

| TooManyMethods              | True         | True               | False         | 5th          |                 0 |                 0 |           0.1424 |             1    |      0.1173 |            3 |



💾 Saved Dual Baseline locked thresholds to disk: /content/e3\_inflection\_thresholds\_checkstyle\_scarcity.json

🏁 Phase E.3 Complete.

🚀 Starting Phase T.3: Chronological K-Fold Calibration Engine

📊 Loaded Temporal Training Set (The Past) with 506 canonical entities.



📈 Executing 5-Fold Cross-Validation Tournament (Chronological; n\_splits=5)...

&#x20;  ⚙️ Processing Temporal Fold 1 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 2 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 3 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 4 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                       | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 7 (P:0.13|R:0.75|F1:0.18) | 8 (P:0.14|R:0.68|F1:0.18) | 10 (P:0.14|R:0.63|F1:0.18) | 14 (P:0.14|R:0.61|F1:0.17) | 18 (P:0.13|R:0.48|F1:0.13) | 23 (P:0.12|R:0.45|F1:0.13) | 28 (P:0.11|R:0.34|F1:0.11) | 37 (P:0.11|R:0.31|F1:0.10) | 59 (P:0.22|R:0.13|F1:0.06) | 79 (P:0.20|R:0.12|F1:0.07) | 133 (P:0.38|R:0.08|F1:0.06) |

| CyclomaticComplexity\_Class  | 2 (P:0.15|R:0.85|F1:0.20) | 3 (P:0.15|R:0.79|F1:0.20) | 4 (P:0.15|R:0.75|F1:0.20)  | 5 (P:0.14|R:0.65|F1:0.19)  | 8 (P:0.15|R:0.55|F1:0.17)  | 10 (P:0.15|R:0.50|F1:0.17) | 12 (P:0.14|R:0.42|F1:0.14) | 17 (P:0.15|R:0.39|F1:0.14) | 28 (P:0.24|R:0.17|F1:0.11) | 36 (P:0.26|R:0.12|F1:0.07) | 39 (P:0.36|R:0.04|F1:0.04)  |

| ExcessivePublicCount        | 2 (P:0.15|R:0.86|F1:0.22) | 2 (P:0.15|R:0.86|F1:0.22) | 2 (P:0.15|R:0.86|F1:0.22)  | 2 (P:0.15|R:0.86|F1:0.22)  | 3 (P:0.16|R:0.69|F1:0.20)  | 3 (P:0.16|R:0.69|F1:0.20)  | 4 (P:0.14|R:0.47|F1:0.15)  | 4 (P:0.14|R:0.34|F1:0.15)  | 6 (P:0.13|R:0.19|F1:0.14)  | 8 (P:0.13|R:0.08|F1:0.05)  | 11 (P:0.18|R:0.04|F1:0.03)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.03|R:0.97|F1:0.06) | 3 (P:0.04|R:0.91|F1:0.08) | 3 (P:0.05|R:0.85|F1:0.08)  | 4 (P:0.08|R:0.80|F1:0.12)  | 5 (P:0.08|R:0.71|F1:0.13)  | 7 (P:0.08|R:0.57|F1:0.12)  | 8 (P:0.08|R:0.51|F1:0.13)  | 12 (P:0.09|R:0.34|F1:0.10) | 19 (P:0.11|R:0.21|F1:0.10) | 21 (P:0.13|R:0.17|F1:0.11) | 22 (P:0.14|R:0.16|F1:0.13)  |

| CyclomaticComplexity\_Method | 1 (P:0.03|R:1.00|F1:0.06) | 1 (P:0.03|R:1.00|F1:0.06) | 1 (P:0.04|R:0.87|F1:0.07)  | 2 (P:0.08|R:0.68|F1:0.13)  | 3 (P:0.09|R:0.59|F1:0.14)  | 3 (P:0.10|R:0.51|F1:0.14)  | 4 (P:0.11|R:0.40|F1:0.14)  | 6 (P:0.13|R:0.30|F1:0.13)  | 8 (P:0.09|R:0.18|F1:0.08)  | 11 (P:0.14|R:0.18|F1:0.10) | 12 (P:0.10|R:0.15|F1:0.10)  |

| TooManyMethods              | 3 (P:0.19|R:0.73|F1:0.22) | 3 (P:0.19|R:0.73|F1:0.22) | 4 (P:0.19|R:0.73|F1:0.23)  | 4 (P:0.18|R:0.69|F1:0.20)  | 5 (P:0.15|R:0.62|F1:0.15)  | 6 (P:0.14|R:0.47|F1:0.13)  | 6 (P:0.14|R:0.42|F1:0.13)  | 7 (P:0.14|R:0.42|F1:0.13)  | 10 (P:0.21|R:0.26|F1:0.09) | 15 (P:0.32|R:0.19|F1:0.09) | 24 (P:0.31|R:0.12|F1:0.10)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                         | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 7 (P:0.13|R:0.75|F0.5:0.15) | 8 (P:0.14|R:0.68|F0.5:0.16) | 10 (P:0.14|R:0.63|F0.5:0.15) | 14 (P:0.14|R:0.61|F0.5:0.15) | 18 (P:0.13|R:0.48|F0.5:0.13) | 23 (P:0.12|R:0.45|F0.5:0.12) | 28 (P:0.11|R:0.34|F0.5:0.11) | 37 (P:0.11|R:0.31|F0.5:0.10) | 59 (P:0.22|R:0.13|F0.5:0.08) | 79 (P:0.20|R:0.12|F0.5:0.08) | 133 (P:0.38|R:0.08|F0.5:0.07) |

| CyclomaticComplexity\_Class  | 2 (P:0.15|R:0.85|F0.5:0.16) | 3 (P:0.15|R:0.79|F0.5:0.16) | 4 (P:0.15|R:0.75|F0.5:0.16)  | 5 (P:0.14|R:0.65|F0.5:0.16)  | 8 (P:0.15|R:0.55|F0.5:0.16)  | 10 (P:0.15|R:0.50|F0.5:0.16) | 12 (P:0.14|R:0.42|F0.5:0.14) | 17 (P:0.15|R:0.39|F0.5:0.14) | 28 (P:0.24|R:0.17|F0.5:0.15) | 36 (P:0.26|R:0.12|F0.5:0.09) | 39 (P:0.36|R:0.04|F0.5:0.06)  |

| ExcessivePublicCount        | 2 (P:0.15|R:0.86|F0.5:0.17) | 2 (P:0.15|R:0.86|F0.5:0.17) | 2 (P:0.15|R:0.86|F0.5:0.17)  | 2 (P:0.15|R:0.86|F0.5:0.17)  | 3 (P:0.16|R:0.69|F0.5:0.17)  | 3 (P:0.16|R:0.69|F0.5:0.17)  | 4 (P:0.14|R:0.47|F0.5:0.15)  | 4 (P:0.14|R:0.34|F0.5:0.14)  | 6 (P:0.13|R:0.19|F0.5:0.13)  | 8 (P:0.13|R:0.08|F0.5:0.07)  | 11 (P:0.18|R:0.04|F0.5:0.04)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.03|R:0.97|F0.5:0.04) | 3 (P:0.04|R:0.91|F0.5:0.05) | 3 (P:0.05|R:0.85|F0.5:0.06)  | 4 (P:0.08|R:0.80|F0.5:0.09)  | 5 (P:0.08|R:0.71|F0.5:0.09)  | 7 (P:0.08|R:0.57|F0.5:0.09)  | 8 (P:0.08|R:0.51|F0.5:0.10)  | 12 (P:0.09|R:0.34|F0.5:0.09) | 19 (P:0.11|R:0.21|F0.5:0.10) | 21 (P:0.13|R:0.17|F0.5:0.11) | 22 (P:0.14|R:0.16|F0.5:0.13)  |

| CyclomaticComplexity\_Method | 1 (P:0.03|R:1.00|F0.5:0.04) | 1 (P:0.03|R:1.00|F0.5:0.04) | 1 (P:0.04|R:0.87|F0.5:0.05)  | 2 (P:0.08|R:0.68|F0.5:0.10)  | 3 (P:0.09|R:0.59|F0.5:0.10)  | 3 (P:0.10|R:0.51|F0.5:0.12)  | 4 (P:0.11|R:0.40|F0.5:0.12)  | 6 (P:0.13|R:0.30|F0.5:0.12)  | 8 (P:0.09|R:0.18|F0.5:0.07)  | 11 (P:0.14|R:0.18|F0.5:0.10) | 12 (P:0.10|R:0.15|F0.5:0.10)  |

| TooManyMethods              | 3 (P:0.19|R:0.73|F0.5:0.20) | 3 (P:0.19|R:0.73|F0.5:0.20) | 4 (P:0.19|R:0.73|F0.5:0.20)  | 4 (P:0.18|R:0.69|F0.5:0.19)  | 5 (P:0.15|R:0.62|F0.5:0.15)  | 6 (P:0.14|R:0.47|F0.5:0.13)  | 6 (P:0.14|R:0.42|F0.5:0.13)  | 7 (P:0.14|R:0.42|F0.5:0.13)  | 10 (P:0.21|R:0.26|F0.5:0.12) | 15 (P:0.32|R:0.19|F0.5:0.13) | 24 (P:0.31|R:0.12|F0.5:0.11)  |



🏆 F1-Optimized Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 15th         |                 8 |                14 |         0.1818 |             1.31 |      0.1094 |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 25th         |                 4 |                 4 |         0.203  |             1.1  |      0.1341 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 35th         |                 2 |                 2 |         0.2188 |             1.31 |      0.1161 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | False              | False         | 65th         |                 8 |                22 |         0.1299 |             2.84 |      0.0299 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 55th         |                 3 |                 6 |         0.1439 |             3.47 |      0.0299 |            5 |

| TooManyMethods              | True         | True               | False         | 25th         |                 4 |                 4 |         0.2282 |             0.88 |      0.219  |            2 |



🎯 Precision-Optimized (F0.5) Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 15th         |                 8 |                14 |           0.1555 |             1.31 |      0.1094 |            3 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 25th         |                 4 |                28 |           0.1647 |             1.1  |      0.1341 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 35th         |                 2 |                 3 |           0.1727 |             1.31 |      0.1161 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                22 |                22 |           0.1296 |             4.72 |      0.0299 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 75th         |                 6 |                 6 |           0.1196 |             4.19 |      0.0299 |            5 |

| TooManyMethods              | True         | True               | False         | 25th         |                 4 |                 4 |           0.2041 |             0.88 |      0.219  |            2 |



💾 Saved Dual Chronological locked thresholds to disk: t3\_inflection\_thresholds\_checkstyle\_chrono\_locked.json

🏁 Phase T.3 Complete.

🚀 Starting Phase B.4: Blind Imminent Predictability Evaluation (Trust-Aware Edition)

✅ Thresholds strictly synchronized from disk.

📊 Final Exam Loaded: Evaluating 188 completely unseen canonical entities.



&#x20;   MASTER BLIND EVALUATION MATRIX (Test Set: 20%)



📊 TABLE 1: F1-Optimized Thresholds (Evaluated on Blind F1 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       133 |         1500 |             12 | ⚠️ 1500 (Fallback) |     0.199 |     0     |    0     |      0.125 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        98 |           80 |              7 | ⚠️ 80 (Fallback)   |     0.158 |     0.087 |    0.087 |      0.109 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        79 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.149 |     0     |    0     |      0.106 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       135 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.126 |     0.042 |    0.042 |      0.042 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       135 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.131 |     0.162 |    0.162 |      0.039 | ➖ Uncalibrated Noise |

| TooManyMethods              |        81 |           10 |              5 | ⚠️ 10 (Fallback)   |     0.2   |     0.104 |    0.104 |      0.1   | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized Thresholds (Evaluated on Blind F0.5 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       133 |         1500 |             12 | ⚠️ 1500 (Fallback) |      0.135 |      0     |     0     |       0.089 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        98 |           80 |              7 | ⚠️ 80 (Fallback)   |      0.105 |      0.151 |     0.151 |       0.077 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        79 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.099 |      0     |     0     |       0.073 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       135 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.112 |      0.088 |     0.088 |       0.027 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       135 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.13  |      0.141 |     0.141 |       0.025 | ➖ Uncalibrated Noise |

| TooManyMethods              |        81 |           10 |              5 | ⚠️ 10 (Fallback)   |      0.136 |      0.082 |     0.082 |       0.07  | ➖ Uncalibrated Noise |



💾 Saved detailed evaluation matrix to: b4\_evaluation\_matrix\_checkstyle.csv



=================================================================

🏆 FINAL BASELINE EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  Test Entities (Strictly Blind):   188

\-----------------------------------------------------------------

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F1 averages.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F0.5 averages.

=================================================================

🏁 Phase B.4 Complete. The threshold hypotheses have been blindly evaluated.

🚀 Starting Phase E.4: Scarcity Predictability Evaluation (Trust-Aware)

📊 Final Scarcity Exam Loaded: Evaluating 188 completely unseen canonical entities.



📊 TABLE 1: F1-Optimized Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       133 |         1500 |             11 | ⚠️ 1500 (Fallback) |     0.191 |     0     |    0     |      0.129 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        98 |           80 |              7 | ⚠️ 80 (Fallback)   |     0.128 |     0.087 |    0.087 |      0.109 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        79 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.127 |     0     |    0     |      0.106 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       135 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.119 |     0.042 |    0.042 |      0.042 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       135 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.114 |     0.162 |    0.162 |      0.039 | ➖ Uncalibrated Noise |

| TooManyMethods              |        81 |           10 |              4 | ⚠️ 10 (Fallback)   |     0.21  |     0.104 |    0.104 |      0.098 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       133 |         1500 |             11 | ⚠️ 1500 (Fallback) |      0.129 |      0     |     0     |       0.092 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        98 |           80 |              7 | ⚠️ 80 (Fallback)   |      0.097 |      0.151 |     0.151 |       0.077 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        79 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.083 |      0     |     0     |       0.073 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       135 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.116 |      0.088 |     0.088 |       0.027 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       135 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.122 |      0.141 |     0.141 |       0.025 | ➖ Uncalibrated Noise |

| TooManyMethods              |        81 |           10 |              4 | ⚠️ 10 (Fallback)   |      0.142 |      0.082 |     0.082 |       0.068 | ➖ Uncalibrated Noise |



=================================================================

🏆 SCARCITY EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

=================================================================



💾 Saved scarcity evaluation matrix to: e4\_evaluation\_matrix\_scarcity\_checkstyle.csv

🏁 Phase E.4 Complete. Scarcity evaluation finalized.

🚀 Starting Phase T.4: Chronological Predictability Evaluation (Trust-Aware)

📊 Final Chronological Exam Loaded: Evaluating against Future Timeline.



📊 TABLE 1: F1-Optimized Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       601 |         1500 |             10 | ⚠️ 1500 (Fallback) |     0.182 |     0     |    0     |      0.09  | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       359 |           80 |              6 | ⚠️ 80 (Fallback)   |     0.203 |     0.03  |    0.03  |      0.081 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       335 |           45 |              2 | ⚠️ 45 (Fallback)   |     0.219 |     0     |    0     |      0.109 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       351 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.13  |     0.021 |    0.021 |      0.031 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       351 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.144 |     0.171 |    0.171 |      0.029 | ➖ Uncalibrated Noise |

| TooManyMethods              |       365 |           10 |              4 | ⚠️ 10 (Fallback)   |     0.228 |     0.086 |    0.086 |      0.066 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       601 |         1500 |             10 | ⚠️ 1500 (Fallback) |      0.155 |      0     |     0     |       0.066 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       359 |           80 |              6 | ⚠️ 80 (Fallback)   |      0.165 |      0.056 |     0.056 |       0.057 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       335 |           45 |              2 | ⚠️ 45 (Fallback)   |      0.173 |      0     |     0     |       0.074 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       351 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.13  |      0.045 |     0.045 |       0.02  | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       351 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.12  |      0.156 |     0.156 |       0.019 | ➖ Uncalibrated Noise |

| TooManyMethods              |       365 |           10 |              4 | ⚠️ 10 (Fallback)   |      0.204 |      0.072 |     0.072 |       0.047 | ➖ Uncalibrated Noise |



=================================================================

🏆 CHRONOLOGICAL EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

=================================================================



💾 Saved chronological evaluation matrix to: t4\_evaluation\_matrix\_chrono\_checkstyle.csv

🏁 Phase T.4 Complete. Chronological evaluation finalized.



=====================================================================================

🚀 INITIATING PHASE 6: MASTER CROSS-REGIME DISCRIMINATION DIAGNOSTIC

=====================================================================================



================ DISCRIMINATION BY SOURCE × RULE ================

AUC-PR \~ base\_rate  ⇒  lift \~ 1.0  ⇒  metric ranks refactoring at chance.



| Source                   | Rule                        |     n |   n\_pos |   base\_rate |   auc\_pr |   lift | flag         |

|:-------------------------|:----------------------------|------:|--------:|------------:|---------:|-------:|:-------------|

| Pooled/all               | NcssCount\_Class             |  6235 |     692 |      0.111  |   0.0856 |   0.77 | ok           |

| Pooled/all               | CyclomaticComplexity\_Class  |  5049 |     448 |      0.0887 |   0.0748 |   0.84 | ok           |

| Pooled/all               | ExcessivePublicCount        |  5098 |     411 |      0.0806 |   0.0693 |   0.86 | ok           |

| Pooled/all               | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | NcssCount\_Method            | 32479 |     443 |      0.0136 |   0.0633 |   4.64 | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Method | 32479 |     443 |      0.0136 |   0.0609 |   4.47 | rare (<5%)   |

| Pooled/all               | TooManyMethods              |  4047 |     440 |      0.1087 |   0.0826 |   0.76 | ok           |

| Spatial/train            | NcssCount\_Class             |  5068 |     559 |      0.1103 |   0.0829 |   0.75 | ok           |

| Spatial/train            | CyclomaticComplexity\_Class  |  4111 |     350 |      0.0851 |   0.0706 |   0.83 | ok           |

| Spatial/train            | ExcessivePublicCount        |  4119 |     332 |      0.0806 |   0.0671 |   0.83 | ok           |

| Spatial/train            | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | NcssCount\_Method            | 25656 |     308 |      0.012  |   0.0589 |   4.91 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Method | 25656 |     308 |      0.012  |   0.0576 |   4.8  | rare (<5%)   |

| Spatial/train            | TooManyMethods              |  3231 |     359 |      0.1111 |   0.0815 |   0.73 | ok           |

| Scarcity/train           | NcssCount\_Class             |  1109 |     117 |      0.1055 |   0.0785 |   0.74 | ok           |

| Scarcity/train           | CyclomaticComplexity\_Class  |   870 |      60 |      0.069  |   0.0643 |   0.93 | ok           |

| Scarcity/train           | ExcessivePublicCount        |   818 |      55 |      0.0672 |   0.0589 |   0.88 | ok           |

| Scarcity/train           | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | NcssCount\_Method            |  5395 |      55 |      0.0102 |   0.0499 |   4.9  | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Method |  5395 |      55 |      0.0102 |   0.0549 |   5.38 | rare (<5%)   |

| Scarcity/train           | TooManyMethods              |   755 |      88 |      0.1166 |   0.0885 |   0.76 | ok           |

| Chronological/train      | NcssCount\_Class             |  2100 |      91 |      0.0433 |   0.0727 |   1.68 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Class  |  1607 |      89 |      0.0554 |   0.0798 |   1.44 | ok           |

| Chronological/train      | ExcessivePublicCount        |  1603 |      76 |      0.0474 |   0.0597 |   1.26 | rare (<5%)   |

| Chronological/train      | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | NcssCount\_Method            |  8866 |      92 |      0.0104 |   0.0318 |   3.06 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Method |  8866 |      92 |      0.0104 |   0.0289 |   2.78 | rare (<5%)   |

| Chronological/train      | TooManyMethods              |  1222 |      75 |      0.0614 |   0.0698 |   1.14 | ok           |

| Spatial/Scarcity/holdout | NcssCount\_Class             |  1167 |     133 |      0.114  |   0.1037 |   0.91 | ok           |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Class  |   938 |      98 |      0.1045 |   0.0934 |   0.89 | ok           |

| Spatial/Scarcity/holdout | ExcessivePublicCount        |   979 |      79 |      0.0807 |   0.0874 |   1.08 | ok           |

| Spatial/Scarcity/holdout | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | NcssCount\_Method            |  6823 |     135 |      0.0198 |   0.0868 |   4.39 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Method |  6823 |     135 |      0.0198 |   0.0735 |   3.71 | rare (<5%)   |

| Spatial/Scarcity/holdout | TooManyMethods              |   816 |      81 |      0.0993 |   0.1053 |   1.06 | ok           |

| Chronological/holdout    | NcssCount\_Class             |  4135 |     601 |      0.1453 |   0.1033 |   0.71 | ok           |

| Chronological/holdout    | CyclomaticComplexity\_Class  |  3442 |     359 |      0.1043 |   0.0807 |   0.77 | ok           |

| Chronological/holdout    | ExcessivePublicCount        |  3495 |     335 |      0.0959 |   0.081  |   0.84 | ok           |

| Chronological/holdout    | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | NcssCount\_Method            | 23613 |     351 |      0.0149 |   0.0782 |   5.26 | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Method | 23613 |     351 |      0.0149 |   0.0772 |   5.19 | rare (<5%)   |

| Chronological/holdout    | TooManyMethods              |  2825 |     365 |      0.1292 |   0.097  |   0.75 | ok           |



\--- LIFT (AUC-PR / base\_rate) by rule × source ---

Lift strictly measures how much better the metric ranks over blind guessing.

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| CyclomaticComplexity\_Class  |         0.84 |            0.83 |             0.93 |                  1.44 |                       0.89 |                    0.77 |

| CyclomaticComplexity\_Method |         4.47 |            4.8  |             5.38 |                  2.78 |                       3.71 |                    5.19 |

| ExcessiveImports            |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| ExcessivePublicCount        |         0.86 |            0.83 |             0.88 |                  1.26 |                       1.08 |                    0.84 |

| NcssCount\_Class             |         0.77 |            0.75 |             0.74 |                  1.68 |                       0.91 |                    0.71 |

| NcssCount\_Method            |         4.64 |            4.91 |             4.9  |                  3.06 |                       4.39 |                    5.26 |

| TooManyMethods              |         0.76 |            0.73 |             0.76 |                  1.14 |                       1.06 |                    0.75 |



\--- AUC-PR (absolute) by rule × source ---

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| CyclomaticComplexity\_Class  |       0.0748 |          0.0706 |           0.0643 |                0.0798 |                     0.0934 |                  0.0807 |

| CyclomaticComplexity\_Method |       0.0609 |          0.0576 |           0.0549 |                0.0289 |                     0.0735 |                  0.0772 |

| ExcessiveImports            |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| ExcessivePublicCount        |       0.0693 |          0.0671 |           0.0589 |                0.0597 |                     0.0874 |                  0.081  |

| NcssCount\_Class             |       0.0856 |          0.0829 |           0.0785 |                0.0727 |                     0.1037 |                  0.1033 |

| NcssCount\_Method            |       0.0633 |          0.0589 |           0.0499 |                0.0318 |                     0.0868 |                  0.0782 |

| TooManyMethods              |       0.0826 |          0.0815 |           0.0885 |                0.0698 |                     0.1053 |                  0.097  |



================ PER-SOURCE SUMMARY ================

(reliable = n\_pos≥30 AND base\_rate≥0.05)



| Source                   | Max Absolute AUC-PR                | Max Reliable Lift                 |

|:-------------------------|:-----------------------------------|:----------------------------------|

| Pooled/all               | 0.086 (NcssCount\_Class)            | 0.86 (ExcessivePublicCount)       |

| Spatial/train            | 0.083 (NcssCount\_Class)            | 0.83 (CyclomaticComplexity\_Class) |

| Scarcity/train           | 0.088 (TooManyMethods)             | 0.93 (CyclomaticComplexity\_Class) |

| Chronological/train      | 0.080 (CyclomaticComplexity\_Class) | 1.44 (CyclomaticComplexity\_Class) |

| Spatial/Scarcity/holdout | 0.105 (TooManyMethods)             | 1.08 (ExcessivePublicCount)       |

| Chronological/holdout    | 0.103 (NcssCount\_Class)            | 0.84 (ExcessivePublicCount)       |



💾 Saved full diagnostic to: discrimination\_diagnostic\_checkstyle.csv

🏁 Phase 5 Complete. The overarching data structure has been successfully diagnosed.



