# Physics-Guided Solar Irradiance Forecasting ☀️🔋

## 📌 Project Overview
**Physics-Guided Solar Irradiance Forecasting** is an advanced environmental data science project developed to predict solar energy potential across 12 distinct regional sites. Traditional forecasting models often struggle with atmospheric interference. To solve this, this project implements a **Physics-Guided LightGBM framework** that establishes a theoretical "Clear Sky" physical baseline, and then utilizes machine learning to calculate the true solar attenuation caused by dynamic meteorological factors and localized air pollution (e.g., PM2.5, Humidity).

## 🚀 Key Features
* **Physics-Informed Architecture:** Integrates a deterministic physical model (`Clear_Sky_GHI`) with a probabilistic machine learning engine (`LightGBM`), significantly improving prediction reliability under complex atmospheric conditions.
* **Large-Scale Data Engineering:** Features a robust data ingestion pipeline that processes, interpolates, and synchronizes 5 years of continuous multi-variate weather and pollutant data across 12 monitoring stations.
* **Seasonal Risk Profiling:** Generates actionable business intelligence for grid operators by mapping the "Average Energy Loss per Month," allowing for strategic energy reserve planning during high-attenuation seasons.
* **Feature Importance Tracking:** Analyzes and ranks the dominant atmospheric drivers of solar loss, proving the statistical impact of variables like temperature, humidity, and airborne particulate matter.

---

## 🏗️ Architecture Details

### The Data Engineering Pipeline (`Dataset_Creation`)
The ETL (Extract, Transform, Load) module consolidates disparate regional and satellite datasets into a unified analytical matrix.
* **Handling Missing Data:** Implements bidirectional linear interpolation (`limit_direction='both'`) to seamlessly patch temporal gaps in the sensor readings without distorting the underlying time-series trends.
* **Feature Consolidation:** Merges standard meteorological data (Temperature, Pressure, Dew Point) with critical air quality indices (PM2.5, PM10, SO2, NO2) and satellite-derived solar metrics.

### The Predictive Engine (`LightGBM`)
The core forecasting model utilizes a highly optimized Gradient Boosting framework.
* **Structure:** Employs `LightGBM` for high-performance, column-wise multi-threaded training, specifically tuned to handle hundreds of thousands of data points efficiently.
* **Physics Integration:** The model uses the theoretical `Clear_Sky_GHI` (Global Horizontal Irradiance) as its anchor feature, learning the non-linear degradation patterns caused by weather and pollution to predict the actual `GHI`.

---

## ⚖️ Forecasting Logic & Grid Strategy
In this framework, the model translates atmospheric data into grid-level financial insights:

1.  **Attenuation Modeling:** Instead of predicting irradiance from scratch, the system calculates the exact power loss ($Loss = Clear\_Sky\_GHI - GHI$) caused by environmental blockers.
2.  **Grid Optimization:** By grouping daylight energy loss dynamically by month, the resulting "Seasonal Risk Profile" directly informs energy providers on when to spin up auxiliary power plants or rely on battery storage.

---

## 📈 Evaluation Metrics
This project utilizes robust visualization and gradient analytics to validate the model's physical accuracy:

* **Feature Dominance:** Real-time tracking of variable importance (e.g., `Clear_Sky_GHI` contributing a score of 3114, closely followed by `TEMP` and `Humidity`), proving the model relies on actual physical drivers rather than spurious correlations.
* **Seasonal Risk Profiling:** Visualized via Seaborn bar plots, quantifying the average W/m² power loss per month for strategic grid load balancing.

---

## 👥 Contributors
This project was developed as an academic dissertation for the **MBA in Data Science & Data Analytics (2024-2026)**.
* **Anik Basu**
