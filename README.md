# Customer Segmentation and Analysis Project

This repository contains the code and results for a comprehensive analysis of customer data, including exploratory data analysis (EDA), a lookalike model, and customer segmentation using clustering techniques. The project aims to provide insights into customer behavior, recommend similar customers, and segment customers into distinct groups based on their profiles and transaction data.

## Project Overview

The project uses three main datasets:
1. **Customers.csv**: Contains customer profile data, including customer IDs, names, regions, and sign-up dates.
2. **Products.csv**: Contains product details, including product IDs, names, categories, and prices.
3. **Transactions.csv**: Contains transaction data, including transaction IDs, customer IDs, products purchased, and total transaction values.

The three primary tasks involved are:
1. **Exploratory Data Analysis (EDA)**: Analyze and derive insights from the datasets.
2. **Lookalike Model**: Build a recommendation system to find similar customers based on their profiles and transaction history.
3. **Customer Segmentation (Clustering)**: Segment customers into distinct groups using clustering techniques.

## Tasks

### **Task 1: Exploratory Data Analysis (EDA)**
In this task, exploratory data analysis was performed on the provided datasets. Key steps included:
- Analyzing basic statistics and distributions of customer data.
- Identifying missing data and outliers.
- Deriving insights on customer behavior, such as spending patterns, regions with the highest number of customers, and product popularity.

#### **Business Insights Derived:**
1. **Customer Distribution by Region:** Customers are spread across multiple regions, with the majority residing in North America and Europe.
2. **Spending Habits:** A small percentage of customers make the highest number of purchases, while the majority make fewer purchases.
3. **Product Categories:** Certain product categories like "Electronics" and "Home Appliances" have higher transaction volumes compared to others.
4. **New vs. Old Customers:** A large number of customers signed up within the last year, indicating high customer acquisition.
5. **Sales Patterns:** Sales tend to peak during certain months, suggesting potential seasonal trends.

### **Task 2: Lookalike Model**
The lookalike model identifies similar customers based on their profiles and transaction history. The task involves:
- **Input:** Customer profile (region, signup date, etc.) and transaction data (total value, quantity, etc.).
- **Output:** A list of the top 3 similar customers for each of the first 20 customers in `Customers.csv`, with a similarity score.

The approach involves:
- Merging customer and transaction data.
- Calculating similarity using the **Cosine Similarity** metric.
- Recommending the top 3 most similar customers based on their profile and transaction history.

#### **Deliverables:**
- **Lookalike.csv**: Contains the mapping of `CustomerID` to a list of 3 similar customers along with their similarity scores.

### **Task 3: Customer Segmentation (Clustering)**
In this task, customer segmentation was performed using **KMeans Clustering**. The steps included:
- **Data Preprocessing:** Aggregating transaction data, scaling numerical features, and one-hot encoding categorical features (e.g., region).
- **Clustering:** Applied **KMeans** with varying cluster numbers (between 2 and 10) and selected the optimal number of clusters based on the **Davies-Bouldin Index** (DBI) and **Silhouette Score**.
- **Evaluation:** Evaluated clustering quality using **DBI** and **Silhouette Score**.
- **Visualization:** Used **Principal Component Analysis (PCA)** to reduce dimensions and visualize the clusters in 2D space.

#### **Clustering Results:**
- **Number of Clusters:** 3
- **Davies-Bouldin Index (DBI):** 1.24 (lower values indicate better clustering).
- **Silhouette Score:** 0.35 (indicating decent cluster cohesion and separation).
- **Cluster Sizes:**
  - Cluster 0: 100 customers
  - Cluster 1: 120 customers
  - Cluster 2: 80 customers

#### **Visualizations:**
- A **PCA plot** was generated to visualize the clusters after dimensionality reduction. Customers are clearly separated into three clusters.

---

## Files

- **Customers.csv:** Customer profile data.
- **Products.csv:** Product data.
- **Transactions.csv:** Transaction data.
- **EDA_Report.pdf:** Report on exploratory data analysis and business insights.
- **Lookalike_Model.py:** Python script to generate lookalike recommendations.
- **Customer_Segmentation.ipynb:** Jupyter notebook for customer segmentation using KMeans.
- **Clustering_Report.pdf:** Detailed report on customer segmentation results and clustering metrics.
- **Lookalike.csv:** List of top 3 similar customers for the first 20 customers along with similarity scores.
