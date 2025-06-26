# Café Rewards - Data Engineering pipeline

This project demonstrates a complete data processing pipeline for the Café Rewards Offer dataset, using PySpark on Databricks. It covers data ingestion, cleaning, transformation and analytical insights from marketing campaigns.



## Architecture overview

architecture.png



## Environment

This project was built using:
- **Databricks Community Edition**
- **Apache Spark (PySpark)**
- **Python 3.x**
- **GitHub**



## Project structure


cafe-rewards-pipeline/
├── 01_bronze_ingestion.py
├── 02_trusted_processing.py
├── 03_refined_analytics.py
├── diagram/
│   └── architecture.png
└── README.md




## How to Run

1. Upload the following files to your Databricks workspace:
   - events.csv
   - offers.csv
   - customers.csv

2. Run notebooks in order:
   - 01_bronze_ingestion.py   → saves data in Bronze layer (`/FileStore/bronze/`)
   - 02_trusted_processing.py → cleans and joins data into Trusted layer
   - 03_refined_analytics.py  → executes KPIs and answers the business questions


## Analytical Questions & Answers

### 1.Which marketing channel is the most effective in terms of offer completion rate?

> Based on the data, the most effective channels (e.g., `email` or `mobile`) had the highest completion rates.  
> Calculated by comparing number of completed offers to number of received offers per channel.



### 2.How is the age distribution of customers who completed offers vs. those who did not?

> Customers who completed offers tend to be younger on average.  
> Histogram and count comparisons were plotted using PySpark groupBy on 'age' and 'status'.



### 3.What is the average time taken by customers to complete an offer after receiving it?

> On average, customers take approximately 'XYZ' hours to complete an offer.  
> This was calculated by subtracting 'received time' from 'completed time' for each customer-offer pair.



## Design Choices

- Layered architecture(Bronze → Trusted → Refined) for data traceability and modularity
- JSON parsingof the value field in the events table using `from_json()
- Exploding channels to assess effectiveness per channel
- Refined metricsto answer actual business questions



##  Dataset

> Dataset Source: [Café Rewards Offer Dataset on Kaggle](https://www.kaggle.com/datasets/something)


## Author

Developed by Hilosi Jose Nunes Miamoto, Senior Data Engineer Candidate  
[GitHub](https://github.com/yourprofile)
