# 🛒 Retail Orders Analysis

This project focuses on analyzing a retail orders dataset using Python and SQL. The dataset was sourced from Kaggle, cleaned using Pandas, and then connected to SQL Server via SQLAlchemy for further analysis using MS SQL.

## 📌 Project Overview

- 📥 **Dataset**: Downloaded from Kaggle.
- 🧹 **Data Cleaning**: Performed using Pandas in Python.
- 🗄 **Database Connection**: Established using SQLAlchemy with SQL Server.
- 📊 **Analysis**: Conducted using Microsoft SQL Server.

## 🚀 Getting Started

### 🔹 Prerequisites

Before running this project, ensure you have:

- **Python 3.x** – [Download Python](https://www.python.org/)
- **Pandas & SQLAlchemy**:
  ```bash
  pip install pandas sqlalchemy pyodbc
  ```
- **MS SQL Server** – [Download SQL Server](https://www.microsoft.com/en-us/sql-server/)
- **Jupyter Notebook** (optional):
  ```bash
  pip install notebook
  ```

### 🔹 Setup Instructions

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/varunpravesh/Retail-Orders.git
   cd Retail-Orders
   ```

2. **Load the Dataset into Pandas**  
   Run `retail_orders.ipynb` or execute:
   ```python
   import pandas as pd
   df = pd.read_csv("data/orders.csv")
   print(df.head())
   ```

3. **Connect to SQL Server**  
   Ensure your database server is running, then configure your connection in `sql_connection.py`:
   ```python
   from sqlalchemy import create_engine

   conn_str = "mssql+pyodbc://username:password@server/database?driver=ODBC+Driver+17+for+SQL+Server"
   engine = create_engine(conn_str)
   connection = engine.connect()
   ```

4. **Run SQL Analysis**  
   Execute queries from `sql_analysis.sql` in Microsoft SQL Server.

## 📊 Analysis Performed

- **Order Trends**: Identifying peak sales periods.
- **Customer Behavior**: Analyzing purchasing patterns.
- **Revenue Insights**: Identifying top-selling products and categories.

## 📈 Sample Query (SQL Server)

```sql
SELECT ProductCategory, SUM(TotalAmount) AS Revenue
FROM Orders
GROUP BY ProductCategory
ORDER BY Revenue DESC;
