# Results data for support-configured UAV thermal super-resolution

Associated manuscript: **Support-Configured Internal Adaptation for UAV Thermal Image Super-Resolution**.

Authors: Haifu Wei, Ruipu Tong, Shiqi Zhao, Hualin Yang, and Jingwen Li.

This package contains selected numerical results distributed with the authors' R2 manuscript materials (2026-10-28). It supports inspection of selected reported results. It is a **partial results-data release**, not a complete experimental reproduction package or a release of all images, trained models, training code, or all figure source data. No journal acceptance or publication is claimed.

## Contents and coverage

| File | Contents | Scope limitation |
|---|---|---|
| `data/Fig05_paired_ts_by_seed.csv` | PSNR, SSIM and LPIPS paired T-S differences for M4T and H30T | Supports numerical gain panels; does not include sampler distributions or image replay panels |
| `data/Fig06_paired_components_by_seed.csv` | Paired residual/error component differences by seed | Retains source diagnostic metrics; some metrics are outside the displayed panels |
| `data/Fig06_residual_absolute_by_seed.csv` | Absolute error components for recorded states and seeds | Retains source states; not every state is shown in each figure panel |
| `data/Fig07_paired_to_T_by_seed.csv` | Recorded rollback/restore comparisons against the complete T state | Retains additional control rows as recorded |
| `data/Fig10_pressure_paired_by_seed.csv` | T-S quality differences for MAIN_M4T and STRESS_R1-R3 | Does not contain the PBVS paired series shown alongside these conditions |
| `data/Fig10_plain_zst_by_seed.csv` | Absolute PBVS zero/source/target quality values | Historical filename; supports PBVS absolute-quality analysis, not a complete source for all Figure 10 panels |

All six CSVs are byte-for-byte copies of the matching files in the R2 delivery. `manifest.json` records row counts and SHA-256 checksums, which were compared with the source delivery's provenance index. This verifies file identity, not an independent rerun of the experiments.

## Interpretation

Z is the no-adaptation state; S and T use source-statistics and target-statistics configurations, respectively. M4T and H30T are the two controlled domains defined in the manuscript. PBVS is the real cross-camera evaluation with semi-registered references. Consult the manuscript and supplementary material for data splits, alignment, metric definitions and protocol limitations.

Use `DATA_DICTIONARY.md` for columns, grouping and units. Keep optimizer-seed variation distinct from acquisition-unit or geographic-scene variation. Do not interpret three optimizer seeds as three independently collected datasets. Rollback effects are not additive.

## What is not included

Original third-party images, author portraits and contact lists, submission correspondence, private review notes, credentials, model checkpoints, and executable method code are not part of this package. Source CSV `evidence` fields refer to historical internal artifacts; those artifacts are not publicly downloadable from this package. Figure 8/9 per-image data and complete Figure 5 sampling data are not included.

## Availability and reuse

Repository: https://github.com/whf1120269857/uav-thermal-sr-results-data

This release shares the six numerical result tables listed above. No DOI has been assigned. No additional reuse license is specified; please contact the authors for reuse permissions beyond applicable law. A license may be added in a subsequent release.
