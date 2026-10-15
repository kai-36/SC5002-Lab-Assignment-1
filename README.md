# SC5002-Lab-Assignment-1

## Overview

This Jupyter notebook compares **Linear Regression** and **Ridge Regression** for predicting California house values. It standardizes the input features, evaluates both models using **5-fold cross-validation** and the **R² score**, tests Ridge Regression with different regularization strengths (`alpha`), and plots the results in a bar chart.

## Dataset

The notebook uses the **California Housing Dataset** from scikit-learn and randomly selects **1,000 samples** (`random_state=42`).

- **Target:** `MedHouseVal` — median house value, expressed in units of $100,000.
- **Input features:** `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, and `Longitude`.

The notebook applies `StandardScaler` to the features and uses an **80/20 train–test split**. Cross-validation is performed on the training portion.

## Results

| Model | Mean 5-Fold Cross-Validation R² |
|---|---:|
| Linear Regression | 0.6457 |
| Ridge Regression (`alpha=0.1`) | 0.6457 |
| Ridge Regression (`alpha=10`) | 0.6443 |
| Ridge Regression (`alpha=1000`) | 0.3574 |

## Conclusion

Linear Regression and Ridge Regression with low regularization achieved nearly identical performance. Increasing Ridge's `alpha` to 10 resulted in a slight reduction in R², while `alpha=1000` caused a substantial drop, consistent with underfitting due to excessive regularization. For the tested settings, Ridge Regression did not improve the average cross-validation score over ordinary Linear Regression.