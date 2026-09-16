<img width="949" height="527" alt="Screenshot 2026-09-16 150325" src="https://github.com/user-attachments/assets/2f120b55-dac6-4bd5-b129-caa6c6b2c3e0" />
<img width="947" height="417" alt="Screenshot 2026-09-16 150405" src="https://github.com/user-attachments/assets/4d802e72-1c19-4b61-94f0-f23cee689f0d" />
<img width="945" height="449" alt="Screenshot 2026-09-16 150444" src="https://github.com/user-attachments/assets/d2d6fb29-10c5-4c6b-9689-7daab5ccc207" />

[amazon_clean_with_calculated_functions.csv](https://github.com/user-attachments/files/32027766/amazon_clean_with_calculated_functions.csv)
[Amazon_cleaned-data.csv](https://github.com/user-attachments/files/32027753/Amazon_cleaned-data.csv)
[Amazon_cleaned-data.csv](https://github.com/user-attachments/files/32027735/Amazon_cleaned-data.csv)
[amazon_delivery_data_dirty_sales_500 (2).csv](https://github.com/user-attachments/files/32027712/amazon_delivery_data_dirty_sales_500.2.csv)
# 🚚 Amazon Delivery Logistics: Data Cleaning & Financial Loss Analysis

## 📌 Project Overview
In last-mile logistics, operational friction—such as delivery delays, package damages, and failed attempts—directly impacts bottom-line profitability. This project analyzes **500+ delivery records** from Q1 2024 to evaluate the financial impact of operational bottlenecks, identify primary loss drivers, and quantify revenue leakage.

This project demonstrates an end-to-end data analysis workflow, transforming raw, "dirty" operational data into structured business intelligence exclusively using **Microsoft Excel**.

---

## 🛠️ Data Cleaning & Transformation Pipeline
The raw dataset contained intentional structural anomalies, missing values, and formatting errors typical of real-world operational logs. The following cleaning procedures were executed in Excel:

* **Duplicate Removal:** Identified and purged 30 duplicate records using **Data > Remove Duplicates** to ensure accurate order counts.
* **Text Standardization:** Utilized `=PROPER()` to resolve case-sensitivity inconsistencies across categorical fields (`Region`, `Vehicle_Type`).
* **Missing Value Imputation:** Isolated blank fields in `Delay_Minutes` and `Package_Weight_Kg` using **Go To Special > Blanks** (`Ctrl + G`) and bulk-imputed `0` via `Ctrl + Enter`.
* **Data Type Normalization:** Applied `=IFERROR(VALUE(), 0)` to convert non-numeric text strings (e.g., `"N/A"`) into clean numerical values.
* **Outlier & Sign Correction:** Used `=ABS()` to convert negative values in `Financial_Loss_USD` and `Package_Weight_Kg` into valid positive figures.
* **Static Value Locking:** Applied **Paste Special > Values** to convert helper formula columns into permanent, static datasets.


## 📊 Key Business Findings (Q1 2024)

* **Gross Sales Revenue:** **$641,899.06**
* **Total Financial Losses:** **$483,661.36**
* **Net Revenue Realized:** **$158,237.70**
* **Overall Loss Margin Ratio:** **75.35%** (Financial losses absorbed nearly three-quarters of total gross revenue).

### Monthly Financial Performance

| Metric | January 2024 | February 2024 | March 2024 | Q1 Total |
| :--- | :--- | :--- | :--- | :--- |
| **Gross Sales (USD)** | $202,795.17 | $196,495.83 | $242,608.06 | **$641,899.06** |
| **Financial Loss (USD)** | $148,349.96 | $148,746.49 | $186,564.91 | **$483,661.36** |
| **Net Revenue (USD)** | $54,445.21 | $47,749.34 | $56,043.15 | **$158,237.70** |
| **Loss Ratio (% Sales)** | **73.15%** | **75.70%** | **76.90%** | **75.35%** |

## 📈 Dashboard & Visualizations Breakdown

The Q1 Performance Dashboard evaluates monthly gross revenue vs. operational financial losses:

* **Sales Trajectory (Orange Bars):** Sales remained stable through January ($202.8K) and February ($196.5K), followed by a significant surge in March ($242.6K)—a **23.5% growth** over February.
* **Financial Loss Trajectory (Blue Bars):** Losses closely tracked monthly sales volume, increasing from $148.3K in January to $186.6K in March—a **25.8% increase** in losses.
* **Key Visual Takeaway:** The side-by-side bar chart clearly illustrates that as revenue grew in March, financial losses grew even faster. This confirms that revenue expansion is currently driving loss escalation due to underlying operational friction.

## 💡 Analytical Insights & Strategy

1. **Volume-Scaling Losses:** Financial losses scaled aggressively alongside order volume. March achieved the highest gross sales ($242.6K) but yielded the highest loss ratio (**76.90%**), demonstrating that volume expansion without operational efficiency erodes profit margins.
2. **Margin Erosion:** Net revenue remained stagnant across the quarter despite revenue growth, indicating systemic operational issues (e.g., damaged goods, vehicle breakdowns, customer refusals).
3. **Actionable Recommendations:** Implement driver-level tracking on high-loss reason codes, establish weight-based vehicle routing optimization, and review packaging standards for high-value items.

---

## 📁 Repository Structure

```text
├── data/
│   ├── raw_amazon_delivery_dirty.csv      # Original uncleaned dataset
│   └── cleaned_amazon_delivery_sales.csv  # Processed, clean dataset
├── dashboards/
│   └── q1_financial_summary_chart.png     # Screenshot of Excel Pivot Chart
└── README.md                              # Project documentation
