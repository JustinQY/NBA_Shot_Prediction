# 🏀 NBA Shot Success Prediction

This project is the final assignment for SEP 785 Machine Learning at McMaster University. It aims to build a machine learning pipeline to predict whether a basketball shot will be made or missed based on game context and spatial data.

## Project Overview

**Goal:**  
Predict the outcome of an NBA shot attempt using game context, player behavior, and spatial features.

**Expected Output:**  
A binary classification (`Made` vs `Missed`) using models like Logistic Regression, Random Forest, and Neural Networks.

**Team Members:**  
- Junchen Ge  
- YiBo Qiao  
- Yang Zhang

## Dataset

We used a combined dataset from:
- 📊 [NBA Shot Logs on Kaggle](https://www.kaggle.com/datasets/dansbecker/nba-shot-logs)
- 🏀 [NBA Official API](https://github.com/swar/nba_api)
- 📎 Reference: [NBA.com/stats](https://www.nba.com/stats)

### Key Features
- `SHOT_CLOCK`, `GAME_CLOCK`, `DRIBBLES`, `SHOT_DISTANCE`
- `ACTION_TYPE`, `SHOT_ZONE_AREA`, `CLOSE_DEF_DIST`, etc.

### Engineered Features
- `IS_BUZZER`: Shot in final 5 seconds  
- `OPEN_SHOT`: Defender > 6 ft away  
- `SHOT_ANGLE_DEG`: Angle of shot from court center  
- `EFFORT_INDEX`: Derived from dribbles and possession time  
- `CLUTCH_THREE`, `IS_FAST_BREAK`, and more

## Data Preparation

- **Cleaning:** Removed illegal values (e.g., DRIBBLES > 30, CLOSE_DEF_DIST < 0)
- **Missing values:** `SHOT_CLOCK` missing → filled with 0 in likely buzzer-beater cases
- **Outliers:** Excluded shots from beyond 40 ft or coordinates off-court

## Data Analysis

- **PCA:** Tried dimensionality reduction but didn't improve correlation with target  
- **Top Correlated Features:**
  - `ACTION_TYPE_Jump Shot` (−0.266)
  - `SHOT_DISTANCE`, `DISTANCE_FROM_CENTER`, `LOC_Y`
  - `ACTION_TYPE_Dunk Shot`, etc.

- **Visualizations:**
  - Shot heatmaps by location and angle
  - Shot success vs. defender distance

## Model Training & Evaluation

| Model              | AUC  | Accuracy | Notes |
|-------------------|------|----------|-------|
| Logistic Regression | 0.65 | ~0.64    | Interpretable, tested L1 & L2 |
| Random Forest       | 0.67 | ~0.64    | Best recall on missed shots |
| Neural Network      | N/A  | ~0.64    | High recall, more sensitive to tuning |

- **GridSearchCV** for hyperparameter tuning  
- Evaluation metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC  
- Best performing: **Random Forest** with `n_estimators=200`, `max_depth=10`

---
