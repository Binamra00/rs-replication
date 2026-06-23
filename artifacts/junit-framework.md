# Junit Framework:





🚀 Setting up replication environment for junit-framework...

📂 Workspace Root: /content

📦 Data Directory: /content/data/junit-framework

☁️ Downloading junit-framework data from Zenodo...

🗜️ Unzipping data...

✅ Download and extraction complete.



\--- 🎯 Configuration Summary ---

Target Repository:  junit-framework

PMD Data Exists:    True

Refm Data Exists:   True

Lineage Exists:     True

Rel Hist Exists:    True

✅ Phase 0 Complete! You can now execute Phase 1.1.

🚀 Starting Phase 1.1: Data Synchronization Check

📂 Loading Release History Ground Truth...

&#x20;  ✅ Target Releases: 1 official releases found in configuration.



📂 Loading Master Lineage (The SHA Map)...

&#x20;  ✅ Lineage Loaded: 12571 total commits.



🔍 Step 1: Verifying PMD Snapshots...



🔍 Step 2: Verifying Refactoring Miner Ground Truth...

\--------------------------------------------------

📊 DATA SYNCHRONIZATION REPORT

&#x20;  🔹 PMD Snapshots: 31 valid snapshots verified in lineage (Expected at least: 1).

&#x20;  🔹 Refactoring Commits Mapped: 6335

&#x20;  🔹 Refactoring Density: 6335 unique commits contain refactorings.



🧾 PARSE INTEGRITY

&#x20;  - PMD unique SHAs observed (success only): 31

&#x20;  - PMD malformed lines: 0

&#x20;  - PMD failed-status lines skipped: 0

&#x20;  - PMD missing sha: 0

&#x20;  - PMD outside-lineage SHAs: 0

&#x20;  - RefMiner total entries read: 6335

&#x20;  - RefMiner malformed lines: 0

&#x20;  - RefMiner missing sha1: 0



🚀 SUCCESS: The three universes are synchronized!

&#x20;  The PMD observation points and Refactoring events exist on the same timeline.

🏁 Phase 1.1 Complete.

🚀 Starting Phase 1.2: Final Gold Class-Level Alias Graph Generation

⏳ Sorted 6335 commits chronologically to guarantee safe alias resolution.

&#x20;  🔍 Discovered 1435 Class Rename path-level aliases.

&#x20;  🔍 Discovered 534 Class Rename basename aliases.



📊 PHASE 1.2 INTEGRITY REPORT:

&#x20;  - Total Path Rename Links:      1435

&#x20;  - Total Basename Rename Links:  534

&#x20;  - Distinct Classes Threaded:    928

&#x20;  - Multi-rename links collapsed: 507

&#x20;  - Path Collisions (Preserved):  98

&#x20;  - Basename Collisions:          46

&#x20;  - Malformed/Skipped:            84

&#x20;      \* Missing Location Data: 84



✅ Identity lineage successfully resolved.

&#x20;  💾 Saved path-level graph to: alias\_tracking\_graph\_paths\_junit-framework.csv

&#x20;  💾 Saved basename graph to:   alias\_tracking\_graph\_junit-framework.csv

🏁 Phase 1.2 Complete.

🚀 Starting Phase 1.3: Final Audited Method Alias Graph Generation

⏳ Sorted 6335 commits chronologically for deterministic method alias chaining.

&#x20;  🔍 Discovered 2160 method lineage links.

&#x20;  ✅ Method lineage resolved.

&#x20;  💾 Saved to method\_alias\_graph\_junit-framework.csv



📊 PHASE 1.3 INTEGRITY REPORT:

&#x20;  - Total Method Links Mapped: 2160

&#x20;  - Collision Overwrites:      40

&#x20;  - Explicitly Skipped / Excluded:

&#x20;      \* Change Parameter Type: 2169



&#x20;  ✅ DATA INTEGRITY VERIFIED: 100% Regex match rate on targeted elements.



🏁 Phase 1.3 Complete.

🚀 Starting Phase D.2: Data Flattening \& Regex Rescue (With Alias Resolution)

⏳ Building PMD Method-Name Resolver from Phase 1.3 Graph...

&#x20;  ⚠️ Resolver collisions (preserved original root): 29

⏳ Loading Timelines and Mapping Ground Truth (Early Binding)...



📉 THE DATA ATTRITION FUNNEL (Ground Truth Mapping):

&#x20;  🧩 Raw Taxonomy-Matched Refactorings: 4036

&#x20;  📌 Total leftSideLocations (all matched refs): 10846

&#x20;  🔍 Total Structural Operations Found: 5534

&#x20;  🛡️  Test Files Purged (Regex Filter):  2916

&#x20;  ✅ Production Refactorings Retained (location-level):  2618

&#x20;  🎯 Mappable retained locations (pre-dedup): 1385

&#x20;  🔗 Unique mapped supervision keys (post-dedup): 667

&#x20;       ├─ God Class    (class-level):  203

&#x20;       └─ Long Method  (method-level): 464

&#x20;  ♻️  Dedup/compression delta: 718



✅ Flattened PMD Data: 292,001 raw metric records extracted.



🚫 Excluded-rule rows dropped from dataset (reported as a finding):

&#x20;     - CouplingBetweenObjects      :    9,473 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveImports            :   17,047 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveParameterList      :   81,201 rows  (no method signature → unmappable)

&#x20;     - TooManyFields               :      965 rows  (no metric value/range emitted)



🔍 DIAGNOSTIC: Checking for Zero-Refactoring Releases across the entire timeline...

&#x20;  ⚠️ WARNING: Found 3 releases with ZERO mapped refactoring events.

&#x20;  (These releases will likely be dropped during downstream Top-K or F-score evaluations).

&#x20;     - Release 4/31 : d49a6ac8bc60b1b028ea2d0e6ceb1b63e21dd3b1

&#x20;     - Release 28/31 : 8545c93a9d86ef7f9c848c0eca4ec792f4e82a37

&#x20;     - Release 30/31 : 1c14c1b83fcdd6091593cd4869f7ce82754f54d0

\-------------------------------------------------------------------------------------



&#x20;  ⚠️ Dropped unrecoverable metric rows: 10989



🏁 Phase D.2 Complete! Saved flat dataset to pmd\_flat\_junit-framework.csv

Note: Train/Test splitting happens in Phase T.2.



📊 POST-FLATTENING DATASET AUDIT:

&#x20;  - Total Observations: 292,001

&#x20;  - Positive Refactoring Labels: 1,991

&#x20;  - Negative Observations: 290,010

&#x20;  - Class Imbalance Ratio: 145.66:1

&#x20;  - Unique Files Tracked: 780

&#x20;  - Unique Commits (Snapshots) Tracked: 31

&#x20;  - Missing/Null Metric Values: 0



&#x20;  - Row Count by Rule Type:

&#x20;      \* CyclomaticComplexity\_Method: 118,061

&#x20;      \* NcssCount\_Method         : 118,061

&#x20;      \* NcssCount\_Class          : 22,235

&#x20;      \* ExcessivePublicCount     : 17,895

&#x20;      \* CyclomaticComplexity\_Class: 15,749



✅ Dataset audit passed: Structure is valid and data is balanced.

&#x20;Audit loaded: 292,001 records for junit-framework



PER-RULE VERDICTS:

&#x20;                     rule      verdict  peak\_rate

&#x20;          NcssCount\_Class    ambiguous   0.026923

CyclomaticComplexity\_Class    ambiguous   0.030879

&#x20;     ExcessivePublicCount       peaked   0.016820

&#x20;         NcssCount\_Method monotonic\_up   0.018344

🚀 Starting Phase B.2: Structural Validation Split (80/20 Stratified)



📊 Executing Stratified Group K-Fold (Canonical Integrity at \~80/20)...

&#x20;  - Training Set (81.0% actual): 236,451 metric rows | 298 Unique Refactoring Events

&#x20;  - Testing Set  (19.0% actual): 55,550 metric rows | 75 Unique Refactoring Events



🔍 Checking per-rule positive event densities (Rule Viability)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=240, test\_pos=57 

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=193, test\_pos=46 

&#x20;  ✅ ExcessivePublicCount           : train\_pos=188, test\_pos=33 

&#x20;  ✅ NcssCount\_Method               : train\_pos=525, test\_pos=92 

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=525, test\_pos=92 



📊 Executing Inner Stratified Group Split for K-Fold IDs...



💾 Saving master datasets to disk...

&#x20;  ✅ Saved Training Set: b2\_train\_spatial\_80\_junit-framework.csv

&#x20;  ✅ Saved Testing Set:  b2\_test\_spatial\_20\_junit-framework.csv



🏁 Phase B.2 Complete. The Data Engine has secured and saved the stratified 80/20 splits!

🚀 Starting Phase E.2: Data Scarcity Branch (True Locked Holdout Architecture)



📊 Isolating the Baseline Test Set (Extracting B.2 holdout via Basenames)...

📊 Starving the Training Set (Simulating Target 20% Total Data Scarcity)...



🧾 E.2 SPLIT GEOMETRY EXPLAINER

&#x20;  - Baseline outer split realized: Train 81.0% | Test 19.0% of total rows

&#x20;  - Scarcity train is 34.0% of baseline-train rows

&#x20;  - Therefore scarcity train is 27.6% of total rows (target was 20.0%)



&#x20;  - Scarcity Training Set (27.6% actual, \~20.0% target): 80,511 metric rows | 85 Unique File-Release Events

&#x20;  - Locked Testing Set (constant baseline holdout): 55,550 metric rows | 75 Unique File-Release Events

&#x20;  - Scarcity event density: 0.001056 events/row

&#x20;  - Locked-test event density: 0.001350 events/row



🔍 Checking per-rule positive event densities (Rule Viability under Scarcity)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=74 , test\_pos=57 

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=62 , test\_pos=46 

&#x20;  ✅ ExcessivePublicCount           : train\_pos=52 , test\_pos=33 

&#x20;  ✅ NcssCount\_Method               : train\_pos=195, test\_pos=92 

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=195, test\_pos=92 



📊 Executing Inner Stratified Group Split for E.3 K-Fold IDs...

&#x20;  ✅ Leakage Assertion Passed: Absolute spatial isolation confirmed.



💾 Saving Scarcity Training dataset to disk...

&#x20;  ✅ Saved Scarcity Training Set: e2\_train\_scarcity\_junit-framework.csv

&#x20;  ✅ Locked Testing Set is preserved at: b2\_test\_spatial\_20\_junit-framework.csv



🏁 Phase E.2 Complete. The Scarcity Data Engine has secured the true locked splits!

🚀 Starting Phase T.2: Chronological Branch (True Git Time-Series Split)



⚠️ MSR Attrition Note: You targeted \~31 official releases from GitHub.

⚠️ PMD parsed 31 releases. The missing 0 failed upstream static analysis.



⏳ Loading true Git commit timestamps to guarantee time-travel protection...



📊 T.2 Dataset Split Breakdown (50/50):

&#x20;  - Total PMD Releases: 31

&#x20;  - T.2 Training Releases (The Past):   15

&#x20;  - T.2 Testing Releases  (The Future): 16

&#x20;  - ⏱️ TRUE Temporal Boundary Lock: Release 15 (Git Timestamp: 1621080617)



&#x20;  - T.2 Training Set (34.8% actual metric rows): 101660 total rows

&#x20;  - T.2 Testing Set  (65.2% actual metric rows): 190341 total rows



&#x20;  🔍 Temporal Imbalance Check:

&#x20;     - Past Refactored Rows:   766

&#x20;     - Future Refactored Rows: 1225



🔍 Checking per-rule positive densities (Past vs Future)...

&#x20;  ✅ NcssCount\_Class                : past\_pos=88  , future\_pos=209 

&#x20;  ✅ CyclomaticComplexity\_Class     : past\_pos=71  , future\_pos=168 

&#x20;  ✅ ExcessivePublicCount           : past\_pos=69  , future\_pos=152 

&#x20;  ✅ NcssCount\_Method               : past\_pos=269 , future\_pos=348 

&#x20;  ✅ CyclomaticComplexity\_Method    : past\_pos=269 , future\_pos=348 



💾 Saved Temporal Training Set: t2\_train\_chrono\_50\_junit-framework.csv

💾 Saved Temporal Testing Set: t2\_test\_chrono\_50\_junit-framework.csv

&#x20;  ✅ Robust chronological splitting validated successfully!

🏁 Phase T.2 Complete. The timeline has been permanently split (No spatial shuffling applied).

🔎 Running T.2 True Chronological Sanity Check...

&#x20;  ✅ Split matrices successfully loaded from disk (No corruption).

&#x20;  ✅ Release counts verified (Past/Train: 15, Future/Test: 16).

&#x20;  ✅ Zero data leakage detected (Past and Future releases are strictly mutually exclusive).

&#x20;  ✅ Chronological boundary mathematically verified via Git History (Max Past TS: 1621080617 < Min Future TS: 1631472254).



📁 Step 4: System Evolution \& Temporal Overlap (T.2 Split)

&#x20;     - Canonical identities in the Past (Train):            516

&#x20;     - Canonical identities in the Future (Test):           752

&#x20;     - Identities persisting across the split (Overlap):    488

&#x20;     - Identities retired/deleted before Future phase:      28

&#x20;     - New identities introduced in Future phase:           264

&#x20;     🎯 Percentage of Future Architecture seen in the Past: 64.89%



🏁 Audit Complete. The T.2 Chronological Split is academically secure and verified.

🚀 Starting Phase B.3: Multi-Percentile Sweep Analysis (Optimized \& Guarded)

📊 Loaded Training Set with 631 canonical entities ready for K-Fold Calibration.



📈 Executing 5-Fold Cross-Validation Tournament...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...

&#x20;  ⚙️ Processing Fold 4 as Validation...

&#x20;  ⚙️ Processing Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.01|R:0.97|F1:0.03) | 4 (P:0.02|R:0.87|F1:0.03) | 6 (P:0.02|R:0.78|F1:0.03) | 10 (P:0.02|R:0.68|F1:0.03) | 14 (P:0.02|R:0.54|F1:0.03) | 20 (P:0.02|R:0.46|F1:0.04) | 26 (P:0.02|R:0.35|F1:0.04) | 37 (P:0.02|R:0.26|F1:0.04) | 65 (P:0.03|R:0.14|F1:0.05) | 89 (P:0.05|R:0.10|F1:0.06) | 113 (P:0.06|R:0.06|F1:0.06) |

| CyclomaticComplexity\_Class  | 1 (P:0.02|R:1.00|F1:0.03) | 2 (P:0.02|R:0.91|F1:0.03) | 3 (P:0.02|R:0.78|F1:0.03) | 4 (P:0.02|R:0.65|F1:0.03)  | 6 (P:0.02|R:0.56|F1:0.03)  | 7 (P:0.02|R:0.45|F1:0.03)  | 10 (P:0.02|R:0.33|F1:0.04) | 15 (P:0.02|R:0.24|F1:0.04) | 23 (P:0.03|R:0.14|F1:0.05) | 29 (P:0.03|R:0.10|F1:0.05) | 44 (P:0.05|R:0.05|F1:0.05)  |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:1.00|F1:0.03) | 2 (P:0.01|R:0.69|F1:0.02)  | 2 (P:0.01|R:0.64|F1:0.02)  | 3 (P:0.01|R:0.49|F1:0.02)  | 3 (P:0.01|R:0.41|F1:0.03)  | 5 (P:0.01|R:0.26|F1:0.02)  | 6 (P:0.01|R:0.17|F1:0.02)  | 7 (P:0.01|R:0.13|F1:0.02)  | 11 (P:0.01|R:0.04|F1:0.01)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.99|F1:0.01) | 2 (P:0.01|R:0.99|F1:0.01) | 2 (P:0.01|R:0.99|F1:0.01) | 2 (P:0.01|R:0.99|F1:0.01)  | 3 (P:0.01|R:0.61|F1:0.02)  | 4 (P:0.01|R:0.49|F1:0.02)  | 5 (P:0.01|R:0.40|F1:0.03)  | 7 (P:0.01|R:0.28|F1:0.03)  | 8 (P:0.02|R:0.18|F1:0.03)  | 10 (P:0.02|R:0.13|F1:0.03) | 14 (P:0.02|R:0.05|F1:0.03)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 2 (P:0.01|R:0.44|F1:0.02)  | 2 (P:0.01|R:0.32|F1:0.02)  | 3 (P:0.01|R:0.23|F1:0.02)  | 4 (P:0.01|R:0.13|F1:0.03)  | 5 (P:0.02|R:0.07|F1:0.03)   |

| TooManyMethods              | 1 (P:0.01|R:0.99|F1:0.02) | 2 (P:0.01|R:0.91|F1:0.02) | 3 (P:0.01|R:0.74|F1:0.03) | 5 (P:0.01|R:0.68|F1:0.03)  | 7 (P:0.02|R:0.54|F1:0.03)  | 8 (P:0.02|R:0.46|F1:0.03)  | 11 (P:0.02|R:0.35|F1:0.03) | 14 (P:0.02|R:0.27|F1:0.05) | 18 (P:0.03|R:0.17|F1:0.05) | 26 (P:0.06|R:0.14|F1:0.07) | 29 (P:0.04|R:0.06|F1:0.04)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.01|R:0.97|F0.5:0.02) | 4 (P:0.02|R:0.87|F0.5:0.02) | 6 (P:0.02|R:0.78|F0.5:0.02) | 10 (P:0.02|R:0.68|F0.5:0.02) | 14 (P:0.02|R:0.54|F0.5:0.02) | 20 (P:0.02|R:0.46|F0.5:0.02) | 26 (P:0.02|R:0.35|F0.5:0.02) | 37 (P:0.02|R:0.26|F0.5:0.03) | 65 (P:0.03|R:0.14|F0.5:0.03) | 89 (P:0.05|R:0.10|F0.5:0.05) | 113 (P:0.06|R:0.06|F0.5:0.06) |

| CyclomaticComplexity\_Class  | 1 (P:0.02|R:1.00|F0.5:0.02) | 2 (P:0.02|R:0.91|F0.5:0.02) | 3 (P:0.02|R:0.78|F0.5:0.02) | 4 (P:0.02|R:0.65|F0.5:0.02)  | 6 (P:0.02|R:0.56|F0.5:0.02)  | 7 (P:0.02|R:0.45|F0.5:0.02)  | 10 (P:0.02|R:0.33|F0.5:0.02) | 15 (P:0.02|R:0.24|F0.5:0.02) | 23 (P:0.03|R:0.14|F0.5:0.04) | 29 (P:0.03|R:0.10|F0.5:0.04) | 44 (P:0.05|R:0.05|F0.5:0.05)  |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:1.00|F0.5:0.02) | 2 (P:0.01|R:0.69|F0.5:0.02)  | 2 (P:0.01|R:0.64|F0.5:0.02)  | 3 (P:0.01|R:0.49|F0.5:0.02)  | 3 (P:0.01|R:0.41|F0.5:0.02)  | 5 (P:0.01|R:0.26|F0.5:0.02)  | 6 (P:0.01|R:0.17|F0.5:0.01)  | 7 (P:0.01|R:0.13|F0.5:0.02)  | 11 (P:0.01|R:0.04|F0.5:0.01)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.99|F0.5:0.01)  | 3 (P:0.01|R:0.61|F0.5:0.01)  | 4 (P:0.01|R:0.49|F0.5:0.01)  | 5 (P:0.01|R:0.40|F0.5:0.02)  | 7 (P:0.01|R:0.28|F0.5:0.02)  | 8 (P:0.02|R:0.18|F0.5:0.02)  | 10 (P:0.02|R:0.13|F0.5:0.02) | 14 (P:0.02|R:0.05|F0.5:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 2 (P:0.01|R:0.44|F0.5:0.01)  | 2 (P:0.01|R:0.32|F0.5:0.01)  | 3 (P:0.01|R:0.23|F0.5:0.02)  | 4 (P:0.01|R:0.13|F0.5:0.02)  | 5 (P:0.02|R:0.07|F0.5:0.02)   |

| TooManyMethods              | 1 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.91|F0.5:0.01) | 3 (P:0.01|R:0.74|F0.5:0.02) | 5 (P:0.01|R:0.68|F0.5:0.02)  | 7 (P:0.02|R:0.54|F0.5:0.02)  | 8 (P:0.02|R:0.46|F0.5:0.02)  | 11 (P:0.02|R:0.35|F0.5:0.02) | 14 (P:0.02|R:0.27|F0.5:0.03) | 18 (P:0.03|R:0.17|F0.5:0.03) | 26 (P:0.06|R:0.14|F0.5:0.06) | 29 (P:0.04|R:0.06|F0.5:0.04)  |



🏆 F1-Optimized Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 90th         |                89 |               113 |         0.0636 |             3.74 |      0.0133 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 85th         |                23 |                44 |         0.0499 |             1.96 |      0.0155 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 5th          |                 1 |                11 |         0.0253 |             1    |      0.0128 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                 8 |                14 |         0.0319 |             3.29 |      0.0054 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                 5 |                 5 |         0.0261 |             3.04 |      0.0054 |            5 |

| TooManyMethods              | True         | True               | False         | 90th         |                26 |                26 |         0.0681 |             5.92 |      0.0094 |            5 |



🎯 Precision-Optimized (F0.5) Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 95th         |               113 |               113 |           0.0579 |             4.53 |      0.0133 |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 95th         |                44 |                44 |           0.0506 |             3.34 |      0.0155 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 65th         |                 3 |                11 |           0.0162 |             1.02 |      0.0128 |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                14 |                14 |           0.0231 |             3.75 |      0.0054 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                 5 |                 5 |           0.0194 |             3.04 |      0.0054 |            5 |

| TooManyMethods              | True         | True               | False         | 90th         |                26 |                26 |           0.0585 |             5.92 |      0.0094 |            5 |



💾 Saved Dual Baseline locked thresholds to disk: /content/b3\_inflection\_thresholds\_junit-framework\_locked.json

🏁 Phase B.3 Complete.

🚀 Starting Phase E.3: Multi-Percentile Sweep Analysis (Scarcity Edition)

📊 Loaded Scarcity Training Set (20%) with 159 canonical entities.



📈 Executing 3-Fold Cross-Validation Tournament (Scarcity)...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                      | 35th                      | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.02|R:0.94|F1:0.03) | 4 (P:0.02|R:0.84|F1:0.03) | 6 (P:0.02|R:0.81|F1:0.04) | 9 (P:0.02|R:0.69|F1:0.04) | 17 (P:0.02|R:0.55|F1:0.04) | 22 (P:0.02|R:0.44|F1:0.04) | 27 (P:0.02|R:0.37|F1:0.05) | 36 (P:0.02|R:0.23|F1:0.04) | 64 (P:0.03|R:0.15|F1:0.04) | 92 (P:0.02|R:0.08|F1:0.03) | 282 (P:0.02|R:0.04|F1:0.02) |

| CyclomaticComplexity\_Class  | 1 (P:0.02|R:0.93|F1:0.03) | 2 (P:0.02|R:0.91|F1:0.04) | 2 (P:0.02|R:0.77|F1:0.03) | 4 (P:0.02|R:0.64|F1:0.03) | 6 (P:0.02|R:0.50|F1:0.03)  | 9 (P:0.02|R:0.48|F1:0.05)  | 12 (P:0.03|R:0.37|F1:0.05) | 16 (P:0.03|R:0.26|F1:0.05) | 24 (P:0.04|R:0.18|F1:0.06) | 56 (P:0.03|R:0.10|F1:0.04) | 219 (P:0.02|R:0.04|F1:0.02) |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:0.88|F1:0.03) | 2 (P:0.01|R:0.77|F1:0.03) | 2 (P:0.01|R:0.74|F1:0.03) | 2 (P:0.01|R:0.74|F1:0.03)  | 2 (P:0.01|R:0.74|F1:0.03)  | 3 (P:0.01|R:0.42|F1:0.02)  | 3 (P:0.01|R:0.29|F1:0.02)  | 7 (P:0.01|R:0.17|F1:0.02)  | 10 (P:0.02|R:0.10|F1:0.03) | 274 (P:0.00|R:0.06|F1:0.01) |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.99|F1:0.01) | 2 (P:0.01|R:0.99|F1:0.01) | 2 (P:0.01|R:0.99|F1:0.01) | 2 (P:0.01|R:0.78|F1:0.01) | 3 (P:0.01|R:0.67|F1:0.02)  | 4 (P:0.01|R:0.61|F1:0.02)  | 5 (P:0.01|R:0.41|F1:0.03)  | 6 (P:0.01|R:0.30|F1:0.03)  | 8 (P:0.02|R:0.24|F1:0.03)  | 11 (P:0.01|R:0.17|F1:0.02) | 14 (P:0.02|R:0.12|F1:0.03)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 2 (P:0.01|R:0.32|F1:0.02)  | 3 (P:0.01|R:0.20|F1:0.02)  | 4 (P:0.01|R:0.18|F1:0.03)  | 5 (P:0.01|R:0.10|F1:0.02)   |

| TooManyMethods              | 2 (P:0.01|R:0.94|F1:0.03) | 2 (P:0.01|R:0.94|F1:0.03) | 2 (P:0.01|R:0.83|F1:0.03) | 4 (P:0.02|R:0.65|F1:0.03) | 5 (P:0.02|R:0.54|F1:0.03)  | 7 (P:0.02|R:0.51|F1:0.04)  | 7 (P:0.02|R:0.48|F1:0.04)  | 15 (P:0.03|R:0.27|F1:0.06) | 23 (P:0.04|R:0.14|F1:0.05) | 28 (P:0.05|R:0.12|F1:0.07) | 35 (P:0.04|R:0.08|F1:0.05)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                        | 35th                        | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.02|R:0.94|F0.5:0.02) | 4 (P:0.02|R:0.84|F0.5:0.02) | 6 (P:0.02|R:0.81|F0.5:0.02) | 9 (P:0.02|R:0.69|F0.5:0.02) | 17 (P:0.02|R:0.55|F0.5:0.03) | 22 (P:0.02|R:0.44|F0.5:0.03) | 27 (P:0.02|R:0.37|F0.5:0.03) | 36 (P:0.02|R:0.23|F0.5:0.03) | 64 (P:0.03|R:0.15|F0.5:0.03) | 92 (P:0.02|R:0.08|F0.5:0.02) | 282 (P:0.02|R:0.04|F0.5:0.02) |

| CyclomaticComplexity\_Class  | 1 (P:0.02|R:0.93|F0.5:0.02) | 2 (P:0.02|R:0.91|F0.5:0.02) | 2 (P:0.02|R:0.77|F0.5:0.02) | 4 (P:0.02|R:0.64|F0.5:0.02) | 6 (P:0.02|R:0.50|F0.5:0.02)  | 9 (P:0.02|R:0.48|F0.5:0.03)  | 12 (P:0.03|R:0.37|F0.5:0.03) | 16 (P:0.03|R:0.26|F0.5:0.04) | 24 (P:0.04|R:0.18|F0.5:0.05) | 56 (P:0.03|R:0.10|F0.5:0.03) | 219 (P:0.02|R:0.04|F0.5:0.02) |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:0.88|F0.5:0.02) | 2 (P:0.01|R:0.77|F0.5:0.02) | 2 (P:0.01|R:0.74|F0.5:0.02) | 2 (P:0.01|R:0.74|F0.5:0.02)  | 2 (P:0.01|R:0.74|F0.5:0.02)  | 3 (P:0.01|R:0.42|F0.5:0.01)  | 3 (P:0.01|R:0.29|F0.5:0.01)  | 7 (P:0.01|R:0.17|F0.5:0.01)  | 10 (P:0.02|R:0.10|F0.5:0.02) | 274 (P:0.00|R:0.06|F0.5:0.01) |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.99|F0.5:0.01) | 2 (P:0.01|R:0.78|F0.5:0.01) | 3 (P:0.01|R:0.67|F0.5:0.01)  | 4 (P:0.01|R:0.61|F0.5:0.01)  | 5 (P:0.01|R:0.41|F0.5:0.02)  | 6 (P:0.01|R:0.30|F0.5:0.02)  | 8 (P:0.02|R:0.24|F0.5:0.02)  | 11 (P:0.01|R:0.17|F0.5:0.02) | 14 (P:0.02|R:0.12|F0.5:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 2 (P:0.01|R:0.32|F0.5:0.01)  | 3 (P:0.01|R:0.20|F0.5:0.01)  | 4 (P:0.01|R:0.18|F0.5:0.02)  | 5 (P:0.01|R:0.10|F0.5:0.01)   |

| TooManyMethods              | 2 (P:0.01|R:0.94|F0.5:0.02) | 2 (P:0.01|R:0.94|F0.5:0.02) | 2 (P:0.01|R:0.83|F0.5:0.02) | 4 (P:0.02|R:0.65|F0.5:0.02) | 5 (P:0.02|R:0.54|F0.5:0.02)  | 7 (P:0.02|R:0.51|F0.5:0.02)  | 7 (P:0.02|R:0.48|F0.5:0.02)  | 15 (P:0.03|R:0.27|F0.5:0.04) | 23 (P:0.04|R:0.14|F0.5:0.04) | 28 (P:0.05|R:0.12|F0.5:0.06) | 35 (P:0.04|R:0.08|F0.5:0.05)  |



🏆 F1-Optimized Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 65th         |                27 |                64 |         0.0463 |             1.59 |      0.0156 |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 85th         |                24 |                24 |         0.0617 |             2.21 |      0.0182 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 90th         |                10 |                10 |         0.0283 |             1.35 |      0.0135 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                 8 |                14 |         0.0305 |             2.63 |      0.0062 |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                 4 |                 4 |         0.0273 |             2.39 |      0.0062 |            3 |

| TooManyMethods              | True         | True               | False         | 90th         |                28 |                28 |         0.0715 |             4.58 |      0.0113 |            3 |



🎯 Precision-Optimized (F0.5) Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 85th         |                64 |               282 |           0.0314 |             1.68 |      0.0156 |            3 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 85th         |                24 |                24 |           0.0465 |             2.21 |      0.0182 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 90th         |                10 |                10 |           0.0212 |             1.35 |      0.0135 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                14 |                14 |           0.0208 |             2.85 |      0.0062 |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                 4 |                 5 |           0.0181 |             2.39 |      0.0062 |            3 |

| TooManyMethods              | True         | True               | False         | 90th         |                28 |                28 |           0.058  |             4.58 |      0.0113 |            3 |



💾 Saved Dual Baseline locked thresholds to disk: /content/e3\_inflection\_thresholds\_junit-framework\_scarcity.json

🏁 Phase E.3 Complete.

🚀 Starting Phase T.3: Chronological K-Fold Calibration Engine

📊 Loaded Temporal Training Set (The Past) with 516 canonical entities.



📈 Executing 5-Fold Cross-Validation Tournament (Chronological; n\_splits=5)...

&#x20;  ⚙️ Processing Temporal Fold 1 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 2 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 3 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 4 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                       | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                       | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|

| NcssCount\_Class             | 4 (P:0.02|R:0.80|F1:0.03) | 6 (P:0.02|R:0.75|F1:0.03) | 11 (P:0.01|R:0.57|F1:0.03) | 16 (P:0.02|R:0.54|F1:0.03) | 20 (P:0.02|R:0.51|F1:0.04) | 28 (P:0.02|R:0.46|F1:0.04) | 36 (P:0.02|R:0.35|F1:0.04) | 46 (P:0.03|R:0.32|F1:0.05) | 67 (P:0.04|R:0.28|F1:0.06) | 83 (P:0.05|R:0.23|F1:0.08) | 135 (P:0.03|R:0.12|F1:0.05) |

| CyclomaticComplexity\_Class  | 2 (P:0.02|R:0.98|F1:0.03) | 3 (P:0.01|R:0.89|F1:0.03) | 4 (P:0.01|R:0.75|F1:0.02)  | 5 (P:0.01|R:0.70|F1:0.03)  | 6 (P:0.02|R:0.68|F1:0.03)  | 8 (P:0.02|R:0.65|F1:0.03)  | 13 (P:0.02|R:0.47|F1:0.04) | 17 (P:0.03|R:0.44|F1:0.05) | 26 (P:0.04|R:0.39|F1:0.07) | 30 (P:0.04|R:0.35|F1:0.07) | 37 (P:0.04|R:0.24|F1:0.06)  |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:1.00|F1:0.03) | 1 (P:0.01|R:0.89|F1:0.03)  | 2 (P:0.01|R:0.85|F1:0.03)  | 2 (P:0.01|R:0.65|F1:0.02)  | 3 (P:0.01|R:0.54|F1:0.03)  | 4 (P:0.02|R:0.54|F1:0.04)  | 5 (P:0.02|R:0.42|F1:0.03)  | 6 (P:0.01|R:0.35|F1:0.02)  | 7 (P:0.01|R:0.27|F1:0.02)  | 10 (P:0.01|R:0.19|F1:0.02)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:0.98|F1:0.01) | 2 (P:0.01|R:0.98|F1:0.01) | 2 (P:0.01|R:0.98|F1:0.01)  | 2 (P:0.01|R:0.98|F1:0.01)  | 2 (P:0.01|R:0.87|F1:0.02)  | 3 (P:0.01|R:0.58|F1:0.02)  | 4 (P:0.01|R:0.54|F1:0.03)  | 5 (P:0.02|R:0.44|F1:0.03)  | 8 (P:0.02|R:0.25|F1:0.04)  | 9 (P:0.03|R:0.19|F1:0.04)  | 12 (P:0.03|R:0.12|F1:0.04)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 1 (P:0.01|R:1.00|F1:0.01)  | 2 (P:0.01|R:0.64|F1:0.02)  | 2 (P:0.01|R:0.43|F1:0.02)  | 3 (P:0.01|R:0.33|F1:0.02)  | 4 (P:0.01|R:0.19|F1:0.02)  | 5 (P:0.02|R:0.08|F1:0.03)   |

| TooManyMethods              | 1 (P:0.01|R:0.96|F1:0.03) | 3 (P:0.01|R:0.84|F1:0.03) | 4 (P:0.01|R:0.71|F1:0.03)  | 5 (P:0.01|R:0.66|F1:0.03)  | 5 (P:0.02|R:0.61|F1:0.03)  | 6 (P:0.02|R:0.59|F1:0.04)  | 10 (P:0.02|R:0.44|F1:0.04) | 12 (P:0.02|R:0.43|F1:0.04) | 15 (P:0.04|R:0.43|F1:0.06) | 18 (P:0.04|R:0.42|F1:0.07) | 21 (P:0.04|R:0.27|F1:0.06)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                         | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                         | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|

| NcssCount\_Class             | 4 (P:0.02|R:0.80|F0.5:0.02) | 6 (P:0.02|R:0.75|F0.5:0.02) | 11 (P:0.01|R:0.57|F0.5:0.02) | 16 (P:0.02|R:0.54|F0.5:0.02) | 20 (P:0.02|R:0.51|F0.5:0.02) | 28 (P:0.02|R:0.46|F0.5:0.03) | 36 (P:0.02|R:0.35|F0.5:0.03) | 46 (P:0.03|R:0.32|F0.5:0.03) | 67 (P:0.04|R:0.28|F0.5:0.05) | 83 (P:0.05|R:0.23|F0.5:0.06) | 135 (P:0.03|R:0.12|F0.5:0.04) |

| CyclomaticComplexity\_Class  | 2 (P:0.02|R:0.98|F0.5:0.02) | 3 (P:0.01|R:0.89|F0.5:0.02) | 4 (P:0.01|R:0.75|F0.5:0.02)  | 5 (P:0.01|R:0.70|F0.5:0.02)  | 6 (P:0.02|R:0.68|F0.5:0.02)  | 8 (P:0.02|R:0.65|F0.5:0.02)  | 13 (P:0.02|R:0.47|F0.5:0.02) | 17 (P:0.03|R:0.44|F0.5:0.03) | 26 (P:0.04|R:0.39|F0.5:0.05) | 30 (P:0.04|R:0.35|F0.5:0.05) | 37 (P:0.04|R:0.24|F0.5:0.04)  |

| ExcessivePublicCount        | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:1.00|F0.5:0.02) | 1 (P:0.01|R:0.89|F0.5:0.02)  | 2 (P:0.01|R:0.85|F0.5:0.02)  | 2 (P:0.01|R:0.65|F0.5:0.02)  | 3 (P:0.01|R:0.54|F0.5:0.02)  | 4 (P:0.02|R:0.54|F0.5:0.02)  | 5 (P:0.02|R:0.42|F0.5:0.02)  | 6 (P:0.01|R:0.35|F0.5:0.02)  | 7 (P:0.01|R:0.27|F0.5:0.01)  | 10 (P:0.01|R:0.19|F0.5:0.01)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:0.98|F0.5:0.01) | 2 (P:0.01|R:0.98|F0.5:0.01) | 2 (P:0.01|R:0.98|F0.5:0.01)  | 2 (P:0.01|R:0.98|F0.5:0.01)  | 2 (P:0.01|R:0.87|F0.5:0.01)  | 3 (P:0.01|R:0.58|F0.5:0.01)  | 4 (P:0.01|R:0.54|F0.5:0.02)  | 5 (P:0.02|R:0.44|F0.5:0.02)  | 8 (P:0.02|R:0.25|F0.5:0.03)  | 9 (P:0.03|R:0.19|F0.5:0.03)  | 12 (P:0.03|R:0.12|F0.5:0.03)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 1 (P:0.01|R:1.00|F0.5:0.01)  | 2 (P:0.01|R:0.64|F0.5:0.01)  | 2 (P:0.01|R:0.43|F0.5:0.01)  | 3 (P:0.01|R:0.33|F0.5:0.02)  | 4 (P:0.01|R:0.19|F0.5:0.02)  | 5 (P:0.02|R:0.08|F0.5:0.02)   |

| TooManyMethods              | 1 (P:0.01|R:0.96|F0.5:0.02) | 3 (P:0.01|R:0.84|F0.5:0.02) | 4 (P:0.01|R:0.71|F0.5:0.02)  | 5 (P:0.01|R:0.66|F0.5:0.02)  | 5 (P:0.02|R:0.61|F0.5:0.02)  | 6 (P:0.02|R:0.59|F0.5:0.02)  | 10 (P:0.02|R:0.44|F0.5:0.03) | 12 (P:0.02|R:0.43|F0.5:0.03) | 15 (P:0.04|R:0.43|F0.5:0.04) | 18 (P:0.04|R:0.42|F0.5:0.05) | 21 (P:0.04|R:0.27|F0.5:0.04)  |



🏆 F1-Optimized Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 90th         |                83 |                83 |         0.08   |             3.62 |      0.015  |            4 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 90th         |                30 |                37 |         0.0672 |             2.56 |      0.016  |            4 |

| ExcessivePublicCount        | True         | False              | False         | 65th         |                 4 |                10 |         0.0358 |             1.28 |      0.0145 |            4 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 90th         |                 9 |                12 |         0.0431 |             4.81 |      0.0054 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                 5 |                 5 |         0.0261 |             3.06 |      0.0054 |            5 |

| TooManyMethods              | True         | True               | False         | 90th         |                18 |                18 |         0.0736 |             3.44 |      0.0122 |            4 |



🎯 Precision-Optimized (F0.5) Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 90th         |                83 |                83 |           0.0617 |             3.62 |      0.015  |            4 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 90th         |                30 |                37 |           0.0479 |             2.56 |      0.016  |            4 |

| ExcessivePublicCount        | True         | False              | False         | 65th         |                 4 |                10 |           0.0231 |             1.28 |      0.0145 |            4 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 95th         |                12 |                12 |           0.0315 |             5.14 |      0.0054 |            5 |

| CyclomaticComplexity\_Method | True         | True               | False         | 95th         |                 5 |                 5 |           0.0194 |             3.06 |      0.0054 |            5 |

| TooManyMethods              | True         | True               | False         | 90th         |                18 |                21 |           0.0504 |             3.44 |      0.0122 |            4 |



💾 Saved Dual Chronological locked thresholds to disk: t3\_inflection\_thresholds\_junit-framework\_chrono\_locked.json

🏁 Phase T.3 Complete.

🚀 Starting Phase B.4: Blind Imminent Predictability Evaluation (Trust-Aware Edition)

✅ Thresholds strictly synchronized from disk.

📊 Final Exam Loaded: Evaluating 149 completely unseen canonical entities.



&#x20;   MASTER BLIND EVALUATION MATRIX (Test Set: 20%)



📊 TABLE 1: F1-Optimized Thresholds (Evaluated on Blind F1 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |        57 |         1500 |             10 | ⚠️ 1500 (Fallback) |     0.064 |     0     |    0     |      0.024 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        46 |           80 |              6 | ⚠️ 80 (Fallback)   |     0.05  |     0     |    0     |      0.024 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        33 |           45 |              2 | ⚠️ 45 (Fallback)   |     0.025 |     0     |    0     |      0.017 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        92 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.032 |     0     |    0     |      0.009 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        92 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.026 |     0     |    0     |      0.008 | ➖ Uncalibrated Noise |

| TooManyMethods              |        35 |           10 |              3 | ⚠️ 10 (Fallback)   |     0.068 |     0.037 |    0.037 |      0.02  | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized Thresholds (Evaluated on Blind F0.5 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |        57 |         1500 |             10 | ⚠️ 1500 (Fallback) |      0.058 |      0     |     0     |       0.015 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        46 |           80 |              6 | ⚠️ 80 (Fallback)   |      0.051 |      0     |     0     |       0.016 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        33 |           45 |              2 | ⚠️ 45 (Fallback)   |      0.016 |      0     |     0     |       0.011 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        92 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.023 |      0     |     0     |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        92 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.019 |      0     |     0     |       0.005 | ➖ Uncalibrated Noise |

| TooManyMethods              |        35 |           10 |              3 | ⚠️ 10 (Fallback)   |      0.059 |      0.024 |     0.024 |       0.012 | ➖ Uncalibrated Noise |



💾 Saved detailed evaluation matrix to: b4\_evaluation\_matrix\_junit-framework.csv



=================================================================

🏆 FINAL BASELINE EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  Test Entities (Strictly Blind):   149

\-----------------------------------------------------------------

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F1 averages.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F0.5 averages.

=================================================================

🏁 Phase B.4 Complete. The threshold hypotheses have been blindly evaluated.

🚀 Starting Phase E.4: Scarcity Predictability Evaluation (Trust-Aware)

📊 Final Scarcity Exam Loaded: Evaluating 149 completely unseen canonical entities.



📊 TABLE 1: F1-Optimized Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |        57 |         1500 |             12 | ⚠️ 1500 (Fallback) |     0.046 |     0     |    0     |      0.024 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        46 |           80 |              6 | ⚠️ 80 (Fallback)   |     0.062 |     0     |    0     |      0.024 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        33 |           45 |              2 | ⚠️ 45 (Fallback)   |     0.028 |     0     |    0     |      0.017 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        92 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.03  |     0     |    0     |      0.009 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        92 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.027 |     0     |    0     |      0.008 | ➖ Uncalibrated Noise |

| TooManyMethods              |        35 |           10 |              3 | ⚠️ 10 (Fallback)   |     0.071 |     0.037 |    0.037 |      0.02  | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |        57 |         1500 |             12 | ⚠️ 1500 (Fallback) |      0.031 |      0     |     0     |       0.016 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        46 |           80 |              6 | ⚠️ 80 (Fallback)   |      0.046 |      0     |     0     |       0.016 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        33 |           45 |              2 | ⚠️ 45 (Fallback)   |      0.021 |      0     |     0     |       0.011 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        92 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.021 |      0     |     0     |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        92 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.018 |      0     |     0     |       0.005 | ➖ Uncalibrated Noise |

| TooManyMethods              |        35 |           10 |              3 | ⚠️ 10 (Fallback)   |      0.058 |      0.024 |     0.024 |       0.012 | ➖ Uncalibrated Noise |



=================================================================

🏆 SCARCITY EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

=================================================================



💾 Saved scarcity evaluation matrix to: e4\_evaluation\_matrix\_scarcity\_junit-framework.csv

🏁 Phase E.4 Complete. Scarcity evaluation finalized.

🚀 Starting Phase T.4: Chronological Predictability Evaluation (Trust-Aware)

📊 Final Chronological Exam Loaded: Evaluating against Future Timeline.



📊 TABLE 1: F1-Optimized Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |       209 |         1500 |             12 | ⚠️ 1500 (Fallback) |     0.08  |     0     |    0     |      0.035 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       168 |           80 |              6 | ⚠️ 80 (Fallback)   |     0.067 |     0.028 |    0.028 |      0.036 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       152 |           45 |              2 | ⚠️ 45 (Fallback)   |     0.036 |     0.03  |    0.03  |      0.027 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       348 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.043 |     0     |    0     |      0.01  | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       348 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.026 |     0     |    0     |      0.009 | ➖ Uncalibrated Noise |

| TooManyMethods              |       100 |           10 |              3 | ⚠️ 10 (Fallback)   |     0.074 |     0.037 |    0.037 |      0.025 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |       209 |         1500 |             12 | ⚠️ 1500 (Fallback) |      0.062 |      0     |     0     |       0.022 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |       168 |           80 |              6 | ⚠️ 80 (Fallback)   |      0.048 |      0.042 |     0.042 |       0.023 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |       152 |           45 |              2 | ⚠️ 45 (Fallback)   |      0.023 |      0.045 |     0.045 |       0.017 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       348 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.032 |      0     |     0     |       0.006 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       348 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.019 |      0     |     0     |       0.006 | ➖ Uncalibrated Noise |

| TooManyMethods              |       100 |           10 |              3 | ⚠️ 10 (Fallback)   |      0.05  |      0.024 |     0.024 |       0.016 | ➖ Uncalibrated Noise |



=================================================================

🏆 CHRONOLOGICAL EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

=================================================================



💾 Saved chronological evaluation matrix to: t4\_evaluation\_matrix\_chrono\_junit-framework.csv

🏁 Phase T.4 Complete. Chronological evaluation finalized.



=====================================================================================

🚀 INITIATING PHASE 6: MASTER CROSS-REGIME DISCRIMINATION DIAGNOSTIC

=====================================================================================



================ DISCRIMINATION BY SOURCE × RULE ================

AUC-PR \~ base\_rate  ⇒  lift \~ 1.0  ⇒  metric ranks refactoring at chance.



| Source                   | Rule                        |      n |   n\_pos |   base\_rate |   auc\_pr |   lift | flag         |

|:-------------------------|:----------------------------|-------:|--------:|------------:|---------:|-------:|:-------------|

| Pooled/all               | NcssCount\_Class             |  22235 |     297 |      0.0134 |   0.0226 |   1.7  | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Class  |  15749 |     239 |      0.0152 |   0.0226 |   1.49 | rare (<5%)   |

| Pooled/all               | ExcessivePublicCount        |  17895 |     221 |      0.0123 |   0.0148 |   1.2  | rare (<5%)   |

| Pooled/all               | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | NcssCount\_Method            | 118061 |     617 |      0.0052 |   0.0115 |   2.2  | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Method | 118061 |     617 |      0.0052 |   0.0078 |   1.49 | rare (<5%)   |

| Pooled/all               | TooManyMethods              |  15826 |     155 |      0.0098 |   0.0201 |   2.05 | rare (<5%)   |

| Spatial/train            | NcssCount\_Class             |  17748 |     240 |      0.0135 |   0.023  |   1.7  | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Class  |  12378 |     193 |      0.0156 |   0.0231 |   1.48 | rare (<5%)   |

| Spatial/train            | ExcessivePublicCount        |  14363 |     188 |      0.0131 |   0.0161 |   1.23 | rare (<5%)   |

| Spatial/train            | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | NcssCount\_Method            |  95981 |     525 |      0.0055 |   0.0116 |   2.11 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Method |  95981 |     525 |      0.0055 |   0.0081 |   1.49 | rare (<5%)   |

| Spatial/train            | TooManyMethods              |  12741 |     120 |      0.0094 |   0.02   |   2.12 | rare (<5%)   |

| Scarcity/train           | NcssCount\_Class             |   4602 |      74 |      0.0161 |   0.0283 |   1.76 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Class  |   3318 |      62 |      0.0187 |   0.0316 |   1.69 | rare (<5%)   |

| Scarcity/train           | ExcessivePublicCount        |   3749 |      52 |      0.0139 |   0.0255 |   1.84 | rare (<5%)   |

| Scarcity/train           | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | NcssCount\_Method            |  34421 |     195 |      0.0057 |   0.0105 |   1.86 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Method |  34421 |     195 |      0.0057 |   0.0076 |   1.34 | rare (<5%)   |

| Scarcity/train           | TooManyMethods              |   3345 |      37 |      0.0111 |   0.0262 |   2.37 | rare (<5%)   |

| Chronological/train      | NcssCount\_Class             |   7400 |      88 |      0.0119 |   0.0183 |   1.54 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Class  |   5381 |      71 |      0.0132 |   0.0168 |   1.27 | rare (<5%)   |

| Chronological/train      | ExcessivePublicCount        |   6163 |      69 |      0.0112 |   0.0127 |   1.13 | rare (<5%)   |

| Chronological/train      | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | NcssCount\_Method            |  41358 |     269 |      0.0065 |   0.0131 |   2.01 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Method |  41358 |     269 |      0.0065 |   0.0089 |   1.36 | rare (<5%)   |

| Chronological/train      | TooManyMethods              |   5641 |      55 |      0.0098 |   0.0156 |   1.6  | rare (<5%)   |

| Spatial/Scarcity/holdout | NcssCount\_Class             |   4487 |      57 |      0.0127 |   0.0239 |   1.88 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Class  |   3371 |      46 |      0.0136 |   0.0226 |   1.66 | rare (<5%)   |

| Spatial/Scarcity/holdout | ExcessivePublicCount        |   3532 |      33 |      0.0093 |   0.0096 |   1.03 | rare (<5%)   |

| Spatial/Scarcity/holdout | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | NcssCount\_Method            |  22080 |      92 |      0.0042 |   0.0127 |   3.05 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Method |  22080 |      92 |      0.0042 |   0.0068 |   1.63 | rare (<5%)   |

| Spatial/Scarcity/holdout | TooManyMethods              |   3085 |      35 |      0.0113 |   0.0241 |   2.12 | rare (<5%)   |

| Chronological/holdout    | NcssCount\_Class             |  14835 |     209 |      0.0141 |   0.0252 |   1.79 | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Class  |  10368 |     168 |      0.0162 |   0.0264 |   1.63 | rare (<5%)   |

| Chronological/holdout    | ExcessivePublicCount        |  11732 |     152 |      0.013  |   0.016  |   1.24 | rare (<5%)   |

| Chronological/holdout    | CouplingBetweenObjects      |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | ExcessiveImports            |      0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | NcssCount\_Method            |  76703 |     348 |      0.0045 |   0.0109 |   2.4  | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Method |  76703 |     348 |      0.0045 |   0.0073 |   1.6  | rare (<5%)   |

| Chronological/holdout    | TooManyMethods              |  10185 |     100 |      0.0098 |   0.0242 |   2.47 | rare (<5%)   |



\--- LIFT (AUC-PR / base\_rate) by rule × source ---

Lift strictly measures how much better the metric ranks over blind guessing.

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| CyclomaticComplexity\_Class  |         1.49 |            1.48 |             1.69 |                  1.27 |                       1.66 |                    1.63 |

| CyclomaticComplexity\_Method |         1.49 |            1.49 |             1.34 |                  1.36 |                       1.63 |                    1.6  |

| ExcessiveImports            |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| ExcessivePublicCount        |         1.2  |            1.23 |             1.84 |                  1.13 |                       1.03 |                    1.24 |

| NcssCount\_Class             |         1.7  |            1.7  |             1.76 |                  1.54 |                       1.88 |                    1.79 |

| NcssCount\_Method            |         2.2  |            2.11 |             1.86 |                  2.01 |                       3.05 |                    2.4  |

| TooManyMethods              |         2.05 |            2.12 |             2.37 |                  1.6  |                       2.12 |                    2.47 |



\--- AUC-PR (absolute) by rule × source ---

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| CyclomaticComplexity\_Class  |       0.0226 |          0.0231 |           0.0316 |                0.0168 |                     0.0226 |                  0.0264 |

| CyclomaticComplexity\_Method |       0.0078 |          0.0081 |           0.0076 |                0.0089 |                     0.0068 |                  0.0073 |

| ExcessiveImports            |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| ExcessivePublicCount        |       0.0148 |          0.0161 |           0.0255 |                0.0127 |                     0.0096 |                  0.016  |

| NcssCount\_Class             |       0.0226 |          0.023  |           0.0283 |                0.0183 |                     0.0239 |                  0.0252 |

| NcssCount\_Method            |       0.0115 |          0.0116 |           0.0105 |                0.0131 |                     0.0127 |                  0.0109 |

| TooManyMethods              |       0.0201 |          0.02   |           0.0262 |                0.0156 |                     0.0241 |                  0.0242 |



================ PER-SOURCE SUMMARY ================

(reliable = n\_pos≥30 AND base\_rate≥0.05)



| Source                   | Max Absolute AUC-PR                | Max Reliable Lift                |

|:-------------------------|:-----------------------------------|:---------------------------------|

| Pooled/all               | 0.023 (NcssCount\_Class)            | — (no statistically stable rule) |

| Spatial/train            | 0.023 (CyclomaticComplexity\_Class) | — (no statistically stable rule) |

| Scarcity/train           | 0.032 (CyclomaticComplexity\_Class) | — (no statistically stable rule) |

| Chronological/train      | 0.018 (NcssCount\_Class)            | — (no statistically stable rule) |

| Spatial/Scarcity/holdout | 0.024 (TooManyMethods)             | — (no statistically stable rule) |

| Chronological/holdout    | 0.026 (CyclomaticComplexity\_Class) | — (no statistically stable rule) |



💾 Saved full diagnostic to: discrimination\_diagnostic\_junit-framework.csv

🏁 Phase 5 Complete. The overarching data structure has been successfully diagnosed.



