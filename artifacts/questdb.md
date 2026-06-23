# Quest DB:



🚀 Setting up replication environment for questdb...

📂 Workspace Root: /content

📦 Data Directory: /content/data/questdb

☁️ Downloading questdb data from Zenodo...

🗜️ Unzipping data...

✅ Download and extraction complete.



\--- 🎯 Configuration Summary ---

Target Repository:  questdb

PMD Data Exists:    True

Refm Data Exists:   True

Lineage Exists:     True

Rel Hist Exists:    True

✅ Phase 0 Complete! You can now execute Phase 1.1.

🚀 Starting Phase 1.1: Data Synchronization Check

📂 Loading Release History Ground Truth...

&#x20;  ✅ Target Releases: 1 official releases found in configuration.



📂 Loading Master Lineage (The SHA Map)...

&#x20;  ✅ Lineage Loaded: 8195 total commits.



🔍 Step 1: Verifying PMD Snapshots...



🔍 Step 2: Verifying Refactoring Miner Ground Truth...

\--------------------------------------------------

📊 DATA SYNCHRONIZATION REPORT

&#x20;  🔹 PMD Snapshots: 35 valid snapshots verified in lineage (Expected at least: 1).

&#x20;  🔹 Refactoring Commits Mapped: 6169

&#x20;  🔹 Refactoring Density: 6203 unique commits contain refactorings.



🧾 PARSE INTEGRITY

&#x20;  - PMD unique SHAs observed (success only): 35

&#x20;  - PMD malformed lines: 0

&#x20;  - PMD failed-status lines skipped: 20

&#x20;  - PMD missing sha: 0

&#x20;  - PMD outside-lineage SHAs: 0

&#x20;  - RefMiner total entries read: 6203

&#x20;  - RefMiner malformed lines: 0

&#x20;  - RefMiner missing sha1: 0



🚀 SUCCESS: The three universes are synchronized!

&#x20;  The PMD observation points and Refactoring events exist on the same timeline.

🏁 Phase 1.1 Complete.

🚀 Starting Phase 1.2: Final Gold Class-Level Alias Graph Generation

⏳ Sorted 6203 commits chronologically to guarantee safe alias resolution.

&#x20;  🔍 Discovered 5071 Class Rename path-level aliases.

&#x20;  🔍 Discovered 966 Class Rename basename aliases.



📊 PHASE 1.2 INTEGRITY REPORT:

&#x20;  - Total Path Rename Links:      5071

&#x20;  - Total Basename Rename Links:  966

&#x20;  - Distinct Classes Threaded:    2997

&#x20;  - Multi-rename links collapsed: 2074

&#x20;  - Path Collisions (Preserved):  59

&#x20;  - Basename Collisions:          31

&#x20;  - Malformed/Skipped:            9

&#x20;      \* Missing Location Data: 9



✅ Identity lineage successfully resolved.

&#x20;  💾 Saved path-level graph to: alias\_tracking\_graph\_paths\_questdb.csv

&#x20;  💾 Saved basename graph to:   alias\_tracking\_graph\_questdb.csv

🏁 Phase 1.2 Complete.

🚀 Starting Phase 1.3: Final Audited Method Alias Graph Generation

⏳ Sorted 6203 commits chronologically for deterministic method alias chaining.

&#x20;  🔍 Discovered 5567 method lineage links.

&#x20;  ✅ Method lineage resolved.

&#x20;  💾 Saved to method\_alias\_graph\_questdb.csv



📊 PHASE 1.3 INTEGRITY REPORT:

&#x20;  - Total Method Links Mapped: 5567

&#x20;  - Collision Overwrites:      49

&#x20;  - Explicitly Skipped / Excluded:

&#x20;      \* Change Parameter Type: 7588



&#x20;  ✅ DATA INTEGRITY VERIFIED: 100% Regex match rate on targeted elements.



🏁 Phase 1.3 Complete.

🚀 Starting Phase D.2: Data Flattening \& Regex Rescue (With Alias Resolution)

⏳ Building PMD Method-Name Resolver from Phase 1.3 Graph...

&#x20;  ⚠️ Resolver collisions (preserved original root): 42

⏳ Loading Timelines and Mapping Ground Truth (Early Binding)...

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'

&#x20;  \[DEBUG] GENUINE failure on METHOD\_DECLARATION: 'FunctionFactories'



📉 THE DATA ATTRITION FUNNEL (Ground Truth Mapping):

&#x20;  🧩 Raw Taxonomy-Matched Refactorings: 16632

&#x20;  📌 Total leftSideLocations (all matched refs): 68439

&#x20;  🔍 Total Structural Operations Found: 20411

&#x20;  🛡️  Test Files Purged (Regex Filter):  4305

&#x20;  ✅ Production Refactorings Retained (location-level):  16106

&#x20;  🎯 Mappable retained locations (pre-dedup): 16089

&#x20;  🔗 Unique mapped supervision keys (post-dedup): 7197

&#x20;       ├─ God Class    (class-level):  2788

&#x20;       └─ Long Method  (method-level): 4409

&#x20;  ♻️  Dedup/compression delta: 8892

&#x20;  ⚠️ Refactorings dropped (missing from lineage gap): 34

&#x20;  ⚠️ Method refactorings dropped (unparseable signature): 16

&#x20;  ⚠️ PMD malformed lines:                0

&#x20;  ⚠️ PMD failed-status entries ignored:  20



✅ Flattened PMD Data: 1,920,451 raw metric records extracted.



🚫 Excluded-rule rows dropped from dataset (reported as a finding):

&#x20;     - CouplingBetweenObjects      :   49,554 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveImports            :   60,587 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveParameterList      :  499,542 rows  (no method signature → unmappable)

&#x20;     - TooManyFields               :   16,893 rows  (no metric value/range emitted)



🔍 DIAGNOSTIC: Checking for Zero-Refactoring Releases across the entire timeline...

&#x20;  ✅ All releases contain at least one mapped refactoring event.

\-------------------------------------------------------------------------------------



&#x20;  ⚠️ Dropped unrecoverable metric rows: 52639



🏁 Phase D.2 Complete! Saved flat dataset to pmd\_flat\_questdb.csv

Note: Train/Test splitting happens in Phase T.2.



📊 POST-FLATTENING DATASET AUDIT:

&#x20;  - Total Observations: 1,920,451

&#x20;  - Positive Refactoring Labels: 15,294

&#x20;  - Negative Observations: 1,905,157

&#x20;  - Class Imbalance Ratio: 124.57:1

&#x20;  - Unique Files Tracked: 4,378

&#x20;  - Unique Commits (Snapshots) Tracked: 35

&#x20;  - Missing/Null Metric Values: 0



&#x20;  - Row Count by Rule Type:

&#x20;      \* CyclomaticComplexity\_Method: 810,392

&#x20;      \* NcssCount\_Method         : 810,392

&#x20;      \* NcssCount\_Class          : 105,412

&#x20;      \* ExcessivePublicCount     : 101,196

&#x20;      \* CyclomaticComplexity\_Class: 93,059



✅ Dataset audit passed: Structure is valid and data is balanced.

&#x20;Audit loaded: 1,920,451 records for questdb



PER-RULE VERDICTS:

&#x20;                     rule      verdict  peak\_rate

&#x20;          NcssCount\_Class    ambiguous   0.040694

CyclomaticComplexity\_Class    ambiguous   0.033147

&#x20;     ExcessivePublicCount    ambiguous   0.032991

&#x20;         NcssCount\_Method monotonic\_up   0.016780

🚀 Starting Phase B.2: Structural Validation Split (80/20 Stratified)



📊 Executing Stratified Group K-Fold (Canonical Integrity at \~80/20)...

&#x20;  - Training Set (78.3% actual): 1,502,957 metric rows | 2424 Unique Refactoring Events

&#x20;  - Testing Set  (21.7% actual): 417,494 metric rows | 602 Unique Refactoring Events



🔍 Checking per-rule positive event densities (Rule Viability)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=2478, test\_pos=610

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=2173, test\_pos=511

&#x20;  ✅ ExcessivePublicCount           : train\_pos=2285, test\_pos=585

&#x20;  ✅ NcssCount\_Method               : train\_pos=2595, test\_pos=731

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=2595, test\_pos=731



📊 Executing Inner Stratified Group Split for K-Fold IDs...



💾 Saving master datasets to disk...

&#x20;  ✅ Saved Training Set: b2\_train\_spatial\_80\_questdb.csv

&#x20;  ✅ Saved Testing Set:  b2\_test\_spatial\_20\_questdb.csv



🏁 Phase B.2 Complete. The Data Engine has secured and saved the stratified 80/20 splits!

🚀 Starting Phase E.2: Data Scarcity Branch (True Locked Holdout Architecture)



📊 Isolating the Baseline Test Set (Extracting B.2 holdout via Basenames)...

📊 Starving the Training Set (Simulating Target 20% Total Data Scarcity)...



🧾 E.2 SPLIT GEOMETRY EXPLAINER

&#x20;  - Baseline outer split realized: Train 78.3% | Test 21.7% of total rows

&#x20;  - Scarcity train is 24.7% of baseline-train rows

&#x20;  - Therefore scarcity train is 19.3% of total rows (target was 20.0%)



&#x20;  - Scarcity Training Set (19.3% actual, \~20.0% target): 371,215 metric rows | 616 Unique File-Release Events

&#x20;  - Locked Testing Set (constant baseline holdout): 417,494 metric rows | 602 Unique File-Release Events

&#x20;  - Scarcity event density: 0.001659 events/row

&#x20;  - Locked-test event density: 0.001442 events/row



🔍 Checking per-rule positive event densities (Rule Viability under Scarcity)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=639, test\_pos=610

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=574, test\_pos=511

&#x20;  ✅ ExcessivePublicCount           : train\_pos=607, test\_pos=585

&#x20;  ✅ NcssCount\_Method               : train\_pos=782, test\_pos=731

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=782, test\_pos=731



📊 Executing Inner Stratified Group Split for E.3 K-Fold IDs...

&#x20;  ✅ Leakage Assertion Passed: Absolute spatial isolation confirmed.



💾 Saving Scarcity Training dataset to disk...

&#x20;  ✅ Saved Scarcity Training Set: e2\_train\_scarcity\_questdb.csv

&#x20;  ✅ Locked Testing Set is preserved at: b2\_test\_spatial\_20\_questdb.csv



🏁 Phase E.2 Complete. The Scarcity Data Engine has secured the true locked splits!

🚀 Starting Phase T.2: Chronological Branch (True Git Time-Series Split)



⚠️ MSR Attrition Note: You targeted \~55 official releases from GitHub.

⚠️ PMD parsed 35 releases. The missing 20 failed upstream static analysis.



⏳ Loading true Git commit timestamps to guarantee time-travel protection...



📊 T.2 Dataset Split Breakdown (50/50):

&#x20;  - Total PMD Releases: 35

&#x20;  - T.2 Training Releases (The Past):   17

&#x20;  - T.2 Testing Releases  (The Future): 18

&#x20;  - ⏱️ TRUE Temporal Boundary Lock: Release 17 (Git Timestamp: 1689092117)



&#x20;  - T.2 Training Set (21.3% actual metric rows): 408636 total rows

&#x20;  - T.2 Testing Set  (78.7% actual metric rows): 1511815 total rows



&#x20;  🔍 Temporal Imbalance Check:

&#x20;     - Past Refactored Rows:   9793

&#x20;     - Future Refactored Rows: 5501



🔍 Checking per-rule positive densities (Past vs Future)...

&#x20;  ✅ NcssCount\_Class                : past\_pos=2316, future\_pos=772 

&#x20;  ✅ CyclomaticComplexity\_Class     : past\_pos=1961, future\_pos=723 

&#x20;  ✅ ExcessivePublicCount           : past\_pos=2112, future\_pos=758 

&#x20;  ✅ NcssCount\_Method               : past\_pos=1702, future\_pos=1624

&#x20;  ✅ CyclomaticComplexity\_Method    : past\_pos=1702, future\_pos=1624



💾 Saved Temporal Training Set: t2\_train\_chrono\_50\_questdb.csv

💾 Saved Temporal Testing Set: t2\_test\_chrono\_50\_questdb.csv

&#x20;  ✅ Robust chronological splitting validated successfully!

🏁 Phase T.2 Complete. The timeline has been permanently split (No spatial shuffling applied).

🔎 Running T.2 True Chronological Sanity Check...

&#x20;  ✅ Split matrices successfully loaded from disk (No corruption).

&#x20;  ✅ Release counts verified (Past/Train: 17, Future/Test: 18).

&#x20;  ✅ Zero data leakage detected (Past and Future releases are strictly mutually exclusive).

&#x20;  ✅ Chronological boundary mathematically verified via Git History (Max Past TS: 1689092117 < Min Future TS: 1691057644).



📁 Step 4: System Evolution \& Temporal Overlap (T.2 Split)

&#x20;     - Canonical identities in the Past (Train):            2840

&#x20;     - Canonical identities in the Future (Test):           3517

&#x20;     - Identities persisting across the split (Overlap):    1979

&#x20;     - Identities retired/deleted before Future phase:      861

&#x20;     - New identities introduced in Future phase:           1538

&#x20;     🎯 Percentage of Future Architecture seen in the Past: 56.27%



🏁 Audit Complete. The T.2 Chronological Split is academically secure and verified.

🚀 Starting Phase B.3: Multi-Percentile Sweep Analysis (Optimized \& Guarded)

📊 Loaded Training Set with 3505 canonical entities ready for K-Fold Calibration.



📈 Executing 5-Fold Cross-Validation Tournament...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...

&#x20;  ⚙️ Processing Fold 4 as Validation...

&#x20;  ⚙️ Processing Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                        | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.03|R:0.99|F1:0.06) | 4 (P:0.03|R:0.86|F1:0.05) | 8 (P:0.03|R:0.77|F1:0.06) | 12 (P:0.03|R:0.67|F1:0.06) | 15 (P:0.03|R:0.57|F1:0.06) | 21 (P:0.03|R:0.46|F1:0.06) | 31 (P:0.03|R:0.36|F1:0.06) | 51 (P:0.03|R:0.25|F1:0.06) | 88 (P:0.03|R:0.15|F1:0.06) | 125 (P:0.04|R:0.10|F1:0.05) | 260 (P:0.05|R:0.05|F1:0.05) |

| CyclomaticComplexity\_Class  | 1 (P:0.03|R:1.00|F1:0.06) | 2 (P:0.03|R:0.93|F1:0.06) | 3 (P:0.03|R:0.78|F1:0.06) | 4 (P:0.03|R:0.68|F1:0.06)  | 5 (P:0.03|R:0.58|F1:0.05)  | 7 (P:0.03|R:0.48|F1:0.06)  | 10 (P:0.03|R:0.37|F1:0.06) | 16 (P:0.03|R:0.26|F1:0.06) | 28 (P:0.03|R:0.16|F1:0.06) | 39 (P:0.03|R:0.11|F1:0.05)  | 82 (P:0.05|R:0.05|F1:0.05)  |

| ExcessivePublicCount        | 1 (P:0.03|R:1.00|F1:0.06) | 2 (P:0.03|R:0.88|F1:0.05) | 2 (P:0.03|R:0.86|F1:0.05) | 3 (P:0.03|R:0.70|F1:0.05)  | 3 (P:0.03|R:0.67|F1:0.05)  | 4 (P:0.03|R:0.50|F1:0.05)  | 5 (P:0.03|R:0.41|F1:0.06)  | 7 (P:0.03|R:0.28|F1:0.06)  | 11 (P:0.03|R:0.15|F1:0.05) | 15 (P:0.03|R:0.11|F1:0.05)  | 21 (P:0.03|R:0.05|F1:0.04)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         |

| NcssCount\_Method            | 2 (P:0.00|R:0.97|F1:0.01) | 2 (P:0.00|R:0.97|F1:0.01) | 3 (P:0.01|R:0.81|F1:0.02) | 4 (P:0.01|R:0.68|F1:0.02)  | 5 (P:0.01|R:0.59|F1:0.02)  | 7 (P:0.01|R:0.47|F1:0.02)  | 10 (P:0.01|R:0.36|F1:0.03) | 15 (P:0.02|R:0.26|F1:0.03) | 25 (P:0.02|R:0.16|F1:0.04) | 34 (P:0.02|R:0.10|F1:0.04)  | 55 (P:0.02|R:0.05|F1:0.03)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01) | 1 (P:0.00|R:1.00|F1:0.01)  | 1 (P:0.00|R:1.00|F1:0.01)  | 2 (P:0.01|R:0.52|F1:0.01)  | 3 (P:0.01|R:0.40|F1:0.02)  | 4 (P:0.01|R:0.29|F1:0.03)  | 8 (P:0.02|R:0.16|F1:0.03)  | 11 (P:0.02|R:0.11|F1:0.03)  | 19 (P:0.02|R:0.05|F1:0.03)  |

| TooManyMethods              | 1 (P:0.02|R:0.98|F1:0.05) | 2 (P:0.03|R:0.90|F1:0.05) | 3 (P:0.02|R:0.81|F1:0.05) | 5 (P:0.03|R:0.67|F1:0.05)  | 5 (P:0.03|R:0.67|F1:0.05)  | 6 (P:0.02|R:0.52|F1:0.05)  | 9 (P:0.03|R:0.36|F1:0.05)  | 12 (P:0.03|R:0.27|F1:0.05) | 18 (P:0.03|R:0.16|F1:0.05) | 24 (P:0.03|R:0.10|F1:0.04)  | 42 (P:0.04|R:0.05|F1:0.04)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                          | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.03|R:0.99|F0.5:0.04) | 4 (P:0.03|R:0.86|F0.5:0.04) | 8 (P:0.03|R:0.77|F0.5:0.04) | 12 (P:0.03|R:0.67|F0.5:0.04) | 15 (P:0.03|R:0.57|F0.5:0.04) | 21 (P:0.03|R:0.46|F0.5:0.04) | 31 (P:0.03|R:0.36|F0.5:0.04) | 51 (P:0.03|R:0.25|F0.5:0.04) | 88 (P:0.03|R:0.15|F0.5:0.04) | 125 (P:0.04|R:0.10|F0.5:0.04) | 260 (P:0.05|R:0.05|F0.5:0.05) |

| CyclomaticComplexity\_Class  | 1 (P:0.03|R:1.00|F0.5:0.04) | 2 (P:0.03|R:0.93|F0.5:0.04) | 3 (P:0.03|R:0.78|F0.5:0.04) | 4 (P:0.03|R:0.68|F0.5:0.04)  | 5 (P:0.03|R:0.58|F0.5:0.04)  | 7 (P:0.03|R:0.48|F0.5:0.04)  | 10 (P:0.03|R:0.37|F0.5:0.04) | 16 (P:0.03|R:0.26|F0.5:0.04) | 28 (P:0.03|R:0.16|F0.5:0.04) | 39 (P:0.03|R:0.11|F0.5:0.04)  | 82 (P:0.05|R:0.05|F0.5:0.05)  |

| ExcessivePublicCount        | 1 (P:0.03|R:1.00|F0.5:0.04) | 2 (P:0.03|R:0.88|F0.5:0.03) | 2 (P:0.03|R:0.86|F0.5:0.03) | 3 (P:0.03|R:0.70|F0.5:0.03)  | 3 (P:0.03|R:0.67|F0.5:0.04)  | 4 (P:0.03|R:0.50|F0.5:0.04)  | 5 (P:0.03|R:0.41|F0.5:0.04)  | 7 (P:0.03|R:0.28|F0.5:0.04)  | 11 (P:0.03|R:0.15|F0.5:0.04) | 15 (P:0.03|R:0.11|F0.5:0.04)  | 21 (P:0.03|R:0.05|F0.5:0.03)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           |

| NcssCount\_Method            | 2 (P:0.00|R:0.97|F0.5:0.01) | 2 (P:0.00|R:0.97|F0.5:0.01) | 3 (P:0.01|R:0.81|F0.5:0.01) | 4 (P:0.01|R:0.68|F0.5:0.01)  | 5 (P:0.01|R:0.59|F0.5:0.01)  | 7 (P:0.01|R:0.47|F0.5:0.01)  | 10 (P:0.01|R:0.36|F0.5:0.02) | 15 (P:0.02|R:0.26|F0.5:0.02) | 25 (P:0.02|R:0.16|F0.5:0.03) | 34 (P:0.02|R:0.10|F0.5:0.03)  | 55 (P:0.02|R:0.05|F0.5:0.03)  |

| CyclomaticComplexity\_Method | 1 (P:0.00|R:1.00|F0.5:0.01) | 1 (P:0.00|R:1.00|F0.5:0.01) | 1 (P:0.00|R:1.00|F0.5:0.01) | 1 (P:0.00|R:1.00|F0.5:0.01)  | 1 (P:0.00|R:1.00|F0.5:0.01)  | 2 (P:0.01|R:0.52|F0.5:0.01)  | 3 (P:0.01|R:0.40|F0.5:0.01)  | 4 (P:0.01|R:0.29|F0.5:0.02)  | 8 (P:0.02|R:0.16|F0.5:0.02)  | 11 (P:0.02|R:0.11|F0.5:0.02)  | 19 (P:0.02|R:0.05|F0.5:0.03)  |

| TooManyMethods              | 1 (P:0.02|R:0.98|F0.5:0.03) | 2 (P:0.03|R:0.90|F0.5:0.03) | 3 (P:0.02|R:0.81|F0.5:0.03) | 5 (P:0.03|R:0.67|F0.5:0.03)  | 5 (P:0.03|R:0.67|F0.5:0.03)  | 6 (P:0.02|R:0.52|F0.5:0.03)  | 9 (P:0.03|R:0.36|F0.5:0.03)  | 12 (P:0.03|R:0.27|F0.5:0.03) | 18 (P:0.03|R:0.16|F0.5:0.03) | 24 (P:0.03|R:0.10|F0.5:0.03)  | 42 (P:0.04|R:0.05|F0.5:0.04)  |



🏆 F1-Optimized Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 5th          |                 2 |               260 |         0.0574 |             1    |      0.0296 |            5 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 65th         |                10 |                82 |         0.0588 |             1.09 |      0.0293 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 65th         |                 5 |                15 |         0.056  |             1.06 |      0.0285 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | False              | False         | 85th         |                25 |                55 |         0.0395 |             5.52 |      0.0041 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                11 |                19 |         0.0325 |             4.76 |      0.0041 |            5 |

| TooManyMethods              | True         | False              | False         | 35th         |                 5 |                42 |         0.0529 |             1.12 |      0.0246 |            5 |



🎯 Precision-Optimized (F0.5) Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 95th         |               260 |               260 |           0.0464 |             1.55 |      0.0296 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 95th         |                82 |                82 |           0.0465 |             1.58 |      0.0293 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 75th         |                 7 |                21 |           0.0376 |             1.09 |      0.0285 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                55 |                55 |           0.0276 |             6.08 |      0.0041 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                19 |                19 |           0.0253 |             5.51 |      0.0041 |            5 |

| TooManyMethods              | True         | True               | False         | 95th         |                42 |                42 |           0.0378 |             1.44 |      0.0246 |            5 |



💾 Saved Dual Baseline locked thresholds to disk: /content/b3\_inflection\_thresholds\_questdb\_locked.json

🏁 Phase B.3 Complete.

🚀 Starting Phase E.3: Multi-Percentile Sweep Analysis (Scarcity Edition)

📊 Loaded Scarcity Training Set (20%) with 874 canonical entities.



📈 Executing 3-Fold Cross-Validation Tournament (Scarcity)...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                        | 90th                        | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|:----------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.03|R:0.99|F1:0.06) | 5 (P:0.03|R:0.85|F1:0.06) | 8 (P:0.03|R:0.76|F1:0.06) | 13 (P:0.03|R:0.66|F1:0.06) | 16 (P:0.03|R:0.55|F1:0.06) | 24 (P:0.03|R:0.45|F1:0.06) | 35 (P:0.03|R:0.35|F1:0.06) | 64 (P:0.04|R:0.26|F1:0.07) | 111 (P:0.05|R:0.15|F1:0.07) | 172 (P:0.05|R:0.10|F1:0.07) | 303 (P:0.07|R:0.05|F1:0.06) |

| CyclomaticComplexity\_Class  | 1 (P:0.03|R:1.00|F1:0.06) | 2 (P:0.03|R:0.93|F1:0.06) | 3 (P:0.03|R:0.80|F1:0.06) | 3 (P:0.03|R:0.73|F1:0.06)  | 5 (P:0.03|R:0.57|F1:0.06)  | 7 (P:0.03|R:0.47|F1:0.06)  | 11 (P:0.04|R:0.36|F1:0.06) | 18 (P:0.04|R:0.27|F1:0.07) | 36 (P:0.04|R:0.15|F1:0.07)  | 53 (P:0.05|R:0.10|F1:0.06)  | 94 (P:0.06|R:0.05|F1:0.05)  |

| ExcessivePublicCount        | 1 (P:0.03|R:1.00|F1:0.06) | 2 (P:0.03|R:0.87|F1:0.06) | 2 (P:0.03|R:0.87|F1:0.06) | 3 (P:0.03|R:0.66|F1:0.06)  | 3 (P:0.03|R:0.66|F1:0.06)  | 4 (P:0.03|R:0.50|F1:0.06)  | 5 (P:0.03|R:0.36|F1:0.06)  | 7 (P:0.03|R:0.27|F1:0.06)  | 10 (P:0.03|R:0.16|F1:0.05)  | 15 (P:0.03|R:0.10|F1:0.05)  | 21 (P:0.03|R:0.05|F1:0.04)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.97|F1:0.01) | 2 (P:0.01|R:0.97|F1:0.01) | 3 (P:0.01|R:0.82|F1:0.02) | 4 (P:0.01|R:0.69|F1:0.02)  | 5 (P:0.01|R:0.58|F1:0.02)  | 8 (P:0.01|R:0.45|F1:0.03)  | 13 (P:0.02|R:0.35|F1:0.03) | 17 (P:0.02|R:0.27|F1:0.04) | 26 (P:0.03|R:0.16|F1:0.05)  | 32 (P:0.03|R:0.11|F1:0.04)  | 50 (P:0.02|R:0.06|F1:0.03)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01)  | 2 (P:0.01|R:0.65|F1:0.01)  | 2 (P:0.01|R:0.52|F1:0.02)  | 3 (P:0.01|R:0.40|F1:0.02)  | 5 (P:0.02|R:0.26|F1:0.03)  | 8 (P:0.02|R:0.17|F1:0.04)   | 10 (P:0.02|R:0.11|F1:0.04)  | 16 (P:0.02|R:0.06|F1:0.03)  |

| TooManyMethods              | 1 (P:0.03|R:0.98|F1:0.05) | 2 (P:0.03|R:0.89|F1:0.05) | 4 (P:0.03|R:0.77|F1:0.05) | 5 (P:0.03|R:0.70|F1:0.05)  | 6 (P:0.03|R:0.59|F1:0.05)  | 8 (P:0.03|R:0.46|F1:0.05)  | 11 (P:0.03|R:0.35|F1:0.06) | 15 (P:0.04|R:0.26|F1:0.06) | 21 (P:0.04|R:0.16|F1:0.06)  | 27 (P:0.04|R:0.10|F1:0.06)  | 43 (P:0.04|R:0.06|F1:0.05)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                          | 90th                          | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|:------------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.03|R:0.99|F0.5:0.04) | 5 (P:0.03|R:0.85|F0.5:0.04) | 8 (P:0.03|R:0.76|F0.5:0.04) | 13 (P:0.03|R:0.66|F0.5:0.04) | 16 (P:0.03|R:0.55|F0.5:0.04) | 24 (P:0.03|R:0.45|F0.5:0.04) | 35 (P:0.03|R:0.35|F0.5:0.04) | 64 (P:0.04|R:0.26|F0.5:0.05) | 111 (P:0.05|R:0.15|F0.5:0.05) | 172 (P:0.05|R:0.10|F0.5:0.06) | 303 (P:0.07|R:0.05|F0.5:0.06) |

| CyclomaticComplexity\_Class  | 1 (P:0.03|R:1.00|F0.5:0.04) | 2 (P:0.03|R:0.93|F0.5:0.04) | 3 (P:0.03|R:0.80|F0.5:0.04) | 3 (P:0.03|R:0.73|F0.5:0.04)  | 5 (P:0.03|R:0.57|F0.5:0.04)  | 7 (P:0.03|R:0.47|F0.5:0.04)  | 11 (P:0.04|R:0.36|F0.5:0.04) | 18 (P:0.04|R:0.27|F0.5:0.05) | 36 (P:0.04|R:0.15|F0.5:0.05)  | 53 (P:0.05|R:0.10|F0.5:0.05)  | 94 (P:0.06|R:0.05|F0.5:0.05)  |

| ExcessivePublicCount        | 1 (P:0.03|R:1.00|F0.5:0.04) | 2 (P:0.03|R:0.87|F0.5:0.04) | 2 (P:0.03|R:0.87|F0.5:0.04) | 3 (P:0.03|R:0.66|F0.5:0.04)  | 3 (P:0.03|R:0.66|F0.5:0.04)  | 4 (P:0.03|R:0.50|F0.5:0.04)  | 5 (P:0.03|R:0.36|F0.5:0.04)  | 7 (P:0.03|R:0.27|F0.5:0.04)  | 10 (P:0.03|R:0.16|F0.5:0.04)  | 15 (P:0.03|R:0.10|F0.5:0.04)  | 21 (P:0.03|R:0.05|F0.5:0.03)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.97|F0.5:0.01) | 2 (P:0.01|R:0.97|F0.5:0.01) | 3 (P:0.01|R:0.82|F0.5:0.01) | 4 (P:0.01|R:0.69|F0.5:0.01)  | 5 (P:0.01|R:0.58|F0.5:0.01)  | 8 (P:0.01|R:0.45|F0.5:0.02)  | 13 (P:0.02|R:0.35|F0.5:0.02) | 17 (P:0.02|R:0.27|F0.5:0.03) | 26 (P:0.03|R:0.16|F0.5:0.03)  | 32 (P:0.03|R:0.11|F0.5:0.03)  | 50 (P:0.02|R:0.06|F0.5:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01)  | 2 (P:0.01|R:0.65|F0.5:0.01)  | 2 (P:0.01|R:0.52|F0.5:0.01)  | 3 (P:0.01|R:0.40|F0.5:0.01)  | 5 (P:0.02|R:0.26|F0.5:0.02)  | 8 (P:0.02|R:0.17|F0.5:0.03)   | 10 (P:0.02|R:0.11|F0.5:0.03)  | 16 (P:0.02|R:0.06|F0.5:0.02)  |

| TooManyMethods              | 1 (P:0.03|R:0.98|F0.5:0.03) | 2 (P:0.03|R:0.89|F0.5:0.03) | 4 (P:0.03|R:0.77|F0.5:0.03) | 5 (P:0.03|R:0.70|F0.5:0.03)  | 6 (P:0.03|R:0.59|F0.5:0.03)  | 8 (P:0.03|R:0.46|F0.5:0.04)  | 11 (P:0.03|R:0.35|F0.5:0.04) | 15 (P:0.04|R:0.26|F0.5:0.04) | 21 (P:0.04|R:0.16|F0.5:0.04)  | 27 (P:0.04|R:0.10|F0.5:0.05)  | 43 (P:0.04|R:0.06|F0.5:0.05)  |



🏆 F1-Optimized Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 85th         |               111 |               172 |         0.0702 |             1.53 |      0.03   |            3 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 75th         |                18 |                53 |         0.0678 |             1.31 |      0.0299 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 75th         |                 7 |                 7 |         0.0603 |             1.16 |      0.0294 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                26 |                32 |         0.0456 |             5.43 |      0.005  |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 85th         |                 8 |                16 |         0.0383 |             4.39 |      0.005  |            3 |

| TooManyMethods              | True         | False              | False         | 75th         |                15 |                43 |         0.0643 |             1.46 |      0.0251 |            3 |



🎯 Precision-Optimized (F0.5) Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 95th         |               303 |               303 |           0.0599 |             2.17 |      0.03   |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 95th         |                94 |                94 |           0.055  |             1.99 |      0.0299 |            3 |

| ExcessivePublicCount        | True         | False              | False         | 75th         |                 7 |                21 |           0.0412 |             1.16 |      0.0294 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                26 |                50 |           0.0325 |             5.43 |      0.005  |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 85th         |                 8 |                16 |           0.0266 |             4.39 |      0.005  |            3 |

| TooManyMethods              | True         | True               | False         | 95th         |                43 |                43 |           0.0456 |             1.73 |      0.0251 |            3 |



💾 Saved Dual Baseline locked thresholds to disk: /content/e3\_inflection\_thresholds\_questdb\_scarcity.json

🏁 Phase E.3 Complete.

🚀 Starting Phase T.3: Chronological K-Fold Calibration Engine

📊 Loaded Temporal Training Set (The Past) with 2840 canonical entities.



📈 Executing 5-Fold Cross-Validation Tournament (Chronological; n\_splits=5)...

&#x20;  ⚙️ Processing Temporal Fold 1 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 2 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 3 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 4 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.05|R:1.00|F1:0.09) | 3 (P:0.05|R:0.88|F1:0.09) | 6 (P:0.05|R:0.83|F1:0.09) | 9 (P:0.05|R:0.74|F1:0.09) | 13 (P:0.05|R:0.60|F1:0.08) | 17 (P:0.05|R:0.50|F1:0.08) | 23 (P:0.05|R:0.41|F1:0.09) | 36 (P:0.05|R:0.32|F1:0.09) | 63 (P:0.07|R:0.22|F1:0.09) | 96 (P:0.07|R:0.16|F1:0.09) | 190 (P:0.09|R:0.08|F1:0.07) |

| CyclomaticComplexity\_Class  | 1 (P:0.05|R:1.00|F1:0.09) | 2 (P:0.05|R:0.96|F1:0.09) | 2 (P:0.05|R:0.87|F1:0.09) | 3 (P:0.05|R:0.75|F1:0.08) | 5 (P:0.05|R:0.54|F1:0.08)  | 7 (P:0.05|R:0.47|F1:0.08)  | 9 (P:0.05|R:0.39|F1:0.09)  | 13 (P:0.06|R:0.28|F1:0.09) | 26 (P:0.06|R:0.16|F1:0.08) | 35 (P:0.06|R:0.13|F1:0.07) | 64 (P:0.09|R:0.08|F1:0.07)  |

| ExcessivePublicCount        | 1 (P:0.05|R:1.00|F1:0.09) | 1 (P:0.05|R:1.00|F1:0.09) | 2 (P:0.05|R:0.84|F1:0.09) | 2 (P:0.05|R:0.84|F1:0.09) | 3 (P:0.05|R:0.62|F1:0.09)  | 3 (P:0.05|R:0.62|F1:0.09)  | 4 (P:0.05|R:0.39|F1:0.08)  | 6 (P:0.05|R:0.27|F1:0.08)  | 9 (P:0.05|R:0.16|F1:0.07)  | 14 (P:0.06|R:0.11|F1:0.07) | 20 (P:0.05|R:0.06|F1:0.05)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.98|F1:0.02) | 2 (P:0.01|R:0.96|F1:0.02) | 3 (P:0.02|R:0.84|F1:0.03) | 3 (P:0.02|R:0.83|F1:0.04) | 4 (P:0.02|R:0.67|F1:0.04)  | 5 (P:0.02|R:0.55|F1:0.04)  | 8 (P:0.03|R:0.45|F1:0.05)  | 12 (P:0.03|R:0.34|F1:0.06) | 20 (P:0.04|R:0.20|F1:0.06) | 28 (P:0.05|R:0.15|F1:0.07) | 44 (P:0.05|R:0.08|F1:0.06)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:0.88|F1:0.02)  | 1 (P:0.01|R:0.73|F1:0.02)  | 2 (P:0.02|R:0.48|F1:0.03)  | 4 (P:0.03|R:0.35|F1:0.05)  | 7 (P:0.04|R:0.21|F1:0.05)  | 9 (P:0.04|R:0.14|F1:0.06)  | 15 (P:0.04|R:0.07|F1:0.05)  |

| TooManyMethods              | 1 (P:0.03|R:0.99|F1:0.06) | 1 (P:0.03|R:0.99|F1:0.06) | 2 (P:0.03|R:0.94|F1:0.07) | 3 (P:0.04|R:0.90|F1:0.07) | 4 (P:0.04|R:0.87|F1:0.08)  | 5 (P:0.04|R:0.83|F1:0.08)  | 6 (P:0.04|R:0.54|F1:0.07)  | 9 (P:0.04|R:0.40|F1:0.07)  | 16 (P:0.05|R:0.21|F1:0.07) | 19 (P:0.05|R:0.18|F1:0.07) | 28 (P:0.06|R:0.14|F1:0.08)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.05|R:1.00|F0.5:0.06) | 3 (P:0.05|R:0.88|F0.5:0.06) | 6 (P:0.05|R:0.83|F0.5:0.06) | 9 (P:0.05|R:0.74|F0.5:0.06) | 13 (P:0.05|R:0.60|F0.5:0.06) | 17 (P:0.05|R:0.50|F0.5:0.06) | 23 (P:0.05|R:0.41|F0.5:0.06) | 36 (P:0.05|R:0.32|F0.5:0.06) | 63 (P:0.07|R:0.22|F0.5:0.07) | 96 (P:0.07|R:0.16|F0.5:0.08) | 190 (P:0.09|R:0.08|F0.5:0.08) |

| CyclomaticComplexity\_Class  | 1 (P:0.05|R:1.00|F0.5:0.06) | 2 (P:0.05|R:0.96|F0.5:0.06) | 2 (P:0.05|R:0.87|F0.5:0.06) | 3 (P:0.05|R:0.75|F0.5:0.06) | 5 (P:0.05|R:0.54|F0.5:0.06)  | 7 (P:0.05|R:0.47|F0.5:0.06)  | 9 (P:0.05|R:0.39|F0.5:0.06)  | 13 (P:0.06|R:0.28|F0.5:0.06) | 26 (P:0.06|R:0.16|F0.5:0.06) | 35 (P:0.06|R:0.13|F0.5:0.07) | 64 (P:0.09|R:0.08|F0.5:0.08)  |

| ExcessivePublicCount        | 1 (P:0.05|R:1.00|F0.5:0.06) | 1 (P:0.05|R:1.00|F0.5:0.06) | 2 (P:0.05|R:0.84|F0.5:0.06) | 2 (P:0.05|R:0.84|F0.5:0.06) | 3 (P:0.05|R:0.62|F0.5:0.06)  | 3 (P:0.05|R:0.62|F0.5:0.06)  | 4 (P:0.05|R:0.39|F0.5:0.06)  | 6 (P:0.05|R:0.27|F0.5:0.06)  | 9 (P:0.05|R:0.16|F0.5:0.06)  | 14 (P:0.06|R:0.11|F0.5:0.06) | 20 (P:0.05|R:0.06|F0.5:0.05)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.98|F0.5:0.01) | 2 (P:0.01|R:0.96|F0.5:0.02) | 3 (P:0.02|R:0.84|F0.5:0.02) | 3 (P:0.02|R:0.83|F0.5:0.03) | 4 (P:0.02|R:0.67|F0.5:0.03)  | 5 (P:0.02|R:0.55|F0.5:0.03)  | 8 (P:0.03|R:0.45|F0.5:0.03)  | 12 (P:0.03|R:0.34|F0.5:0.04) | 20 (P:0.04|R:0.20|F0.5:0.05) | 28 (P:0.05|R:0.15|F0.5:0.05) | 44 (P:0.05|R:0.08|F0.5:0.05)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:0.88|F0.5:0.01)  | 1 (P:0.01|R:0.73|F0.5:0.01)  | 2 (P:0.02|R:0.48|F0.5:0.02)  | 4 (P:0.03|R:0.35|F0.5:0.03)  | 7 (P:0.04|R:0.21|F0.5:0.04)  | 9 (P:0.04|R:0.14|F0.5:0.05)  | 15 (P:0.04|R:0.07|F0.5:0.04)  |

| TooManyMethods              | 1 (P:0.03|R:0.99|F0.5:0.04) | 1 (P:0.03|R:0.99|F0.5:0.04) | 2 (P:0.03|R:0.94|F0.5:0.04) | 3 (P:0.04|R:0.90|F0.5:0.05) | 4 (P:0.04|R:0.87|F0.5:0.05)  | 5 (P:0.04|R:0.83|F0.5:0.05)  | 6 (P:0.04|R:0.54|F0.5:0.05)  | 9 (P:0.04|R:0.40|F0.5:0.05)  | 16 (P:0.05|R:0.21|F0.5:0.05) | 19 (P:0.05|R:0.18|F0.5:0.06) | 28 (P:0.06|R:0.14|F0.5:0.07)  |



🏆 F1-Optimized Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 85th         |                63 |                96 |         0.0937 |             1.38 |      0.0472 |            5 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 15th         |                 2 |                64 |         0.0926 |             1.04 |      0.0477 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 5th          |                 1 |                 6 |         0.0914 |             1    |      0.0489 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 90th         |                28 |                28 |         0.0669 |             4.37 |      0.0112 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                 9 |                15 |         0.0575 |             3.72 |      0.0112 |            5 |

| TooManyMethods              | True         | False              | False         | 55th         |                 5 |                28 |         0.0831 |             1.43 |      0.0313 |            5 |



🎯 Precision-Optimized (F0.5) Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 90th         |                96 |               190 |           0.0792 |             1.56 |      0.0472 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 95th         |                64 |                64 |           0.0802 |             1.88 |      0.0477 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 45th         |                 3 |                20 |           0.0611 |             1.03 |      0.0489 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 90th         |                28 |                44 |           0.054  |             4.37 |      0.0112 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                 9 |                15 |           0.0463 |             3.72 |      0.0112 |            5 |

| TooManyMethods              | True         | True               | False         | 95th         |                28 |                28 |           0.0679 |             2.04 |      0.0313 |            5 |



💾 Saved Dual Chronological locked thresholds to disk: t3\_inflection\_thresholds\_questdb\_chrono\_locked.json

🏁 Phase T.3 Complete.

🚀 Starting Phase B.4: Blind Imminent Predictability Evaluation (Trust-Aware Edition)

✅ Thresholds strictly synchronized from disk.

📊 Final Exam Loaded: Evaluating 873 completely unseen canonical entities.



&#x20;   MASTER BLIND EVALUATION MATRIX (Test Set: 20%)



📊 TABLE 1: F1-Optimized Thresholds (Evaluated on Blind F1 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       610 |         1500 |             18 | ⚠️ 1500 (Fallback) |     0.057 |     0.015 |    0.015 |      0.055 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       511 |           80 |              6 | ⚠️ 80 (Fallback)   |     0.059 |     0.033 |    0.033 |      0.056 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       585 |           45 |              4 | ⚠️ 45 (Fallback)   |     0.056 |     0.016 |    0.016 |      0.054 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       731 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.04  |     0.04  |    0.04  |      0.009 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       731 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.033 |     0.044 |    0.044 |      0.008 | ➖ Uncalibrated Noise |

| TooManyMethods              |       328 |           10 |              6 | ⚠️ 10 (Fallback)   |     0.053 |     0.043 |    0.043 |      0.046 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized Thresholds (Evaluated on Blind F0.5 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       610 |         1500 |             18 | ⚠️ 1500 (Fallback) |      0.046 |      0.029 |     0.029 |       0.036 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       511 |           80 |              6 | ⚠️ 80 (Fallback)   |      0.046 |      0.032 |     0.032 |       0.036 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       585 |           45 |              4 | ⚠️ 45 (Fallback)   |      0.038 |      0.017 |     0.017 |       0.035 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       731 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.028 |      0.035 |     0.035 |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       731 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.025 |      0.031 |     0.031 |       0.005 | ➖ Uncalibrated Noise |

| TooManyMethods              |       328 |           10 |              6 | ⚠️ 10 (Fallback)   |      0.038 |      0.028 |     0.028 |       0.03  | ➖ Uncalibrated Noise |



💾 Saved detailed evaluation matrix to: b4\_evaluation\_matrix\_questdb.csv



=================================================================

🏆 FINAL BASELINE EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  Test Entities (Strictly Blind):   873

\-----------------------------------------------------------------

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F1 averages.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F0.5 averages.

=================================================================

🏁 Phase B.4 Complete. The threshold hypotheses have been blindly evaluated.

🚀 Starting Phase E.4: Scarcity Predictability Evaluation (Trust-Aware)

📊 Final Scarcity Exam Loaded: Evaluating 873 completely unseen canonical entities.



📊 TABLE 1: F1-Optimized Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       610 |         1500 |             18 | ⚠️ 1500 (Fallback) |     0.07  |     0.015 |    0.015 |      0.055 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       511 |           80 |              5 | ⚠️ 80 (Fallback)   |     0.068 |     0.033 |    0.033 |      0.051 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       585 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.06  |     0.016 |    0.016 |      0.054 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       731 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.046 |     0.04  |    0.04  |      0.009 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       731 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.038 |     0.044 |    0.044 |      0.008 | ➖ Uncalibrated Noise |

| TooManyMethods              |       328 |           10 |              6 | ⚠️ 10 (Fallback)   |     0.064 |     0.043 |    0.043 |      0.046 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       610 |         1500 |             18 | ⚠️ 1500 (Fallback) |      0.06  |      0.029 |     0.029 |       0.036 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       511 |           80 |              5 | ⚠️ 80 (Fallback)   |      0.055 |      0.032 |     0.032 |       0.033 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       585 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.041 |      0.017 |     0.017 |       0.035 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       731 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.033 |      0.035 |     0.035 |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       731 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.027 |      0.031 |     0.031 |       0.005 | ➖ Uncalibrated Noise |

| TooManyMethods              |       328 |           10 |              6 | ⚠️ 10 (Fallback)   |      0.046 |      0.028 |     0.028 |       0.03  | ➖ Uncalibrated Noise |



=================================================================

🏆 SCARCITY EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

=================================================================



💾 Saved scarcity evaluation matrix to: e4\_evaluation\_matrix\_scarcity\_questdb.csv

🏁 Phase E.4 Complete. Scarcity evaluation finalized.

🚀 Starting Phase T.4: Chronological Predictability Evaluation (Trust-Aware)

📊 Final Chronological Exam Loaded: Evaluating against Future Timeline.



📊 TABLE 1: F1-Optimized Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       772 |         1500 |             15 | ⚠️ 1500 (Fallback) |     0.094 |     0.012 |    0.012 |      0.025 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       723 |           80 |              5 | ⚠️ 80 (Fallback)   |     0.093 |     0.028 |    0.028 |      0.026 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       758 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.091 |     0.017 |    0.017 |      0.024 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |      1624 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.067 |     0.031 |    0.031 |      0.005 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |      1624 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.058 |     0.025 |    0.025 |      0.005 | ➖ Uncalibrated Noise |

| TooManyMethods              |       349 |           10 |              5 | ⚠️ 10 (Fallback)   |     0.083 |     0.024 |    0.024 |      0.021 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       772 |         1500 |             15 | ⚠️ 1500 (Fallback) |      0.079 |      0.019 |     0.019 |       0.016 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       723 |           80 |              5 | ⚠️ 80 (Fallback)   |      0.08  |      0.021 |     0.021 |       0.016 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       758 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.061 |      0.015 |     0.015 |       0.015 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |      1624 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.054 |      0.024 |     0.024 |       0.003 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |      1624 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.046 |      0.017 |     0.017 |       0.003 | ➖ Uncalibrated Noise |

| TooManyMethods              |       349 |           10 |              5 | ⚠️ 10 (Fallback)   |      0.068 |      0.015 |     0.015 |       0.013 | ➖ Uncalibrated Noise |



=================================================================

🏆 CHRONOLOGICAL EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

=================================================================



💾 Saved chronological evaluation matrix to: t4\_evaluation\_matrix\_chrono\_questdb.csv

🏁 Phase T.4 Complete. Chronological evaluation finalized.



=====================================================================================

🚀 INITIATING PHASE 6: MASTER CROSS-REGIME DISCRIMINATION DIAGNOSTIC

=====================================================================================



================ DISCRIMINATION BY SOURCE × RULE ================

AUC-PR \~ base\_rate  ⇒  lift \~ 1.0  ⇒  metric ranks refactoring at chance.



| Source                   | Rule                        |      n |   n\_pos |   base\_rate |   auc\_pr |   lift | flag         |

|:-------------------------|:----------------------------|-------:|--------:|------------:|---------:|-------:|:-------------|

| Pooled/all               | NcssCount\_Class             | 105412 |    3088 |      0.0293 |   0.0316 |   1.08 | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Class  |  93059 |    2684 |      0.0288 |   0.0313 |   1.09 | rare (<5%)   |

| Pooled/all               | ExcessivePublicCount        | 101196 |    2870 |      0.0284 |   0.0291 |   1.03 | rare (<5%)   |

| Pooled/all               | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | NcssCount\_Method            | 810392 |    3326 |      0.0041 |   0.0144 |   3.5  | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Method | 810392 |    3326 |      0.0041 |   0.0104 |   2.53 | rare (<5%)   |

| Pooled/all               | TooManyMethods              |  66685 |    1635 |      0.0245 |   0.0277 |   1.13 | rare (<5%)   |

| Spatial/train            | NcssCount\_Class             |  83762 |    2478 |      0.0296 |   0.0319 |   1.08 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Class  |  74120 |    2173 |      0.0293 |   0.0319 |   1.09 | rare (<5%)   |

| Spatial/train            | ExcessivePublicCount        |  80237 |    2285 |      0.0285 |   0.0297 |   1.04 | rare (<5%)   |

| Spatial/train            | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | NcssCount\_Method            | 632419 |    2595 |      0.0041 |   0.0138 |   3.37 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Method | 632419 |    2595 |      0.0041 |   0.0102 |   2.5  | rare (<5%)   |

| Spatial/train            | TooManyMethods              |  53114 |    1307 |      0.0246 |   0.0285 |   1.16 | rare (<5%)   |

| Scarcity/train           | NcssCount\_Class             |  21263 |     639 |      0.0301 |   0.037  |   1.23 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Class  |  19143 |     574 |      0.03   |   0.0367 |   1.22 | rare (<5%)   |

| Scarcity/train           | ExcessivePublicCount        |  20671 |     607 |      0.0294 |   0.0326 |   1.11 | rare (<5%)   |

| Scarcity/train           | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | NcssCount\_Method            | 155069 |     782 |      0.005  |   0.0165 |   3.27 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Method | 155069 |     782 |      0.005  |   0.0114 |   2.26 | rare (<5%)   |

| Scarcity/train           | TooManyMethods              |  13236 |     332 |      0.0251 |   0.0348 |   1.39 | rare (<5%)   |

| Chronological/train      | NcssCount\_Class             |  25335 |    2316 |      0.0914 |   0.096  |   1.05 | ok           |

| Chronological/train      | CyclomaticComplexity\_Class  |  21848 |    1961 |      0.0898 |   0.0962 |   1.07 | ok           |

| Chronological/train      | ExcessivePublicCount        |  23687 |    2112 |      0.0892 |   0.0892 |   1    | ok           |

| Chronological/train      | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | NcssCount\_Method            | 168883 |    1702 |      0.0101 |   0.0282 |   2.8  | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Method | 168883 |    1702 |      0.0101 |   0.0202 |   2.01 | rare (<5%)   |

| Chronological/train      | TooManyMethods              |  16684 |    1286 |      0.0771 |   0.0848 |   1.1  | ok           |

| Spatial/Scarcity/holdout | NcssCount\_Class             |  21650 |     610 |      0.0282 |   0.0308 |   1.09 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Class  |  18939 |     511 |      0.027  |   0.0293 |   1.08 | rare (<5%)   |

| Spatial/Scarcity/holdout | ExcessivePublicCount        |  20959 |     585 |      0.0279 |   0.0279 |   1    | rare (<5%)   |

| Spatial/Scarcity/holdout | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | NcssCount\_Method            | 177973 |     731 |      0.0041 |   0.0165 |   4.03 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Method | 177973 |     731 |      0.0041 |   0.0114 |   2.78 | rare (<5%)   |

| Spatial/Scarcity/holdout | TooManyMethods              |  13571 |     328 |      0.0242 |   0.0264 |   1.09 | rare (<5%)   |

| Chronological/holdout    | NcssCount\_Class             |  80077 |     772 |      0.0096 |   0.0155 |   1.61 | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Class  |  71211 |     723 |      0.0102 |   0.0145 |   1.43 | rare (<5%)   |

| Chronological/holdout    | ExcessivePublicCount        |  77509 |     758 |      0.0098 |   0.0145 |   1.48 | rare (<5%)   |

| Chronological/holdout    | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | NcssCount\_Method            | 641509 |    1624 |      0.0025 |   0.0113 |   4.46 | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Method | 641509 |    1624 |      0.0025 |   0.0086 |   3.38 | rare (<5%)   |

| Chronological/holdout    | TooManyMethods              |  50001 |     349 |      0.007  |   0.0145 |   2.07 | rare (<5%)   |



\--- LIFT (AUC-PR / base\_rate) by rule × source ---

Lift strictly measures how much better the metric ranks over blind guessing.

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| CyclomaticComplexity\_Class  |         1.09 |            1.09 |             1.22 |                  1.07 |                       1.08 |                    1.43 |

| CyclomaticComplexity\_Method |         2.53 |            2.5  |             2.26 |                  2.01 |                       2.78 |                    3.38 |

| ExcessiveImports            |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| ExcessivePublicCount        |         1.03 |            1.04 |             1.11 |                  1    |                       1    |                    1.48 |

| NcssCount\_Class             |         1.08 |            1.08 |             1.23 |                  1.05 |                       1.09 |                    1.61 |

| NcssCount\_Method            |         3.5  |            3.37 |             3.27 |                  2.8  |                       4.03 |                    4.46 |

| TooManyMethods              |         1.13 |            1.16 |             1.39 |                  1.1  |                       1.09 |                    2.07 |



\--- AUC-PR (absolute) by rule × source ---

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| CyclomaticComplexity\_Class  |       0.0313 |          0.0319 |           0.0367 |                0.0962 |                     0.0293 |                  0.0145 |

| CyclomaticComplexity\_Method |       0.0104 |          0.0102 |           0.0114 |                0.0202 |                     0.0114 |                  0.0086 |

| ExcessiveImports            |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| ExcessivePublicCount        |       0.0291 |          0.0297 |           0.0326 |                0.0892 |                     0.0279 |                  0.0145 |

| NcssCount\_Class             |       0.0316 |          0.0319 |           0.037  |                0.096  |                     0.0308 |                  0.0155 |

| NcssCount\_Method            |       0.0144 |          0.0138 |           0.0165 |                0.0282 |                     0.0165 |                  0.0113 |

| TooManyMethods              |       0.0277 |          0.0285 |           0.0348 |                0.0848 |                     0.0264 |                  0.0145 |



================ PER-SOURCE SUMMARY ================

(reliable = n\_pos≥30 AND base\_rate≥0.05)



| Source                   | Max Absolute AUC-PR                | Max Reliable Lift                |

|:-------------------------|:-----------------------------------|:---------------------------------|

| Pooled/all               | 0.032 (NcssCount\_Class)            | — (no statistically stable rule) |

| Spatial/train            | 0.032 (NcssCount\_Class)            | — (no statistically stable rule) |

| Scarcity/train           | 0.037 (NcssCount\_Class)            | — (no statistically stable rule) |

| Chronological/train      | 0.096 (CyclomaticComplexity\_Class) | 1.10 (TooManyMethods)            |

| Spatial/Scarcity/holdout | 0.031 (NcssCount\_Class)            | — (no statistically stable rule) |

| Chronological/holdout    | 0.015 (NcssCount\_Class)            | — (no statistically stable rule) |



💾 Saved full diagnostic to: discrimination\_diagnostic\_questdb.csv

🏁 Phase 5 Complete. The overarching data structure has been successfully diagnosed.



