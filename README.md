# Plant Stress Risk Modeling With Tuned Boosting Classifiers

This project predicts plant health status from soil, nutrient, environmental, and biosensor measurements. The target classes are `Healthy`, `Moderate Stress`, and `High Stress`.

## Workflow

- Load the local plant health dataset
- Review class balance and sensor distributions
- Tune LightGBM, CatBoost, and XGBoost with `GridSearchCV`
- Rank models with macro F1-score
- Review feature importance for the selected model
- Run one sample plant stress prediction

## Models

- LightGBM
- CatBoost
- XGBoost

## Results

On the current train/test split:

| Model | CV Macro F1 | Accuracy | Macro Precision | Macro Recall | Macro F1 |
| --- | ---: | ---: | ---: | ---: | ---: |
| LightGBM | 0.9923 | 1.0000 | 1.0000 | 1.0000 | 1.0000 |
| CatBoost | 0.9972 | 0.9958 | 0.9959 | 0.9967 | 0.9963 |
| XGBoost | 0.9926 | 0.9958 | 0.9945 | 0.9958 | 0.9951 |

Best model: `LightGBM`

Best parameters:

```text
LightGBM: learning_rate=0.05, max_depth=-1, n_estimators=100, num_leaves=15
CatBoost: depth=4, iterations=150, learning_rate=0.05
XGBoost: learning_rate=0.05, max_depth=5, n_estimators=100, subsample=0.85
```

## Files

```text
Plant_Stress_Risk_Boosting_Models.ipynb
data/
  plant_health_data.csv
README.md
```


## How to Run

Install the required packages:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn lightgbm catboost xgboost
```

Open and run:

```text
Plant_Stress_Risk_Boosting_Models.ipynb
```
