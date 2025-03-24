# 🌍 Air Quality Prediction for Major Cities in Massachusetts  
**Project Type:** Independent ML Project  
**Tools:** Python
**Date:** March 2025  

---

## 📓 Project Notebook  
➡️ [View Jupyter Notebook](./Air_Quality_Prediction_for_Major_Cities_MA_V3.ipynb)

---

## 🧠 Objective  
Predict the Air Quality Index (AQI) for 15 major cities in Massachusetts using machine learning models, aiming to identify the most accurate and generalizable algorithm through evaluation, transformation, and dimensionality reduction.

---

## 🔧 Tools & Libraries Used  
- **Languages:** Python (Pandas, NumPy)  
- **Visualization:** Altair, Matplotlib  
- **Machine Learning:** scikit-learn, XGBoost  
- **Data Management:** API Integration, JSON, AWS  
- **Model Evaluation:** RMSE, MAE, R² Score  

---

## 📊 Workflow Overview  

1. **Data Collection**  
   - Queried hourly pollutant data (PM2.5, PM10, CO, NO₂, SO₂, O₃) for 15 cities using the Weatherbit Air Quality API.  
   - Stored results in structured JSON format.

2. **Data Cleaning & Preprocessing**  
   - Combined data from multiple cities, and removed duplicates and outliers.  
   - Applied Box-Cox transformation for long-tailed variables (CO, NO₂, SO₂).  
   - Standardized features using `StandardScaler`.

3. **Feature Engineering**  
   - Created transformed variables (e.g., `co_boxcox`, `pm25_scaled`).  
   - Added time-based features (`hour`, `dayofweek`, `is_weekend`).  
   - One-hot encoded cities and defined `aqi_scaled` as the prediction target.

4. **Dimensionality Reduction with PCA**  
   - Reduced seven pollution variables to four principal components (explaining >90% variance).  
   - Combined PCA with undersampling to avoid bias from extreme pollution cases.

5. **Modeling & Tuning**  
   - Trained and evaluated:
     - Linear models: Linear, Ridge, Lasso  
     - Tree-based models: Random Forest, Gradient Boosting, XGBoost  
     - Others: KNN 
   - Final evaluation focused on PCA + undersampling results.

---

## 🏆 Best Models & Performance (PCA + Undersampling)

| Model               | RMSE (Test) | R² (Test) | MAE (Test) |
|--------------------|-------------|-----------|------------|
| Random Forest       | 0.2795      | 0.9017    | 0.2018     |
| **Gradient Boosting** | **0.1498**   | **0.9718** | **0.0997** |
| XGBoost             | 0.2009      | 0.9492    | 0.1230     |

- **Random Forest** was less precise in capturing high-AQI variance.
- **Gradient Boosting** achieved the highest accuracy with minimal overfitting.  
- **XGBoost** offered a good balance between accuracy and model complexity.  

---

## 📈 Visual Highlights  

- **📌 Actual vs Predicted AQI:** Points align closely with the diagonal line.  
- **📌 Residual Plots:** Errors are centered around zero, showing stable variance.  
- **📌 AQI Time Trend:** Altair line charts show that predictions follow true AQI changes well.  
- **📌 Learning Curves:** Gradient Boosting converged fastest and with lowest validation RMSE.

---

## ✅ Key Takeaways  

- **Data transformation (Box-Cox)** and **PCA dimensionality reduction** helped mitigate skewness and improved model generalization.
- **Gradient Boosting** is the most reliable model for AQI forecasting.
- Undersampling of pollution-heavy records helped balance the training set and reduce bias.
- The project demonstrates a full ML pipeline, from **data acquisition**, **cleaning**, **feature engineering**, **modeling**, to **visual evaluation**.

---
