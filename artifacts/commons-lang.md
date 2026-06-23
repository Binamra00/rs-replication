Commons Lang:

🚀 Setting up replication environment for commons-lang...

📂 Workspace Root: /content

📦 Data Directory: /content/data/commons-lang

☁️ Downloading commons-lang data from Zenodo...

🗜️ Unzipping data...

✅ Download and extraction complete.



\--- 🎯 Configuration Summary ---

Target Repository:  commons-lang

PMD Data Exists:    True

Refm Data Exists:   True

Lineage Exists:     True

Rel Hist Exists:    True

✅ Phase 0 Complete! You can now execute Phase 1.1.

🚀 Starting Phase 1.1: Data Synchronization Check

📂 Loading Release History Ground Truth...

&#x20;  ✅ Target Releases: 35 official releases found in configuration.



📂 Loading Master Lineage (The SHA Map)...

&#x20;  ✅ Lineage Loaded: 9742 total commits.



🔍 Step 1: Verifying PMD Snapshots...



🔍 Step 2: Verifying Refactoring Miner Ground Truth...

\--------------------------------------------------

📊 DATA SYNCHRONIZATION REPORT

&#x20;  🔹 PMD Snapshots: 35 valid snapshots verified in lineage (Expected at least: 35).

&#x20;  🔹 Refactoring Commits Mapped: 6739

&#x20;  🔹 Refactoring Density: 6751 unique commits contain refactorings.



🧾 PARSE INTEGRITY

&#x20;  - PMD unique SHAs observed (success only): 35

&#x20;  - PMD malformed lines: 0

&#x20;  - PMD failed-status lines skipped: 0

&#x20;  - PMD missing sha: 0

&#x20;  - PMD outside-lineage SHAs: 0

&#x20;  - RefMiner total entries read: 6751

&#x20;  - RefMiner malformed lines: 0

&#x20;  - RefMiner missing sha1: 0



🚀 SUCCESS: The three universes are synchronized!

&#x20;  The PMD observation points and Refactoring events exist on the same timeline.

🏁 Phase 1.1 Complete.

🚀 Starting Phase 1.2: Final Gold Class-Level Alias Graph Generation

⏳ Sorted 6751 commits chronologically to guarantee safe alias resolution.

&#x20;  🔍 Discovered 551 Class Rename path-level aliases.

&#x20;  🔍 Discovered 64 Class Rename basename aliases.



📊 PHASE 1.2 INTEGRITY REPORT:

&#x20;  - Total Path Rename Links:      551

&#x20;  - Total Basename Rename Links:  64

&#x20;  - Distinct Classes Threaded:    488

&#x20;  - Multi-rename links collapsed: 63

&#x20;  - Path Collisions (Preserved):  3

&#x20;  - Basename Collisions:          1

&#x20;  - Malformed/Skipped:            10

&#x20;      \* Missing Location Data: 10



✅ Identity lineage successfully resolved.

&#x20;  💾 Saved path-level graph to: alias\_tracking\_graph\_paths\_commons-lang.csv

&#x20;  💾 Saved basename graph to:   alias\_tracking\_graph\_commons-lang.csv

🏁 Phase 1.2 Complete.

🚀 Starting Phase 1.3: Final Audited Method Alias Graph Generation

⏳ Sorted 6751 commits chronologically for deterministic method alias chaining.

&#x20;  🔍 Discovered 872 method lineage links.

&#x20;  ✅ Method lineage resolved.

&#x20;  💾 Saved to method\_alias\_graph\_commons-lang.csv



📊 PHASE 1.3 INTEGRITY REPORT:

&#x20;  - Total Method Links Mapped: 872

&#x20;  - Collision Overwrites:      1

&#x20;  - Explicitly Skipped / Excluded:

&#x20;      \* Change Parameter Type: 887



&#x20;  ✅ DATA INTEGRITY VERIFIED: 100% Regex match rate on targeted elements.



🏁 Phase 1.3 Complete.

🚀 Starting Phase D.2: Data Flattening \& Regex Rescue (With Alias Resolution)

⏳ Building PMD Method-Name Resolver from Phase 1.3 Graph...

⏳ Loading Timelines and Mapping Ground Truth (Early Binding)...



📉 THE DATA ATTRITION FUNNEL (Ground Truth Mapping):

&#x20;  🧩 Raw Taxonomy-Matched Refactorings: 1624

&#x20;  📌 Total leftSideLocations (all matched refs): 5492

&#x20;  🔍 Total Structural Operations Found: 1935

&#x20;  🛡️  Test Files Purged (Regex Filter):  922

&#x20;  ✅ Production Refactorings Retained (location-level):  1013

&#x20;  🎯 Mappable retained locations (pre-dedup): 778

&#x20;  🔗 Unique mapped supervision keys (post-dedup): 422

&#x20;       ├─ God Class    (class-level):  190

&#x20;       └─ Long Method  (method-level): 232

&#x20;  ♻️  Dedup/compression delta: 356

&#x20;  ⚠️ Refactorings dropped (missing from lineage gap): 12



✅ Flattened PMD Data: 221,351 raw metric records extracted.



🚫 Excluded-rule rows dropped from dataset (reported as a finding):

&#x20;     - CouplingBetweenObjects      :    2,449 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveImports            :    3,974 rows  (coupling metric; out of size+complexity scope)

&#x20;     - ExcessiveParameterList      :   75,589 rows  (no method signature → unmappable)

&#x20;     - TooManyFields               :      730 rows  (no metric value/range emitted)



🔍 DIAGNOSTIC: Checking for Zero-Refactoring Releases across the entire timeline...

&#x20;  ⚠️ WARNING: Found 13 releases with ZERO mapped refactoring events.

&#x20;  (These releases will likely be dropped during downstream Top-K or F-score evaluations).

&#x20;     - Release 1/35 : 010845ae7b145637882f425b10552befeb77fdd3

&#x20;     - Release 2/35 : 6a3b1617c312199c4dc6fad4b55bc9e47fb4f7a1

&#x20;     - Release 3/35 : c2d14ce1e65eb3f243a362137b48112076620d08

&#x20;     - Release 4/35 : d6535dd5fe2e6129f1cea78f6a90997470cfa543

&#x20;     - Release 5/35 : e1e9d4d7c84809fea2f91d600d29f4a65cffb1d4

&#x20;     - Release 6/35 : e358f2112a6a1bb453c70227fe8ab82b88dffa16

&#x20;     - Release 10/35 : f4853044131835912df73c0ea2598fe493151b9d

&#x20;     - Release 13/35 : c61e891a65763f566722b27dca9580c9bcddc426

&#x20;     - Release 15/35 : af2986309044fd663a1b5ced2b400a1edc353278

&#x20;     - Release 16/35 : 8cbc5815f783dfa226d12315577e965222bc0af6

&#x20;     - Release 22/35 : 9801e2fb9fcbf7ddd19221e9342608940d778f8c

&#x20;     - Release 23/35 : eb5b11a25c9e61f9b25a540682816ebb103b735c

&#x20;     - Release 31/35 : 6a2a10d88885343cfe37c1d9fa42ac5edda7cab5

\-------------------------------------------------------------------------------------



&#x20;  ⚠️ Dropped unrecoverable metric rows: 5035



🏁 Phase D.2 Complete! Saved flat dataset to pmd\_flat\_commons-lang.csv

Note: Train/Test splitting happens in Phase T.2.



📊 POST-FLATTENING DATASET AUDIT:

&#x20;  - Total Observations: 221,351

&#x20;  - Positive Refactoring Labels: 2,340

&#x20;  - Negative Observations: 219,011

&#x20;  - Class Imbalance Ratio: 93.59:1

&#x20;  - Unique Files Tracked: 230

&#x20;  - Unique Commits (Snapshots) Tracked: 35

&#x20;  - Missing/Null Metric Values: 0



&#x20;  - Row Count by Rule Type:

&#x20;      \* CyclomaticComplexity\_Method: 99,616

&#x20;      \* NcssCount\_Method         : 99,616

&#x20;      \* NcssCount\_Class          : 8,054

&#x20;      \* ExcessivePublicCount     : 7,209

&#x20;      \* CyclomaticComplexity\_Class: 6,856



✅ Dataset audit passed: Structure is valid and data is balanced.

&#x20;Audit loaded: 221,351 records for commons-lang



PER-RULE VERDICTS:

&#x20;                      rule      verdict  peak\_rate

&#x20;           NcssCount\_Class    ambiguous   0.071535

&#x20;CyclomaticComplexity\_Class    ambiguous   0.063047

&#x20;      ExcessivePublicCount    ambiguous   0.067657

&#x20;          NcssCount\_Method monotonic\_up   0.015569

CyclomaticComplexity\_Method       peaked   0.017880

🚀 Starting Phase B.2: Structural Validation Split (80/20 Stratified)



📊 Executing Stratified Group K-Fold (Canonical Integrity at \~80/20)...

&#x20;  - Training Set (86.5% actual): 191,500 metric rows | 191 Unique Refactoring Events

&#x20;  - Testing Set  (13.5% actual): 29,851 metric rows | 39 Unique Refactoring Events



🔍 Checking per-rule positive event densities (Rule Viability)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=267, test\_pos=42

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=243, test\_pos=40

&#x20;  ✅ ExcessivePublicCount           : train\_pos=249, test\_pos=31

&#x20;  ✅ NcssCount\_Method               : train\_pos=713, test\_pos=21

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=713, test\_pos=21



📊 Executing Inner Stratified Group Split for K-Fold IDs...



💾 Saving master datasets to disk...

&#x20;  ✅ Saved Training Set: b2\_train\_spatial\_80\_commons-lang.csv

&#x20;  ✅ Saved Testing Set:  b2\_test\_spatial\_20\_commons-lang.csv



🏁 Phase B.2 Complete. The Data Engine has secured and saved the stratified 80/20 splits!

🚀 Starting Phase E.2: Data Scarcity Branch (True Locked Holdout Architecture)



📊 Isolating the Baseline Test Set (Extracting B.2 holdout via Basenames)...

📊 Starving the Training Set (Simulating Target 20% Total Data Scarcity)...



🧾 E.2 SPLIT GEOMETRY EXPLAINER

&#x20;  - Baseline outer split realized: Train 86.5% | Test 13.5% of total rows

&#x20;  - Scarcity train is 27.5% of baseline-train rows

&#x20;  - Therefore scarcity train is 23.7% of total rows (target was 20.0%)



&#x20;  - Scarcity Training Set (23.7% actual, \~20.0% target): 52,567 metric rows | 57 Unique File-Release Events

&#x20;  - Locked Testing Set (constant baseline holdout): 29,851 metric rows | 39 Unique File-Release Events

&#x20;  - Scarcity event density: 0.001084 events/row

&#x20;  - Locked-test event density: 0.001306 events/row



🔍 Checking per-rule positive event densities (Rule Viability under Scarcity)...

&#x20;  ✅ NcssCount\_Class                : train\_pos=117, test\_pos=42

&#x20;  ✅ CyclomaticComplexity\_Class     : train\_pos=109, test\_pos=40

&#x20;  ✅ ExcessivePublicCount           : train\_pos=116, test\_pos=31

&#x20;  ✅ NcssCount\_Method               : train\_pos=157, test\_pos=21

&#x20;  ✅ CyclomaticComplexity\_Method    : train\_pos=157, test\_pos=21



📊 Executing Inner Stratified Group Split for E.3 K-Fold IDs...

&#x20;  ✅ Leakage Assertion Passed: Absolute spatial isolation confirmed.



💾 Saving Scarcity Training dataset to disk...

&#x20;  ✅ Saved Scarcity Training Set: e2\_train\_scarcity\_commons-lang.csv

&#x20;  ✅ Locked Testing Set is preserved at: b2\_test\_spatial\_20\_commons-lang.csv



🏁 Phase E.2 Complete. The Scarcity Data Engine has secured the true locked splits!

🚀 Starting Phase T.2: Chronological Branch (True Git Time-Series Split)



⚠️ MSR Attrition Note: You targeted \~35 official releases from GitHub.

⚠️ PMD parsed 35 releases. The missing 0 failed upstream static analysis.



⏳ Loading true Git commit timestamps to guarantee time-travel protection...



📊 T.2 Dataset Split Breakdown (50/50):

&#x20;  - Total PMD Releases: 35

&#x20;  - T.2 Training Releases (The Past):   17

&#x20;  - T.2 Testing Releases  (The Future): 18

&#x20;  - ⏱️ TRUE Temporal Boundary Lock: Release 17 (Git Timestamp: 1396785931)



&#x20;  - T.2 Training Set (34.2% actual metric rows): 75693 total rows

&#x20;  - T.2 Testing Set  (65.8% actual metric rows): 145658 total rows



&#x20;  🔍 Temporal Imbalance Check:

&#x20;     - Past Refactored Rows:   1009

&#x20;     - Future Refactored Rows: 1331



🔍 Checking per-rule positive densities (Past vs Future)...

&#x20;  ✅ NcssCount\_Class                : past\_pos=275 , future\_pos=34

&#x20;  ✅ CyclomaticComplexity\_Class     : past\_pos=260 , future\_pos=23

&#x20;  ✅ ExcessivePublicCount           : past\_pos=256 , future\_pos=24

&#x20;  ✅ NcssCount\_Method               : past\_pos=109 , future\_pos=625

&#x20;  ✅ CyclomaticComplexity\_Method    : past\_pos=109 , future\_pos=625



💾 Saved Temporal Training Set: t2\_train\_chrono\_50\_commons-lang.csv

💾 Saved Temporal Testing Set: t2\_test\_chrono\_50\_commons-lang.csv

&#x20;  ✅ Robust chronological splitting validated successfully!

🏁 Phase T.2 Complete. The timeline has been permanently split (No spatial shuffling applied).

🔎 Running T.2 True Chronological Sanity Check...

&#x20;  ✅ Split matrices successfully loaded from disk (No corruption).

&#x20;  ✅ Release counts verified (Past/Train: 17, Future/Test: 18).

&#x20;  ✅ Zero data leakage detected (Past and Future releases are strictly mutually exclusive).

&#x20;  ✅ Chronological boundary mathematically verified via Git History (Max Past TS: 1396785931 < Min Future TS: 1428064096).



📁 Step 4: System Evolution \& Temporal Overlap (T.2 Split)

&#x20;     - Canonical identities in the Past (Train):            145

&#x20;     - Canonical identities in the Future (Test):           207

&#x20;     - Identities persisting across the split (Overlap):    122

&#x20;     - Identities retired/deleted before Future phase:      23

&#x20;     - New identities introduced in Future phase:           85

&#x20;     🎯 Percentage of Future Architecture seen in the Past: 58.94%



🏁 Audit Complete. The T.2 Chronological Split is academically secure and verified.

🚀 Starting Phase B.3: Multi-Percentile Sweep Analysis (Optimized \& Guarded)

📊 Loaded Training Set with 186 canonical entities ready for K-Fold Calibration.



📈 Executing 5-Fold Cross-Validation Tournament...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...

&#x20;  ⚙️ Processing Fold 4 as Validation...

&#x20;  ⚙️ Processing Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                       | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                        | 90th                        | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|:----------------------------|:----------------------------|

| NcssCount\_Class             | 2 (P:0.04|R:0.95|F1:0.07) | 6 (P:0.04|R:0.86|F1:0.08) | 10 (P:0.04|R:0.73|F1:0.08) | 13 (P:0.05|R:0.68|F1:0.08) | 15 (P:0.04|R:0.56|F1:0.07) | 19 (P:0.04|R:0.50|F1:0.08) | 48 (P:0.05|R:0.45|F1:0.09) | 88 (P:0.06|R:0.28|F1:0.09) | 202 (P:0.07|R:0.18|F1:0.10) | 290 (P:0.06|R:0.11|F1:0.07) | 597 (P:0.05|R:0.05|F1:0.05) |

| CyclomaticComplexity\_Class  | 2 (P:0.04|R:0.96|F1:0.08) | 3 (P:0.04|R:0.89|F1:0.08) | 4 (P:0.04|R:0.79|F1:0.08)  | 5 (P:0.04|R:0.71|F1:0.08)  | 6 (P:0.04|R:0.64|F1:0.08)  | 10 (P:0.05|R:0.55|F1:0.09) | 24 (P:0.06|R:0.46|F1:0.11) | 42 (P:0.06|R:0.34|F1:0.10) | 88 (P:0.06|R:0.17|F1:0.09)  | 132 (P:0.06|R:0.13|F1:0.07) | 220 (P:0.04|R:0.07|F1:0.05) |

| ExcessivePublicCount        | 1 (P:0.04|R:1.00|F1:0.07) | 1 (P:0.04|R:0.85|F1:0.07) | 2 (P:0.04|R:0.72|F1:0.07)  | 3 (P:0.04|R:0.65|F1:0.08)  | 3 (P:0.04|R:0.64|F1:0.08)  | 4 (P:0.05|R:0.56|F1:0.08)  | 10 (P:0.06|R:0.44|F1:0.10) | 18 (P:0.06|R:0.29|F1:0.10) | 26 (P:0.05|R:0.16|F1:0.07)  | 32 (P:0.04|R:0.12|F1:0.06)  | 55 (P:0.06|R:0.08|F1:0.07)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:1.00|F1:0.02) | 2 (P:0.01|R:1.00|F1:0.02) | 3 (P:0.01|R:0.77|F1:0.02)  | 4 (P:0.01|R:0.66|F1:0.03)  | 4 (P:0.01|R:0.55|F1:0.02)  | 6 (P:0.01|R:0.47|F1:0.03)  | 8 (P:0.01|R:0.32|F1:0.03)  | 10 (P:0.01|R:0.27|F1:0.03) | 12 (P:0.01|R:0.17|F1:0.02)  | 14 (P:0.01|R:0.12|F1:0.02)  | 17 (P:0.01|R:0.07|F1:0.02)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:1.00|F1:0.02) | 1 (P:0.01|R:0.92|F1:0.02)  | 2 (P:0.01|R:0.74|F1:0.03)  | 3 (P:0.02|R:0.63|F1:0.03)  | 3 (P:0.02|R:0.60|F1:0.03)  | 4 (P:0.02|R:0.40|F1:0.03)  | 5 (P:0.01|R:0.29|F1:0.03)  | 5 (P:0.01|R:0.20|F1:0.02)   | 7 (P:0.01|R:0.12|F1:0.02)   | 9 (P:0.01|R:0.07|F1:0.01)   |

| TooManyMethods              | 1 (P:0.03|R:0.97|F1:0.07) | 3 (P:0.04|R:0.85|F1:0.07) | 6 (P:0.04|R:0.76|F1:0.08)  | 9 (P:0.05|R:0.67|F1:0.09)  | 11 (P:0.05|R:0.57|F1:0.09) | 16 (P:0.05|R:0.47|F1:0.09) | 17 (P:0.05|R:0.36|F1:0.08) | 21 (P:0.05|R:0.27|F1:0.08) | 40 (P:0.07|R:0.16|F1:0.09)  | 43 (P:0.05|R:0.11|F1:0.07)  | 85 (P:0.03|R:0.05|F1:0.04)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                         | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                          | 90th                          | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|:------------------------------|:------------------------------|

| NcssCount\_Class             | 2 (P:0.04|R:0.95|F0.5:0.05) | 6 (P:0.04|R:0.86|F0.5:0.05) | 10 (P:0.04|R:0.73|F0.5:0.06) | 13 (P:0.05|R:0.68|F0.5:0.06) | 15 (P:0.04|R:0.56|F0.5:0.05) | 19 (P:0.04|R:0.50|F0.5:0.05) | 48 (P:0.05|R:0.45|F0.5:0.07) | 88 (P:0.06|R:0.28|F0.5:0.07) | 202 (P:0.07|R:0.18|F0.5:0.08) | 290 (P:0.06|R:0.11|F0.5:0.06) | 597 (P:0.05|R:0.05|F0.5:0.05) |

| CyclomaticComplexity\_Class  | 2 (P:0.04|R:0.96|F0.5:0.05) | 3 (P:0.04|R:0.89|F0.5:0.05) | 4 (P:0.04|R:0.79|F0.5:0.05)  | 5 (P:0.04|R:0.71|F0.5:0.05)  | 6 (P:0.04|R:0.64|F0.5:0.05)  | 10 (P:0.05|R:0.55|F0.5:0.06) | 24 (P:0.06|R:0.46|F0.5:0.07) | 42 (P:0.06|R:0.34|F0.5:0.08) | 88 (P:0.06|R:0.17|F0.5:0.07)  | 132 (P:0.06|R:0.13|F0.5:0.06) | 220 (P:0.04|R:0.07|F0.5:0.04) |

| ExcessivePublicCount        | 1 (P:0.04|R:1.00|F0.5:0.05) | 1 (P:0.04|R:0.85|F0.5:0.05) | 2 (P:0.04|R:0.72|F0.5:0.05)  | 3 (P:0.04|R:0.65|F0.5:0.05)  | 3 (P:0.04|R:0.64|F0.5:0.05)  | 4 (P:0.05|R:0.56|F0.5:0.06)  | 10 (P:0.06|R:0.44|F0.5:0.07) | 18 (P:0.06|R:0.29|F0.5:0.07) | 26 (P:0.05|R:0.16|F0.5:0.06)  | 32 (P:0.04|R:0.12|F0.5:0.05)  | 55 (P:0.06|R:0.08|F0.5:0.06)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:1.00|F0.5:0.01) | 2 (P:0.01|R:1.00|F0.5:0.01) | 3 (P:0.01|R:0.77|F0.5:0.02)  | 4 (P:0.01|R:0.66|F0.5:0.02)  | 4 (P:0.01|R:0.55|F0.5:0.01)  | 6 (P:0.01|R:0.47|F0.5:0.02)  | 8 (P:0.01|R:0.32|F0.5:0.02)  | 10 (P:0.01|R:0.27|F0.5:0.02) | 12 (P:0.01|R:0.17|F0.5:0.02)  | 14 (P:0.01|R:0.12|F0.5:0.01)  | 17 (P:0.01|R:0.07|F0.5:0.01)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:0.92|F0.5:0.01)  | 2 (P:0.01|R:0.74|F0.5:0.02)  | 3 (P:0.02|R:0.63|F0.5:0.02)  | 3 (P:0.02|R:0.60|F0.5:0.02)  | 4 (P:0.02|R:0.40|F0.5:0.02)  | 5 (P:0.01|R:0.29|F0.5:0.02)  | 5 (P:0.01|R:0.20|F0.5:0.01)   | 7 (P:0.01|R:0.12|F0.5:0.01)   | 9 (P:0.01|R:0.07|F0.5:0.01)   |

| TooManyMethods              | 1 (P:0.03|R:0.97|F0.5:0.04) | 3 (P:0.04|R:0.85|F0.5:0.05) | 6 (P:0.04|R:0.76|F0.5:0.05)  | 9 (P:0.05|R:0.67|F0.5:0.06)  | 11 (P:0.05|R:0.57|F0.5:0.06) | 16 (P:0.05|R:0.47|F0.5:0.06) | 17 (P:0.05|R:0.36|F0.5:0.06) | 21 (P:0.05|R:0.27|F0.5:0.06) | 40 (P:0.07|R:0.16|F0.5:0.08)  | 43 (P:0.05|R:0.11|F0.5:0.06)  | 85 (P:0.03|R:0.05|F0.5:0.03)  |



🏆 F1-Optimized Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 85th         |               202 |               202 |         0.0958 |             1.86 |      0.038  |            5 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 65th         |                24 |                42 |         0.1063 |             1.49 |      0.0414 |            5 |

| ExcessivePublicCount        | True         | True               | False         | 75th         |                18 |                18 |         0.0994 |             1.57 |      0.039  |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | False              | False         | 55th         |                 6 |                17 |         0.0273 |             1.69 |      0.0083 |            5 |

| CyclomaticComplexity\_Method | True         | False              | False         | 65th         |                 4 |                 9 |         0.0316 |             1.99 |      0.0083 |            5 |

| TooManyMethods              | True         | True               | False         | 85th         |                40 |                40 |         0.094  |             2.2  |      0.033  |            5 |



🎯 Precision-Optimized (F0.5) Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 85th         |               202 |               202 |           0.0784 |             1.86 |      0.038  |            5 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 75th         |                42 |               132 |           0.0753 |             1.54 |      0.0414 |            5 |

| ExcessivePublicCount        | True         | False              | False         | 75th         |                18 |                55 |           0.0723 |             1.57 |      0.039  |            5 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | False              | False         | 55th         |                 6 |                17 |           0.0174 |             1.69 |      0.0083 |            5 |

| CyclomaticComplexity\_Method | True         | False              | False         | 65th         |                 4 |                 9 |           0.0204 |             1.99 |      0.0083 |            5 |

| TooManyMethods              | True         | True               | False         | 85th         |                40 |                40 |           0.0791 |             2.2  |      0.033  |            5 |



💾 Saved Dual Baseline locked thresholds to disk: /content/b3\_inflection\_thresholds\_commons-lang\_locked.json

🏁 Phase B.3 Complete.

🚀 Starting Phase E.3: Multi-Percentile Sweep Analysis (Scarcity Edition)

📊 Loaded Scarcity Training Set (20%) with 47 canonical entities.



📈 Executing 3-Fold Cross-Validation Tournament (Scarcity)...

&#x20;  ⚙️ Processing Fold 1 as Validation...

&#x20;  ⚙️ Processing Fold 2 as Validation...

&#x20;  ⚙️ Processing Fold 3 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                       | 35th                       | 45th                       | 55th                       | 65th                       | 75th                       | 85th                       | 90th                        | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|:----------------------------|

| NcssCount\_Class             | 3 (P:0.04|R:0.97|F1:0.08) | 8 (P:0.04|R:0.83|F1:0.08) | 11 (P:0.04|R:0.78|F1:0.08) | 13 (P:0.04|R:0.75|F1:0.08) | 14 (P:0.04|R:0.53|F1:0.06) | 17 (P:0.04|R:0.50|F1:0.06) | 25 (P:0.04|R:0.49|F1:0.06) | 46 (P:0.04|R:0.46|F1:0.07) | 77 (P:0.05|R:0.27|F1:0.08) | 229 (P:0.05|R:0.19|F1:0.06) | 445 (P:0.05|R:0.10|F1:0.04) |

| CyclomaticComplexity\_Class  | 3 (P:0.04|R:0.95|F1:0.08) | 3 (P:0.04|R:0.81|F1:0.08) | 4 (P:0.04|R:0.81|F1:0.08)  | 5 (P:0.04|R:0.78|F1:0.08)  | 5 (P:0.04|R:0.56|F1:0.07)  | 6 (P:0.04|R:0.50|F1:0.06)  | 10 (P:0.04|R:0.49|F1:0.06) | 22 (P:0.04|R:0.47|F1:0.07) | 38 (P:0.05|R:0.21|F1:0.07) | 122 (P:0.03|R:0.17|F1:0.04) | 136 (P:0.02|R:0.17|F1:0.04) |

| ExcessivePublicCount        | 1 (P:0.03|R:0.76|F1:0.07) | 2 (P:0.04|R:0.76|F1:0.07) | 2 (P:0.04|R:0.76|F1:0.07)  | 2 (P:0.04|R:0.76|F1:0.07)  | 3 (P:0.03|R:0.50|F1:0.06)  | 3 (P:0.03|R:0.49|F1:0.06)  | 4 (P:0.04|R:0.49|F1:0.06)  | 13 (P:0.05|R:0.49|F1:0.08) | 22 (P:0.04|R:0.21|F1:0.07) | 25 (P:0.04|R:0.14|F1:0.05)  | 32 (P:0.01|R:0.08|F1:0.02)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         |

| NcssCount\_Method            | 2 (P:0.01|R:1.00|F1:0.01) | 2 (P:0.01|R:0.82|F1:0.01) | 3 (P:0.01|R:0.60|F1:0.02)  | 3 (P:0.01|R:0.60|F1:0.02)  | 4 (P:0.01|R:0.59|F1:0.02)  | 5 (P:0.01|R:0.57|F1:0.02)  | 6 (P:0.01|R:0.54|F1:0.02)  | 10 (P:0.01|R:0.31|F1:0.02) | 13 (P:0.01|R:0.22|F1:0.02) | 17 (P:0.01|R:0.06|F1:0.01)  | 24 (P:0.01|R:0.06|F1:0.01)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F1:0.01) | 1 (P:0.01|R:1.00|F1:0.01) | 2 (P:0.01|R:0.72|F1:0.02)  | 3 (P:0.01|R:0.66|F1:0.03)  | 3 (P:0.01|R:0.66|F1:0.03)  | 4 (P:0.01|R:0.28|F1:0.02)  | 4 (P:0.01|R:0.28|F1:0.02)  | 6 (P:0.01|R:0.22|F1:0.02)  | 8 (P:0.02|R:0.22|F1:0.03)  | 9 (P:0.01|R:0.10|F1:0.01)   | 9 (P:0.01|R:0.06|F1:0.01)   |

| TooManyMethods              | 5 (P:0.04|R:0.83|F1:0.08) | 6 (P:0.04|R:0.79|F1:0.08) | 8 (P:0.04|R:0.66|F1:0.08)  | 11 (P:0.05|R:0.64|F1:0.09) | 15 (P:0.05|R:0.59|F1:0.10) | 17 (P:0.05|R:0.43|F1:0.08) | 19 (P:0.04|R:0.34|F1:0.07) | 20 (P:0.04|R:0.34|F1:0.08) | 22 (P:0.04|R:0.26|F1:0.07) | 31 (P:0.02|R:0.09|F1:0.03)  | 32 (P:0.02|R:0.09|F1:0.03)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                         | 35th                         | 45th                         | 55th                         | 65th                         | 75th                         | 85th                         | 90th                          | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|:------------------------------|

| NcssCount\_Class             | 3 (P:0.04|R:0.97|F0.5:0.05) | 8 (P:0.04|R:0.83|F0.5:0.05) | 11 (P:0.04|R:0.78|F0.5:0.05) | 13 (P:0.04|R:0.75|F0.5:0.05) | 14 (P:0.04|R:0.53|F0.5:0.04) | 17 (P:0.04|R:0.50|F0.5:0.04) | 25 (P:0.04|R:0.49|F0.5:0.04) | 46 (P:0.04|R:0.46|F0.5:0.05) | 77 (P:0.05|R:0.27|F0.5:0.06) | 229 (P:0.05|R:0.19|F0.5:0.05) | 445 (P:0.05|R:0.10|F0.5:0.04) |

| CyclomaticComplexity\_Class  | 3 (P:0.04|R:0.95|F0.5:0.05) | 3 (P:0.04|R:0.81|F0.5:0.05) | 4 (P:0.04|R:0.81|F0.5:0.05)  | 5 (P:0.04|R:0.78|F0.5:0.05)  | 5 (P:0.04|R:0.56|F0.5:0.04)  | 6 (P:0.04|R:0.50|F0.5:0.04)  | 10 (P:0.04|R:0.49|F0.5:0.04) | 22 (P:0.04|R:0.47|F0.5:0.05) | 38 (P:0.05|R:0.21|F0.5:0.05) | 122 (P:0.03|R:0.17|F0.5:0.03) | 136 (P:0.02|R:0.17|F0.5:0.02) |

| ExcessivePublicCount        | 1 (P:0.03|R:0.76|F0.5:0.04) | 2 (P:0.04|R:0.76|F0.5:0.04) | 2 (P:0.04|R:0.76|F0.5:0.04)  | 2 (P:0.04|R:0.76|F0.5:0.04)  | 3 (P:0.03|R:0.50|F0.5:0.04)  | 3 (P:0.03|R:0.49|F0.5:0.04)  | 4 (P:0.04|R:0.49|F0.5:0.04)  | 13 (P:0.05|R:0.49|F0.5:0.06) | 22 (P:0.04|R:0.21|F0.5:0.05) | 25 (P:0.04|R:0.14|F0.5:0.04)  | 32 (P:0.01|R:0.08|F0.5:0.02)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           |

| NcssCount\_Method            | 2 (P:0.01|R:1.00|F0.5:0.01) | 2 (P:0.01|R:0.82|F0.5:0.01) | 3 (P:0.01|R:0.60|F0.5:0.01)  | 3 (P:0.01|R:0.60|F0.5:0.01)  | 4 (P:0.01|R:0.59|F0.5:0.01)  | 5 (P:0.01|R:0.57|F0.5:0.01)  | 6 (P:0.01|R:0.54|F0.5:0.02)  | 10 (P:0.01|R:0.31|F0.5:0.01) | 13 (P:0.01|R:0.22|F0.5:0.02) | 17 (P:0.01|R:0.06|F0.5:0.01)  | 24 (P:0.01|R:0.06|F0.5:0.01)  |

| CyclomaticComplexity\_Method | 1 (P:0.01|R:1.00|F0.5:0.01) | 1 (P:0.01|R:1.00|F0.5:0.01) | 2 (P:0.01|R:0.72|F0.5:0.01)  | 3 (P:0.01|R:0.66|F0.5:0.02)  | 3 (P:0.01|R:0.66|F0.5:0.02)  | 4 (P:0.01|R:0.28|F0.5:0.02)  | 4 (P:0.01|R:0.28|F0.5:0.02)  | 6 (P:0.01|R:0.22|F0.5:0.01)  | 8 (P:0.02|R:0.22|F0.5:0.02)  | 9 (P:0.01|R:0.10|F0.5:0.01)   | 9 (P:0.01|R:0.06|F0.5:0.01)   |

| TooManyMethods              | 5 (P:0.04|R:0.83|F0.5:0.05) | 6 (P:0.04|R:0.79|F0.5:0.05) | 8 (P:0.04|R:0.66|F0.5:0.05)  | 11 (P:0.05|R:0.64|F0.5:0.06) | 15 (P:0.05|R:0.59|F0.5:0.06) | 17 (P:0.05|R:0.43|F0.5:0.06) | 19 (P:0.04|R:0.34|F0.5:0.05) | 20 (P:0.04|R:0.34|F0.5:0.05) | 22 (P:0.04|R:0.26|F0.5:0.05) | 31 (P:0.02|R:0.09|F0.5:0.02)  | 32 (P:0.02|R:0.09|F0.5:0.02)  |



🏆 F1-Optimized Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 35th         |                13 |                77 |         0.0815 |             1.16 |      0.0377 |            3 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 35th         |                 5 |                38 |         0.0823 |             1.09 |      0.0402 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 75th         |                13 |                13 |         0.0776 |             1.18 |      0.0396 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                13 |                13 |         0.0243 |             2.49 |      0.0053 |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 85th         |                 8 |                 8 |         0.0282 |             2.93 |      0.0053 |            3 |

| TooManyMethods              | True         | True               | False         | 45th         |                15 |                15 |         0.0969 |             1.55 |      0.0342 |            2 |



🎯 Precision-Optimized (F0.5) Scarcity Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | False              | False         | 85th         |                77 |               445 |           0.06   |             1.43 |      0.0377 |            3 |

| CyclomaticComplexity\_Class  | True         | False              | False         | 35th         |                 5 |                38 |           0.054  |             1.09 |      0.0402 |            3 |

| ExcessivePublicCount        | True         | True               | False         | 75th         |                13 |                22 |           0.0555 |             1.18 |      0.0396 |            3 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 85th         |                13 |                24 |           0.0162 |             2.49 |      0.0053 |            3 |

| CyclomaticComplexity\_Method | True         | True               | False         | 85th         |                 8 |                 9 |           0.019  |             2.93 |      0.0053 |            3 |

| TooManyMethods              | True         | True               | False         | 45th         |                15 |                22 |           0.0649 |             1.55 |      0.0342 |            2 |



💾 Saved Dual Baseline locked thresholds to disk: /content/e3\_inflection\_thresholds\_commons-lang\_scarcity.json

🏁 Phase E.3 Complete.

🚀 Starting Phase T.3: Chronological K-Fold Calibration Engine

📊 Loaded Temporal Training Set (The Past) with 145 canonical entities.



📈 Executing 5-Fold Cross-Validation Tournament (Chronological; n\_splits=5)...

&#x20;  ⚙️ Processing Temporal Fold 1 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 2 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 3 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 4 as Validation...

&#x20;  ⚙️ Processing Temporal Fold 5 as Validation...



🔍 Standard F1 Sweep Matrix \[ Int Threshold (P | R | F1) ]:

| Rule                        | 5th                       | 15th                      | 25th                       | 35th                       | 45th                       | 55th                       | 65th                       | 75th                        | 85th                        | 90th                        | 95th                        |

|:----------------------------|:--------------------------|:--------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:---------------------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|

| NcssCount\_Class             | 4 (P:0.31|R:0.92|F1:0.40) | 8 (P:0.31|R:0.85|F1:0.40) | 13 (P:0.31|R:0.69|F1:0.37) | 15 (P:0.29|R:0.52|F1:0.33) | 25 (P:0.27|R:0.33|F1:0.28) | 46 (P:0.26|R:0.25|F1:0.25) | 71 (P:0.26|R:0.19|F1:0.21) | 105 (P:0.28|R:0.16|F1:0.19) | 237 (P:0.30|R:0.09|F1:0.12) | 289 (P:0.31|R:0.07|F1:0.10) | 475 (P:0.31|R:0.03|F1:0.05) |

| CyclomaticComplexity\_Class  | 2 (P:0.31|R:0.95|F1:0.41) | 3 (P:0.31|R:0.92|F1:0.40) | 5 (P:0.31|R:0.74|F1:0.37)  | 6 (P:0.28|R:0.46|F1:0.32)  | 11 (P:0.27|R:0.33|F1:0.28) | 23 (P:0.26|R:0.25|F1:0.25) | 33 (P:0.26|R:0.19|F1:0.21) | 47 (P:0.27|R:0.15|F1:0.18)  | 97 (P:0.30|R:0.09|F1:0.12)  | 133 (P:0.25|R:0.04|F1:0.07) | 186 (P:0.29|R:0.02|F1:0.04) |

| ExcessivePublicCount        | 1 (P:0.32|R:1.00|F1:0.42) | 2 (P:0.32|R:0.92|F1:0.41) | 3 (P:0.30|R:0.65|F1:0.36)  | 3 (P:0.30|R:0.65|F1:0.36)  | 6 (P:0.26|R:0.30|F1:0.27)  | 10 (P:0.26|R:0.25|F1:0.25) | 13 (P:0.26|R:0.21|F1:0.22) | 22 (P:0.27|R:0.15|F1:0.18)  | 27 (P:0.29|R:0.10|F1:0.13)  | 34 (P:0.28|R:0.04|F1:0.07)  | 50 (P:0.27|R:0.02|F1:0.05)  |

| CouplingBetweenObjects      | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         | N/A                         | N/A                         |

| ExcessiveImports            | N/A                       | N/A                       | N/A                        | N/A                        | N/A                        | N/A                        | N/A                        | N/A                         | N/A                         | N/A                         | N/A                         |

| NcssCount\_Method            | 3 (P:0.01|R:0.80|F1:0.02) | 3 (P:0.01|R:0.80|F1:0.02) | 4 (P:0.01|R:0.80|F1:0.02)  | 4 (P:0.01|R:0.80|F1:0.02)  | 4 (P:0.01|R:0.80|F1:0.02)  | 4 (P:0.01|R:0.80|F1:0.02)  | 4 (P:0.01|R:0.80|F1:0.02)  | 10 (P:0.02|R:0.34|F1:0.03)  | 13 (P:0.01|R:0.14|F1:0.03)  | 15 (P:0.00|R:0.02|F1:0.00)  | 19 (P:0.00|R:0.02|F1:0.01)  |

| CyclomaticComplexity\_Method | 2 (P:0.01|R:0.78|F1:0.02) | 3 (P:0.01|R:0.56|F1:0.02) | 3 (P:0.01|R:0.56|F1:0.02)  | 3 (P:0.01|R:0.56|F1:0.03)  | 3 (P:0.01|R:0.56|F1:0.03)  | 4 (P:0.01|R:0.45|F1:0.03)  | 4 (P:0.01|R:0.28|F1:0.02)  | 5 (P:0.01|R:0.20|F1:0.02)   | 7 (P:0.01|R:0.14|F1:0.02)   | 7 (P:0.02|R:0.13|F1:0.03)   | 11 (P:0.00|R:0.01|F1:0.00)  |

| TooManyMethods              | 1 (P:0.51|R:1.00|F1:0.67) | 6 (P:0.52|R:0.81|F1:0.63) | 6 (P:0.52|R:0.81|F1:0.63)  | 8 (P:0.52|R:0.73|F1:0.61)  | 13 (P:0.52|R:0.47|F1:0.49) | 16 (P:0.52|R:0.42|F1:0.47) | 17 (P:0.51|R:0.33|F1:0.40) | 20 (P:0.55|R:0.20|F1:0.29)  | 31 (P:0.61|R:0.14|F1:0.22)  | 40 (P:0.64|R:0.11|F1:0.19)  | 53 (P:0.67|R:0.05|F1:0.09)  |



🎯 Precision-Optimized Sweep Matrix \[ Int Threshold (P | R | F0.5) ]:

| Rule                        | 5th                         | 15th                        | 25th                         | 35th                         | 45th                         | 55th                         | 65th                         | 75th                          | 85th                          | 90th                          | 95th                          |

|:----------------------------|:----------------------------|:----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:-----------------------------|:------------------------------|:------------------------------|:------------------------------|:------------------------------|

| NcssCount\_Class             | 4 (P:0.31|R:0.92|F0.5:0.34) | 8 (P:0.31|R:0.85|F0.5:0.34) | 13 (P:0.31|R:0.69|F0.5:0.33) | 15 (P:0.29|R:0.52|F0.5:0.30) | 25 (P:0.27|R:0.33|F0.5:0.27) | 46 (P:0.26|R:0.25|F0.5:0.25) | 71 (P:0.26|R:0.19|F0.5:0.24) | 105 (P:0.28|R:0.16|F0.5:0.23) | 237 (P:0.30|R:0.09|F0.5:0.18) | 289 (P:0.31|R:0.07|F0.5:0.15) | 475 (P:0.31|R:0.03|F0.5:0.10) |

| CyclomaticComplexity\_Class  | 2 (P:0.31|R:0.95|F0.5:0.34) | 3 (P:0.31|R:0.92|F0.5:0.34) | 5 (P:0.31|R:0.74|F0.5:0.33)  | 6 (P:0.28|R:0.46|F0.5:0.29)  | 11 (P:0.27|R:0.33|F0.5:0.27) | 23 (P:0.26|R:0.25|F0.5:0.26) | 33 (P:0.26|R:0.19|F0.5:0.24) | 47 (P:0.27|R:0.15|F0.5:0.22)  | 97 (P:0.30|R:0.09|F0.5:0.18)  | 133 (P:0.25|R:0.04|F0.5:0.12) | 186 (P:0.29|R:0.02|F0.5:0.09) |

| ExcessivePublicCount        | 1 (P:0.32|R:1.00|F0.5:0.35) | 2 (P:0.32|R:0.92|F0.5:0.35) | 3 (P:0.30|R:0.65|F0.5:0.32)  | 3 (P:0.30|R:0.65|F0.5:0.32)  | 6 (P:0.26|R:0.30|F0.5:0.26)  | 10 (P:0.26|R:0.25|F0.5:0.26) | 13 (P:0.26|R:0.21|F0.5:0.24) | 22 (P:0.27|R:0.15|F0.5:0.22)  | 27 (P:0.29|R:0.10|F0.5:0.19)  | 34 (P:0.28|R:0.04|F0.5:0.12)  | 50 (P:0.27|R:0.02|F0.5:0.09)  |

| CouplingBetweenObjects      | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           | N/A                           | N/A                           |

| ExcessiveImports            | N/A                         | N/A                         | N/A                          | N/A                          | N/A                          | N/A                          | N/A                          | N/A                           | N/A                           | N/A                           | N/A                           |

| NcssCount\_Method            | 3 (P:0.01|R:0.80|F0.5:0.01) | 3 (P:0.01|R:0.80|F0.5:0.01) | 4 (P:0.01|R:0.80|F0.5:0.02)  | 4 (P:0.01|R:0.80|F0.5:0.02)  | 4 (P:0.01|R:0.80|F0.5:0.02)  | 4 (P:0.01|R:0.80|F0.5:0.02)  | 4 (P:0.01|R:0.80|F0.5:0.02)  | 10 (P:0.02|R:0.34|F0.5:0.02)  | 13 (P:0.01|R:0.14|F0.5:0.02)  | 15 (P:0.00|R:0.02|F0.5:0.00)  | 19 (P:0.00|R:0.02|F0.5:0.00)  |

| CyclomaticComplexity\_Method | 2 (P:0.01|R:0.78|F0.5:0.01) | 3 (P:0.01|R:0.56|F0.5:0.01) | 3 (P:0.01|R:0.56|F0.5:0.01)  | 3 (P:0.01|R:0.56|F0.5:0.02)  | 3 (P:0.01|R:0.56|F0.5:0.02)  | 4 (P:0.01|R:0.45|F0.5:0.02)  | 4 (P:0.01|R:0.28|F0.5:0.01)  | 5 (P:0.01|R:0.20|F0.5:0.01)   | 7 (P:0.01|R:0.14|F0.5:0.02)   | 7 (P:0.02|R:0.13|F0.5:0.02)   | 11 (P:0.00|R:0.01|F0.5:0.00)  |

| TooManyMethods              | 1 (P:0.51|R:1.00|F0.5:0.56) | 6 (P:0.52|R:0.81|F0.5:0.56) | 6 (P:0.52|R:0.81|F0.5:0.56)  | 8 (P:0.52|R:0.73|F0.5:0.55)  | 13 (P:0.52|R:0.47|F0.5:0.51) | 16 (P:0.52|R:0.42|F0.5:0.50) | 17 (P:0.51|R:0.33|F0.5:0.46) | 20 (P:0.55|R:0.20|F0.5:0.41)  | 31 (P:0.61|R:0.14|F0.5:0.36)  | 40 (P:0.64|R:0.11|F0.5:0.33)  | 53 (P:0.67|R:0.05|F0.5:0.19)  |



🏆 F1-Optimized Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f1 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|---------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 5th          |                 4 |                 8 |         0.4026 |             0.99 |      0.3124 |            2 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 5th          |                 2 |                 3 |         0.4056 |             1    |      0.309  |            2 |

| ExcessivePublicCount        | True         | True               | False         | 5th          |                 1 |                 2 |         0.4191 |             1    |      0.3167 |            2 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 75th         |                10 |                13 |         0.0309 |             2.15 |      0.0076 |            2 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                 7 |                 7 |         0.0289 |             2.15 |      0.0076 |            2 |

| TooManyMethods              | True         | True               | False         | 5th          |                 1 |                 1 |         0.6722 |             1    |      0.5062 |            1 |



🎯 Precision-Optimized (F0.5) Chronological Thresholds:

|                             | calibrated   | threshold\_stable   | trustworthy   | percentile   |   threshold\_value |   band\_divergence |   kfold\_avg\_f0\_5 |   precision\_lift |   base\_rate |   folds\_used |

|:----------------------------|:-------------|:-------------------|:--------------|:-------------|------------------:|------------------:|-----------------:|-----------------:|------------:|-------------:|

| NcssCount\_Class             | True         | True               | False         | 15th         |                 8 |                 8 |           0.3401 |             1    |      0.3124 |            2 |

| CyclomaticComplexity\_Class  | True         | True               | False         | 15th         |                 3 |                 3 |           0.3427 |             1.02 |      0.309  |            2 |

| ExcessivePublicCount        | True         | True               | False         | 15th         |                 2 |                 2 |           0.3532 |             1.02 |      0.3167 |            2 |

| CouplingBetweenObjects      | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| ExcessiveImports            | False        | False              | False         | Default      |                   |                   |                  |             0    |      0      |            0 |

| NcssCount\_Method            | True         | True               | False         | 75th         |                10 |                13 |           0.0201 |             2.15 |      0.0076 |            2 |

| CyclomaticComplexity\_Method | True         | True               | False         | 90th         |                 7 |                 7 |           0.0197 |             2.15 |      0.0076 |            2 |

| TooManyMethods              | True         | False              | False         | 5th          |                 1 |                 8 |           0.5617 |             1    |      0.5062 |            1 |



💾 Saved Dual Chronological locked thresholds to disk: t3\_inflection\_thresholds\_commons-lang\_chrono\_locked.json

🏁 Phase T.3 Complete.

🚀 Starting Phase B.4: Blind Imminent Predictability Evaluation (Trust-Aware Edition)

✅ Thresholds strictly synchronized from disk.

📊 Final Exam Loaded: Evaluating 44 completely unseen canonical entities.



&#x20;   MASTER BLIND EVALUATION MATRIX (Test Set: 20%)



📊 TABLE 1: F1-Optimized Thresholds (Evaluated on Blind F1 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |        42 |         1500 |             15 | ⚠️ 1500 (Fallback) |     0.096 |     0     |    0     |      0.064 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        40 |           80 |              7 | ⚠️ 80 (Fallback)   |     0.106 |     0.061 |    0.061 |      0.074 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        31 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.099 |     0     |    0     |      0.071 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        21 |           60 |              3 | ⚠️ 60 (Fallback)   |     0.027 |     0     |    0     |      0.007 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        21 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.032 |     0.027 |    0.027 |      0.003 | ➖ Uncalibrated Noise |

| TooManyMethods              |        30 |           10 |              8 | ⚠️ 10 (Fallback)   |     0.094 |     0.085 |    0.085 |      0.097 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized Thresholds (Evaluated on Blind F0.5 Score)

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |        42 |         1500 |             15 | ⚠️ 1500 (Fallback) |      0.078 |      0     |     0     |       0.042 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        40 |           80 |              7 | ⚠️ 80 (Fallback)   |      0.075 |      0.05  |     0.05  |       0.048 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        31 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.072 |      0     |     0     |       0.046 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        21 |           60 |              3 | ⚠️ 60 (Fallback)   |      0.017 |      0     |     0     |       0.004 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        21 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.02  |      0.018 |     0.018 |       0.002 | ➖ Uncalibrated Noise |

| TooManyMethods              |        30 |           10 |              8 | ⚠️ 10 (Fallback)   |      0.079 |      0.057 |     0.057 |       0.064 | ➖ Uncalibrated Noise |



💾 Saved detailed evaluation matrix to: b4\_evaluation\_matrix\_commons-lang.csv



=================================================================

🏆 FINAL BASELINE EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  Test Entities (Strictly Blind):   44

\-----------------------------------------------------------------

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F1 averages.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria. Cannot compute F0.5 averages.

=================================================================

🏁 Phase B.4 Complete. The threshold hypotheses have been blindly evaluated.

🚀 Starting Phase E.4: Scarcity Predictability Evaluation (Trust-Aware)

📊 Final Scarcity Exam Loaded: Evaluating 44 completely unseen canonical entities.



📊 TABLE 1: F1-Optimized Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |        42 |         1500 |             14 | ⚠️ 1500 (Fallback) |     0.082 |     0     |    0     |      0.063 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        40 |           80 |              5 | ⚠️ 80 (Fallback)   |     0.082 |     0.061 |    0.061 |      0.063 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        31 |           45 |              3 | ⚠️ 45 (Fallback)   |     0.078 |     0     |    0     |      0.071 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        21 |           60 |              2 | ⚠️ 60 (Fallback)   |     0.024 |     0     |    0     |      0.003 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        21 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.028 |     0.027 |    0.027 |      0.003 | ➖ Uncalibrated Noise |

| TooManyMethods              |        30 |           10 |              8 | ⚠️ 10 (Fallback)   |     0.097 |     0.085 |    0.085 |      0.097 | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Scarcity Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |        42 |         1500 |             14 | ⚠️ 1500 (Fallback) |      0.06  |      0     |     0     |       0.041 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        40 |           80 |              5 | ⚠️ 80 (Fallback)   |      0.054 |      0.05  |     0.05  |       0.041 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        31 |           45 |              3 | ⚠️ 45 (Fallback)   |      0.056 |      0     |     0     |       0.046 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |        21 |           60 |              2 | ⚠️ 60 (Fallback)   |      0.016 |      0     |     0     |       0.002 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |        21 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.019 |      0.018 |     0.018 |       0.002 | ➖ Uncalibrated Noise |

| TooManyMethods              |        30 |           10 |              8 | ⚠️ 10 (Fallback)   |      0.065 |      0.057 |     0.057 |       0.064 | ➖ Uncalibrated Noise |



=================================================================

🏆 SCARCITY EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria under scarcity.

=================================================================



💾 Saved scarcity evaluation matrix to: e4\_evaluation\_matrix\_scarcity\_commons-lang.csv

🏁 Phase E.4 Complete. Scarcity evaluation finalized.

🚀 Starting Phase T.4: Chronological Predictability Evaluation (Trust-Aware)

📊 Final Chronological Exam Loaded: Evaluating against Future Timeline.



📊 TABLE 1: F1-Optimized Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F1 |   Cust\_F1 |   PMD\_F1 |   Naive\_F1 | Drift\_Alert\_F1        |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|----------:|----------:|---------:|-----------:|:----------------------|

| NcssCount\_Class             |        34 |         1500 |             27 | ⚠️ 1500 (Fallback) |     0.403 |     0.057 |    0.057 |      0.008 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        23 |           80 |             12 | ⚠️ 80 (Fallback)   |     0.406 |     0.009 |    0.009 |      0.007 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        24 |           45 |              6 | ⚠️ 45 (Fallback)   |     0.419 |     0.018 |    0.018 |      0.006 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       625 |           60 |              3 | ⚠️ 60 (Fallback)   |     0.031 |     0.012 |    0.012 |      0.03  | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       625 |           10 |              1 | ⚠️ 10 (Fallback)   |     0.029 |     0.024 |    0.024 |      0.019 | ➖ Uncalibrated Noise |

| TooManyMethods              |         9 |           10 |             10 | ⚠️ 10 (Fallback)   |     0.672 |     0.01  |    0.01  |      0.01  | ➖ Uncalibrated Noise |



🎯 TABLE 2: Precision-Optimized (F0.5) Chronological Evaluation

| Metric                      |   Support |   PMD\_Thresh |   Naive\_Thresh | Cust\_Thresh        |   Hist\_F05 |   Cust\_F05 |   PMD\_F05 |   Naive\_F05 | Drift\_Alert\_F05       |

|:----------------------------|----------:|-------------:|---------------:|:-------------------|-----------:|-----------:|----------:|------------:|:----------------------|

| NcssCount\_Class             |        34 |         1500 |             27 | ⚠️ 1500 (Fallback) |      0.34  |      0.056 |     0.056 |       0.005 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Class  |        23 |           80 |             12 | ⚠️ 80 (Fallback)   |      0.343 |      0.006 |     0.006 |       0.005 | ➖ Uncalibrated Noise |

| ExcessivePublicCount        |        24 |           45 |              6 | ⚠️ 45 (Fallback)   |      0.353 |      0.012 |     0.012 |       0.004 | ➖ Uncalibrated Noise |

| NcssCount\_Method            |       625 |           60 |              3 | ⚠️ 60 (Fallback)   |      0.02  |      0.018 |     0.018 |       0.019 | ➖ Uncalibrated Noise |

| CyclomaticComplexity\_Method |       625 |           10 |              1 | ⚠️ 10 (Fallback)   |      0.02  |      0.019 |     0.019 |       0.012 | ➖ Uncalibrated Noise |

| TooManyMethods              |         9 |           10 |             10 | ⚠️ 10 (Fallback)   |      0.562 |      0.006 |     0.006 |       0.006 | ➖ Uncalibrated Noise |



=================================================================

🏆 CHRONOLOGICAL EVALUATION SUMMARY (Trustworthy Rules Only)

=================================================================

&#x20;  \[ TRACK 1: Standard F1 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

\-----------------------------------------------------------------

&#x20;  \[ TRACK 2: Precision-Weighted F0.5 Score ]

&#x20;  ⚠️ No rules met the Trustworthy criteria.

=================================================================



💾 Saved chronological evaluation matrix to: t4\_evaluation\_matrix\_chrono\_commons-lang.csv

🏁 Phase T.4 Complete. Chronological evaluation finalized.



=====================================================================================

🚀 INITIATING PHASE 6: MASTER CROSS-REGIME DISCRIMINATION DIAGNOSTIC

=====================================================================================



================ DISCRIMINATION BY SOURCE × RULE ================

AUC-PR \~ base\_rate  ⇒  lift \~ 1.0  ⇒  metric ranks refactoring at chance.



| Source                   | Rule                        |     n |   n\_pos |   base\_rate |   auc\_pr |   lift | flag         |

|:-------------------------|:----------------------------|------:|--------:|------------:|---------:|-------:|:-------------|

| Pooled/all               | NcssCount\_Class             |  8054 |     309 |      0.0384 |   0.0533 |   1.39 | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Class  |  6856 |     283 |      0.0413 |   0.0545 |   1.32 | rare (<5%)   |

| Pooled/all               | ExcessivePublicCount        |  7209 |     280 |      0.0388 |   0.0488 |   1.26 | rare (<5%)   |

| Pooled/all               | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Pooled/all               | NcssCount\_Method            | 99616 |     734 |      0.0074 |   0.0123 |   1.66 | rare (<5%)   |

| Pooled/all               | CyclomaticComplexity\_Method | 99616 |     734 |      0.0074 |   0.013  |   1.77 | rare (<5%)   |

| Pooled/all               | TooManyMethods              |  4421 |     147 |      0.0333 |   0.0509 |   1.53 | rare (<5%)   |

| Spatial/train            | NcssCount\_Class             |  6665 |     267 |      0.0401 |   0.0553 |   1.38 | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Class  |  5561 |     243 |      0.0437 |   0.0561 |   1.28 | rare (<5%)   |

| Spatial/train            | ExcessivePublicCount        |  6130 |     249 |      0.0406 |   0.0496 |   1.22 | rare (<5%)   |

| Spatial/train            | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/train            | NcssCount\_Method            | 86572 |     713 |      0.0082 |   0.0132 |   1.6  | rare (<5%)   |

| Spatial/train            | CyclomaticComplexity\_Method | 86572 |     713 |      0.0082 |   0.0142 |   1.73 | rare (<5%)   |

| Spatial/train            | TooManyMethods              |  3551 |     117 |      0.0329 |   0.0536 |   1.63 | rare (<5%)   |

| Scarcity/train           | NcssCount\_Class             |  2363 |     117 |      0.0495 |   0.0567 |   1.15 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Class  |  2108 |     109 |      0.0517 |   0.0556 |   1.08 | ok           |

| Scarcity/train           | ExcessivePublicCount        |  2230 |     116 |      0.052  |   0.0512 |   0.98 | ok           |

| Scarcity/train           | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Scarcity/train           | NcssCount\_Method            | 22933 |     157 |      0.0068 |   0.0134 |   1.95 | rare (<5%)   |

| Scarcity/train           | CyclomaticComplexity\_Method | 22933 |     157 |      0.0068 |   0.0196 |   2.87 | rare (<5%)   |

| Scarcity/train           | TooManyMethods              |  1014 |      33 |      0.0325 |   0.0489 |   1.5  | rare (<5%)   |

| Chronological/train      | NcssCount\_Class             |  2385 |     275 |      0.1153 |   0.1309 |   1.14 | ok           |

| Chronological/train      | CyclomaticComplexity\_Class  |  2241 |     260 |      0.116  |   0.1307 |   1.13 | ok           |

| Chronological/train      | ExcessivePublicCount        |  2157 |     256 |      0.1187 |   0.1304 |   1.1  | ok           |

| Chronological/train      | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/train      | NcssCount\_Method            | 34455 |     109 |      0.0032 |   0.0058 |   1.84 | rare (<5%)   |

| Chronological/train      | CyclomaticComplexity\_Method | 34455 |     109 |      0.0032 |   0.0071 |   2.25 | rare (<5%)   |

| Chronological/train      | TooManyMethods              |  1430 |     138 |      0.0965 |   0.1365 |   1.41 | ok           |

| Spatial/Scarcity/holdout | NcssCount\_Class             |  1389 |      42 |      0.0302 |   0.049  |   1.62 | rare (<5%)   |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Class  |  1295 |      40 |      0.0309 |   0.0537 |   1.74 | rare (<5%)   |

| Spatial/Scarcity/holdout | ExcessivePublicCount        |  1079 |      31 |      0.0287 |   0.0536 |   1.86 | rare (<5%)   |

| Spatial/Scarcity/holdout | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Spatial/Scarcity/holdout | NcssCount\_Method            | 13044 |      21 |      0.0016 |   0.0067 |   4.18 | low n\_pos    |

| Spatial/Scarcity/holdout | CyclomaticComplexity\_Method | 13044 |      21 |      0.0016 |   0.0059 |   3.66 | low n\_pos    |

| Spatial/Scarcity/holdout | TooManyMethods              |   870 |      30 |      0.0345 |   0.049  |   1.42 | rare (<5%)   |

| Chronological/holdout    | NcssCount\_Class             |  5669 |      34 |      0.006  |   0.0222 |   3.7  | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Class  |  4615 |      23 |      0.005  |   0.0222 |   4.45 | low n\_pos    |

| Chronological/holdout    | ExcessivePublicCount        |  5052 |      24 |      0.0048 |   0.0115 |   2.42 | low n\_pos    |

| Chronological/holdout    | CouplingBetweenObjects      |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | ExcessiveImports            |     0 |       0 |    nan      | nan      | nan    | no positives |

| Chronological/holdout    | NcssCount\_Method            | 65161 |     625 |      0.0096 |   0.0167 |   1.74 | rare (<5%)   |

| Chronological/holdout    | CyclomaticComplexity\_Method | 65161 |     625 |      0.0096 |   0.0176 |   1.84 | rare (<5%)   |

| Chronological/holdout    | TooManyMethods              |  2991 |       9 |      0.003  |   0.0126 |   4.17 | low n\_pos    |



\--- LIFT (AUC-PR / base\_rate) by rule × source ---

Lift strictly measures how much better the metric ranks over blind guessing.

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| CyclomaticComplexity\_Class  |         1.32 |            1.28 |             1.08 |                  1.13 |                       1.74 |                    4.45 |

| CyclomaticComplexity\_Method |         1.77 |            1.73 |             2.87 |                  2.25 |                       3.66 |                    1.84 |

| ExcessiveImports            |       nan    |          nan    |           nan    |                nan    |                     nan    |                  nan    |

| ExcessivePublicCount        |         1.26 |            1.22 |             0.98 |                  1.1  |                       1.86 |                    2.42 |

| NcssCount\_Class             |         1.39 |            1.38 |             1.15 |                  1.14 |                       1.62 |                    3.7  |

| NcssCount\_Method            |         1.66 |            1.6  |             1.95 |                  1.84 |                       4.18 |                    1.74 |

| TooManyMethods              |         1.53 |            1.63 |             1.5  |                  1.41 |                       1.42 |                    4.17 |



\--- AUC-PR (absolute) by rule × source ---

| Rule                        |   Pooled/all |   Spatial/train |   Scarcity/train |   Chronological/train |   Spatial/Scarcity/holdout |   Chronological/holdout |

|:----------------------------|-------------:|----------------:|-----------------:|----------------------:|---------------------------:|------------------------:|

| CouplingBetweenObjects      |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| CyclomaticComplexity\_Class  |       0.0545 |          0.0561 |           0.0556 |                0.1307 |                     0.0537 |                  0.0222 |

| CyclomaticComplexity\_Method |       0.013  |          0.0142 |           0.0196 |                0.0071 |                     0.0059 |                  0.0176 |

| ExcessiveImports            |     nan      |        nan      |         nan      |              nan      |                   nan      |                nan      |

| ExcessivePublicCount        |       0.0488 |          0.0496 |           0.0512 |                0.1304 |                     0.0536 |                  0.0115 |

| NcssCount\_Class             |       0.0533 |          0.0553 |           0.0567 |                0.1309 |                     0.049  |                  0.0222 |

| NcssCount\_Method            |       0.0123 |          0.0132 |           0.0134 |                0.0058 |                     0.0067 |                  0.0167 |

| TooManyMethods              |       0.0509 |          0.0536 |           0.0489 |                0.1365 |                     0.049  |                  0.0126 |



================ PER-SOURCE SUMMARY ================

(reliable = n\_pos≥30 AND base\_rate≥0.05)



| Source                   | Max Absolute AUC-PR                | Max Reliable Lift                 |

|:-------------------------|:-----------------------------------|:----------------------------------|

| Pooled/all               | 0.054 (CyclomaticComplexity\_Class) | — (no statistically stable rule)  |

| Spatial/train            | 0.056 (CyclomaticComplexity\_Class) | — (no statistically stable rule)  |

| Scarcity/train           | 0.057 (NcssCount\_Class)            | 1.08 (CyclomaticComplexity\_Class) |

| Chronological/train      | 0.137 (TooManyMethods)             | 1.41 (TooManyMethods)             |

| Spatial/Scarcity/holdout | 0.054 (CyclomaticComplexity\_Class) | — (no statistically stable rule)  |

| Chronological/holdout    | 0.022 (NcssCount\_Class)            | — (no statistically stable rule)  |



💾 Saved full diagnostic to: discrimination\_diagnostic\_commons-lang.csv

🏁 Phase 5 Complete. The overarching data structure has been successfully diagnosed.

