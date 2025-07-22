
# Country-Level Spend Forecasting with Prophet

## 📈 Objective
This notebook forecasts daily company spend at the country level using historical transactional data. The focus is on selected European markets and leverages Facebook Prophet for time series forecasting.

---

## 🔧 Features & Workflow

1. **🔗 Data Extraction (Google BigQuery)**
   - Fetches company and spend data from:
     - `analytics_companies.companies_current`
     - `analytics_ssot.spend_per_customer_daily`
   - Filters data from **February 2021 onwards**.
   - Aggregates spend metrics by `performed_date` and `country`.

2. **🌍 Country Segmentation**
   - Markets explicitly grouped: GB, DK, DE, ES, SE, NL, FR.
   - All others grouped under `'Other Markets'`.

3. **📊 Feature Engineering**
   - Calculates:
     - Daily spend
     - Spending customer count
     - Spend per spending customer

4. **📅 Time Series Forecasting**
   - Uses **Facebook Prophet** for modeling.
   - Handles public holidays using the `holidays` library.
   - Forecast is done **per country**, modeling each time series individually.

5. **🧪 Model Evaluation**
   - Metrics used: **RMSE**, **R²**, and **MAE**.

6. **📈 Visualization**
   - Plots historical vs. forecasted spend using `matplotlib` and `seaborn`.

---

## ⚙️ Dependencies

- `pandas`, `numpy`
- `seaborn`, `matplotlib`
- `holidays`, `datetime`, `timedelta`
- `prophet`
- `google.cloud.bigquery`, `pandas_gbq`
- `sklearn.metrics`

---

## 📁 How to Use

1. Authenticate to Google Cloud.
2. Run the notebook in a Python environment with access to BigQuery and Prophet.
3. Review and adjust the SQL query as needed.
4. Execute cells to generate forecasts and evaluate performance.

---

## 🔍 Potential Improvements

- Automate model tuning per country.
- Add cross-validation.
- Include macroeconomic or marketing variables as regressors.
- Deploy results to a dashboard or API.
