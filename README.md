# Predictive Intelligence in Distributed E-Commerce
**An Explainable and Prescriptive Framework for Delivery Lead-Time Optimization**

## 📌 Overview
The shift towards decentralized e-commerce systems has created significant information gaps, rendering delivery lead times highly unpredictable, particularly in geographically vast markets. This repository contains a scalable, explainable, and prescriptive machine learning framework designed to optimize delivery lead times and reduce shipping delays. By targeting both the occurrence of a delay and its severity, the project provides actionable business insights to decrease customer churn and logistics expenses.

## 📊 Dataset
The project utilizes the **[Olist Brazilian E-Commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)**, encompassing over 100,000 historical orders. 
* A robust **PySpark** data engineering pipeline was used to merge multiple relational tables.
* Engineered features include dynamic temporal constraints, operational lags (e.g., seller preparation times), and geospatial disparities (geolocation distances).

## 🛠️ Tech Stack
* **Data Processing & Engineering:** PySpark, Python, Pandas, SQL
* **Machine Learning:** Scikit-Learn, LightGBM, CatBoost, XGBoost
* **Explainable AI (XAI):** SHAP, LIME
* **Evaluation Metrics:** RMSE, MAE, R², ROC-AUC, Recall, Precision

## 🚀 Methodology: A Dual-Target Approach
The framework tackles delivery prediction through a dual-target modeling strategy to handle the heavy-tailed, highly imbalanced logistics data:

1. **Classification (Delay Occurrence):** Detecting the likelihood of a late delivery. **CatBoost** achieved the best performance, prioritizing high recall to successfully flag true delivery failures early in the operational pipeline.
2. **Regression (Delay Severity):** Predicting the exact duration of the delivery lead time. **LightGBM** demonstrated algorithmic superiority for the continuous prediction task.

## 🧠 Explainability & Prescriptive Analytics
To mitigate the "black-box" limitations of advanced gradient boosting ensembles, this project heavily integrates Explainable AI (XAI) to turn predictions into prescriptive business logic:
* **SHAP (SHapley Additive exPlanations)** is utilized for global feature importance and to map the interactions between variables (e.g., geospatial distance and freight ratios).
* **LIME (Local Interpretable Model-agnostic Explanations)** provides local instance explanations, detailing the exact drivers behind specific edge cases (e.g., massive delays vs. on-time deliveries).
* **Business Impact:** These insights are translated into prescriptive actions, such as implementing dynamic Service Level Agreements (SLAs) and proactive carrier reallocation.
