📊 Sales Analytics Dashboard — Power BI
Overview
An interactive sales analytics dashboard built in Power BI analysing transactional sales data across UAE emirates, product subdivisions, and customer accounts. The dashboard enables business stakeholders to monitor revenue performance, margin health, and sales trends across multiple fiscal years.
🛠️ Tools & Technologies

Power BI Desktop — dashboard development and visualisation
DAX — custom measures for KPIs and margin analysis
Microsoft Excel — data source and preparation
Power Query — data transformation and cleaning

📁 Dataset

9,939 sales transactions spanning October 2022 to April 2026
Covers 3 product subdivisions across 8 UAE emirates
Fields include: invoice date, account name, salesman, product, quantity, rate, sales value, cost, margin, and VAT


⚠️ Note: Dataset used in this project is pseudo/anonymised data generated to replicate the structure of real sales data. No real company or customer information is included.



📌 Dashboard Features

Date range slicer — filter all visuals by invoice date
Fiscal year filter — slice by FY22-23 through FY25-26
Total Sales KPI card — AED 589M total across the period
Margin Calculator gauge — current margin vs 43% target
Sales Value by Emirate — bar chart showing regional revenue distribution
Sales Value by Month — trend line showing monthly revenue patterns
Sales Value by Subdivision — pie chart showing product category split
Top Products table — ranked by sales value with quantity
Top Accounts table — customer level revenue and margin breakdown

📐 Key DAX Measures
daxTotal Sales = SUM('Table 1 (Sheet1)'[SALES VALUE])

Margin % = DIVIDE(SUM('Table 1 (Sheet1)'[MARGIN]), SUM('Table 1 (Sheet1)'[SALES VALUE]), 0)

Target Margin = 0.43

Average Order Value = DIVIDE([Total Sales], COUNTROWS('Table 1 (Sheet1)'), 0)

Total Transactions = COUNTROWS('Table 1 (Sheet1)')

MoM Growth =
VAR CurrentMonth = [Total Sales]
VAR LastMonth = CALCULATE([Total Sales], DATEADD('Table 1 (Sheet1)'[INVOICE DATE], -1, MONTH))
RETURN DIVIDE(CurrentMonth - LastMonth, LastMonth, 0)
📊 Key Insights

Dubai accounts for the largest share of revenue at approximately 49% of total sales
Certify Spares subdivision drives 70.83% of total revenue
November and December show consistent revenue peaks across fiscal years
Average margin of 53% is above the 43% target
Total of 9,939 transactions recorded across the analysis period

🖼️ Dashboard Screenshots
Page 1 — Sales Overview
Show Image

📂 Repository Structure
├── README.md
├── data/
│   └── WD_SALES_DATA_PSEUDO.xlsx
└── screenshots/
    ├── Bar Chart Sales Value By Emirate.png
    └── KPI Trackers And Filters.png
    └── Pie Chart_Sales Value By Sub Division
    └── Sales Dashboard Overall
    └── Sales Value By Month
    └── Tables Showing Highest Sold Parts And Most Profitable Customers
👤 Author
Snehal D Souza
Data & Operations Analyst | MSc Data Science (Distinction) | AWS & Power BI Certified

This project was built as part of a personal portfolio to demonstrate data analytics and business intelligence skills.
