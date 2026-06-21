📊 DataCo Global: Supply Chain & Logistics Performance Analytics
!(https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
!(https://img.shields.io/badge/DAX-Data_Analysis_Expressions-blue?style=for-the-badge)
!(https://img.shields.io/badge/Domain-Supply_Chain_&_Logistics-success?style=for-the-badge)

An end-to-end Power BI portfolio project analyzing 180,000+ supply chain transactions from DataCo Global for the year 2025. This project focuses on translating raw operations data into actionable strategic recommendations for the VP of Logistics and VP of Sales, employing advanced data modeling, clean UI/UX design, and deep-dive business intelligence.

📊 Dashboard Architecture & Layout
The dashboard is designed across 3 highly cohesive pages adhering to professional UI/UX standards, using a custom Dark Theme (Deep Charcoal base to reduce eye strain and meet WCAG contrast guidelines).  

Page 1: Executive Overview
Focuses on high-level financial and operational health.

KPI Cards: Total Sales ($36.78M), Net Profit ($3.97M), Profit Margin (11%), and Orders Count (65.8K).

Time Series Analysis: Stacked Column & Line chart showing Order Volume vs. Late Delivery Rate by Season (Seasonality impact).

Product Performance: Horizontal Bar Chart comparing Sales vs. Profit Margin across categories, identifying Fishing as our most profitable product line ($0.76M).

Shipping Volume: Donut chart outlining the share of orders by shipping mode (Standard Class driving 59.69% of total volume).

<img width="1321" height="742" alt="Executive overview" src="https://github.com/user-attachments/assets/20189cd3-9306-44d9-8b5e-a8f08cd0948a" />

Page 2: Supply Chain & Operations Deep-Dive
Focuses on operational bottlenecks, shipping SLAs, and category-level risk.

Logistics Matrix: Expanded Shipping Mode hierarchy displaying order status details (Fraud, Cancelled, Completed) alongside profit margins and on-time delivery rates.

Scheduled vs. Real Shipping: Clustered Column Chart identifying the SLA breaches in First Class and Second Class shipping.

Top 15 Risk Categories: Sliced bar chart highlighting the top 15 categories driving the late delivery risk.

<img width="1322" height="742" alt="Supply Chain   Operations deep dive" src="https://github.com/user-attachments/assets/9957012d-e5ee-4d7f-87b0-1bf066beb099" />


Page 3: Geographical & Market Insights<img width="1321" height="742" alt="Geographical   Market insights" src="https://github.com/user-attachments/assets/9964ba23-13bc-48ea-a5d8-f491dea17bdc" />

Focuses on global sales distribution and network-wide bottlenecks.

Global Sales Treemap: Hierarchical view of global market share (Europe leading with $11M, followed by LATAM with $10M).

Market Contribution to Late Deliveries: Donut chart showcasing the uniform distribution of delivery failures globally (~20% per market).


🔍 Key Business Findings & Actionable Recommendations
1. The Premium Shipping Paradox (SLA Misalignment)
Customers paying extra for premium shipping options (First Class and Second Class) are experiencing a high rate of delays.

First Class (scheduled for 1 day) always takes 2 days.

Second Class (scheduled for 2 days) always takes 4 days.

Standard Class (budget option) is 100% on target, delivering in exactly 4 days.

Recommendation: This is a system configuration and contractual issue rather than a carrier failure. DataCo must adjust its promised SLA days in the ERP system or renegotiate carrier contracts to align with actual fulfillment capabilities.

2. The 80/20 Rule of Late Delivery Risk
Out of 40+ product categories, 3 categories are responsible for the vast majority of the company's late delivery risk:

Women's Apparel (11.5K delayed shipments)

Water Sports (8.5K delayed shipments)

Shop By Sport (6.1K delayed shipments)

Recommendation: Prioritize warehouse picking operations, inventory allocation, and local hub fulfillment specifically for these three categories to resolve the company-wide delay crisis.

3. Systemic Network Failure
Late deliveries are distributed equally at ~20% across all global markets (Europe, LATAM, APAC, USCA, Africa).

Recommendation: Since the failure rate is uniform, this points to a systemic bottleneck in the central hub's global dispatching process rather than localized customs or regional port delays.

🛠️ Technical Implementation Details
Data Modeling & Power Query
Built a highly optimized Star Schema with a dedicated, custom-coded Calendar Table connected via a 1:Many relationship to support dynamic quarterly filters.

Constructed date hierarchies and grouped months into seasons using conditional logic in Power Query to capture seasonal operational trends.

Standardized column names and stripped redundant attributes (e.g., placeholder emails/passwords) to optimize file size and model refresh times.

Key DAX Measures
Late Delivery Rate (LDR):dax
LateDeliveryRate =
DIVIDE(
CALCULATE(COUNT(DataCo[Order Id]), DataCo = "Late delivery"),
COUNT(DataCo[Order Id]),
0
)

Average Shipping Days (Real):

Code snippet
AVG_Shipping_Days_Real = AVERAGE(DataCo)
🎨 UI/UX Best Practices Applied
Contrast Ratio: Complied with WCAG Contrast standards (

ContrastRatio≥4.5:1
for body text and labels, and

ContrastRatio≥3:1
 for visual boundaries/axes).  

Color Token System: Consistent color meanings used throughout (Blue for Sales/Volume, Orange/Red for Risk/Delays).  

Decluttering: Cleaned all visuals by removing redundant axes, using Top-N filters to eliminate scrollbars, and rounding large values to millions (M) and thousands (K) for executive readability.

👤 Author
Name: Mohamed Salah

Role: Senior Supply Chain Data Analyst

LinkedIn: https://www.linkedin.com/in/mohamed-salah-76b45a1b4
