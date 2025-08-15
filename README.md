# 🚀 Azure Project End-to-End Pipeline

This repository contains a complete data engineering pipeline using **Azure SQL Database**, **Apache Spark**, and **Azure Blob Storage** within a Databricks environment. The project demonstrates how to ingest, clean, transform, and store retail outlet data in a scalable and cloud-based architecture.

---

## 📦 Overview

The pipeline performs the following steps:

1. Connects to Azure SQL Database using JDBC.
2. Reads retail outlet data into a Spark DataFrame.
3. Cleans and transforms the data:
   - Fills missing values in `Outlet_Size` and `Outlet_Location_Type`.
   - Standardizes `Item_Fat_Content` values.
4. Mounts Azure Blob Storage to Databricks.
5. Writes the cleaned data to Azure Blob Storage in CSV format.

---

## 🧰 Technologies Used

- Azure SQL Database
- Apache Spark (PySpark)
- Azure Blob Storage
- Databricks
- Python

---

## 📊 Dataset Schema

The dataset includes the following columns:

- `Item_Identifier`
- `Item_Weight`
- `Item_Fat_Content`
- `Item_Visibility`
- `Item_Type`
- `Item_MRP`
- `Outlet_Identifier`
- `Outlet_Establishment_Year`
- `Outlet_Size`
- `Outlet_Location_Type`
- `Outlet_Type`
- `Item_Outlet_Sales`

---

## 🧼 Data Cleaning

- Replaced nulls in `Outlet_Size` with `"Small"`.
- Replaced nulls in `Outlet_Location_Type` with `"Tier 1"`.
- Standardized `Item_Fat_Content` by replacing `"LF"` with `"Low Fat"`.

---

## 🔐 Blob Storage Mount

The script mounts Azure Blob Storage using the following configuration:

```python
dbutils.fs.mount(
    source = "wasbs://<container>@<storageaccount>.blob.core.windows.net",
    mount_point = "/mnt/outlet1",
    extra_configs = {
        "fs.azure.account.key.<storageaccount>.blob.core.windows.net": "<your-access-key>"
    }
)

# Azure Data Pipeline Project

## 💾 Output
The cleaned data is saved to:

## ▶️ How to Run

1. Set up your Azure SQL and Blob Storage credentials.
2. Upload the script to Databricks.
3. Run each cell sequentially to execute the pipeline.

---

## 🧠 Author

**Abdur-Rasheed Adeoye**  
Commercial Analyst | Data Scientist | Bioinformatics Enthusiast

---

## 📬 Contact

For questions or collaborations, feel free to reach out via:
- [LinkedIn](https://www.linkedin.com/in/abdur-rasheed-adeoye/)
- [GitHub](https://github.com/Abdur-RasheedAde)
