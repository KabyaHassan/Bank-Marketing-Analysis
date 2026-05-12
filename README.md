# Bank Marketing Subscription Prediction

This repository contains a comprehensive machine learning project focused on predicting whether a client will subscribe to a term deposit. By analyzing historical marketing campaign data, this project implements various supervised and unsupervised models to optimize targeting strategies and improve conversion rates.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset Summary](#dataset-summary)
- [Methodology](#methodology)
- [Models & Performance](#models--performance)
- [Key Insights](#key-insights)
- [Installation & Usage](#installation--usage)
- [Authors](#authors)

## Project Overview
Direct marketing campaigns, particularly via phone calls, are resource-intensive. This project aims to use Artificial Intelligence to identify high-probability leads, thereby reducing unnecessary contact and operational costs while maximizing successful subscriptions.

## Dataset Summary
The project utilizes the **Bank Marketing Dataset** (41,188 samples).
- **Features:** 20 input variables including customer demographics (age, job, education), social/economic indicators (employment variation rate, euribor 3m), and past campaign data.
- **Target Variable:** `y` (binary: "yes" or "no").
- **Challenge:** The dataset is heavily imbalanced, with only 11.2% of clients having subscribed.

## Methodology
1. **Preprocessing:** Handled "unknown" values, applied Label Encoding for categorical data, and used `StandardScaler` for numerical normalization.
2. **Splitting:** Conducted a stratified 80/20 train-test split.
3. **Dimensionality Reduction:** Used PCA (Principal Component Analysis) for visual representation and clustering.
4. **Evaluation:** Prioritized AUC-ROC and Recall over accuracy due to the high class imbalance.

## Models & Performance
Four different models were implemented to compare predictive power:

| Model | Accuracy | Precision | Recall | AUC |
| :--- | :--- | :--- | :--- | :--- |
| **Decision Tree** | 0.9136 | 0.6385 | 0.5280 | 0.8953 |
| **Logistic Regression** | 0.8524 | 0.4079 | 0.8491 | 0.9303 |
| **Neural Network (MLP)** | 0.9080 | 0.5835 | 0.6552 | 0.9348 |
| **K-Means Clustering** | - | - | - | - |

* **Logistic Regression** (with balanced weights) is recommended when the priority is to capture the maximum number of potential subscribers (highest Recall).
* **Neural Network** provides the most robust overall classification (highest AUC).

## Key Insights
- **Call Duration:** Identified as the strongest predictor, though it is technically "leakage" as it is unknown prior to a call.
- **Class Imbalance:** Traditional accuracy is misleading; the model's ability to distinguish classes (AUC) is a more reliable success metric here.
- **Clustering:** K-Means identified two distinct customer segments, suggesting that subscribers share common social-economic profiles.

## Installation & Usage
1. **Clone the repo:**
   ```bash
   git clone [https://github.com/your-username/bank-marketing-analysis-ai.git](https://github.com/your-username/bank-marketing-analysis-ai.git)
