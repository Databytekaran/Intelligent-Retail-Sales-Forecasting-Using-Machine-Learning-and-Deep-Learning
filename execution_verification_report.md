# Execution verification report – 01_eda.ipynb

**Environment:** Python 3.13, pandas 3.0.5, numpy 2.5.3, scipy 1.18.1, matplotlib 3.11.2, seaborn 0.13.2, pyarrow 26, nbconvert 7.17 (kernel `python3`). Data: the real Rossmann CSVs (train 1,017,209 rows).

| Check | Result |
|---|---|
| Notebook executed top to bottom with `jupyter nbconvert --execute` | 32 of 32 code cells executed, execution counts 1…32 in order |
| Error outputs / stderr output | 0 / 0 |
| Run time / memory | ≈ 62 s; pipeline alone ≈ 0.7 GB RAM, whole notebook kernel peak ≈ 3.2 GB |
| Reproducibility (2 full runs from empty processed/figures/logs) | identical printed output (only the intentional log-format fix differs) |
| Portability (project copied to another folder, run with working directory = project root) | executed with 0 errors |
| Reconstructed `src/` vs the numbers recorded in the original notebook run | train (1,017,209×50), test (41,088×46), store (1,115×14); 11,094 / 11,829 outliers; 31,230 holiday rows / 38 dates / 24 national; 54 open-zero-sales; 11 imputed Open; 36 features; store-history correlations 0.774 / 0.639; 13.6 % December outliers; clipped mean 6,937.2 and max 38,025 – all identical |
| Original cells: printed output old run vs new run | 26 of 29 identical; 3 differ only cosmetically (log line order / table header, extra figure names) |
| Logging | `logging` via `src.utils.logger.setup_logging` (console + `logs/project.log`), single handler set (no duplicate lines), warnings and exceptions logged (`log.exception` in the pipeline) |
| Paths | none hard-coded; all from `config/config.yaml`, resolved from the config file location |
| Q1 Promo share | 44.5 % = train, same 856 stores as test (used in the test); 44.6 % = train, all 1,115 stores; test 46.3 %. Both correct; text now states which population each number uses |
