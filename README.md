# Project 6 – Sales forecasting across multiple Rossmann stores (Part 1: EDA)

## Run
```bash
pip install -r requirements.txt
# put train.csv, test.csv, store.csv, sample_submission.csv into data/raw/
jupyter nbconvert --to notebook --execute notebooks/01_eda.ipynb      # or open the notebook and "Run All"
python -m src.data.make_dataset                                        # pipeline only (writes data/processed/)
```
All paths come from `config/config.yaml` and are resolved relative to the project root (no hard-coded folders).

## Structure
```
config/config.yaml            paths, seed, outlier + holiday settings, logging
data/raw/                     original CSVs (never modified)
data/processed/               train/test parquet, store csv, holiday calendar, feature manifest, cleaning report, gap table
notebooks/01_eda.ipynb        EDA notebook (Q1-Q11 + SchoolHoliday, StoreType promo lift, data gaps)
reports/figures/              figures saved by the notebook
logs/project.log              log file (console + file)
src/utils/                    config.py, logger.py, constants.py
src/data/                     loader.py, inspection.py, cleaning.py, outliers.py, make_dataset.py
src/features/                 date_, holiday_, promo_, competition_, history_features.py
src/visualization/plotting.py shared colours and helpers
```
