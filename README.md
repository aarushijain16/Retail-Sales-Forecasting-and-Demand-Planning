# Retail-Sales-Forecasting-and-Demand-Planning

# Overview
This project demonstrates how machine learning-based sales forecasting can support inventory planning, promotion strategy, and operational decision-making for a multi-store retail chain.

Using Python, SAS, and Excel, I built and evaluated predictive models to forecast retail sales while accounting for:

- Store heterogeneity

- Promotions

- Holidays and seasonality

- Assortment differences

Due to data confidentiality, raw datasets and full code cannot be shared. This case study focuses on approach, insights, and business relevance.

# Business Problem

Retail drugstore chains face recurring challenges:

- Demand volatility across store types

- Promotion that work in some contexts butnot others

- Seasonal and holiday-driven demand spikes

- Difficulty aligning inventory and staffing with expected sales

Key questions addressed:

- How can sales be forecasted accurately at store level?

- Which variables have the strongest impact on sales?

- How can forecasting models be adapted for different store profiles?

- How can insights trabslate into better promotion and inventory planning?

# Solution Approach

I designed a cluster-aware forecasting framework to improve prediction accuracy across heterogeneous retail stores.

**🔹 Exploratory Data Analysis**

- Analysed sales and customer patterns by:

- Store type

- Assortment

- Day of week

- State and school holidays

- Promotional flags

- Identified strong variability across store contexts, motivating segmentation before modeling.

**🔹 Feature Engineering**

- Time-based features (day, month, year, seasonality)

- Holiday and promotion indicators

- Store and assortment attributes

- Customer count as a demand signal

**🔹 Store Clustering for Model Optimization**

- Grouped stores with similar sales and customer behavior

- Further sub-clustered based on seasonality patterns

- Enabled model specialization per cluster instead of one-size-fits-all forecasting

**🔹 Predictive Modeling**

- Random Forest Regressor (best-performing model)

- Multilayer Perceptron (Neural Network) as a benchmark

- Models evaluated using RMSE and RMSPE

- Best model selected per cluster to maximize accuracy

# Key Business Insights and Impact

## *(Scaled to large retail operations)*

- Store type and assortment were major drivers of sales variability
 → Forecasts must be context-specific, not global

- Promotions showed uneven impact across stores and time periods
 → Targeted promotions outperform blanket discounting

- Holidays significantly altered demand patterns
 → Advance forecasting enables proactive inventory and staffing alignment

- Cluster-based Random Forest models delivered the most reliable forecasts
 → Improved short-term planning and reduced demand uncertainty

# Strategic Recommendations

- Use cluster-specific forecasting models for demand planning

- Align inventory replenishment with predicted demand by store type

- Focus promotions on historically underperforming contexts

- Avoid over-promotion in stores where uplift is marginal

- Integrate forecasts into weekly and monthly planning cycles

# Tools & Technologies

- Python (Pandas, NumPy, Scikit-learn)

- Machine Learning: Random Forest, Neural Networks

- SAS Enterprise Guide

- Excel

- Visualization: Matplotlib, Seaborn

# Why this Matters for Your Business

This project shows how sales forecasting can:

- Reduce stock-outs and excess inventory

-   Improve promotion ROI

- Support store-level operational planning

- Turn historical sales data into forward-looking decisions

The same framework can be adapted for:

- Retail chains

- Supermarkets and drugstores

- Multi-location businesses

- Promotion-heavy retail environments

# 📌 Confidentiality Note

This project was completed using a confidential proprietary dataset from a German drugstore chain.

Raw data and full code cannot be shared publicly.

# 💬 How I Can Help You

If your business needs to:

- Forecast sales across stores or regions

- Improve inventory and promotion planning

- Handle strong seasonality and demand variability

I can adapt this approach to your real retail data and deliver:

- Forecasting models

- Demand insights

- Planning-ready outputs

- Clear, business-focused recommendations
