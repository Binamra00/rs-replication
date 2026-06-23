# Dubbo:





🚀 Setting up replication environment for dubbo...

📂 Workspace Root: /content

📦 Data Directory: /content/data/dubbo

☁️ Downloading dubbo data from Zenodo...

🗜️ Unzipping data...

✅ Download and extraction complete.



\--- 🎯 Configuration Summary ---

Target Repository:  dubbo

PMD Data Exists:    True

Refm Data Exists:   True

Lineage Exists:     True

Rel Hist Exists:    True

✅ Phase 0 Complete! You can now execute Phase 1.1.

🚀 Starting Phase 1.1: Data Synchronization Check

📂 Loading Release History Ground Truth...

&#x20;  ✅ Target Releases: 1 official releases found in configuration.



📂 Loading Master Lineage (The SHA Map)...

&#x20;  ✅ Lineage Loaded: 10230 total commits.



🔍 Step 1: Verifying PMD Snapshots...



🔍 Step 2: Verifying Refactoring Miner Ground Truth...

\--------------------------------------------------

📊 DATA SYNCHRONIZATION REPORT

&#x20;  🔹 PMD Snapshots: 24 valid snapshots verified in lineage (Expected at least: 1).

&#x20;  🔹 Refactoring Commits Mapped: 7079

&#x20;  🔹 Refactoring Density: 7079 unique commits contain refactorings.



🧾 PARSE INTEGRITY

&#x20;  - PMD unique SHAs observed (success only): 24

&#x20;  - PMD malformed lines: 0

&#x20;  - PMD failed-status lines skipped: 0

&#x20;  - PMD missing sha: 0

&#x20;  - PMD outside-lineage SHAs: 0

&#x20;  - RefMiner total entries read: 7079

&#x20;  - RefMiner malformed lines: 0

&#x20;  - RefMiner missing sha1: 0



🚀 SUCCESS: The three universes are synchronized!

&#x20;  The PMD observation points and Refactoring events exist on the same timeline.

🏁 Phase 1.1 Complete.

🚀 Starting Phase 1.2: Final Gold Class-Level Alias Graph Generation

⏳ Sorted 7079 commits chronologically to guarantee safe alias resolution.

&#x20;  🔍 Discovered 1545 Class Rename path-level aliases.

&#x20;  🔍 Discovered 314 Class Rename basename aliases.



📊 PHASE 1.2 INTEGRITY REPORT:

&#x20;  - Total Path Rename Links:      1545

&#x20;  - Total Basename Rename Links:  314

&#x20;  - Distinct Classes Threaded:    1214

&#x20;  - Multi-rename links collapsed: 331

&#x20;  - Path Collisions (Preserved):  55

&#x20;  - Basename Collisions:          12

&#x20;  - Malformed/Skipped:            279

&#x20;      \* Missing Location Data: 279



✅ Identity lineage successfully resolved.

&#x20;  💾 Saved path-level graph to: alias\_tracking\_graph\_paths\_dubbo.csv

&#x20;  💾 Saved basename graph to:   alias\_tracking\_graph\_dubbo.csv

🏁 Phase 1.2 Complete.

🚀 Starting Phase 1.3: Final Audited Method Alias Graph Generation

⏳ Sorted 7079 commits chronologically for deterministic method alias chaining.

&#x20;  🔍 Discovered 1592 method lineage links.

&#x20;  ✅ Method lineage resolved.

&#x20;  💾 Saved to method\_alias\_graph\_dubbo.csv



📊 PHASE 1.3 INTEGRITY REPORT:

&#x20;  - Total Method Links Mapped: 1592

&#x20;  - Collision Overwrites:      71

&#x20;  - Explicitly Skipped / Excluded:

&#x20;      \* Change Parameter Type: 2293



&#x20;  ✅ DATA INTEGRITY VERIFIED: 100% Regex match rate on targeted elements.



🏁 Phase 1.3 Complete.

🚀 Starting Phase D.2: Data Flattening \& Regex Rescue (With Alias Resolution)

⏳ Building PMD Method-Name Resolver from Phase 1.3 Graph...

&#x20;  ⚠️ Resolver collisions (preserved original root): 13

⏳ Loading Timelines and Mapping Ground Truth (Early Binding)...



📉 THE DATA ATTRITION FUNNEL (Ground Truth Mapping):

&#x20;  🧩 Raw Taxonomy-Matched Refactorings: 6299

&#x20;  📌 Total leftSideLocations (all matched refs): 20084

&#x20;  🔍 Total Structural Operations Found: 7325

&#x20;  🛡️  Test Files Purged (Regex Filter):  843

&#x20;  ✅ Production Refactorings Retained (location-level):  6482

&#x20;  🎯 Mappable retained locations (pre-dedup): 6378

&#x20;  🔗 Unique mapped supervision keys (post-dedup): 3243

&#x20;       ├─ God Class    (class-level):  1862

&#x20;       └─ Long Method  (method-level): 1381

&#x20;  ♻️  Dedup/compression delta: 3135



✅ Flattened PMD Data: 505,335 raw metric records extracted.



🚫 Excluded-rule rows dropped from dataset (reported as a finding):

&#x20;     - CouplingBetweenObjects      :   16,538 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveImports            :   23,733 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveParameterList      :  136,177 rows  (no method signature → unmappable)

&#x20;     - TooManyFields               :    4,908 rows  (no metric value/range emitted)



🔍 DIAGNOSTIC: Checking for Zero-Refactoring Releases across the entire timeline...

&#x20;  ⚠️ WARNING: Found 4 releases with ZERO mapped refactoring events.

&#x20;  (These releases will likely be dropped during downstream Top-K or F-score evaluations).

&#x20;     - Release 5/24 : 683dba388139b058e828b9a0761ca7f421c24f24

&#x20;     - Release 8/24 : 0c65f971b92fb243d12386f3ebca2dc70418f9e7

&#x20;     - Release 18/24 : 80aef49ab51f4ccdc0ee6e2e1a7ca63f2fda509c

&#x20;     - Release 23/24 : f1585880bee4ca7776f44380c47c994217721ffe

\-------------------------------------------------------------------------------------



&#x20;  ⚠️ Dropped unrecoverable metric rows: 15446



🏁 Phase D.2 Complete! Saved flat dataset to pmd\_flat\_dubbo.csv

Note: Train/Test splitting happens in Phase T.2.



📊 POST-FLATTENING DATASET AUDIT:

&#x20;  - Total Observations: 505,335

&#x20;  - Positive Refactoring Labels: 6,027

&#x20;  - Negative Observations: 499,308

&#x20;  - Class Imbalance Ratio: 82.85:1

&#x20;  - Unique Files Tracked: 3,203

&#x20;  - Unique Commits (Snapshots) Tracked: 24

&#x20;  - Missing/Null Metric Values: 0



&#x20;  - Row Count by Rule Type:

&#x20;      \* NcssCount\_Method         : 209,557

&#x20;      \* CyclomaticComplexity\_Method: 209,557

&#x20;      \* NcssCount\_Class          : 31,669

&#x20;      \* ExcessivePublicCount     : 29,127

&#x20;      \* CyclomaticComplexity\_Class: 25,425



✅ Dataset audit passed: Structure is valid and data is balanced.

&#x20;Audit loaded: 505,335 records for dubbo



PER-RULE VERDICTS:

&#x20;                      rule      verdict  peak\_rate

&#x20;           NcssCount\_Class         flat   0.051675

&#x20;CyclomaticComplexity\_Class    ambiguous   0.054340

&#x20;      ExcessivePublicCount    ambiguous   0.050688

&#x20;          NcssCount\_Method monotonic\_up   0.017037

CyclomaticComplexity\_Method monotonic\_up   0.017439

🚀 Starting Phase B.2: Structural Validation Split (80/20 Stratified)



📊 Executing Stratified Group K-Fold (Canonical Integrity at \~80/20)...

&#x20;  - Training Set (81.4% actual): 411,415 metric rows | 1096 Unique Refactoring Events

&#x20;  - Testing Set  (18.6% actual): 93,920 metric rows | 251 Unique Refactoring Events



🔍 Checking per-rule positive event densities (Rule Viability)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=1162, test\_pos=327

&#x20;  ✅ ExcessivePublicCount           : train\_pos=1076, test\_pos=287

&#x20;  ✅ NcssCount\_Method               : train\_pos=789, test\_pos=179

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=789, test\_pos=179

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=974, test\_pos=265



📊 Executing Inner Stratified Group Split for K-Fold IDs...



💾 Saving master datasets to disk...

&#x20;  ✅ Saved Training Set: b2\_train\_spatial\_80\_dubbo.csv

&#x20;  ✅ Saved Testing Set:  b2\_test\_spatial\_20\_dubbo.csv



🏁 Phase B.2 Complete. The Data Engine has secured and saved the stratified 80/20 splits!

🚀 Starting Phase E.2: Data Scarcity Branch (True Locked Holdout Architecture)



📊 Isolating the Baseline Test Set (Extracting B.2 holdout via Basenames)...

📊 Starving the Training Set (Simulating Target 20% Total Data Scarcity)...



🧾 E.2 SPLIT GEOMETRY EXPLAINER

&#x20;  - Baseline outer split realized: Train 81.4% | Test 18.6% of total rows

&#x20;  - Scarcity train is 26.9% of baseline-train rows

&#x20;  - Therefore scarcity train is 21.9% of total rows (target was 20.0%)



&#x20;  - Scarcity Training Set (21.9% actual, \~20.0% target): 110,627 metric rows | 289 Unique File-Release Events

&#x20;  - Locked Testing Set (constant baseline holdout): 93,920 metric rows | 251 Unique File-Release Events

&#x20;  - Scarcity event density: 0.002612 events/row

&#x20;  - Locked-test event density: 0.002672 events/row



🔍 Checking per-rule positive event densities (Rule Viability under Scarcity)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=331, test\_pos=327

&#x20;  ✅ ExcessivePublicCount           : train\_pos=319, test\_pos=287

&#x20;  ✅ NcssCount\_Method               : train\_pos=173, test\_pos=179

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=173, test\_pos=179

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=279, test\_pos=265



📊 Executing Inner Stratified Group Split for E.3 K-Fold IDs...

&#x20;  ✅ Leakage Assertion Passed: Absolute spatial isolation confirmed.



💾 Saving Scarcity Training dataset to disk...

&#x20;  ✅ Saved Scarcity Training Set: e2\_train\_scarcity\_dubbo.csv

&#x20;  ✅ Locked Testing Set is preserved at: b2\_test\_spatial\_20\_dubbo.csv



🏁 Phase E.2 Complete. The Scarcity Data Engine has secured the true locked splits!

🚀 Starting Phase T.2: Chronological Branch (True Git Time-Series Split)



⚠️ MSR Attrition Note: You targeted \~24 official releases from GitHub.

⚠️ PMD parsed 24 releases. The missing 0 failed upstream static analysis.



⏳ Loading true Git commit timestamps to guarantee time-travel protection...



📊 T.2 Dataset Split Breakdown (50/50):

&#x20;  - Total PMD Releases: 24

&#x20;  - T.2 Training Releases (The Past):   12

&#x20;  - T.2 Testing Releases  (The Future): 12

&#x20;  - ⏱️ TRUE Temporal Boundary Lock: Release 12 (Git Timestamp: 1515316905)



&#x20;  - T.2 Training Set (26.4% actual metric rows): 133267 total rows

&#x20;  - T.2 Testing Set  (73.6% actual metric rows): 372068 total rows



&#x20;  🔍 Temporal Imbalance Check:

&#x20;     - Past Refactored Rows:   756

&#x20;     - Future Refactored Rows: 5271



🔍 Checking per-rule positive densities (Past vs Future)...

&#x20;  ✅ NcssCount\_Class                : past\_pos=153 , future\_pos=1336

&#x20;  ✅ ExcessivePublicCount           : past\_pos=148 , future\_pos=1215

&#x20;  ✅ NcssCount\_Method               : past\_pos=158 , future\_pos=810 

&#x20;  ✅ CyclomaticComplexity\_Method    : past\_pos=158 , future\_pos=810 

&#x20;  ✅ CyclomaticComplexity\_Class     : past\_pos=139 , future\_pos=1100



💾 Saved Temporal Training Set: t2\_train\_chrono\_50\_dubbo.csv

💾 Saved Temporal Testing Set: t2\_test\_chrono\_50\_dubbo.csv

&#x20;  ✅ Robust chronological splitting validated successfully!

🏁 Phase T.2 Complete. The timeline has been permanently split (No spatial shuffling applied).

🔎 Running T.2 True Chronological Sanity Check...

&#x20;  ✅ Split matrices successfully loaded from disk (No corruption).

&#x20;  ✅ Release counts verified (Past/Train: 12, Future/Test: 12).

&#x20;  ✅ Zero data leakage detected (Past and Future releases are strictly mutually exclusive).

&#x20;  ✅ Chronological boundary mathematically verified via Git History (Max Past TS: 1515316905 < Min Future TS: 1520905330).



📁 Step 4: System Evolution \& Temporal Overlap (T.2 Split)

&#x20;     - Canonical identities in the Past (Train):            965

&#x20;     - Canonical identities in the Future (Test):           3168

&#x20;     - Identities persisting across the split (Overlap):    930

&#x20;     - Identities retired/deleted before Future phase:      35

&#x20;     - New identities introduced in Future phase:           2238

&#x20;     🎯 Percentage of Future Architecture seen in the Past: 29.36%



🏁 Audit Complete. The T.2 Chronological Split is academically secure and verified.

🚀 Starting Phase B.3: Multi-Percentile Sweep Analysis (Optimized \& Guarded)

📊 Loaded Training Set with 2564 canonical entities ready for K-Fold Calibration.



📈 Executing 5-Fold Cross-Validation Tournament...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...

&#x20;  ⚙️ Processing Fold 4 as Validation...

&#x20;  ⚙️ Processing Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.05|R:0.98|F1:0.09) | 3 (P:0.04|R:0.88|F1:0.09) | 4 (P:0.04|R:0.79|F1:0.08) | 8 (P:0.04|R:0.65|F1:0.08) | 12 (P:0.05|R:0.56|F1:0.08) | 21 (P:0.05|R:0.45|F1:0.09) | 30 (P:0.05|R:0.36|F1:0.08) | 42 (P:0.05|R:0.25|F1:0.08) | 65 (P:0.04|R:0.15|F1:0.07) | 94 (P:0.05|R:0.11|F1:0.06) | 171 (P:0.06|R:0.05|F1:0.05) |

| CyclomaticComplexity\_Class  | 1 (P:0.05|R:1.00|F1:0.09) | 2 (P:0.05|R:0.89|F1:0.09) | 3 (P:0.05|R:0.78|F1:0.09) | 4 (P:0.05|R:0.69|F1:0.09) | 6 (P:0.05|R:0.57|F1:0.09)  | 10 (P:0.05|R:0.45|F1:0.09) | 13 (P:0.05|R:0.36|F1:0.08) | 18 (P:0.05|R:0.26|F1:0.08) | 29 (P:0.05|R:0.15|F1:0.07) | 49 (P:0.05|R:0.11|F1:0.07) | 76 (P:0.06|R:0.05|F1:0.05)  |

| ExcessivePublicCount        | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.04|R:0.91|F1:0.08) | 2 (P:0.04|R:0.62|F1:0.08)  | 3 (P:0.04|R:0.47|F1:0.08)  | 5 (P:0.05|R:0.38|F1:0.08)  | 7 (P:0.05|R:0.28|F1:0.08)  | 11 (P:0.05|R:0.16|F1:0.07) | 14 (P:0.04|R:0.11|F1:0.06) | 22 (P:0.04|R:0.05|F1:0.05)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.97|F1:0.01) | 2 (P:0.01|R:0.97|F1:0.01) | 2 (P:0.01|R:0.91|F1:0.01) | 4 (P:0.01|R:0.71|F1:0.02) | 5 (P:0.01|R:0.60|F1:0.02)  | 8 (P:0.01|R:0.47|F1:0.03)  | 10 (P:0.01|R:0.39|F1:0.03) | 14 (P:0.02|R:0.26|F1:0.03) | 22 (P:0.02|R:0.15|F1:0.03) | 31 (P:0.03|R:0.10|F1:0.04) | 52 (P:0.04|R:0.04|F1:0.04)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 2 (P:0.01|R:0.61|F1:0.02)  | 3 (P:0.01|R:0.49|F1:0.02)  | 5 (P:0.01|R:0.37|F1:0.03)  | 7 (P:0.02|R:0.26|F1:0.04)  | 9 (P:0.02|R:0.15|F1:0.03)  | 12 (P:0.02|R:0.10|F1:0.04) | 21 (P:0.03|R:0.04|F1:0.04)  |

| TooManyMethods              | 1 (P:0.04|R:0.98|F1:0.08) | 1 (P:0.04|R:0.98|F1:0.08) | 2 (P:0.04|R:0.79|F1:0.08) | 2 (P:0.04|R:0.76|F1:0.08) | 4 (P:0.05|R:0.57|F1:0.08)  | 5 (P:0.05|R:0.47|F1:0.08)  | 7 (P:0.05|R:0.37|F1:0.08)  | 10 (P:0.05|R:0.27|F1:0.08) | 14 (P:0.05|R:0.16|F1:0.07) | 20 (P:0.05|R:0.10|F1:0.06) | 29 (P:0.05|R:0.06|F1:0.05)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.05|R:0.98|F0.5:0.06) | 3 (P:0.04|R:0.88|F0.5:0.06) | 4 (P:0.04|R:0.79|F0.5:0.05) | 8 (P:0.04|R:0.65|F0.5:0.06) | 12 (P:0.05|R:0.56|F0.5:0.06) | 21 (P:0.05|R:0.45|F0.5:0.06) | 30 (P:0.05|R:0.36|F0.5:0.06) | 42 (P:0.05|R:0.25|F0.5:0.05) | 65 (P:0.04|R:0.15|F0.5:0.05) | 94 (P:0.05|R:0.11|F0.5:0.05) | 171 (P:0.06|R:0.05|F0.5:0.05) |

| CyclomaticComplexity\_Class  | 1 (P:0.05|R:1.00|F0.5:0.06) | 2 (P:0.05|R:0.89|F0.5:0.06) | 3 (P:0.05|R:0.78|F0.5:0.06) | 4 (P:0.05|R:0.69|F0.5:0.06) | 6 (P:0.05|R:0.57|F0.5:0.06)  | 10 (P:0.05|R:0.45|F0.5:0.06) | 13 (P:0.05|R:0.36|F0.5:0.06) | 18 (P:0.05|R:0.26|F0.5:0.05) | 29 (P:0.05|R:0.15|F0.5:0.05) | 49 (P:0.05|R:0.11|F0.5:0.06) | 76 (P:0.06|R:0.05|F0.5:0.05)  |

| ExcessivePublicCount        | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.04|R:0.91|F0.5:0.06) | 2 (P:0.04|R:0.62|F0.5:0.05)  | 3 (P:0.04|R:0.47|F0.5:0.05)  | 5 (P:0.05|R:0.38|F0.5:0.06)  | 7 (P:0.05|R:0.28|F0.5:0.06)  | 11 (P:0.05|R:0.16|F0.5:0.05) | 14 (P:0.04|R:0.11|F0.5:0.05) | 22 (P:0.04|R:0.05|F0.5:0.04)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.97|F0.5:0.01) | 2 (P:0.01|R:0.97|F0.5:0.01) | 2 (P:0.01|R:0.91|F0.5:0.01) | 4 (P:0.01|R:0.71|F0.5:0.01) | 5 (P:0.01|R:0.60|F0.5:0.01)  | 8 (P:0.01|R:0.47|F0.5:0.02)  | 10 (P:0.01|R:0.39|F0.5:0.02) | 14 (P:0.02|R:0.26|F0.5:0.02) | 22 (P:0.02|R:0.15|F0.5:0.02) | 31 (P:0.03|R:0.10|F0.5:0.03) | 52 (P:0.04|R:0.04|F0.5:0.04)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F0.5:0.01) | 1 (P:0.00|R:1.00|F0.5:0.01) | 1 (P:0.00|R:1.00|F0.5:0.01) | 1 (P:0.00|R:1.00|F0.5:0.01) | 2 (P:0.01|R:0.61|F0.5:0.01)  | 3 (P:0.01|R:0.49|F0.5:0.01)  | 5 (P:0.01|R:0.37|F0.5:0.02)  | 7 (P:0.02|R:0.26|F0.5:0.02)  | 9 (P:0.02|R:0.15|F0.5:0.02)  | 12 (P:0.02|R:0.10|F0.5:0.03) | 21 (P:0.03|R:0.04|F0.5:0.03)  |

| TooManyMethods              | 1 (P:0.04|R:0.98|F0.5:0.05) | 1 (P:0.04|R:0.98|F0.5:0.05) | 2 (P:0.04|R:0.79|F0.5:0.05) | 2 (P:0.04|R:0.76|F0.5:0.05) | 4 (P:0.05|R:0.57|F0.5:0.06)  | 5 (P:0.05|R:0.47|F0.5:0.06)  | 7 (P:0.05|R:0.37|F0.5:0.06)  | 10 (P:0.05|R:0.27|F0.5:0.06) | 14 (P:0.05|R:0.16|F0.5:0.05) | 20 (P:0.05|R:0.10|F0.5:0.05) | 29 (P:0.05|R:0.06|F0.5:0.05)  |



🏆 F1-Optimized Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 5th          |                 2 |                42 |         0.0877 |             1.01 |      0.0456 |            5 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 5th          |                 1 |                49 |         0.0905 |             1    |      0.0474 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 5th          |                 1 |                14 |         0.0874 |             1    |      0.0457 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 90th         |                31 |                52 |         0.0398 |             5.48 |      0.0046 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                21 |                21 |         0.0372 |             7.17 |      0.0046 |            5 |

| TooManyMethods              | True         | False              | False         | 45th         |                 4 |                29 |         0.0841 |             1.1  |      0.0414 |            5 |



🎯 Precision-Optimized (F0.5) Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 55th         |                21 |               171 |           0.058  |             1.05 |      0.0456 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 90th         |                49 |                76 |           0.0587 |             1.12 |      0.0474 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 5th          |                 1 |                22 |           0.0565 |             1    |      0.0457 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                52 |                52 |           0.0372 |             8.32 |      0.0046 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                21 |                21 |           0.0344 |             7.17 |      0.0046 |            5 |

| TooManyMethods              | True         | False              | False         | 75th         |                10 |                29 |           0.0578 |             1.17 |      0.0414 |            5 |



💾 Saved Dual Baseline locked thresholds to disk: /content/b3\_inflection\_thresholds\_dubbo\_locked.json

🏁 Phase B.3 Complete.

🚀 Starting Phase E.3: Multi-Percentile Sweep Analysis (Scarcity Edition)

📊 Loaded Scarcity Training Set (20%) with 640 canonical entities.



📈 Executing 3-Fold Cross-Validation Tournament (Scarcity)...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                      | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.04|R:1.00|F1:0.09) | 3 (P:0.04|R:0.87|F1:0.08) | 4 (P:0.04|R:0.76|F1:0.08) | 6 (P:0.04|R:0.68|F1:0.08) | 9 (P:0.04|R:0.59|F1:0.08) | 14 (P:0.05|R:0.47|F1:0.08) | 29 (P:0.05|R:0.36|F1:0.08) | 42 (P:0.05|R:0.26|F1:0.08) | 59 (P:0.05|R:0.18|F1:0.07) | 90 (P:0.05|R:0.13|F1:0.07) | 142 (P:0.05|R:0.06|F1:0.04) |

| CyclomaticComplexity\_Class  | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.05|R:0.91|F1:0.09) | 2 (P:0.04|R:0.76|F1:0.08) | 3 (P:0.04|R:0.71|F1:0.08) | 4 (P:0.05|R:0.64|F1:0.09) | 7 (P:0.05|R:0.47|F1:0.08)  | 12 (P:0.05|R:0.38|F1:0.09) | 17 (P:0.05|R:0.29|F1:0.08) | 27 (P:0.06|R:0.20|F1:0.08) | 44 (P:0.06|R:0.12|F1:0.07) | 88 (P:0.06|R:0.06|F1:0.04)  |

| ExcessivePublicCount        | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.04|R:0.81|F1:0.08) | 2 (P:0.04|R:0.68|F1:0.08) | 3 (P:0.05|R:0.51|F1:0.08)  | 4 (P:0.05|R:0.41|F1:0.09)  | 7 (P:0.05|R:0.29|F1:0.08)  | 11 (P:0.05|R:0.17|F1:0.08) | 15 (P:0.06|R:0.12|F1:0.07) | 19 (P:0.05|R:0.06|F1:0.05)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.00|R:0.97|F1:0.01) | 2 (P:0.00|R:0.97|F1:0.01) | 4 (P:0.01|R:0.79|F1:0.01) | 4 (P:0.01|R:0.66|F1:0.02) | 5 (P:0.01|R:0.61|F1:0.02) | 7 (P:0.01|R:0.45|F1:0.02)  | 9 (P:0.01|R:0.39|F1:0.02)  | 12 (P:0.01|R:0.26|F1:0.02) | 22 (P:0.02|R:0.18|F1:0.03) | 28 (P:0.02|R:0.12|F1:0.03) | 57 (P:0.02|R:0.06|F1:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:0.84|F1:0.01) | 2 (P:0.01|R:0.59|F1:0.02) | 3 (P:0.01|R:0.48|F1:0.02)  | 4 (P:0.01|R:0.42|F1:0.02)  | 5 (P:0.01|R:0.28|F1:0.02)  | 9 (P:0.02|R:0.19|F1:0.03)  | 14 (P:0.02|R:0.10|F1:0.03) | 21 (P:0.02|R:0.08|F1:0.03)  |

| TooManyMethods              | 1 (P:0.04|R:0.99|F1:0.08) | 1 (P:0.04|R:0.99|F1:0.08) | 2 (P:0.04|R:0.79|F1:0.08) | 3 (P:0.05|R:0.70|F1:0.08) | 4 (P:0.05|R:0.59|F1:0.09) | 5 (P:0.05|R:0.46|F1:0.08)  | 7 (P:0.05|R:0.37|F1:0.08)  | 10 (P:0.05|R:0.27|F1:0.08) | 15 (P:0.05|R:0.17|F1:0.08) | 18 (P:0.05|R:0.11|F1:0.07) | 29 (P:0.06|R:0.05|F1:0.05)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                        | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.04|R:1.00|F0.5:0.06) | 3 (P:0.04|R:0.87|F0.5:0.05) | 4 (P:0.04|R:0.76|F0.5:0.05) | 6 (P:0.04|R:0.68|F0.5:0.05) | 9 (P:0.04|R:0.59|F0.5:0.05) | 14 (P:0.05|R:0.47|F0.5:0.06) | 29 (P:0.05|R:0.36|F0.5:0.06) | 42 (P:0.05|R:0.26|F0.5:0.06) | 59 (P:0.05|R:0.18|F0.5:0.06) | 90 (P:0.05|R:0.13|F0.5:0.06) | 142 (P:0.05|R:0.06|F0.5:0.04) |

| CyclomaticComplexity\_Class  | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.05|R:0.91|F0.5:0.06) | 2 (P:0.04|R:0.76|F0.5:0.06) | 3 (P:0.04|R:0.71|F0.5:0.05) | 4 (P:0.05|R:0.64|F0.5:0.06) | 7 (P:0.05|R:0.47|F0.5:0.05)  | 12 (P:0.05|R:0.38|F0.5:0.06) | 17 (P:0.05|R:0.29|F0.5:0.06) | 27 (P:0.06|R:0.20|F0.5:0.06) | 44 (P:0.06|R:0.12|F0.5:0.06) | 88 (P:0.06|R:0.06|F0.5:0.04)  |

| ExcessivePublicCount        | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.04|R:0.81|F0.5:0.05) | 2 (P:0.04|R:0.68|F0.5:0.05) | 3 (P:0.05|R:0.51|F0.5:0.06)  | 4 (P:0.05|R:0.41|F0.5:0.06)  | 7 (P:0.05|R:0.29|F0.5:0.06)  | 11 (P:0.05|R:0.17|F0.5:0.06) | 15 (P:0.06|R:0.12|F0.5:0.06) | 19 (P:0.05|R:0.06|F0.5:0.05)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.00|R:0.97|F0.5:0.01) | 2 (P:0.00|R:0.97|F0.5:0.01) | 4 (P:0.01|R:0.79|F0.5:0.01) | 4 (P:0.01|R:0.66|F0.5:0.01) | 5 (P:0.01|R:0.61|F0.5:0.01) | 7 (P:0.01|R:0.45|F0.5:0.01)  | 9 (P:0.01|R:0.39|F0.5:0.01)  | 12 (P:0.01|R:0.26|F0.5:0.01) | 22 (P:0.02|R:0.18|F0.5:0.02) | 28 (P:0.02|R:0.12|F0.5:0.02) | 57 (P:0.02|R:0.06|F0.5:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F0.5:0.00) | 1 (P:0.00|R:1.00|F0.5:0.00) | 1 (P:0.00|R:1.00|F0.5:0.00) | 1 (P:0.00|R:0.84|F0.5:0.01) | 2 (P:0.01|R:0.59|F0.5:0.01) | 3 (P:0.01|R:0.48|F0.5:0.01)  | 4 (P:0.01|R:0.42|F0.5:0.01)  | 5 (P:0.01|R:0.28|F0.5:0.01)  | 9 (P:0.02|R:0.19|F0.5:0.02)  | 14 (P:0.02|R:0.10|F0.5:0.02) | 21 (P:0.02|R:0.08|F0.5:0.02)  |

| TooManyMethods              | 1 (P:0.04|R:0.99|F0.5:0.05) | 1 (P:0.04|R:0.99|F0.5:0.05) | 2 (P:0.04|R:0.79|F0.5:0.05) | 3 (P:0.05|R:0.70|F0.5:0.06) | 4 (P:0.05|R:0.59|F0.5:0.06) | 5 (P:0.05|R:0.46|F0.5:0.06)  | 7 (P:0.05|R:0.37|F0.5:0.06)  | 10 (P:0.05|R:0.27|F0.5:0.06) | 15 (P:0.05|R:0.17|F0.5:0.06) | 18 (P:0.05|R:0.11|F0.5:0.06) | 29 (P:0.06|R:0.05|F0.5:0.05)  |



🏆 F1-Optimized Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 5th          |                 2 |                90 |         0.086  |             1.01 |      0.0444 |            3 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 5th          |                 1 |                44 |         0.0895 |             1    |      0.0469 |            3 |

| ExcessivePublicCount        | True         | False              | False         | 5th          |                 1 |                15 |         0.0867 |             1    |      0.0453 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | False              | False         | 85th         |                22 |                57 |         0.0285 |             4.04 |      0.0039 |            3 |

| CyclomaticComplexity\_Method | True         | False              | False         | 85th         |                 9 |                21 |         0.0341 |             4.84 |      0.0039 |            3 |

| TooManyMethods              | True         | False              | False         | 45th         |                 4 |                15 |         0.0905 |             1.14 |      0.0429 |            3 |



🎯 Precision-Optimized (F0.5) Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 65th         |                29 |                90 |           0.0588 |             1.1  |      0.0444 |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 85th         |                27 |                44 |           0.0622 |             1.18 |      0.0469 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 90th         |                15 |                15 |           0.064  |             1.32 |      0.0453 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | False              | False         | 90th         |                28 |                57 |           0.0194 |             4.17 |      0.0039 |            3 |

| CyclomaticComplexity\_Method | True         | False              | False         | 85th         |                 9 |                21 |           0.0229 |             4.84 |      0.0039 |            3 |

| TooManyMethods              | True         | True               | False         | 85th         |                15 |                29 |           0.0603 |             1.22 |      0.0429 |            3 |



💾 Saved Dual Baseline locked thresholds to disk: /content/e3\_inflection\_thresholds\_dubbo\_scarcity.json

🏁 Phase E.3 Complete.

🚀 Starting Phase T.3: Chronological K-Fold Calibration Engine

📊 Loaded Temporal Training Set (The Past) with 965 canonical entities.



📈 Executing 5-Fold Cross-Validation Tournament (Chronological; n\_splits=5)...

&#x20;  ⚙️ Processing Temporal Fold 1 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 2 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 3 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 4 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                        | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.01|R:0.98|F1:0.03) | 4 (P:0.02|R:0.86|F1:0.03) | 4 (P:0.02|R:0.77|F1:0.03) | 7 (P:0.02|R:0.66|F1:0.03) | 13 (P:0.01|R:0.42|F1:0.03) | 18 (P:0.01|R:0.36|F1:0.03) | 29 (P:0.01|R:0.31|F1:0.03) | 40 (P:0.01|R:0.21|F1:0.02) | 54 (P:0.01|R:0.12|F1:0.02) | 114 (P:0.01|R:0.08|F1:0.02) | 177 (P:0.01|R:0.05|F1:0.02) |

| CyclomaticComplexity\_Class  | 1 (P:0.02|R:1.00|F1:0.04) | 1 (P:0.02|R:1.00|F1:0.04) | 2 (P:0.02|R:0.81|F1:0.04) | 4 (P:0.02|R:0.67|F1:0.03) | 6 (P:0.02|R:0.50|F1:0.03)  | 8 (P:0.01|R:0.38|F1:0.03)  | 12 (P:0.02|R:0.34|F1:0.03) | 19 (P:0.01|R:0.16|F1:0.02) | 27 (P:0.01|R:0.10|F1:0.02) | 48 (P:0.01|R:0.02|F1:0.01)  | 75 (P:0.01|R:0.02|F1:0.01)  |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.02|R:0.93|F1:0.03) | 2 (P:0.02|R:0.55|F1:0.03)  | 3 (P:0.02|R:0.43|F1:0.03)  | 5 (P:0.02|R:0.31|F1:0.03)  | 6 (P:0.02|R:0.23|F1:0.03)  | 9 (P:0.02|R:0.15|F1:0.03)  | 10 (P:0.02|R:0.13|F1:0.03)  | 15 (P:0.01|R:0.06|F1:0.02)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         |

| NcssCount\_Method            | 1 (P:0.00|R:0.97|F1:0.00) | 2 (P:0.00|R:0.94|F1:0.00) | 3 (P:0.00|R:0.77|F1:0.01) | 5 (P:0.00|R:0.72|F1:0.01) | 5 (P:0.00|R:0.72|F1:0.01)  | 8 (P:0.01|R:0.53|F1:0.01)  | 10 (P:0.01|R:0.48|F1:0.01) | 14 (P:0.01|R:0.36|F1:0.01) | 22 (P:0.01|R:0.27|F1:0.01) | 32 (P:0.01|R:0.18|F1:0.02)  | 60 (P:0.01|R:0.12|F1:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F1:0.00) | 1 (P:0.00|R:1.00|F1:0.00) | 1 (P:0.00|R:1.00|F1:0.00) | 2 (P:0.00|R:0.59|F1:0.01) | 3 (P:0.00|R:0.54|F1:0.01)  | 3 (P:0.00|R:0.52|F1:0.01)  | 5 (P:0.00|R:0.40|F1:0.01)  | 7 (P:0.01|R:0.36|F1:0.01)  | 10 (P:0.01|R:0.26|F1:0.01) | 14 (P:0.01|R:0.23|F1:0.02)  | 24 (P:0.01|R:0.11|F1:0.02)  |

| TooManyMethods              | 1 (P:0.02|R:0.99|F1:0.03) | 1 (P:0.02|R:0.99|F1:0.03) | 1 (P:0.02|R:0.92|F1:0.03) | 2 (P:0.02|R:0.67|F1:0.03) | 3 (P:0.02|R:0.59|F1:0.03)  | 4 (P:0.02|R:0.51|F1:0.04)  | 6 (P:0.02|R:0.37|F1:0.04)  | 8 (P:0.02|R:0.31|F1:0.04)  | 13 (P:0.02|R:0.16|F1:0.03) | 15 (P:0.01|R:0.10|F1:0.02)  | 21 (P:0.01|R:0.05|F1:0.02)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                          | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.01|R:0.98|F0.5:0.02) | 4 (P:0.02|R:0.86|F0.5:0.02) | 4 (P:0.02|R:0.77|F0.5:0.02) | 7 (P:0.02|R:0.66|F0.5:0.02) | 13 (P:0.01|R:0.42|F0.5:0.02) | 18 (P:0.01|R:0.36|F0.5:0.02) | 29 (P:0.01|R:0.31|F0.5:0.02) | 40 (P:0.01|R:0.21|F0.5:0.02) | 54 (P:0.01|R:0.12|F0.5:0.01) | 114 (P:0.01|R:0.08|F0.5:0.01) | 177 (P:0.01|R:0.05|F0.5:0.01) |

| CyclomaticComplexity\_Class  | 1 (P:0.02|R:1.00|F0.5:0.02) | 1 (P:0.02|R:1.00|F0.5:0.02) | 2 (P:0.02|R:0.81|F0.5:0.02) | 4 (P:0.02|R:0.67|F0.5:0.02) | 6 (P:0.02|R:0.50|F0.5:0.02)  | 8 (P:0.01|R:0.38|F0.5:0.02)  | 12 (P:0.02|R:0.34|F0.5:0.02) | 19 (P:0.01|R:0.16|F0.5:0.02) | 27 (P:0.01|R:0.10|F0.5:0.02) | 48 (P:0.01|R:0.02|F0.5:0.01)  | 75 (P:0.01|R:0.02|F0.5:0.01)  |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.02|R:0.93|F0.5:0.02) | 2 (P:0.02|R:0.55|F0.5:0.02)  | 3 (P:0.02|R:0.43|F0.5:0.02)  | 5 (P:0.02|R:0.31|F0.5:0.02)  | 6 (P:0.02|R:0.23|F0.5:0.02)  | 9 (P:0.02|R:0.15|F0.5:0.02)  | 10 (P:0.02|R:0.13|F0.5:0.02)  | 15 (P:0.01|R:0.06|F0.5:0.01)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           |

| NcssCount\_Method            | 1 (P:0.00|R:0.97|F0.5:0.00) | 2 (P:0.00|R:0.94|F0.5:0.00) | 3 (P:0.00|R:0.77|F0.5:0.00) | 5 (P:0.00|R:0.72|F0.5:0.01) | 5 (P:0.00|R:0.72|F0.5:0.01)  | 8 (P:0.01|R:0.53|F0.5:0.01)  | 10 (P:0.01|R:0.48|F0.5:0.01) | 14 (P:0.01|R:0.36|F0.5:0.01) | 22 (P:0.01|R:0.27|F0.5:0.01) | 32 (P:0.01|R:0.18|F0.5:0.01)  | 60 (P:0.01|R:0.12|F0.5:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F0.5:0.00) | 1 (P:0.00|R:1.00|F0.5:0.00) | 1 (P:0.00|R:1.00|F0.5:0.00) | 2 (P:0.00|R:0.59|F0.5:0.00) | 3 (P:0.00|R:0.54|F0.5:0.00)  | 3 (P:0.00|R:0.52|F0.5:0.01)  | 5 (P:0.00|R:0.40|F0.5:0.01)  | 7 (P:0.01|R:0.36|F0.5:0.01)  | 10 (P:0.01|R:0.26|F0.5:0.01) | 14 (P:0.01|R:0.23|F0.5:0.01)  | 24 (P:0.01|R:0.11|F0.5:0.02)  |

| TooManyMethods              | 1 (P:0.02|R:0.99|F0.5:0.02) | 1 (P:0.02|R:0.99|F0.5:0.02) | 1 (P:0.02|R:0.92|F0.5:0.02) | 2 (P:0.02|R:0.67|F0.5:0.02) | 3 (P:0.02|R:0.59|F0.5:0.02)  | 4 (P:0.02|R:0.51|F0.5:0.02)  | 6 (P:0.02|R:0.37|F0.5:0.02)  | 8 (P:0.02|R:0.31|F0.5:0.02)  | 13 (P:0.02|R:0.16|F0.5:0.02) | 15 (P:0.01|R:0.10|F0.5:0.02)  | 21 (P:0.01|R:0.05|F0.5:0.01)  |



🏆 F1-Optimized Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 15th         |                 4 |               177 |         0.0309 |             1.1  |      0.0143 |            5 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 5th          |                 1 |                27 |         0.0363 |             1    |      0.0185 |            4 |

| ExcessivePublicCount        | True         | True               | False         | 65th         |                 5 |                10 |         0.0335 |             1.2  |      0.0149 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                60 |                60 |         0.0233 |             5.79 |      0.0022 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                24 |                24 |         0.0239 |             6.04 |      0.0022 |            5 |

| TooManyMethods              | True         | False              | False         | 55th         |                 4 |                21 |         0.0374 |             1.15 |      0.0169 |            4 |



🎯 Precision-Optimized (F0.5) Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 15th         |                 4 |               177 |           0.0196 |             1.1  |      0.0143 |            5 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 5th          |                 1 |                75 |           0.0231 |             1    |      0.0185 |            4 |

| ExcessivePublicCount        | True         | False              | False         | 65th         |                 5 |                15 |           0.022  |             1.2  |      0.0149 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                60 |                60 |           0.0157 |             5.79 |      0.0022 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                24 |                24 |           0.0163 |             6.04 |      0.0022 |            5 |

| TooManyMethods              | True         | False              | False         | 55th         |                 4 |                21 |           0.0241 |             1.15 |      0.0169 |            4 |



💾 Saved Dual Chronological locked thresholds to disk: t3\_inflection\_thresholds\_dubbo\_chrono\_locked.json

🏁 Phase T.3 Complete.

🚀 Starting Phase B.4: Blind Imminent Predictability Evaluation (Trust-Aware Edition)

✅ Thresholds strictly synchronized from disk.

📊 Final Exam Loaded: Evaluating 639 completely unseen canonical entities.



&#x20;   MASTER BLIND EVALUATION MATRIX (Test Set: 20%)



📊 TABLE 1: F1-Optimized Thresholds (Evaluated on Blind F1 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       327 |         1500 |             15 | ⚠️ 1500 (Fallback) |     0.088 |     0     |    0     |      0.087 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       265 |           80 |              8 | ⚠️ 80 (Fallback)   |     0.09  |     0.033 |    0.033 |      0.083 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       287 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.087 |     0.011 |    0.011 |      0.079 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       179 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.04  |     0     |    0     |      0.01  | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       179 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.037 |     0.04  |    0.04  |      0.009 | ➖ Uncalibrated Noise |

| TooManyMethods              |       199 |           10 |              3 | ⚠️ 10 (Fallback)   |     0.084 |     0.084 |    0.084 |      0.077 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized Thresholds (Evaluated on Blind F0.5 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       327 |         1500 |             15 | ⚠️ 1500 (Fallback) |      0.058 |      0     |     0     |       0.059 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       265 |           80 |              8 | ⚠️ 80 (Fallback)   |      0.059 |      0.04  |     0.04  |       0.056 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       287 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.057 |      0.017 |     0.017 |       0.053 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       179 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.037 |      0     |     0     |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       179 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.034 |      0.029 |     0.029 |       0.006 | ➖ Uncalibrated Noise |

| TooManyMethods              |       199 |           10 |              3 | ⚠️ 10 (Fallback)   |      0.058 |      0.06  |     0.06  |       0.051 | ➖ Uncalibrated Noise |



💾 Saved detailed evaluation matrix to: b4\_evaluation\_matrix\_dubbo.csv



=================================================================

🏆 FINAL BASELINE EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  Test Entities (Strictly Blind):   639

\-----------------------------------------------------------------

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F1 averages.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F0.5 averages.

=================================================================

🏁 Phase B.4 Complete. The threshold hypotheses have been blindly evaluated.

🚀 Starting Phase E.4: Scarcity Predictability Evaluation (Trust-Aware)

📊 Final Scarcity Exam Loaded: Evaluating 639 completely unseen canonical entities.



📊 TABLE 1: F1-Optimized Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       327 |         1500 |             13 | ⚠️ 1500 (Fallback) |     0.086 |     0     |    0     |      0.086 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       265 |           80 |              7 | ⚠️ 80 (Fallback)   |     0.089 |     0.033 |    0.033 |      0.082 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       287 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.087 |     0.011 |    0.011 |      0.079 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       179 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.029 |     0     |    0     |      0.01  | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       179 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.034 |     0.04  |    0.04  |      0.009 | ➖ Uncalibrated Noise |

| TooManyMethods              |       199 |           10 |              4 | ⚠️ 10 (Fallback)   |     0.09  |     0.084 |    0.084 |      0.08  | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       327 |         1500 |             13 | ⚠️ 1500 (Fallback) |      0.059 |      0     |     0     |       0.058 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       265 |           80 |              7 | ⚠️ 80 (Fallback)   |      0.062 |      0.04  |     0.04  |       0.055 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       287 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.064 |      0.017 |     0.017 |       0.053 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       179 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.019 |      0     |     0     |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       179 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.023 |      0.029 |     0.029 |       0.006 | ➖ Uncalibrated Noise |

| TooManyMethods              |       199 |           10 |              4 | ⚠️ 10 (Fallback)   |      0.06  |      0.06  |     0.06  |       0.054 | ➖ Uncalibrated Noise |



=================================================================

🏆 SCARCITY EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

=================================================================



💾 Saved scarcity evaluation matrix to: e4\_evaluation\_matrix\_scarcity\_dubbo.csv

🏁 Phase E.4 Complete. Scarcity evaluation finalized.

🚀 Starting Phase T.4: Chronological Predictability Evaluation (Trust-Aware)

📊 Final Chronological Exam Loaded: Evaluating against Future Timeline.



📊 TABLE 1: F1-Optimized Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |      1336 |         1500 |             14 | ⚠️ 1500 (Fallback) |     0.031 |     0     |    0     |      0.106 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |      1100 |           80 |              7 | ⚠️ 80 (Fallback)   |     0.036 |     0.057 |    0.057 |      0.109 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |      1215 |           45 |              2 | ⚠️ 45 (Fallback)   |     0.034 |     0.025 |    0.025 |      0.094 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       810 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.023 |     0.032 |    0.032 |      0.011 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       810 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.024 |     0.05  |    0.05  |      0.01  | ➖ Uncalibrated Noise |

| TooManyMethods              |       877 |           10 |              3 | ⚠️ 10 (Fallback)   |     0.037 |     0.099 |    0.099 |      0.096 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |      1336 |         1500 |             14 | ⚠️ 1500 (Fallback) |      0.02  |      0     |     0     |       0.072 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |      1100 |           80 |              7 | ⚠️ 80 (Fallback)   |      0.023 |      0.069 |     0.069 |       0.074 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |      1215 |           45 |              2 | ⚠️ 45 (Fallback)   |      0.022 |      0.038 |     0.038 |       0.062 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       810 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.016 |      0.042 |     0.042 |       0.007 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       810 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.016 |      0.036 |     0.036 |       0.006 | ➖ Uncalibrated Noise |

| TooManyMethods              |       877 |           10 |              3 | ⚠️ 10 (Fallback)   |      0.024 |      0.072 |     0.072 |       0.064 | ➖ Uncalibrated Noise |



=================================================================

🏆 CHRONOLOGICAL EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

=================================================================



💾 Saved chronological evaluation matrix to: t4\_evaluation\_matrix\_chrono\_dubbo.csv

🏁 Phase T.4 Complete. Chronological evaluation finalized.



=====================================================================================

🚀 INITIATING PHASE 6: MASTER CROSS-REGIME DISCRIMINATION DIAGNOSTIC

=====================================================================================



================ DISCRIMINATION BY SOURCE × RULE ================

AUC-PR \~ base\_rate  ⇒  lift \~ 1.0  ⇒  metric ranks refactoring at chance.



| Source                   | Rule                        |      n |   n\_pos |   base\_rate |   auc\_pr |   lift | flag         |

|:-------------------------|:----------------------------|-------:|--------:|------------:|---------:|-------:|:-------------|

| Pooled/all               | NcssCount\_Class             |  31669 |    1489 |      0.047  |   0.0475 |   1.01 | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Class  |  25425 |    1239 |      0.0487 |   0.0489 |   1    | rare (<5%)   |

| Pooled/all               | ExcessivePublicCount        |  29127 |    1363 |      0.0468 |   0.0453 |   0.97 | rare (<5%)   |

| Pooled/all               | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | NcssCount\_Method            | 209557 |     968 |      0.0046 |   0.0135 |   2.93 | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Method | 209557 |     968 |      0.0046 |   0.0129 |   2.8  | rare (<5%)   |

| Pooled/all               | TooManyMethods              |  24009 |     997 |      0.0415 |   0.0448 |   1.08 | rare (<5%)   |

| Spatial/train            | NcssCount\_Class             |  25518 |    1162 |      0.0455 |   0.0468 |   1.03 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Class  |  20592 |     974 |      0.0473 |   0.0488 |   1.03 | rare (<5%)   |

| Spatial/train            | ExcessivePublicCount        |  23563 |    1076 |      0.0457 |   0.0455 |   1    | rare (<5%)   |

| Spatial/train            | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | NcssCount\_Method            | 170871 |     789 |      0.0046 |   0.0139 |   3.02 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Method | 170871 |     789 |      0.0046 |   0.0134 |   2.91 | rare (<5%)   |

| Spatial/train            | TooManyMethods              |  19294 |     798 |      0.0414 |   0.0452 |   1.09 | rare (<5%)   |

| Scarcity/train           | NcssCount\_Class             |   7365 |     331 |      0.0449 |   0.0465 |   1.03 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Class  |   5877 |     279 |      0.0475 |   0.0488 |   1.03 | rare (<5%)   |

| Scarcity/train           | ExcessivePublicCount        |   6959 |     319 |      0.0458 |   0.0488 |   1.06 | rare (<5%)   |

| Scarcity/train           | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | NcssCount\_Method            |  45213 |     173 |      0.0038 |   0.0099 |   2.59 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Method |  45213 |     173 |      0.0038 |   0.0093 |   2.44 | rare (<5%)   |

| Scarcity/train           | TooManyMethods              |   5095 |     218 |      0.0428 |   0.0503 |   1.17 | rare (<5%)   |

| Chronological/train      | NcssCount\_Class             |   9349 |     153 |      0.0164 |   0.0157 |   0.96 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Class  |   7925 |     139 |      0.0175 |   0.0158 |   0.9  | rare (<5%)   |

| Chronological/train      | ExcessivePublicCount        |   8887 |     148 |      0.0167 |   0.0177 |   1.07 | rare (<5%)   |

| Chronological/train      | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | NcssCount\_Method            |  53553 |     158 |      0.003  |   0.0145 |   4.91 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Method |  53553 |     158 |      0.003  |   0.0147 |   5    | rare (<5%)   |

| Chronological/train      | TooManyMethods              |   7070 |     120 |      0.017  |   0.0177 |   1.04 | rare (<5%)   |

| Spatial/Scarcity/holdout | NcssCount\_Class             |   6151 |     327 |      0.0532 |   0.0512 |   0.96 | ok           |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Class  |   4833 |     265 |      0.0548 |   0.0506 |   0.92 | ok           |

| Spatial/Scarcity/holdout | ExcessivePublicCount        |   5564 |     287 |      0.0516 |   0.0459 |   0.89 | ok           |

| Spatial/Scarcity/holdout | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | NcssCount\_Method            |  38686 |     179 |      0.0046 |   0.0122 |   2.63 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Method |  38686 |     179 |      0.0046 |   0.0113 |   2.44 | rare (<5%)   |

| Spatial/Scarcity/holdout | TooManyMethods              |   4715 |     199 |      0.0422 |   0.0442 |   1.05 | rare (<5%)   |

| Chronological/holdout    | NcssCount\_Class             |  22320 |    1336 |      0.0599 |   0.0615 |   1.03 | ok           |

| Chronological/holdout    | CyclomaticComplexity\_Class  |  17500 |    1100 |      0.0629 |   0.0651 |   1.04 | ok           |

| Chronological/holdout    | ExcessivePublicCount        |  20240 |    1215 |      0.06   |   0.0563 |   0.94 | ok           |

| Chronological/holdout    | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | NcssCount\_Method            | 156004 |     810 |      0.0052 |   0.017  |   3.28 | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Method | 156004 |     810 |      0.0052 |   0.0162 |   3.11 | rare (<5%)   |

| Chronological/holdout    | TooManyMethods              |  16939 |     877 |      0.0518 |   0.0551 |   1.06 | ok           |



\--- LIFT (AUC-PR / base\_rate) by rule × source ---

Lift strictly measures how much better the metric ranks over blind guessing.

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| CyclomaticComplexity\_Class  |         1    |            1.03 |             1.03 |                  0.9  |                       0.92 |                    1.04 |

| CyclomaticComplexity\_Method |         2.8  |            2.91 |             2.44 |                  5    |                       2.44 |                    3.11 |

| ExcessiveImports            |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| ExcessivePublicCount        |         0.97 |            1    |             1.06 |                  1.07 |                       0.89 |                    0.94 |

| NcssCount\_Class             |         1.01 |            1.03 |             1.03 |                  0.96 |                       0.96 |                    1.03 |

| NcssCount\_Method            |         2.93 |            3.02 |             2.59 |                  4.91 |                       2.63 |                    3.28 |

| TooManyMethods              |         1.08 |            1.09 |             1.17 |                  1.04 |                       1.05 |                    1.06 |



\--- AUC-PR (absolute) by rule × source ---

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| CyclomaticComplexity\_Class  |       0.0489 |          0.0488 |           0.0488 |                0.0158 |                     0.0506 |                  0.0651 |

| CyclomaticComplexity\_Method |       0.0129 |          0.0134 |           0.0093 |                0.0147 |                     0.0113 |                  0.0162 |

| ExcessiveImports            |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| ExcessivePublicCount        |       0.0453 |          0.0455 |           0.0488 |                0.0177 |                     0.0459 |                  0.0563 |

| NcssCount\_Class             |       0.0475 |          0.0468 |           0.0465 |                0.0157 |                     0.0512 |                  0.0615 |

| NcssCount\_Method            |       0.0135 |          0.0139 |           0.0099 |                0.0145 |                     0.0122 |                  0.017  |

| TooManyMethods              |       0.0448 |          0.0452 |           0.0503 |                0.0177 |                     0.0442 |                  0.0551 |



================ PER-SOURCE SUMMARY ================

(reliable = n\_pos≥30 AND base\_rate≥0.05)



| Source                   | Max Absolute AUC-PR                | Max Reliable Lift                |

|:-------------------------|:-----------------------------------|:---------------------------------|

| Pooled/all               | 0.049 (CyclomaticComplexity\_Class) | — (no statistically stable rule) |

| Spatial/train            | 0.049 (CyclomaticComplexity\_Class) | — (no statistically stable rule) |

| Scarcity/train           | 0.050 (TooManyMethods)             | — (no statistically stable rule) |

| Chronological/train      | 0.018 (ExcessivePublicCount)       | — (no statistically stable rule) |

| Spatial/Scarcity/holdout | 0.051 (NcssCount\_Class)            | 0.96 (NcssCount\_Class)           |

| Chronological/holdout    | 0.065 (CyclomaticComplexity\_Class) | 1.06 (TooManyMethods)            |



💾 Saved full diagnostic to: discrimination\_diagnostic\_dubbo.csv

🏁 Phase 5 Complete. The overarching data structure has been successfully diagnosed.



