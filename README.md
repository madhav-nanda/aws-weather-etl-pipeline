# ☁️ AWS SQL ETL Pipeline | Automated Cloud Data Workflow

This project demonstrates a fully automated **ETL (Extract–Transform–Load)** pipeline built on **AWS**, integrating **Lambda, RDS (MySQL), Glue, and S3**.  
It extracts live **weather data** from the **OpenWeather API**, stores it in a **MySQL RDS database**, transforms it using **AWS Glue (SQL + PySpark)**, and loads the clean data into **Amazon S3** in **Parquet** format for analytics and visualization.

---

## 🚀 Project Architecture

![AWS Glue ETL Visual](architecture/aws_glue_etl_flow.png)

**Workflow Overview:**
1. **AWS Lambda** — Fetches real-time weather data from the OpenWeather API every hour using a **CloudWatch trigger**.  
2. **AWS RDS (MySQL)** — Stores raw weather data with city, temperature, humidity, wind speed, and timestamp.  
3. **AWS Glue ETL** — Cleans, filters, and transforms data using **SQL queries** and **PySpark scripts**.  
4. **Amazon S3** — Loads the transformed Parquet files for scalable data storage and future analytics.  
5. **Amazon EC2** — Provides an instance for testing, connection management, and monitoring.  

---

## 🧠 Key Concepts

- Serverless Data Ingestion with **AWS Lambda**
- **ETL orchestration** via **AWS Glue** (SQL + PySpark)
- Data warehousing using **RDS MySQL**
- Data Lake storage in **Amazon S3**
- **CloudWatch Logs** for monitoring job runs
- **IAM Roles & Policies** for secure resource access

---

## 🧩 Tech Stack

| Category | Tools & Services |
|-----------|----------------|
| **Languages** | Python, SQL |
| **AWS Services** | Lambda, RDS (MySQL), Glue, S3, EC2, CloudWatch |
| **Libraries** | `requests`, `pymysql`, `boto3` |
| **Data Format** | JSON → Parquet |
| **Transformations** | SQL + PySpark |
| **Visualization** | AWS Console & Workbench |
| **Version Control** | Git & GitHub |

---

## 📁 Repository Structure

aws-sql-etl-pipeline/
├── architecture/
│ └── aws_glue_etl_flow.png # Visual architecture
├── src/
│ ├── lambda_function.py # Data extraction & insertion into MySQL
│ └── glue_sql_transformations.sql # SQL transformation queries in Glue
├── outputs/
│ ├── mysql_sample_output.png # MySQL table result (raw data)
│ └── s3_transformed_output.png # Parquet output stored in S3
├── .gitignore
├── LICENSE
└── README.md


---

## 🧾 Sample Data Flow

**Extracted Data (MySQL – Raw):**
| City | Weather | Temp (°C) | Humidity | Wind Speed | Recorded At |
|------|----------|-----------|-----------|-------------|-------------|
| New York US | overcast clouds | 12.19 | 66 | 7.2 | 2025-10-29 16:46:10 |
| Los Angeles US | clear sky | 26.47 | 26 | 3.6 | 2025-10-29 16:46:10 |

**Transformed Data (S3 – Parquet):**
Stored in `s3://weather-etl-output/parquet/`  
Structured and compressed for query via **Athena**, **Redshift**, or **Power BI**.

---

## ⚙️ Automation & Scheduling

- Lambda trigger via **CloudWatch Event Rule** — every 1 hour.  
- Glue job executes ETL automatically once new records appear.  
- Logs streamed to **CloudWatch Logs** for transparency.  

---

## 🏆 Outcome

✔️ Complete AWS-based ETL workflow (serverless & scalable)  
✔️ Automated hourly data refresh from external API  
✔️ Cloud-native transformation + storage pipeline  
✔️ Industry-standard best practices for data engineering  

---

## 📎 GitHub Repository
🔗 [AWS SQL ETL Pipeline](https://github.com/madhav-nanda/aws-sql-etl-pipeline)

---

> 💡 *Built to demonstrate real-world data engineering on AWS — integrating API extraction, RDS storage, Glue transformation, and S3 data lake automation.*
