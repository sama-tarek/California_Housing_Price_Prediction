# 🏠 California Housing Price Prediction

## 📌 Project Overview

This project focuses on predicting **California house prices** using demographic, geographic, and housing-related features.

The project applies a **Multiple Linear Regression** model to understand the relationships between housing characteristics and median house values. It includes data exploration, preprocessing, feature scaling, model training, evaluation, and feature coefficient analysis.

The dataset is provided by **scikit-learn** through the California Housing dataset.

---

## 🎯 Project Objectives

* Explore and understand the California Housing dataset.
* Perform data preprocessing and preparation.
* Analyze relationships between features and house prices.
* Train a Multiple Linear Regression model.
* Evaluate model performance using regression metrics.
* Analyze the contribution of different features using model coefficients.
* Visualize actual vs. predicted house values.

---

## 📊 Dataset

The dataset contains information about California districts and their corresponding median house values.

### Features

| Feature      | Description                              |
| ------------ | ---------------------------------------- |
| `MedInc`     | Median income in the block group         |
| `HouseAge`   | Median house age                         |
| `AveRooms`   | Average number of rooms per household    |
| `AveBedrms`  | Average number of bedrooms per household |
| `Population` | Block group population                   |
| `AveOccup`   | Average number of household members      |
| `Latitude`   | Geographic latitude                      |
| `Longitude`  | Geographic longitude                     |

### Target

| Target        | Description                            |
| ------------- | -------------------------------------- |
| `MedHouseVal` | Median house value for the block group |

The target is measured in units of **$100,000**.

For example:

```text
2.5 → $250,000
```

---

## 🛠️ Technologies & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook
* Anaconda

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Feature / Target Separation
   ↓
Train-Test Split
   ↓
Feature Scaling
   ↓
Multiple Linear Regression
   ↓
Model Evaluation
   ↓
Actual vs Predicted Visualization
   ↓
Ridge (L2 Regularization)
   ↓
Model Evaluation
   ↓
Feature Coefficient Analysis

```

---

## 🧹 Data Preprocessing

The dataset was inspected for:

* Missing values
* Duplicate records
* Data types
* Statistical distributions
* Feature relationships

The target variable was separated from the input features.

The dataset was then divided into training and testing sets using an **80/20 split**.

### Feature Scaling

`StandardScaler` was used to standardize the numerical features.

The scaler was fitted only on the training data and then applied to both training and testing data to avoid data leakage.

---

## 🤖 Model

### Multiple Linear Regression

Multiple Linear Regression was selected as the baseline regression model.

The model predicts the median house value based on the available housing, demographic, and geographic features.

---

## 📈 Model Evaluation

The model was evaluated using four regression metrics:

* **MAE (Mean Absolute Error):** Measures the average absolute difference between actual and predicted values. Lower values indicate better performance.
* **MSE (Mean Squared Error):** Measures the average squared difference between actual and predicted values. Lower values indicate better performance, with larger errors receiving more weight.
* **RMSE (Root Mean Squared Error):** Measures the square root of the average squared prediction errors. Lower values indicate better performance and the result is expressed in the same units as the target.
* **R² Score:** Measures how much of the variation in the target variable is explained by the model. A value closer to 1 indicates better performance.

### Results

| Metric |    Score |
| ------ | -------: |
| MAE    | **0.50** |
| MSE    | **0.46** |
| RMSE   | **0.68** |
| R²     | **0.65** |

The model achieved an **R² score of 0.65**, meaning that approximately **65% of the variation in median house values is explained by the model on the test set**.

---

## 🔍 Feature Coefficients

The standardized feature coefficients obtained from the model were:

| Feature      | Coefficient |
| ------------ | ----------: |
| `Longitude`  |      -0.823 |
| `Latitude`   |      -0.902 |
| `MedInc`     |   **0.803** |
| `HouseAge`   |       0.147 |
| `AveBedrms`  |       0.125 |
| `Population` |       0.049 |
| `AveRooms`   |      -0.093 |
| `AveOccup`   |      -0.282 |

Because the features were standardized before training, the coefficient magnitudes can be compared to understand their relative contribution within the linear model.

`MedInc` has a strong positive coefficient, while `Latitude` and `Longitude` have relatively large coefficients in magnitude, indicating that geographic location plays an important role in the model's predictions.

---

## 📊 Visualization

The project includes an **Actual vs Predicted House Values** visualization.

The plot compares the actual house values from the test set with the values predicted by the regression model.

Points closer to the diagonal reference line represent predictions closer to the actual values.

---

## 💡 Key Insights

* **Median income (`MedInc`)** has a strong positive relationship with predicted house values.
* Geographic features such as **Latitude** and **Longitude** have substantial coefficients, highlighting the importance of location.
* `AveOccup` has a negative coefficient in the fitted linear model.
* The baseline model explains around **65% of the variance** in the target variable.
* The model provides a useful baseline but still leaves a substantial portion of the target variation unexplained.

---

## 🚀 Future Improvements

Several improvements can be explored in future versions of the project:

* Perform **5-fold cross-validation**.
* Compare Multiple Linear Regression with:

  * Ridge Regression
  * Lasso Regression
  * Decision Tree Regressor
  * Random Forest Regressor
  * Gradient Boosting Regressor
* Apply feature engineering.
* Perform hyperparameter tuning.
* Conduct deeper residual analysis.
* Explore the geographic distribution of house prices.
* Compare baseline and optimized models.

---

## 📁 Project Structure

```text
California_Housing_Price_Prediction/
│
├── California_Housing_Price_Prediction.ipynb
├── Actual_Vs_Predicted.jpg
├── README.md
└── requirements.txt
```

---

## 📚 Dataset Source

The dataset is the **California Housing dataset** available through `sklearn.datasets.fetch_california_housing`.

---

## 👩‍💻 Author

**Sama Tarek**

Computer Science & Artificial Intelligence Student
Interested in **Data Science and Machine Learning**.

---

## ⭐ Conclusion

This project demonstrates an end-to-end regression workflow, starting from data exploration and preprocessing through model training, evaluation, visualization, and feature interpretation.

The Multiple Linear Regression model achieved an **R² score of 0.65**, providing a solid baseline for predicting California house values. Future experimentation with ensemble models, feature engineering, cross-validation, and hyperparameter tuning can be used to further investigate and potentially improve predictive performance.
