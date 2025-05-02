# 🏀 NBA Shot Prediction

This project aims to predict whether an NBA player can successfully make a shot from a specific position on the court using machine learning classification models. It leverages real shot log data from the NBA and applies data preprocessing, feature engineering, and model training to generate meaningful insights.

## 📌 Problem Statement

With the growing popularity of NBA games, predicting shot success based on in-game data can provide fans and analysts with deeper insights into player performance and game dynamics. This project uses machine learning techniques to build a classifier that determines whether a shot attempt will be successful based on features such as shot distance, defender proximity, game clock, and more.

## 👥 Team Members

- Gary Qiao
- Junchen Ge
- Yang Zhang

## 📂 Dataset

- **Source:** [NBA Shot Logs (Kaggle)](https://www.kaggle.com/datasets/dansbecker/nba-shot-logs)
- **Reference:** [NBA Official Stats](https://www.nba.com/stats)

The dataset includes detailed information about player shot attempts, including:
- Player and defender names
- Shot clock
- Touch time
- Shot distance
- Close defender distance
- Shot result (made/missed)

## ✅ Expected Outcome

A trained classification model that predicts shot success (`True` for a made shot, `False` for a missed shot) given a set of contextual in-game features.

## 🛠️ Methodology

1. **Data Preprocessing**  
   - Handled missing values and inconsistent data
   - Selected relevant features for prediction
   - Encoded categorical variables and normalized numerical features

2. **Model Selection and Training**  
   - Compared several classifiers including:
     - Logistic Regression
     - Random Forest
     - XGBoost
   - Evaluated models using accuracy, precision, recall, and ROC-AUC

3. **Model Evaluation**  
   - Performed k-fold cross-validation
   - Visualized confusion matrix and feature importance
   - Tuned hyperparameters for optimal performance

## 📈 Results

The final model achieved strong classification performance, with the XGBoost classifier delivering the highest accuracy and best generalization on the test set.

## 📄 Report

The full project report and methodology details are available in [`Machine Learning Project Description.pdf`](Machine%20Learning%20Project%20Description.pdf).

## 📎 License

This project is for educational purposes only.

---
