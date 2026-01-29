# 🚀 Cloud-Native ELT & Predictive Analytics Platform for News Intelligence

This project implements a fully automated, cloud-native analytics platform designed to ingest, transform, analyze, and predict publishing trends from The New York Times (NYT) dataset. Built on Google Cloud Platform (GCP), the solution combines ELT pipelines, a centralized data warehouse, business intelligence dashboards, and machine learning models to enable real-time and historical insights.

---

## 📌 Project Goals

The primary objective of this project is to design a scalable and secure analytics framework capable of supporting both descriptive and predictive decision-making.

Key goals include:

- Automating ingestion of historical and real-time NYT data  
- Building a centralized data warehouse for analytics  
- Enabling modular, version-controlled data transformations  
- Delivering interactive KPI dashboards for stakeholders  
- Forecasting article publishing trends using machine learning  

---

## 🧱 System Architecture Overview

NYT APIs
↓
Python Extractors
↓
Apache Airflow (GCP Composer)
↓
Google BigQuery (Raw & Transformed Layers)
↓
DBT (Star Schema Modeling)
↓
Power BI Dashboards
↓
ML Forecasting (Polynomial Regression)



---

## 🛠️ Tech Stack

### Data & Cloud
- **Data Source:** New York Times Archive API & Article Search API  
- **Cloud Platform:** Google Cloud Platform (GCP)  
- **Networking:** GCP Virtual Private Cloud (VPC)  

### Pipeline & Warehousing
- **Orchestration:** Apache Airflow (Google Composer)  
- **Data Warehouse:** Google BigQuery  
- **Transformations:** DBT (macros, star schema modeling)  

### Analytics & ML
- **Visualization:** Microsoft Power BI (BigQuery connector)  
- **Machine Learning:** Polynomial Regression (Python, Scikit-learn)  

---

## 🔄 Data Pipeline Workflow

### 1️⃣ Data Ingestion

- Historical articles retrieved via NYT Archive API  
- Real-time articles retrieved via NYT Article Search API  
- API rate limits handled using recursive extraction logic and timed delays  
- Pagination and daily API constraints managed programmatically  

---

### 2️⃣ Orchestration with Airflow

- Daily DAG scheduled at **5:00 PM PST**
- Extracts newly published articles and checks for updates  
- Logs record changes and ensures idempotent data loads  
- DAGs deployed and monitored using **Google Composer**

---

### 3️⃣ Data Loading into BigQuery

- Raw and processed datasets stored in separate layers  
- Schema-enforced JSON ingestion using Python loaders  
- Incremental updates applied to prevent duplication  
- Change tracking ensures data accuracy over time  

---

### 4️⃣ Data Transformation with DBT

- Implemented a **Star Schema** for analytical efficiency  
- Fact tables store article metrics  
- Dimension tables include authors, regions, dates, and keywords  
- DBT macros used for reusable transformations (e.g., UTC → PST conversion)  
- Git-based version control for transformation logic  

---

### 5️⃣ Business Intelligence & Dashboards

- Power BI connected directly to BigQuery  
- Built interactive dashboards featuring:
  - KPI cards (daily, monthly, cumulative articles)
  - Time-series trend analysis
  - Regional distribution visualizations
  - Word clouds for topic frequency
  - Author contribution metrics  

---

### 6️⃣ Machine Learning & Forecasting

- Polynomial Regression model used to predict article publishing volume  
- Degree-2 polynomial captures non-linear publishing trends  
- Forecasts support editorial planning and resource optimization  

---

## 📊 Key Insights

- Article publication volume shows periodic surges tied to major events  
- Political and business topics dominate keyword frequency  
- Europe and Africa regions produce the highest article volumes  
- Asia-Pacific shows comparatively lower publishing frequency  
- Predictive trends enable proactive content planning  

---

## 📈 Business Value & Recommendations

### Editorial Strategy
- Align publishing schedules with forecasted demand  
- Increase output during high-engagement periods  

### Resource Optimization
- Allocate editorial teams based on predicted article volume  
- Optimize infrastructure usage using historical trends  

### Audience Engagement
- Focus on high-frequency keywords and trending regions  
- Adapt content strategies dynamically using real-time analytics  

---

---

## 🧠 Conclusion

This project demonstrates how modern cloud analytics architectures can seamlessly integrate ELT pipelines, data warehousing, BI dashboards, and machine learning. By leveraging GCP, Airflow, DBT, BigQuery, Power BI, and Python-based ML models, the platform delivers scalable, automated, and predictive insights suitable for real-world enterprise analytics use cases.

---

## 👤 Author

**Gnana Prasuna Nimeesha Vakacharla**  
Data Science | Machine Learning | Cloud Analytics  

---

⭐ *If this project helped you or inspired ideas, feel free to star the repository!*


