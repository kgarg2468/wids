# WiDS 2026 Wildfire Data Preparation

This repository contains a Colab-compatible notebook for end-to-end data preparation for the WiDS Global Datathon 2026 wildfire survival analysis task.

## Main file

- `wids_data_prep.ipynb`: Full pipeline notebook with:
  - data loading
  - exploratory data analysis
  - data cleaning
  - feature engineering
  - feature selection
  - train and validation splitting
  - scaling
  - saving processed datasets and artifacts

## Data location

All raw files are expected in the `data/` folder:

- `train.csv`
- `test.csv`
- `sample_submission.csv`
- `metaData.csv`

## How to run

1. Open `wids_data_prep.ipynb` in Google Colab or Jupyter.
2. Make sure the project root is your working directory.
3. Run all cells from top to bottom.

If running in Colab, upload this project folder or mount Google Drive so the `data/` path is available.

## Outputs created by the notebook

The notebook writes the following files to `data/`:

- `train_processed.csv`
- `val_processed.csv`
- `test_processed.csv`
- `train_scaled.csv`
- `val_scaled.csv`
- `test_scaled.csv`
- `feature_names.json`
- `cv_folds.pkl`
- `standard_scaler.pkl`

## Notes

- The notebook uses `random_state=42` for reproducibility.
- Train and validation splitting is stratified on `event`.
- Scaling is fit on train only to reduce leakage risk.
