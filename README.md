# RFM Customer Segmentation Using Python

A data analytics project that uses **Recency, Frequency and Monetary (RFM) analysis** to understand customer purchasing behaviour, identify valuable customers, and develop data-driven marketing strategies.

## 1. Project Overview

Customer segmentation helps businesses understand different types of customers based on their purchasing behaviour.

In this project, RFM analysis is applied to an online retail transaction dataset to classify customers into six segments:

- Champions
- Loyal Customers
- Potential Loyalists
- At Risk
- Lost
- Others

The objective is to help businesses improve customer retention, identify high-value customers and make better marketing decisions.

## 2. Business Problem

Retail businesses generate large amounts of transaction data but may struggle to identify:

- Who are their most valuable customers?
- Which customers purchase frequently?
- Which customers have stopped purchasing?
- Which customers have the potential to become loyal?
- How should marketing strategies differ across customer groups?

This project addresses these questions using RFM-based customer segmentation.

## 3. Dataset

**Dataset:** Online Retail Dataset

**Source:** UCI Machine Learning Repository

The dataset contains retail transaction records with the following columns:

| Column | Description |
|---|---|
| InvoiceNo | Unique invoice number |
| StockCode | Product code |
| Description | Product description |
| Quantity | Number of products purchased |
| InvoiceDate | Transaction date and time |
| UnitPrice | Price per unit |
| CustomerID | Unique customer identifier |
| Country | Customer's country |

## 4. Technologies Used

- **Python** – Data analysis and processing
- **Pandas** – Data cleaning and manipulation
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Google Colab** – Development environment
- **GitHub** – Project documentation and version control

## 5. Project Workflow

### Step 1: Data Loading and Exploration
- Loaded the retail transaction dataset.
- Inspected dataset dimensions, columns and data types.
- Identified missing values and duplicate records.

### Step 2: Data Cleaning
- Removed records with missing CustomerID.
- Removed duplicate transaction rows.
- Removed cancelled invoices beginning with `C`.
- Removed transactions with invalid quantities and prices.
- Converted InvoiceDate into datetime format.
- Created a TotalAmount column using:

  `TotalAmount = Quantity × UnitPrice`

### Step 3: RFM Metric Calculation

Calculated three customer-level metrics:

| Metric | Definition |
|---|---|
| Recency | Number of days since the customer's latest purchase |
| Frequency | Number of unique invoices per customer |
| Monetary | Total amount spent by the customer |

The snapshot date was defined as one day after the latest transaction date.

### Step 4: RFM Scoring

- Assigned scores from 1 to 5 using quintile-based scoring.
- Lower Recency values received higher scores.
- Higher Frequency and Monetary values received higher scores.
- Combined the three scores into a three-digit RFM score.

### Step 5: Customer Segmentation

Customers were classified into six segments using their Recency and Frequency scores.

| Segment | Description |
|---|---|
| Champions | Recent and frequent purchasers |
| Loyal Customers | Regular purchasers |
| Potential Loyalists | Recent customers with lower purchase frequency |
| At Risk | Previously frequent customers who have not purchased recently |
| Lost | Inactive and infrequent customers |
| Others | Customers who do not match the other segment conditions |

### Step 6: Segment Analysis

Analysed customer segments using:
- Customer count
- Customer percentage
- Average Recency
- Average Frequency
- Total segment revenue
- Revenue contribution percentage

### Step 7: Data Visualization

Created four visualizations:

1. Customer Distribution Across Segments
2. Revenue Contribution by Customer Segment
3. Purchase Frequency vs Monetary Value
4. Customer Recency Distribution

### Step 8: Business Recommendations

Developed targeted marketing strategies for each customer segment based on its purchasing behaviour.

## 6. Key Findings

The analysis identified the following customer distribution:

| Customer Segment | Customer Percentage |
|---|---:|
| Champions | 26.26% |
| Lost | 24.55% |
| Loyal Customers | 18.93% |
| At Risk | 14.82% |
| Others | 8.09% |
| Potential Loyalists | 7.35% |

**Key observations:**

- Champions form the largest customer segment.
- Lost customers represent a significant opportunity for reactivation analysis.
- Loyal Customers provide opportunities for repeat purchases and cross-selling.
- The Recency distribution identifies customers with extended periods of inactivity.
- Champions appear to contribute a substantial proportion of total revenue. The exact contribution should be taken from the final segment summary.

## 7. Business Recommendations

| Customer Segment | Recommended Strategy |
|---|---|
| Champions | Loyalty rewards, exclusive benefits and early product access |
| Loyal Customers | Upselling, cross-selling and referral programs |
| Potential Loyalists | Welcome offers and second-purchase discounts |
| At Risk | Personalized discounts and win-back campaigns |
| Lost | Low-cost customer reactivation campaigns |
| Others | Monitor purchasing behaviour and test relevant promotions |

## 8. Project Structure

```text
rfm-customer-segmentation/
│
├── data/
│   └── Online Retail.xlsx
│
├── notebooks/
│   └── RFM_Customer_Segmentation.ipynb
│
├── outputs/
│   ├── cleaned_retail_data.csv
│   ├── rfm_segments.csv
│   ├── segment_summary.csv
│   ├── customer_distribution.png
│   ├── revenue_contribution.png
│   ├── frequency_vs_monetary.png
│   └── recency_distribution.png
│
└── README.md
```

## 9. How to Run the Project

### Step 1: Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/rfm-customer-segmentation.git
```

### Step 2: Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn openpyxl
```

### Step 3: Open the notebook

Open `RFM_Customer_Segmentation.ipynb` using Google Colab or Jupyter Notebook.

### Step 4: Load the dataset

Download the Online Retail dataset from the UCI Machine Learning Repository and upload it to your notebook environment.

### Step 5: Execute the notebook

Run the notebook cells sequentially to perform data cleaning, RFM calculation, customer segmentation, analysis and visualization.

## 10. Future Enhancements

The project can be extended with:

- K-Means clustering to compare machine-learning-based customer groups with rule-based RFM segments.
- Power BI dashboard for interactive customer analysis.
- Customer Lifetime Value (CLV) estimation.
- Time-based RFM analysis to monitor changes in customer behaviour.
- Campaign performance evaluation and customer retention analysis.

## 11. Conclusion

This project demonstrates how retail transaction data can be transformed into actionable customer insights using Python and RFM analysis.

By identifying valuable, loyal, potential, at-risk and inactive customers, businesses can develop targeted marketing strategies, improve customer engagement and make data-driven decisions.

## 12. Author

**Samhitha Sura**

