# E-commerce Customer Intelligence & Prediction Pipeline

## Overview
An end-to-end machine learning pipeline that segments e-commerce customers based on purchasing behavior and predicts their segment using supervised classification. Built for automated marketing orchestration and retention tracking.

## Technical Architecture
1. **Data Ingestion & Cleaning:** Handled 540k+ rows, stripped missing IDs, and removed anomalous return data.
2. **Feature Engineering (RFM):** Computed Recency, Frequency, and Monetary metrics. Applied IQR outlier filtering and StandardScaler normalization.
3. **Unsupervised Clustering:** Evaluated K-Means, Agglomerative Hierarchical, and DBSCAN. K-Means (k=4) selected via Silhouette Score to define target personas (Champions, Loyal/Regulars, New/Promising, Lost/Churned).
4. **Predictive Classification:** Supervised modeling using a Random Forest Classifier. Tuned via GridSearchCV to achieve 99.0% accuracy in predicting customer segments.

## Repository Structure
├── data/
│   ├── data.csv                      # Raw transactional dataset
│   └── customer_segments.csv         # Processed RFM data with cluster labels
├── notebooks/
│   └── E_commerce_Segmentation.ipynb # Core ML pipeline and EDA
├── models/
│   └── tuned_rf_segmentation.pkl     # Serialized Random Forest model
├── dashboards/
│   └── Customer_Intelligence.pbix    # Power BI dashboard file
├── docs/
│   └── Final_Report.docx             # Stakeholder business insights report
└── README.md

## Installation & Execution
1. Clone the repository and install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn joblib