# Forecasting Approach - German Drugstore Retail Sales

# Forecasting Objective

The objective of this project was to accurately forecast daily retail sales for a large German drugstore chain in order to support:

- Inventory planning

- Promotion effectiveness analysis

- Operational and staffing decisions

Given the heterogeneity across store types, strong seasonality, and promotion-driven demand spikes, a single global forecasting model was deemed inappropriate. Instead, a segmented, machine learning–based forecasting framework was designed.

# Key Forecasting Challenge

Unlike standard time-series forecasting problems, this dataset exhibits:

- Strong cross-sectional variation (store type, assortment)

- Non-linear demand drivers (promotions, holidays)

- Store-specific seasonality

- Missing and irregular observations

Therefore, the forecasting problem was treated as a supervised regression task with temporal features, rather than a pure univariate time-series model.

# Forecasting Strategy Overview

The final forecasting approach consists of four structured stages:

1. Data Preparation & Feature Engineering

- Sales demand was modeled as a function of:

- Store attributes (store type, assortment)

- Promotional activity (Promo, Promo2)

- Calendar effects (day of week, state holidays, school holidays)

- Competition dynamics (competition distance, duration)

Key preprocessing steps included:

- Cleaning missing and inconsistent sales records

- Encoding categorical variables

- Creating time-based features (weekday, seasonality indicators)

- Removing low-informative predictors identified during EDA

*📌 This ensured that demand signals were captured without leaking future information.*

2. Store Segmentation (Clustering-Based Forecasting)

To handle demand heterogeneity, a two-stage segmentation approach was applied:

- Stage 1: Store-Type Grouping

Stores were first grouped based on average sales behavior, separating fundamentally different store types.

- Stage 2: Seasonality-Based Clustering

Within each store-type group:

  - K-Means clustering was applied on normalized sales patterns

  - Optimal cluster count selected using the Elbow Method

  - Result: 9 homogeneous demand clusters

*📌 Each cluster represents stores with similar demand volatility, seasonality, and promotion sensitivity.*

3. Predictive Modeling

For each cluster, two machine learning models were evaluated:

- Random Forest Regressor

- Multilayer Perceptron (MLP) Regressor

Training Strategy

- Feature scaling using MinMaxScaler

- Time-aware train–test split

- Cluster-specific model training

- Hyperparameters tuned per cluster

This approach avoids the instability of fitting a single model across structurally different stores.

4. Model Evaluation & Selection

Models were evaluated using cluster-level error metrics, focusing on robustness rather than isolated accuracy.

- Metrics Used

  - RMSE (Root Mean Squared Error) — primary metric

  - RMSPE — secondary diagnostic metric

- Final Model Selection

  - Random Forest consistently outperformed MLP

  - Lower RMSE across almost all clusters

  - More stable performance across high- and low-volume stores

# 📌 Final Model Chosen:

👉 Cluster-wise Random Forest Regressor

# Note on Actual vs Predicted Visuals

Although actual-vs-predicted plots were explored during analysis, they were not emphasized in the final portfolio due to:

- Use of proxy-driven preprocessing in missing demand periods

- Risk of misrepresenting true demand accuracy

Instead, model comparison visuals (RMSE & RMSPE) were used as the primary validation mechanism, ensuring methodological integrity.
