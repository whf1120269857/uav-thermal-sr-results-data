# Data dictionary

CSV files retain their original values, labels and precision. Missing seed values remain empty; they must not be imputed as independent runs.

## Fig05_paired_ts_by_seed.csv

Rows: 18. Columns: `domain`, `optimizer_seed`, `metric`, `value`, `comparison`, `n_images`, `unit`, `category`, `category_order`, `series_id`.

domain: H30T, M4T.

metric: LPIPS, PSNR, SSIM.

comparison: T-S.

unit: dB, dimensionless.

## Fig06_paired_components_by_seed.csv

Rows: 42. Columns: `domain`, `metric`, `seed`, `value`, `category`, `category_order`, `series_id`.

domain: H30T, M4T.

metric: bias2, centered_mse, edge_gradient_mse, edge_mse, flat_mse, hf_energy, lf_energy, total_mse.

## Fig06_residual_absolute_by_seed.csv

Rows: 120. Columns: `domain`, `state_kind`, `optimizer_seed`, `metric`, `value`, `category`, `category_order`, `series_id`.

domain: H30T, M4T.

metric: bias2, centered_mse, edge_mse, flat_mse, hf_energy, total_mse.

state_kind: DAA, S, T, Z.

## Fig07_paired_to_T_by_seed.csv

Rows: 99. Columns: `domain`, `route`, `optimizer_seed`, `metric`, `value`, `unit`, `category`, `category_order`, `series_id`.

domain: H30T, M4T.

metric: LPIPS, PSNR, SSIM.

route: ALL_SOURCE, RB_G0, RB_G1, RB_G3, RESTORED_T, T.

unit: dB, dimensionless.

## Fig10_plain_zst_by_seed.csv

Rows: 21. Columns: `condition`, `state`, `optimizer_seed`, `metric`, `Y`, `evidence`, `category`, `category_order`, `series_id`.

metric: LPIPS, PSNR, SSIM.

condition: source, target, zero.

## Fig10_pressure_paired_by_seed.csv

Rows: 12. Columns: `condition`, `optimizer_seed`, `comparison`, `PSNR_delta`, `SSIM_delta`, `LPIPS_delta`, `category`, `category_order`.

condition: MAIN_M4T, STRESS_R1, STRESS_R2, STRESS_R3.

comparison: T-S.

## Shared conventions

- `optimizer_seed` / `seed`: optimization seed identifier. Seeds are repeated optimization runs, not independent acquisition scenes.
- `value`: value of the metric named in `metric`; `Y` is the corresponding absolute metric in the PBVS table.
- `T-S`: target-statistics configuration minus source-statistics configuration. Positive PSNR/SSIM and negative LPIPS indicate improvement.
- `n_images`: number of evaluation images associated with an aggregate, not a count of optimization replicates.
- `category`, `category_order`, `series_id`: original plotting labels, order and grouping identifiers.
- `evidence`: historical relative evidence-file references and hashes retained from the source CSV. The referenced raw files are not distributed here; these strings are not download URLs.
- `state`: historical experiment identifier, retained for traceability. These identifiers are not publication titles or public code entry points.

The CSV values are stored in native numerical units. Figure 6 applies a display scaling of 10^-3; do not treat display labels as a change to the underlying CSV values. Some CSVs contain extra diagnostic states or metrics beyond the panels selected for the manuscript. They must not all be treated as plotted results.
