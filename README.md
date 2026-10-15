# 🛒 Retail Demand Forecasting & Inventory Optimization

An intelligent retail analytics and inventory decision-support system that combines **demand forecasting, inventory analysis, risk detection, and what-if scenario simulation** to help businesses make proactive inventory decisions.

> **Don't just predict what will sell — predict what will happen and recommend what the business should do next.**

---

## 📌 Project Overview

Retail businesses need to maintain the right amount of inventory while responding to changing customer demand, promotions, pricing, holidays, and supplier lead times.

This project uses the **M5 Walmart Retail Forecasting Dataset** to build an end-to-end retail analytics and inventory optimization workflow.

The system can:

* Forecast future product demand
* Analyze historical demand and seasonality
* Calculate recommended stock
* Estimate safety stock
* Identify stockout risk
* Detect potential overstock
* Simulate price and promotion scenarios
* Consider holiday/event impact
* Account for supplier lead time
* Calculate product priority
* Generate inventory recommendations
* Provide an interactive Streamlit dashboard

---

# 🎯 Project Objectives

The main objectives of the project are:

1. Forecast future retail product demand.
2. Build a reliable retail data pipeline.
3. Transform raw sales data into analytics-ready datasets.
4. Analyze demand trends and seasonality.
5. Estimate recommended inventory requirements.
6. Identify potential stockout situations.
7. Detect excess inventory.
8. Simulate different business scenarios.
9. Generate actionable inventory recommendations.
10. Provide an interactive dashboard for business decision-making.

---

# 🧠 Key Innovation

Traditional forecasting systems mainly answer:

> **"How much will we sell?"**

This project goes one step further:

> **"What is likely to happen, and what should the business do next?"**

The system connects demand forecasting with inventory decision intelligence.

### Decision Flow

```text
Historical Sales
       ↓
Data Engineering
       ↓
Data Transformation
       ↓
Demand Forecast
       ↓
What-If Scenario Analysis
       ↓
Inventory Requirement
       ↓
Stockout / Overstock Risk
       ↓
Priority Score
       ↓
Recommended Action
       ↓
Interactive Dashboard
```

---

# 📊 Dataset

The project uses the **M5 Forecasting Dataset**, based on Walmart retail sales data.

The dataset contains information related to:

* Products
* Departments
* Categories
* Stores
* States
* Daily sales
* Calendar events
* Prices
* Historical demand

### Main Data Sources

```text
sales_train_validation
sales_train_evaluation
calendar
sell_prices
```

---

# 🏗️ System Architecture

```text
                 M5 Retail Dataset
                         │
                         ▼
                  Google BigQuery
                         │
                         ▼
                       dbt
                         │
                         ▼
               Data Transformation
                         │
                         ▼
                Analytics-Ready Data
                         │
                         ▼
              ┌───────────────────┐
              │ Demand Forecasting│
              │      Prophet      │
              └───────────────────┘
                         │
                         ▼
                 Forecast Output
                         │
            ┌────────────┼────────────┐
            ▼            ▼            ▼
       Stockout      Overstock    What-If
         Risk          Risk       Scenarios
            │            │            │
            └────────────┼────────────┘
                         ▼
                 Inventory Intelligence
                         │
                         ▼
                Recommended Actions
                         │
                         ▼
                  Streamlit Dashboard
```

---

# 🛠️ Technology Stack

| Technology      | Purpose                              |
| --------------- | ------------------------------------ |
| Python          | Data processing and machine learning |
| Pandas          | Data manipulation                    |
| SQL             | Data querying                        |
| Google BigQuery | Cloud data warehouse                 |
| dbt             | Data transformation                  |
| Prophet         | Time-series demand forecasting       |
| Streamlit       | Interactive dashboard                |
| Git             | Version control                      |
| GitHub          | Source control and collaboration     |

---

# 📁 Project Structure

```text
retail-demand-forecasting/
│
├── dashboard.py
│
├── forecasting/
│   ├── prophet_forecast.py
│   ├── prophet_evaluation.py
│   ├── prophet_seasonality.py
│   └── prophet_metrics_improved.py
│
├── models/
│   ├── staging/
│   ├── intermediate/
│   └── marts/
│
├── data/
│
├── outputs/
│
├── logs/
│
├── target/
│
├── dbt_project.yml
├── README.md
└── .gitignore
```

---

# 🔄 Project Development

## Week 1 — Data Architecture & ETL

### Completed Work

* BigQuery environment setup
* M5 raw data integration
* Data quality validation
* Data cleaning
* Data readiness checks
* Data formatting
* Documentation and handover

### Objective

Prepare the raw M5 retail data for reliable downstream transformation and forecasting.

---

# 🔧 Week 2 — dbt Data Transformation

The project uses **dbt** to transform raw BigQuery data into analytics-ready datasets.

### Completed Work

* dbt project setup
* BigQuery connection verification
* Raw source configuration
* Daily sales transformation
* Sales and pricing integration
* Weekly demand aggregation
* Demand mart creation
* Transformation documentation

### Transformation Pipeline

```text
Raw BigQuery Tables
        ↓
Daily Sales
        ↓
Sales + Pricing
        ↓
Weekly Demand
        ↓
Analytics Mart
```

---

# 📈 Week 3 — Demand Forecasting

The project uses **Prophet** for time-series demand forecasting.

### Forecasting Capabilities

* Historical demand analysis
* Trend detection
* Weekly seasonality
* Yearly seasonality
* Holiday/event effects
* Future demand prediction
* Forecast confidence intervals

### Model Evaluation

The forecasting workflow includes:

* MAE
* RMSE
* MAPE
* WAPE
* SMAPE

> Model performance depends on the selected product and forecasting configuration.

---

# 🖥️ Week 4 — Dashboard & Inventory Intelligence

The fourth week focuses on converting forecasting results into an interactive inventory decision-support system.

## Day 1 — Streamlit Dashboard

### Features

* Streamlit dashboard setup
* Professional dashboard structure
* Store selection
* Department/category selection
* Forecast period selection
* Demand forecast visualization
* Actual vs forecast comparison
* Confidence interval visualization
* Demand trend analysis
* Initial stockout risk visualization

---

## Day 2 — Inventory Recommendations

### Features

* Forecasted demand calculation
* Safety stock calculation
* Recommended stock calculation
* Restocking recommendation
* Restock priority
* Inventory requirement analysis

### Recommended Stock

```text
Recommended Stock
=
Forecasted Demand
+
Safety Stock
```

The current safety-stock approach uses a forecast-based percentage.

---

## Day 3 — What-If Scenario Simulator

The dashboard includes an interactive scenario simulator.

### Scenario Inputs

* Price change
* Promotion impact
* Holiday/event impact
* Supplier lead time
* Current inventory

### Price Change

Users can simulate the estimated impact of price changes on demand.

### Promotion Impact

Users can simulate increased demand caused by promotional activity.

### Holiday/Event Impact

Users can simulate additional demand caused by events or holidays.

### Lead Time

The system estimates additional inventory requirements based on supplier lead time.

```text
Lead Time Stock
=
Daily Demand × Lead Time
```

### Inventory Impact

The system compares:

```text
Required Inventory
vs
Current Inventory
```

and calculates the inventory gap.

### Stockout Risk

The dashboard converts inventory shortage into a risk score from:

```text
0 → 100
```

Risk classification:

```text
0–39   → Low Risk
40–69  → Medium Risk
70–100 → High Risk
```

---

## Day 4 — Dashboard Intelligence

Day 4 adds decision-oriented intelligence to the dashboard.

### 🎯 Product Priority

A priority score is generated using stockout risk and demand change.

```text
Priority Score
=
Stockout Risk × 60%
+
Demand Change × 40%
```

Priority levels:

```text
70–100 → High Priority
40–69  → Medium Priority
0–39   → Low Priority
```

### ⚠️ Risk Classification

Products/scenarios are classified into:

```text
🔴 High Risk
🟡 Medium Risk
🟢 Low Risk
```

### 📦 Overstock Detection

The dashboard identifies potential excess inventory by comparing current inventory against a forecast-based threshold.

### 💡 Recommended Action

The system provides an inventory action based on the current scenario, such as:

* Increase inventory
* Prioritize replenishment
* Monitor inventory
* Reduce excess inventory
* Maintain current inventory

### 📊 Inventory Action Summary

The dashboard summarizes:

* Priority Score
* Stockout Risk
* Inventory Condition
* Recommended Action

---

# 👥 Team Development

The project was developed collaboratively.

### Week 4 Team Completion

| Day   | Status      | Responsibility             |
| ----- | ----------- | -------------------------- |
| Day 1 | ✅ Completed | Dashboard foundation       |
| Day 2 | ✅ Completed | Inventory recommendations  |
| Day 3 | ✅ Completed | What-if scenario simulator |
| Day 4 | ✅ Completed | Dashboard intelligence     |
| Day 5 | ✅ Completed | Teammate                   |
| Day 6 | ✅ Completed | Teammate                   |
| Day 7 | ✅ Completed | Teammate                   |

**Week 4 is therefore fully completed as a team.**

---

# 🎯 Business Value

## Reduce Stockouts

Identify products that may require replenishment before demand exceeds available inventory.

## Reduce Overstock

Detect inventory levels that may be unnecessarily high.

## Improve Inventory Planning

Use demand forecasts to support procurement and replenishment decisions.

## Simulate Business Scenarios

Test possible changes in:

* Pricing
* Promotions
* Holidays
* Supplier lead time
* Inventory

before making decisions.

## Improve Decision Making

Convert forecasting outputs into practical inventory actions.

---

# 🧪 Testing

The dashboard was tested using multiple scenarios.

### Test 1 — Normal Inventory

```text
Current Inventory = 100
```

Used to verify normal inventory behavior.

### Test 2 — Low Inventory

```text
Current Inventory = 10
```

Used to verify increased stockout risk.

### Test 3 — Overstock

```text
Current Inventory = 1000
```

Used to verify overstock detection.

### Test 4 — High Demand Scenario

```text
Holiday Impact = 50%
Lead Time = 30 days
```

Used to verify increased inventory requirements.

---

# 🚀 How to Run the Project

## 1. Clone the Repository

```bash
git clone https://github.com/shubhamsinghsarkar61/retail-demand-forecasting.git
```

```bash
cd retail-demand-forecasting
```

---

## 2. Install Dependencies

```bash
pip install pandas numpy prophet streamlit google-cloud-bigquery dbt-bigquery
```

---

## 3. Configure Google Cloud

The project uses Google BigQuery for retail data.

Configure Google Cloud authentication:

```bash
gcloud auth application-default login
```

---

## 4. Check dbt

```bash
dbt debug
```

---

## 5. Compile dbt Models

```bash
dbt compile
```

---

## 6. Run the Streamlit Dashboard

```bash
streamlit run dashboard.py
```

Then open:

```text
http://localhost:8501
```

---

# 📌 Project Progress

| Phase                                    | Status                  |
| ---------------------------------------- | ----------------------- |
| Week 1 — Data Architecture & ETL         | ✅ Completed             |
| Week 2 — dbt Transformation              | ✅ Completed             |
| Week 3 — Prophet Forecasting             | ✅ Completed             |
| Week 4 Day 1 — Dashboard Foundation      | ✅ Completed             |
| Week 4 Day 2 — Inventory Recommendations | ✅ Completed             |
| Week 4 Day 3 — What-If Simulator         | ✅ Completed             |
| Week 4 Day 4 — Dashboard Intelligence    | ✅ Completed             |
| Week 4 Day 5                             | ✅ Completed by teammate |
| Week 4 Day 6                             | ✅ Completed by teammate |
| Week 4 Day 7                             | ✅ Completed by teammate |
| **Overall Project**                      | **✅ Completed**         |

---

# 🔮 Future Enhancements

Potential future improvements include:

* LightGBM granular item forecasting
* SHAP-based forecast explanations
* Multi-product priority ranking
* Store-to-store inventory transfer recommendations
* Advanced inventory optimization
* Automated reorder quantity
* More realistic safety-stock calculations
* Supplier optimization
* Advanced what-if simulations
* Dashboard authentication
* Production deployment

---

# 👩‍💻 My Contribution

**Keerdhagshini K**
B.Tech — Artificial Intelligence & Data Analytics

### Key Contributions

* Data quality and preparation
* dbt transformations
* Prophet demand forecasting
* Forecast evaluation
* Seasonality analysis
* Streamlit dashboard development
* Inventory intelligence
* What-if scenario analysis
* Stockout risk analysis
* Overstock detection
* Product priority scoring
* Inventory action recommendations
* Git/GitHub version control

The project was completed collaboratively with the team, with additional Week 4 work contributed by teammates.

---

# ⭐ Project Vision

The long-term vision is to evolve the system from a demand forecasting application into an **AI-powered retail inventory decision assistant**.

The system aims to help businesses answer four important questions:

> **What will happen?**

> **Why will it happen?**

> **What should we do?**

> **When should we act?**

---

# 🔗 Repository

GitHub:

https://github.com/shubhamsinghsarkar61/retail-demand-forecasting

---

# 📜 Project Status

✅ **Project Completed**

The four-week retail demand forecasting and inventory optimization workflow has been completed as a collaborative team project.

---

## 📄 License

This project is developed for educational and project-development purposes.
