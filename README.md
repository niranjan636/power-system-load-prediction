# Power System Load Type Prediction

## Overview

This project uses machine learning to classify power-system load conditions into three categories: `Light_Load`, `Medium_Load`, and `Maximum_Load`, based on historical electrical measurements and time-based features.

## Objective

To develop and evaluate a machine learning classification pipeline that predicts load type using historical power-system data.

## Dataset

The dataset contains electrical measurements and time-related information, including:

- Energy consumption (`Usage_kWh`)
- Lagging and leading reactive power
- Carbon dioxide emissions (`CO2(tCO2)`)
- Power factor measurements
- Number of seconds from midnight (`NSM`)
- Date and time
- Target variable (`Load_Type`)

## Methodology

1. Data loading and preprocessing
2. Exploratory data analysis (EDA)
3. Handling missing values and invalid power-factor readings
4. Time-based and cyclical feature engineering
5. Chronological training, validation, and testing
6. Model comparison and evaluation

## Data Splitting

- **Training:** January–September 2018
- **Validation:** October–November 2018
- **Final testing:** December 2018

This chronological approach evaluates performance on later, unseen data.

## Models Evaluated

- Logistic Regression
- Random Forest
- HistGradientBoosting

HistGradientBoosting was selected based on the validation results.

## Final Test Results

Evaluation on the December 2018 test set:

| Metric | Score |
|---|---:|
| Accuracy | 90.86% |
| Macro Precision | 87.95% |
| Macro Recall | 94.80% |
| Macro F1-score | 90.56% |

## Project Structure

```text
power-system-load-prediction/
├── data/
│   └── load_data.csv
├── load_type_prediction.ipynb
├── Problem statement.docx
├── README.md
└── .gitignore
```

## How to Run

1. Clone or download this repository.
2. Install the required Python libraries used in the notebook, such as pandas, NumPy, Matplotlib, Seaborn, and scikit-learn.
3. Open `load_type_prediction.ipynb` in Jupyter Notebook or VS Code.
4. Run the notebook cells from top to bottom.

## Limitations and Future Improvements

Validation performance varied between October and November, suggesting potential temporal variation in the dataset. Future work could investigate distribution shifts, test additional temporal validation windows, and evaluate feature importance.

## Author

Niranjan Murthy V.