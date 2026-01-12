# 🍽️ Zomato Restaurant Analysis & Rating Prediction

## 📌 Project Overview

This project combines **Business Intelligence (Power BI)** and **Machine Learning (Python)** to analyze Zomato restaurant data and predict restaurant ratings based on multiple features such as location, price range, votes, cuisines, and online services.

The project is divided into two major parts:

1. **Interactive Power BI Dashboard** for exploratory analysis
2. **Restaurant Rating Prediction Model** using Machine Learning

---

## 📊 Power BI Dashboard – Zomato Restaurant Analysis

### Dashboard Highlights

* Total Restaurants, Cuisines, Countries, Cities, Votes, and Average Rating
* City-wise restaurant distribution
* Cuisine-wise restaurant count
* Impact of:

  * Table Booking
  * Online Delivery
* Restaurant chains vs average ratings
* Country and Year filters for interactive analysis

### Dashboard Screenshot

```markdown
![Zomato Dashboard](screenshots/zomato_dashboard.png)
```

> Place the dashboard image inside a folder named **`screenshots/`**

---

## 🤖 Machine Learning – Restaurant Rating Prediction

### Objective

Predict restaurant ratings using historical Zomato data and engineered features.

---

## 🧠 Workflow

### 1️⃣ Data Loading

* Dataset: `zomato_data.xlsx`
* Tool: `pandas`

### 2️⃣ Data Cleaning

* Removed irrelevant columns (IDs, addresses, currency, unnamed columns)
* Handled missing values
* Merged multiple cuisine columns into a single feature

### 3️⃣ Feature Engineering

* Encoded categorical features
* One-hot encoded cuisines using `MultiLabelBinarizer`
* Extracted date features:

  * Opening Year
  * Opening Month
  * Restaurant Age (in days)
* Capped extreme outliers in cost

### 4️⃣ Exploratory Data Analysis (EDA)

* Price Range vs Rating
* Online Delivery vs Rating
* Table Booking vs Rating
* Correlation Heatmap

### 5️⃣ Model Building

Models implemented:

* Linear Regression (Baseline)
* Ridge Regression
* Random Forest Regressor (Final Model)

---

## 📈 Model Performance

| Model             | R² Score | MSE            |
| ----------------- | -------- | -------------- |
| Linear Regression | ~0.00    | Extremely High |
| Ridge Regression  | 0.39     | 0.80           |
| **Random Forest** | **0.93** | **0.09**       |

✔ **Random Forest achieved the best performance**

---

## 🔍 Top Features Influencing Ratings

* Votes
* Longitude & Latitude
* Average Cost for Two
* Cuisine Types (North Indian, Fast Food, Continental)
* Online Delivery Availability

---

## 🧪 Cross Validation

* 5-Fold Cross Validation
* **Average R² Score:** `0.86`

---

## 💾 Model Saving

The trained Random Forest model is saved using `joblib`:

```python
joblib.dump(rf, 'restaurant_rating_model.pkl')
```

The model can be reloaded and used for prediction without retraining.

---

## 🛠️ Tech Stack

### Data Analysis & ML

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

### Visualization

* Power BI

### Model Deployment Ready

* `joblib` for model persistence

---

## 📌 Key Learnings

* End-to-end data science workflow
* Feature engineering for high-dimensional categorical data
* Model comparison and evaluation
* Business insights using Power BI
* Correlation between votes, cost, and restaurant ratings

---

## 🚀 Future Enhancements

* Hyperparameter tuning (GridSearchCV)
* XGBoost / LightGBM models
* Web app deployment (Flask / Streamlit)
* Integration of Power BI & ML predictions
* Real-time rating prediction system

---
