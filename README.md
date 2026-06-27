# Global-Boomerang-Sales

Design and Implementation of a Scalable Big Data Ecosystem for Advanced Analytics

Project Overview
This project focuses on building a scalable Big Data ecosystem for E-commerce Sales and Customer Analytics.

The goal is to transform large-scale raw retail transaction data into structured, clean, and useful insights that support business decision-making through cloud-based processing and interactive dashboards.

The system analyzes sales transactions across different product categories, countries, and sales channels to understand revenue performance, profitability, customer behavior, and market trends.

---

## Problem Statement
Modern retail companies generate large amounts of data from different sources and sales channels. Traditional tools such as Excel are not efficient for handling millions of records, complex joins, and large-scale analytics.

This project solves that problem by designing and implementing a Big Data pipeline that supports:

- Large-scale data ingestion
- Distributed cloud storage
- Scalable data processing
- Data warehousing
- Business intelligence dashboards

---

## Objectives
The main objectives of this project are:

1. Design and implement a multi-stage Big Data pipeline.
2. Integrate data ingestion, distributed storage, processing, warehousing, and visualization.
3. Clean, transform, and aggregate large transactional datasets using distributed technologies.
4. Store processed data in a cloud data warehouse for fast analytical queries.
5. Build an interactive Power BI dashboard to support data-driven decisions.

---

## Dataset
The project uses a private high-volume operational and financial dataset representing global sales transactions for a company specializing in sports and recreational boomerangs.

The dataset contains approximately 7 million transaction records before cleaning, and around 6 million records after removing duplicates.

The data includes:

- Transactions
- Products
- Countries
- Sales channels
- Cost
- Discounts
- Quantity sold
- Dates

---

## Big Data Architecture

The project follows a multi-layer Big Data ecosystem:

```text
SQL Server Database
        ↓
AWS Glue / Apache Spark
        ↓
Amazon S3 Landing Zone
        ↓
AWS Glue Processing Layer
        ↓
Snowflake Data Warehouse
        ↓
Power BI Dashboard
````

---

## Tools and Technologies

| Layer               | Tool Used              | Purpose                                            |
| ------------------- | ---------------------- | -------------------------------------------------- |
| Data Source         | Microsoft SQL Server   | Stores the original transactional data             |
| Data Ingestion      | AWS Glue               | Extracts data from SQL Server using JDBC           |
| Processing          | Apache Spark / PySpark | Cleans, transforms, and processes large-scale data |
| Distributed Storage | Amazon S3              | Stores raw and processed data in Parquet format    |
| Data Warehouse      | Snowflake              | Stores structured analytical data                  |
| Visualization       | Power BI               | Builds interactive dashboards and reports          |
| Query Language      | SQL                    | Used for data loading, mapping, and analytics      |
| Analytics Logic     | DAX                    | Used to create business measures in Power BI       |

---

## Implementation Stages

### 1. Data Source

The original data was stored in Microsoft SQL Server as relational tables, including fact and dimension tables.

### 2. Data Ingestion

AWS Glue was used to connect to SQL Server through JDBC. The data was extracted into Spark DataFrames and stored in Amazon S3 using Parquet format.

### 3. Distributed Storage

Amazon S3 was used as the landing zone for raw and intermediate data. Parquet was selected because it is efficient for large-scale analytical workloads.

### 4. Data Processing

AWS Glue with Apache Spark was used to process the data. The main processing steps included:

* Loading data from S3
* Previewing schemas
* Checking row counts
* Removing duplicate records
* Extracting Year and Month from the Date column
* Standardizing website/channel names
* Joining transaction data with product and country dimensions
* Saving the final processed dataset back to S3

### 5. Data Warehouse

Snowflake was used to store the processed dataset. The integration between S3 and Snowflake was configured using:

* IAM policies
* IAM roles
* Storage integration
* External stage
* Parquet file format
* COPY INTO command

### 6. Analysis and Visualization

Power BI was connected to Snowflake to create interactive dashboards. The dashboards provide insights into:

* Total sales
* Total profit
* Net sales
* Revenue trends
* Product performance
* Country-based sales
* Sales channels
* Discount impact
* Profit margin

---

## Key Results and Insights

The analysis showed that:

* The company processed around 6 million transactions.
* Sales reached 124 countries.
* Around 173 million units were sold.
* The Beginner category was the strongest performing category.
* Amazon was the dominant sales channel.
* Discounts had a major impact on potential revenue.
* The company achieved around $1 billion in total profit.
* Medium discounts performed better than high and low discount strategies.
* The Quad product was one of the strongest profit-generating products.

---

## Why This Is a Big Data Project

This project is considered a Big Data solution because it addresses the main Big Data characteristics:

### Volume

The dataset contains millions of records, which makes traditional analysis tools inefficient.

### Variety

The system integrates multiple tables and dimensions, including transactions, products, countries, dates, and sales channels.

### Velocity

The pipeline supports fast movement of data from ingestion to processing and visualization.

### Scalability

The architecture can scale by using cloud services such as AWS Glue, Amazon S3, and Snowflake.

### Distributed Processing

Apache Spark allows the data to be processed across multiple nodes instead of relying on a single machine.

---

## Challenges

Some challenges faced during the project included:

* Learning and integrating AWS Glue, Spark, Snowflake, and Power BI.
* Configuring IAM roles and trust relationships securely.
* Handling millions of records efficiently.
* Debugging errors in a large-scale dataset.
* Understanding financial and business metrics without a domain expert.

---

## Future Improvements

Possible future improvements include:

* Building a real-time streaming pipeline.
* Adding automated data quality checks.
* Improving dashboard interactivity.
* Adding predictive analytics or machine learning models.
* Creating alerts for unusual sales or profit changes.
* Expanding the system to support more data sources.

---

## Ethics and Privacy

The project uses a private operational dataset. Security and privacy were considered by applying the Principle of Least Privilege, where Snowflake was given read-only access to the required S3 folders.

The integration between AWS and Snowflake was secured using IAM roles, trust relationships, and storage integration objects.

AI tools such as ChatGPT and Gemini were used only for research, debugging support, and documentation assistance, while the final implementation and validation were completed by the project team.

---

## Team Members
* Nehal Alzahrani
* Joud Alhuthali
* Hanin Almalki
* Mrooj Munshi

---

## Course

Big Data Mining - DS5411

## Instructor

A/Prof. Olfat Mirza

---

## Repository Structure

```text
.
├── README.md
├── notebooks/
│   ├── data_ingestion.ipynb
│   └── data_processing.ipynb
├── dashboard/
│   └── powerbi_dashboard.pbix
└── report/
    └── FinalBigDataProject.pdf
```

```
```
