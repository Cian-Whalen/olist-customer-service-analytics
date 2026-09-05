Olist E-Commerce Delivery & Customer Satisfaction Analytics

Project Overview

This project analyzes the Olist Brazilian E-Commerce Dataset to evaluate delivery performance, fulfillment efficiency, seller and geographic risk, and the relationship between delivery delays and customer satisfaction.
The analysis combines multiple transactional and customer-feedback datasets using Python, SQL, and Google Looker Studio to identify where delivery issues occur, how severe those delays are, and how delivery performance is associated with customer review outcomes.
The final deliverable is an interactive three-page dashboard designed to help identify operational delivery risks and their impact on the customer experience.
________________________________________
Business Problem

Reliable delivery is an important component of the e-commerce customer experience. Understanding where and how delivery delays occur can help businesses identify operational problem areas and prioritize improvement opportunities.

This project addresses questions including:
•	How frequently are orders delivered late?
•	Is delivery performance improving or worsening over time?
•	How does delivery performance relate to customer satisfaction?
•	How severe are delivery delays when they occur?
•	Where in the fulfillment process do delays occur?
•	Which seller states and sellers have the highest late delivery rates?
•	Which seller-to-customer routes present the greatest delivery risk?
•	How does carrier transit time differ between on-time and late orders?
•	How does customer satisfaction vary across different levels of delivery delay?
________________________________________
Dataset

The project uses the publicly available Olist Brazilian E-Commerce Dataset, which contains information about approximately 100,000 orders across multiple interconnected tables.

Key Tables
Dataset	Description
olist_orders_dataset	Order status, purchase dates, delivery dates, and estimated delivery dates
olist_order_items_dataset	Products and sellers associated with each order
olist_order_reviews_dataset	Customer review scores
olist_customers_dataset	Customer identifiers and geographic information
olist_sellers_dataset	Seller identifiers and geographic information
olist_products_dataset	Product and category information
olist_order_payments_dataset	Payment information
olist_geolocation_dataset	Geographic information associated with Brazilian ZIP codes
The analysis accounts for the difference between order-level and item-level data, since individual orders can contain multiple products and order items.
________________________________________
Tools & Technologies
•	Python
o	Pandas
o	Data cleaning and transformation
o	Exploratory data analysis
o	Data validation
•	SQL / SQLite
o	Multi-table joins
o	Aggregations
o	Business metric calculations
o	Date-based analysis
•	Google Colab
o	Analysis and data preparation environment
•	Google Looker Studio
o	Interactive dashboard development
o	KPI visualization
o	Geographic analysis
o	Operational performance analysis
________________________________________
Data Preparation & Validation
Before conducting the analysis, the datasets were examined for structure, completeness, and relationship integrity.
Key validation steps included:
•	Reviewing table schemas and row counts
•	Checking relationships between orders, customers, products, sellers, payments, and reviews
•	Identifying unmatched records
•	Accounting for differences in table granularity
•	Creating delivery-performance classifications
•	Calculating fulfillment and transit-time metrics
•	Validating analytical results before incorporating them into the dashboard
The analysis focused primarily on delivered orders when evaluating delivery performance.
________________________________________
Key Performance Metrics
The analysis identified the following overall delivery-performance baseline:
Metric	Result
Delivered Orders	96,470
Late Orders	7,826
Late Delivery Rate	8.11%
This means approximately 8% of delivered orders were delivered after the expected delivery date.
________________________________________
Key Findings

1. Late delivery is strongly associated with lower customer satisfaction

Customer review scores differed substantially based on delivery performance.
Delivery Performance	Average Review Score
On Time	4.29 / 5
Late	2.57 / 5
Late orders also had a substantially higher one-star review rate:
Delivery Performance	1-Star Review Rate
On Time	6.60%
Late	46.16%
The analysis therefore identifies a strong relationship between delivery performance and customer satisfaction.
Business Implication
Delivery reliability represents an important customer-experience metric. Monitoring late delivery alongside review performance can help organizations understand the customer impact of operational delivery issues.
________________________________________
2. Delivery performance generally improved over time

The Average Days Late by Month visualization shows a generally downward trend from 2016 through 2018.
Although individual months fluctuate, the overall direction indicates that average delivery lateness decreased over the period analyzed.
Business Implication
The long-term improvement suggests that delivery performance was generally becoming more efficient over the period, while monthly variation indicates that operational performance was not completely consistent.
________________________________________
3. Late deliveries can vary considerably in severity

The dashboard categorizes late orders into four delay-severity groups:
•	1–3 days late
•	4–7 days late
•	8–14 days late
•	15+ days late
This provides a more detailed view than simply classifying orders as late or on time.
Business Implication
A binary late/on-time metric can hide the magnitude of a delivery problem. Separating delays by severity allows businesses to distinguish relatively minor delays from significantly overdue orders.
________________________________________
4. Carrier transit time is substantially longer for late orders

The analysis found a large difference in carrier transit time between late and on-time orders.
Late Orders
•	Approval → Carrier: 5.3 days
•	Carrier → Customer: 25.7 days
•	Total fulfillment: 31.0 days
On-Time Orders
•	Approval → Carrier: 2.6 days
•	Carrier → Customer: 7.9 days
•	Total fulfillment: 10.5 days
The largest observed fulfillment-time difference occurs during the carrier-to-customer stage.
Business Implication
The carrier transit stage represents a key area for operational investigation because the difference between late and on-time orders is substantially larger during this portion of fulfillment than during approval-to-carrier processing.
________________________________________
5. Carrier transit times are widely distributed

The carrier transit-time distribution shows that delivery times are spread across several ranges:
Carrier Transit Time	Records
<5 days	29,470
5–9 days	35,460
10–14 days	16,488
15–19 days	6,665
20+ days	11,368
The largest group falls within the 5–9 day range, followed by orders taking less than five days.
However, more than 18,000 records fall into the 15+ day ranges, demonstrating that a meaningful portion of orders experienced substantially longer carrier transit times.
Business Implication
The distribution highlights the importance of monitoring unusually long transit times rather than relying solely on average transit time.
________________________________________
6. Seller and geographic performance varies considerably

The dashboard evaluates late delivery rates across seller states and individual sellers to identify areas with elevated delivery risk.
Rather than focusing solely on overall delivery performance, this analysis allows potential problem areas to be isolated at both the seller and geographic level.
One particularly high-risk seller-to-customer route was:
São Paulo (SP) → Alagoas (AL): 26.17% late delivery rate
Business Implication
Route-level analysis can reveal delivery risks that may be hidden when performance is aggregated at the national or state level. High-risk routes can therefore be investigated for potential transportation, geographic, or fulfillment challenges.
________________________________________
7. Review scores remain relatively strong across most states

The geographic review-score analysis shows that the majority of states have average review scores in the 4.XX range.
This suggests that customer satisfaction is generally strong across geographic markets, despite differences in delivery performance.
Business Implication
State-level review analysis provides additional context when evaluating delivery performance. A state with a higher or lower delivery-risk profile does not necessarily have an equally extreme customer-satisfaction outcome, making geographic analysis useful for identifying where operational and customer-experience metrics diverge.
________________________________________
Dashboard

The final dashboard consists of three pages, moving from overall performance to operational root causes and then customer satisfaction.
________________________________________
Page 1 — Executive Overview

The first page provides a high-level view of overall delivery and customer-experience performance.

KPI Cards
•	Total Orders
•	Late Delivery Rate
•	Average Fulfillment Time
•	Average Review Score
•	1-Star Review Rate

Visualizations
Average Days Late by Month — Line chart

Shows how average delivery lateness changes over time, with the overall trend generally declining from 2016 through 2018.

Late Delivery Rate by Customer State — Horizontal bar chart

Compares late delivery rates across customer states.

Delivery Performance vs. Customer Satisfaction — Vertical bar chart

Compares customer review performance based on whether an order was delivered on time or late.

Delivery Delay Severity — Vertical bar chart

Breaks late deliveries into 1–3, 4–7, 8–14, and 15+ day delay categories.

Carrier Transit Time vs. Delivery Performance — Vertical bar chart

Compares carrier transit time based on delivery performance.

Top Sellers by Late Delivery Rate — Horizontal bar chart

Highlights sellers with elevated late delivery rates without relying on seller names in the written analysis.
________________________________________
Page 2 — Root Cause & Operational Analysis

The second page moves deeper into the operational factors associated with delivery performance.

Visualizations

Approval to Carrier Time by Delivery Performance — Vertical bar chart

Compares the time required to move an order from approval to carrier handoff for on-time versus late deliveries.

Top Seller States by Late Delivery Rate — Horizontal bar chart

Identifies seller states with higher late delivery rates.

Highest Risk Sellers by Late Delivery Rate — Horizontal bar chart

Identifies individual sellers with the highest observed late delivery rates.

Highest Risk Seller by Customer Routes — Table

Examines seller-to-customer state routes to identify combinations with elevated delivery risk.

Carrier Transit Time by Delivery Performance — Vertical bar chart

Further compares transit duration between on-time and late orders.

Carrier Transit Time Distribution — Vertical bar chart

Shows the distribution of orders across carrier transit-time ranges.
________________________________________
Page 3 — Customer Satisfaction

The third page focuses specifically on the relationship between delivery performance and customer feedback.

Visualizations

1-Star Rate by Delivery Performance — Vertical bar chart

Compares the percentage of one-star reviews for on-time and late orders.

Review Score by Delay Severity — Vertical bar chart

Shows how customer review scores vary as delivery delays become more severe.

Review Score by State — Filled map

Provides a geographic view of average customer review scores across Brazilian states.
________________________________________
Analytical Approach

The project followed a structured analytics workflow.
1. Data Exploration & Validation
Examined the available Olist tables, their schemas, row counts, relationships, and potential unmatched records.
2. Data Preparation
Combined relevant order, seller, customer, and review information while accounting for differences in data granularity.
3. Metric Development
Created analytical measures for:
•	Delivery performance
•	Late delivery rate
•	Fulfillment time
•	Approval-to-carrier time
•	Carrier transit time
•	Delivery delay severity
•	Average review score
•	One-star review rate
4. Exploratory Analysis
Analyzed relationships between:
•	Delivery timing
•	Delivery performance
•	Seller performance
•	Geographic performance
•	Customer review scores
5. Dashboard Development
Built an interactive three-page Looker Studio dashboard that progresses from:
Executive Performance → Operational Root Causes → Customer Satisfaction
This structure allows users to first identify the overall delivery problem, then investigate where operational risk is concentrated, and finally examine the associated customer-experience outcomes.
________________________________________
Business Recommendations
Based on the analysis, several areas warrant further operational investigation:
1. Investigate extended carrier transit times
The substantial difference in carrier-to-customer time between late and on-time orders makes extended transit time an important area for investigation.
2. Monitor high-risk sellers
Sellers with unusually high late delivery rates can be monitored separately from overall marketplace performance to identify potential fulfillment issues.
3. Monitor high-risk geographic routes
Routes such as SP → AL, which showed a 26.17% late delivery rate, can be investigated for recurring transportation or geographic challenges.
4. Track delay severity alongside late delivery rate
Monitoring only whether an order was late does not capture how late it was. Severity buckets provide additional context for prioritizing the most significant delivery issues.
5. Connect operational performance to customer satisfaction
Because late orders have substantially lower average review scores and much higher one-star review rates, delivery KPIs should be evaluated alongside customer-experience metrics.
________________________________________
Project Outcome
This project demonstrates how multi-table e-commerce data can be transformed into actionable operational and customer-experience insights.
The analysis identified an 8.11% late delivery rate among delivered orders and found a substantial relationship between delivery performance and customer satisfaction. Late orders averaged 2.57/5 compared with 4.29/5 for on-time orders, while their one-star review rate was 46.16% compared with 6.60% for on-time orders.
Operationally, the largest observed fulfillment-time difference occurs during the carrier-to-customer stage, while seller and route-level analysis reveals areas with elevated delivery risk.
The resulting dashboard provides a structured way to move from overall delivery performance to operational risk and customer satisfaction, demonstrating the use of data analytics to investigate business performance and identify opportunities for improvement.
________________________________________
Skills Demonstrated
Data Analysis
•	Exploratory data analysis
•	KPI development
•	Operational performance analysis
•	Customer satisfaction analysis
•	Root-cause analysis
•	Geographic analysis
SQL
•	Multi-table joins
•	Aggregations
•	Conditional logic
•	Date calculations
•	Business metric development
Python
•	Pandas
•	Data cleaning
•	Data validation
•	Data transformation
•	Exploratory analysis
Data Visualization
•	Google Looker Studio
•	KPI dashboards
•	Horizontal and vertical bar charts
•	Line charts
•	Filled maps
•	Operational tables
•	Interactive dashboard design
Business Analytics
•	Delivery performance analysis
•	Fulfillment analysis
•	Seller risk identification
•	Geographic risk analysis
•	Customer experience analysis
•	Data-driven recommendations

Dashboard Linked Here: https://github.com/Cian-Whalen/olist-customer-service-analytics/blob/main/Olist%20E-Commerce%20Delivery%20%26%20Customer%20Satisfaction%20Analytics%20Dashboard.pdf
