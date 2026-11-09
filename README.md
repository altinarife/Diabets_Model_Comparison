# Diabetes Model Comparison

A capstone machine-learning project comparing Logistic Regression, K-Nearest Neighbors (KNN), and Gaussian Naïve Bayes for binary diabetes-outcome prediction from clinical measurements.

The analysis is implemented in [`Comparison_Diabets_Prection.ipynb`](Comparison_Diabets_Prection.ipynb). It explores and quality-checks the data, addresses missing values and medically implausible zero measurements, and evaluates classification models. The notebook also investigates repeated records in the supplied dataset, an important consideration when interpreting model performance.

> **Important:** This is an educational analysis, not a medical diagnostic tool. Predictions must not be used for clinical decisions.

## Project contents

- `Comparison_Diabets_Prection.ipynb` — data exploration, preprocessing, model comparison, and evaluation.
- `Extended_Diabetes_Dataset.csv` — required input data referenced by the notebook. It is not currently included in this repository; obtain it from the project owner or approved source before running the notebook.

## Dataset

The notebook expects a CSV named `Extended_Diabetes_Dataset.csv` in the same directory as the notebook. The analyzed dataset contains 10,000 rows and nine columns:

| Column | Description |
| --- | --- |
| `Pregnancies` | Number of pregnancies |
| `Glucose` | Glucose measurement |
| `BloodPressure` | Blood pressure measurement |
| `SkinThickness` | Skin thickness measurement |
| `Insulin` | Insulin measurement |
| `BMI` | Body mass index |
| `DiabetesPedigreeFunction` | Diabetes pedigree function value |
| `Age` | Age in years |
| `Outcome` | Binary target: 0 or 1 |

The notebook checks missing values, zero values in measurements where zero may represent missing data, and duplicate records. In its current analysis, it reports 7,424 exact duplicate rows and explores a patient fingerprint based on `Pregnancies`, `Age`, and `DiabetesPedigreeFunction`. These findings make duplicate handling and the dataset's provenance especially important when interpreting reported evaluation scores.

## Models and evaluation

The project compares:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Gaussian Naïve Bayes

The notebook imports scikit-learn tools for imputation, feature scaling, pipelines, cross-validation, parameter search, and classification metrics. Review the notebook's results and evaluation setup for the detailed comparison; this README does not claim a best-performing model or specific score.

## Getting started

1. Clone or download this repository.
2. Place the authorized `Extended_Diabetes_Dataset.csv` file beside the notebook. The dataset is not committed here.
3. Install Python and the notebook dependencies. The notebook uses `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, and Jupyter.
4. Open and run `Comparison_Diabets_Prection.ipynb` from top to bottom.

Example setup:

```bash
python -m pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook Comparison_Diabets_Prection.ipynb
```

The notebook sets a random state (`42`) for reproducibility. Exact results can still depend on package versions and the input dataset.

## Notes on interpretation

- A zero in `Pregnancies` is valid; zeros in some physiological measurements may indicate missing values and should be handled deliberately.
- Repeated or duplicated observations can make train/test and cross-validation scores overly optimistic if related copies appear across splits. Interpret results in light of the notebook's duplicate investigation and data provenance.
- This project is for learning and model-comparison purposes only. It does not establish clinical validity, fairness, or suitability for real-world screening.
