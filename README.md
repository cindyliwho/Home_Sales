# Home Sales Analysis with PySpark

## Overview
This project analyzes a home sales dataset using **PySpark and Spark SQL**, with a focus on **query performance optimization**. It demonstrates how different Spark techniques—SQL queries, caching, and Parquet partitioning—affect runtime and efficiency when working with large datasets.

The notebook performs exploratory SQL analysis on housing attributes and compares execution times across:
- Raw CSV data
- Cached DataFrames
- Partitioned Parquet files

---

## Dataset
The dataset is loaded from an AWS S3 source and contains home sales records with features such as:
- Sale date
- Number of bedrooms and bathrooms
- Number of floors
- Square footage
- Year built
- View rating
- Sale price

---

## Technologies Used
- **Python**
- **Apache Spark (PySpark)**
- **Spark SQL**
- **Parquet**
- **AWS S3**
- Libraries:
  - `pyspark`
  - `findspark`
  - `time`

---


## Key Tasks & Analysis

### 1. Data Loading
- Initializes a Spark session.
- Loads a CSV dataset from AWS S3 into a Spark DataFrame.
- Creates a temporary SQL view (`home_sales`) for Spark SQL queries.

### 2. SQL-Based Analysis
The notebook runs several aggregation queries, including:
- Average home price per year for 4-bedroom homes.
- Average price by year built for homes with:
  - 3 bedrooms and 3 bathrooms
  - 2 floors
  - ≥ 2000 square feet
- Average price per view rating for homes priced ≥ $350,000.

### 3. Performance Benchmarking
- Measures execution time for queries using:
  - Raw CSV data
  - Cached DataFrames
- Evaluates the impact of caching on repeated queries.

### 4. Parquet Optimization
- Writes the dataset to **Parquet format**, partitioned by `date_built`.
- Reloads the Parquet data and re-runs the same queries.
- Compares query performance between CSV and Parquet storage formats.

### 5. Cache Management
- Demonstrates caching and uncaching of Spark tables.
- Verifies cache status using Spark catalog utilities.

---

## Key Learnings
- Spark SQL enables efficient analytical queries on large datasets.
- Caching can significantly improve performance for repeated queries.
- Parquet files offer faster query execution and better storage efficiency than CSV.
- Partitioning data can further optimize query performance when filtering on partitioned columns.

---

## How to Run
1. Ensure Apache Spark and PySpark are installed.
2. Open the notebook:
   ```bash
   jupyter notebook Home_Sales.ipynb
