# 🌍 Air Quality Prediction for Major Cities in Massachusetts  
**Project Type:** Independent ML Project  
**Tools:** Python, scikit-learn, XGBoost, Altair, AWS  
**Date:** March 2025  
---
## 📓 Project Notebook

➡️ [View Jupyter Notebook](./Air_Quality_Prediction_for_Major_Cities_MA.ipynb)

---

## 🧠 Objective  
Predict the Air Quality Index (AQI) for 15 major cities in Massachusetts using machine learning models, with a focus on identifying the best-performing algorithm through rigorous evaluation.

---

## 🔧 Tools & Libraries Used  
- **Languages:** Python (Pandas, NumPy)  
- **Visualization:** Altair, Matplotlib  
- **Machine Learning:** scikit-learn, XGBoost, MLP, SVR  
- **Data Management:** API calls, JSON handling, AWS  
- **Model Evaluation:** RMSE, MAE, R² Score  

---

## 📊 Workflow Overview  

1. **Data Collection**  
   - Queried hourly pollutant data (PM2.5, PM10, CO, NO₂, SO₂, O₃) for 15 cities using the Air Quality API.  
   - Parsed and stored JSON results locally.

2. **Data Cleaning & Preprocessing**  
   - Merged datasets, removed duplicates, handled missing values.  
   - Applied IQR for outlier detection and Box-Cox transformation for skewed variables (CO, NO₂, SO₂).  
   - Standardized features with `StandardScaler`.

3. **Feature Engineering**  
   - Created new features: `co_boxcox`, `no2_boxcox`, etc.  
   - Scaled AQI and pollutant metrics.  
   - Defined `aqi_scaled` as the target variable.

4. **Modeling & Tuning**  
   - Trained 9 models using `GridSearchCV` with 5-fold cross-validation:  
     - Linear Regression, Ridge, Lasso  
     - Random Forest, Gradient Boosting, XGBoost  
     - MLP Regressor, KNN, SVR  
   - Optimized hyperparameters for each model.

---

## 🏆 Best Models & Performance

| Model               | RMSE   | R²     | MAE    |
|--------------------|--------|--------|--------|
| **Gradient Boosting** | 0.0223 | 0.9995 | 0.0072 |
| Random Forest       | 0.0250 | 0.9994 | 0.0058 |
| XGBoost             | 0.0317 | 0.9990 | 0.0130 |

- Gradient Boosting yielded the **highest accuracy** and most reliable results.
- All top models generalize well with low error and minimal overfitting.

---

## 📈 Visual Highlights  
- **Actual vs Predicted AQI:** Points closely align with the diagonal.  
- **Residual Plots:** Errors are centered around zero, indicating strong fit.  
- **Learning Curves:** Fast convergence with low validation RMSE (~0.03).  
- **Time Series Trend:** Altair plots revealed city-level air quality changes over time.

---

## ✅ Key Takeaways  
- Data transformation (e.g., Box-Cox) and robust tuning significantly boosted model performance.  
- Gradient Boosting proved most effective for AQI forecasting.  
- End-to-end pipeline demonstrates skills in **data acquisition**, **preprocessing**, **model training**, and **performance evaluation**.

---

