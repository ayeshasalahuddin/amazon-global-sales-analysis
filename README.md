# 🛒 Amazon Global Sales Analysis | Power BI Project

## 📊 Overview
An end-to-end business intelligence project analyzing Amazon's global retail sales data (2010–2017) to uncover profitability patterns across regions, product categories, and sales channels — culminating in a 9-page interactive Power BI dashboard with cross-filtering, slicers, and navigation.

---

## 🎯 Business Problem
Amazon's global retail operations span **7 regions** and **100+ countries** with **12 product categories**, yet management lacks visibility into which regions, item types, and sales channels are most profitable. With increasing global competition, leadership needs a data-driven strategy to:

- Identify top-performing markets
- Prioritize high-margin product categories
- Optimize between Online and Offline channels
- Improve fulfilment efficiency across regions

---

## 🗂️ Dataset

| Detail | Value |
|--------|-------|
| **Source** | [Kaggle – Amazon Sales Data](https://www.kaggle.com/datasets/mithilesh9/amazon-sales-data-analysis) |
| **Records** | 1,000 global sales orders |
| **Time Period** | 2010 – 2017 |
| **Coverage** | 7 regions, 100+ countries, 12 product categories |
| **KPIs (Numerical Facts)** | Total Revenue, Total Profit, Total Cost, Units Sold |
| **Categorical Variables** | Region, Country, Item Type, Sales Channel, Order Priority |

---

## 🛠️ Tech Stack

- **Python** (pandas, numpy, matplotlib, seaborn) — data cleaning & exploratory analysis
- **Power BI Desktop** — interactive dashboard, DAX measures, Power Query
- **Jupyter Notebook** — documented cleaning workflow

---

## 🧹 Data Cleaning Highlights

| Step | Action |
|------|--------|
| Date parsing | Converted `Order Date` & `Ship Date` from text to datetime |
| Priority decoding | Mapped codes `H/M/L/C` → `High/Medium/Low/Critical` |
| Feature engineering | Derived `Year`, `Month`, `Quarter`, `Day Name` from Order Date |
| Fulfilment metric | Created `Days to Ship` = Ship Date − Order Date |
| Profitability metric | Created `Profit Margin %` = (Total Profit ÷ Total Revenue) × 100 |
| Validation | Confirmed no missing values or duplicate orders |

Full step-by-step code is in [`notebooks/Amazon_Data_Cleaning.ipynb`](notebooks/Amazon_Data_Cleaning.ipynb).

---

## 📈 Key Findings

| # | Finding | Insight |
|---|---------|---------|
| 1 | 🌍 **Sub-Saharan Africa leads** | #1 region by revenue ($39M) and profit — challenges assumptions about Western-market dominance |
| 2 | 💰 **Margin ≠ Revenue** | Cosmetics tops revenue ($19M), but Office Supplies has the strongest profit margins (35%+) |
| 3 | 💻 **Online edges out Offline** | 57.6% of revenue comes from Online, with slightly higher margins |
| 4 | 📉 **2014 anomaly** | Sharp, unexplained dip in both revenue and profit — flagged for further investigation |
| 5 | 📅 **Seasonality** | April is consistently the strongest month for sales |
| 6 | 🚚 **Fulfilment gap** | Average shipping time of ~25 days, with regional variation worth addressing |

---

## 💡 Recommendations

1. **Investigate the 2014 revenue crash** — identify root cause to prevent recurrence
2. **Increase investment in Sub-Saharan Africa** — already the top-performing region
3. **Shift marketing budget toward the Online channel** — higher margins, growing share
4. **Expand Cosmetics & Office Supplies category lines** — dominant in revenue and profit respectively
5. **Reduce fulfilment time in slower regions** — build regional logistics capacity

---

## 📸 Dashboard Preview

| Executive Summary | Regional Analysis |
|---|---|
| ![Executive Summary](screenshots/03_executive_summary.png) | ![Regional Analysis](screenshots/04_regional.png) |

| Category Performance | Time Series Trend |
|---|---|
| ![Category Performance](screenshots/06_category.png) | ![Time Series](screenshots/08_timeseries.png) |

*(See the `screenshots/` folder for all dashboard pages)*

---

## 📂 Repository Structure

```
Amazon-Global-Sales-Analysis/
│
├── README.md                              ← You are here
├── .gitignore
├── data/
│   └── Amazon_Sales_Clean.csv              ← Cleaned dataset
├── notebooks/
│   └── Amazon_Data_Cleaning.ipynb          ← Python cleaning & EDA
├── powerbi/
│   └── Amazon_Sales_Analysis.pbix          ← Power BI report file
├── report/
│   └── Amazon_Global_Sales_Report.docx     ← Full written report
├── presentation/
│   └── Amazon_Final_Presentation.pptx      ← Slide deck
└── screenshots/
    ├── 01_title.png
    ├── 02_problem.png
    ├── 03_executive_summary.png
    ├── 04_regional.png
    ├── 05_country.png
    ├── 06_category.png
    ├── 07_channel.png
    └── 08_timeseries.png
```

---

## 🚀 How to Run This Project

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/amazon-global-sales-analysis.git
   ```
2. **Run the data cleaning notebook**
   - Open `notebooks/Amazon_Data_Cleaning.ipynb` in Jupyter Notebook, VS Code, or Google Colab
   - Run all cells to regenerate the cleaned CSV
3. **Open the Power BI report**
   - Open `powerbi/Amazon_Sales_Analysis.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
   - Explore the 9 interactive pages: Title, Problem Statement, Executive Summary, Regional Analysis, Country Performance, Category Analysis, Channel Comparison, Time Series, and Recommendations

---

## 📊 DAX Measures Used

```dax
Total Revenue = SUM('Amazon Sales data'[Total Revenue])
Total Profit = SUM('Amazon Sales data'[Total Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Revenue], 0) * 100
Avg Days to Ship = AVERAGE('Amazon Sales data'[Days to Ship])
Total Orders = COUNTROWS('Amazon Sales data')
```

---

## 👥 Authors

- **Ayesha Salahuddin** (29157)
- **Narin Nadeem** (29167)

---

## 📄 License

This project is for educational purposes as part of a Business Intelligence course assignment.
