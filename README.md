# 💎 Gemstone Price Prediction - Dhiraj Durande

## 📌 Introduction
This is a machine learning regression project built to **predict the price of diamonds** based on various features like carat, cut, clarity, etc.



## 📊 Dataset Description

The dataset consists of 10 input features and 1 target feature:

| Column   | Description |
|----------|-------------|
| `id`     | Unique identifier for each diamond |
| `carat`  | Weight of the diamond in carats |
| `cut`    | Quality of the diamond cut |
| `color`  | Color grade of the diamond |
| `clarity`| Clarity grade showing internal flaws |
| `depth`  | Depth percentage (z / average(x, y)) |
| `table`  | Width of the top of the diamond |
| `x`      | Length in mm |
| `y`      | Width in mm |
| `z`      | Depth in mm |
| `price`  |  Target variable: Price of the diamond |

---

##Data Source
**Dataset used**: [Kaggle Playground S3E8 - Gemstone Prices](https://www.kaggle.com/competitions/playground-series-s3e8/data)

---

## ML Approach

### 🔹 1. Data Ingestion
- Load data from CSV
- Perform Train-Test split
- Save data to `artifacts/train.csv`, `test.csv`

### 🔹 2. Data Transformation
- **Numerical columns**: `SimpleImputer (median)` → `StandardScaler`
- **Categorical columns**: `SimpleImputer (most_frequent)` → `OrdinalEncoder` → `StandardScaler`
- Save the preprocessor as `preprocessor.pkl`

### 🔹 3. Model Training
- Tested models: Linear Regression, Ridge, Lasso, Decision Tree, Random Forest, KNN, XGBoost, CatBoost, AdaBoost
- **Best model found**: `CatBoost Regressor`
- Hyperparameter tuning applied on CatBoost and KNN
- Final model: `Voting Regressor` (CatBoost, XGBoost, KNN)
- Final model saved as `model.pkl`

### 🔹 4. Deployment
- Built with **Flask Web App**
- User interface for entering features and getting predicted price
- Model deployed using **Render.com** (Free Hosting)

---

## Feature Input Guide

| Feature | Description | Example |
|---------|-------------|---------|
| `carat` | Weight in carats | `0.72` |
| `cut`   | Diamond cut quality | `Ideal`, `Premium` |
| `color` | Diamond color grade | `G`, `H`, `I` |
| `clarity` | Internal flaw rating | `SI1`, `VS2` |
| `depth` | Depth % | `61.5` |
| `table` | Table width | `57` |
| `x`     | Length (mm) | `5.8` |
| `y`     | Width (mm) | `5.9` |
| `z`     | Depth (mm) | `3.6` |

---

## Live Web App (via Render)

- 🌐 **Live URL**: *Coming Soon*
- **API Endpoint**: `/predictAPI` (POST method using JSON)

---

## 📸 Sample UI (Screenshot)

> 📷  `Screenshots\Homepage.png`


