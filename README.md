# Thyroid Disease Classification System

A Python-based machine learning repository designed to clean, analyze, and classify thyroid diagnoses using patient clinical data. The project applies data cleaning techniques to manage skewness and kurtosis, handles outliers through Interquartile Range (IQR) filtering, and implements a K-Nearest Neighbors (KNN) classification model to categorize patient test results into string-based diagnostic outcomes.

---

## Dataset Information

This project utilizes the **Thyroid Disease Data** dataset curated by Emmanuel Fwerr, which combines reconciled data groups from the classic UCI Machine Learning Repository.

* **Source File:** `thyroidDF.csv`
* **Dimensions:** 9,172 rows × 31 attributes
* **Attributes Included:** Patient age, sex, historical background flags, and explicit chemical blood panels including **TSH**, **T3**, **TT4**, **T4U**, and **FTI**.
* **Official Link:** [https://www.kaggle.com/datasets/emmanuelfwerr/thyroid-disease-data](https://www.kaggle.com/datasets/emmanuelfwerr/thyroid-disease-data)

---

## Features

### Exploratory Data Analysis & Statistical Modeling

* **Descriptive Summaries:** Generates baseline metrics across numerical matrices tracking global variables including Mean, Median, Mode, Standard Deviation, and Variance.
* **Asymmetry Evaluation:** Continuously tracks distribution changes by processing and contrasting **Skewness** and **Kurtosis** limits both before and after data transformation steps.

### Pipeline Processing

* **Feature Trimming:** Drops redundant operational markers like `patient_id` to prevent data leakage.
* **Imputation Strategy:** Fills structural missing numerical array fields using computed mean values.
* **Boundary Checking:** Enforces strict logical human thresholds for age indices ($0 \le \text{age} \le 120$), resetting extreme outlier data back to baseline means.
* **String Target Categorization:** Reconciles composite bracket characters (`|`) and converts encoded letter classifications into intuitive clinical diagnostics:
* `-` $\rightarrow$ `'No disease'`
* `A, B, C, D` $\rightarrow$ `'Hyperthyroidism'`
* `E, F, G, H` $\rightarrow$ `'Hypothyroidism'`



### Data Visualization

* Generates multi-plot comparison curves comparing raw skewness/kurtosis performance side-by-side.
* Builds specialized outlier identification plots using exploratory `boxplot` methods.

### Predictive Modeling

* Splits structured subsets using an 80/20 train/test distribution protocol.
* Fits a specialized K-Nearest Neighbors Classifier ($k=3$) to predict categorical string outcomes directly.

---

## Core Algorithm Formulas

### Skewness Evaluation

$$\text{Skewness} = \frac{\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^3}{\left(\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2\right)^{3/2}}$$

### Kurtosis Evaluation

$$\text{Kurtosis} = \frac{\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^4}{\left(\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2\right)^2} - 3$$

### IQR Outlier Boundaries

$$\text{IQR} = Q_3 - Q_1$$

$$\text{Lower Bound} = Q_1 - 1.5 \times \text{IQR}$$

$$\text{Upper Bound} = Q_3 + 1.5 \times \text{IQR}$$

---

## Structural Project Layout

```text
├── thyroid_classification.py  # Main pipeline script (EDA, cleaning, plots, and KNN model)
├── thyroidDF.csv              # Downloaded data source file from Kaggle
└── README.md                  # Project documentation overview

```

---

## Requirements

Ensure you have the following packages installed before running the main script:

* `pandas`
* `numpy`
* `matplotlib`
* `scikit-learn`

Install them quickly via terminal command line:

```bash
pip install pandas numpy matplotlib scikit-learn

```

---

## How to Run

1. Clone or download this repository.
2. Ensure `thyroidDF.csv` is saved in the directory matched by your runtime file tracker (e.g., `/content/` or locally).
3. Run the Python application file:

```bash
python thyroid_classification.py

```

---

## License

This project is open-source and licensed under the MIT License.

---

*Developed by Romil Atmaramani*
