# Machine Learning Assignment 2: Bagging, Boosting, and Bias–Variance

**Student:** Rahul Kumar Bhikundia  
**Roll Number:** M26CSA006  
**Course:** Machine Learning (CSL7620)  
**Dataset:** Olivetti Faces  
**Random Seed:** `26006`

## Overview

This repository contains the Jupyter notebook, saved models, numerical results, and figures for Machine Learning Assignment 2. The experiments investigate decision trees, bagging, multiclass SAMME boosting, robustness to masked image regions, and empirical bias–variance analysis.

## Repository Structure

```text
.
├── assignment.ipynb
├── README.md
├── Data/
│   ├── olivetti_py3.pkz
│   ├── X_train.npy.npz
│   ├── X_valid.npy.npz
│   └── X_test.npy.npz
├── Models/
│   ├── baseline_model.joblib
│   ├── bagging_model_B50.joblib
│   ├── boostingModel.joblib
│   └── model_config.joblib
├── assignment_figures/
├── assignment_results_csv/
└── assignment_results_tables.xlsx
```

## Dataset and Experimental Setup

- **Dataset:** Olivetti Faces, comprising 400 images across 40 identities.
- **Image representation:** Raw flattened 64 × 64 pixel arrays, without PCA or other dimensionality reduction.
- **Data split:** Six training images, two validation images, and two test images per identity.
- **Random seed:** `26006`, derived from the numeric characters of roll number `M26CSA006`.
- **Robustness experiment:** A centered 16 × 16 region, covering rows and columns 24–39, is set to zero in the test images. Models are trained exclusively on clean images.
- **Model selection:** Validation accuracy is used to select model configurations before final test evaluation.
- **Ensemble methods:** Bagging and SAMME boosting are implemented in the notebook.
- **Bias–variance analysis:** Uses 30 resampled training sets with a fixed clean test set.

## Saved Artifacts

- `Models/` contains the saved baseline tree, selected bagging ensemble, boosting model, and model configuration.
- `assignment_results_csv/` contains exported numerical result tables.
- `assignment_results_tables.xlsx` consolidates the result tables into a workbook.
- `assignment_figures/` contains exported experimental figures.
- `assignment.ipynb` contains the experiment code and saved cell outputs.

These artifacts allow results to be inspected without retraining every model. Executing the full notebook may take substantially longer because some cells train models and run repeated experiments.

## Environment Setup

Use Python with the libraries required by the notebook, including NumPy, scikit-learn, Matplotlib, pandas, joblib, and Jupyter. Record the exact versions used in the submitted experiments in `requirements.txt` or `environment.yml`.

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it in Git Bash on Windows:

```bash
source .venv/Scripts/activate
```

Install the recorded dependencies:

```bash
pip install -r requirements.txt
```

## Inspecting and Reproducing Results

Clone the repository:

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_DIRECTORY>
```

Launch the notebook:

```bash
jupyter notebook assignment.ipynb
```

Review the saved notebook outputs, CSV tables, workbook, and figures to inspect the existing results. To reproduce the experiments from scratch, execute the relevant notebook cells in order. Training cells should not be rerun merely to inspect the saved outputs.

## Reproducibility Notes

- Preserve the saved data arrays, labels, split information, random seeds, and model configurations.
- Maintain the same train/validation/test partition across experiments.
- Generate masked test images using the specified centered zero mask; do not train models on masked images.
- The notebook is the primary source of experiment logic; exported tables and figures are supplementary artifacts.
- Include the exact environment dependencies and reproduction instructions required for evaluation.
- After the final repository commit, record the repository URL and commit hash in the report.

## Main Entry Point

The main entry point is `assignment.ipynb`. The saved model artifacts, figures, and numerical tables are provided for convenient inspection of the completed experiments.
