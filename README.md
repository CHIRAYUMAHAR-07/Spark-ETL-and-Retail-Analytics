# Spark-ETL-and-Retail-Analytics

# UData Lakehouse Project
Built with: Databricks · Delta Lake · Apache Spark · PySpark · MLflow · Power BI Focus: End-to-End ETL Pipeline · Scalable Data Lakehouse Architecture · Retail Analytics · Dashboarding · Observability

# Project Purpose
This project demonstrates how to build a modern, scalable data platform using the Lakehouse paradigm. It’s designed to handle raw retail data, transform it into clean, queryable formats, and deliver business insights through interactive dashboards. The architecture combines the reliability of data warehouses with the flexibility of data lakes, using Delta Lake and Apache Spark as the backbone.

The goal is to showcase how raw, messy data can be turned into structured, insightful analytics — all within a reproducible, production-grade pipeline.


# Dataset Description
The dataset used is the Online Retail dataset, which contains transactional records from a global e-commerce business. It includes fields such as invoice numbers, product codes, descriptions, quantities, unit prices, customer IDs, and countries. With over 500,000 rows, it provides a rich foundation for building scalable ETL pipelines and extracting insights across time, geography, and product categories.

# ETL Pipeline Architecture
The pipeline begins with raw data ingestion using PySpark. Excel and CSV files are read into Spark DataFrames, with schema inference and null handling applied. Initial cleaning steps include removing duplicates, filtering out invalid entries such as negative quantities or prices, and standardizing column formats for consistency.
Once cleaned, the data is written into Delta Lake tables. These tables support ACID transactions, schema evolution, and time travel, making them ideal for reliable storage and iterative development. Partitioning is applied based on country and invoice date to optimize query performance and reduce latency.
Feature engineering steps include deriving new columns such as total amount (calculated by multiplying quantity and unit price), extracting year and month from invoice dates, and generating synthetic data to simulate larger workloads. Aggregations are performed to calculate total sales, invoice counts, and product-level metrics across different countries.
The pipeline is monitored using MLflow, which tracks metrics such as row counts, processing time, and error rates. This adds observability and reproducibility to the workflow, ensuring that each run is logged and traceable.

# <img width="2700" height="1224" alt="Country - visual selection" src="https://github.com/user-attachments/assets/a16b2aaa-558f-44c4-b4d3-8b88e13efff6" />
<img width="3240" height="1764" alt="Country - visual selection (5)" src="https://github.com/user-attachments/assets/79ff45ef-2dd1-4e87-9c90-82663e2c3305" />
<img width="2952" height="1656" alt="Country - visual selection (4)" src="https://github.com/user-attachments/assets/aac6d464-c0e3-4d8a-810c-ed5158517780" />
<img width="1944" height="1692" alt="Country - visual selection (3)" src="https://github.com/user-attachments/assets/facff42c-e25e-4014-8a13-8ba5fd1c5c81" />
<img width="2700" height="1224" alt="Country - visual selection (2)" src="https://github.com/user-attachments/assets/70b17f62-432e-4454-8481-6c4ca5d61dc3" />
<img width="1815" height="1179" alt="Country - visual selection (1)" src="https://github.com/user-attachments/assets/f28d458d-7443-48b4-b49d-4506148a615b" />

# Data Modeling and Delta Lake Optimization
Delta Lake is used to store the transformed data in a versioned, ACID-compliant format. Tables are partitioned by country and invoice date to improve query performance. Z-Ordering is applied to optimize file layout and reduce scan time for frequently queried columns.

Schema evolution is enabled to allow for flexible updates to the data model. Time travel features are used to compare historical versions of the data, enabling rollback and audit capabilities.

Synthetic data generation is included to test pipeline scalability and performance under load. This ensures that the architecture can handle real-world data volumes and complexity.

# Dashboarding and Business Intelligence
Power BI is used to build interactive dashboards that visualize key metrics and trends. These dashboards include:
A breakdown of top invoices by country, showing which regions contribute the most to revenue.
A Sankey diagram that visualizes the flow of purchases from countries to invoices and product categories.
A line chart that tracks historical distribution of product quantities from 2009 to 2011.
A bar chart that shows stock code distribution across regions and time.
A product category breakdown that highlights seasonal demand for items like vintage home decor and magnets.
A global market reach chart that shows invoice distribution and country coverage over time.

# Business Insights Extracted
The analytics reveal that Australia is the top-performing country in terms of purchase volume, contributing over 40,000 units and more than 7 percent of total revenue. Cyprus, while smaller in volume, shows an upward trend, indicating potential for market expansion.
Product categories such as vintage home decor and magnets exhibit seasonal demand spikes, which can inform inventory planning and marketing strategies. The increase in market reach from 1.3K in 2010 to 1.5K in 2011 suggests successful penetration into new regions.
These insights are not just descriptive — they’re prescriptive. They help guide decisions around product stocking, regional targeting, and promotional timing.

# Technical Highlights
This project leverages Delta Lake’s capabilities for versioned, ACID-compliant storage, enabling reliable data management. Apache Spark provides distributed processing power, allowing the pipeline to scale with data volume. MLflow adds transparency and monitoring, while Power BI delivers intuitive, stakeholder-friendly dashboards.
The modular notebook design ensures reproducibility and ease of maintenance. Synthetic data generation allows for stress testing and performance benchmarking. Partitioning and Z-Ordering are used to optimize query speed and reduce latency.
Each notebook is designed to be standalone yet interconnected, allowing for flexible development and testing. The code is written with production readiness in mind, including error handling, logging, and environment-agnostic configurations.

# Observability and Monitoring
MLflow is integrated to track pipeline runs, log metrics, and store artifacts. This adds a layer of observability that’s crucial for debugging, auditing, and performance tuning. Each stage of the pipeline is monitored for row counts, processing time, and error rates.

Optional integration with Airflow is planned to orchestrate pipeline runs and manage dependencies. This will allow for scheduled execution, retry logic, and DAG-based workflow management.

# Future Enhancements
Planned improvements include:
Integrating Airflow for orchestration and scheduling.
Adding Great Expectations for data quality validation.
Deploying dashboards to cloud services like Power BI Service or Tableau Server.
Implementing CI/CD pipelines for notebook versioning and deployment.
Extending the architecture to support real-time streaming using Kafka and Spark Structured Streaming.

# What This Project Demonstrates
This project is a flagship example of how to architect a modern data platform that combines technical rigor with business relevance. It shows your ability to build scalable ETL pipelines, optimize data storage, generate actionable insights, and communicate results through compelling dashboards.

![ETL Monitoring Power BI Dashboard_page-0001](https://github.com/user-attachments/assets/e8993a2c-aeea-41a9-a7d3-9cb9d1a93974)


