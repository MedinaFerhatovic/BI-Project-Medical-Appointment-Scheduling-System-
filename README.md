# Medical Appointments Scheduling System

**BI Project**

## Project Summary

This project demonstrates a complete ETL pipeline and analytical data model built for processing and analyzing medical appointment data. The workflow covers raw data ingestion, data transformation, dimensional modeling, and data visualization.

The solution covers the full lifecycle: from raw CSV ingestion to a star-schema data warehouse and interactive Power BI dashboards.

---

## Architecture Overview

**Flow:**
CSV Files → n8n ETL → PostgreSQL → Dimensional Model → Power BI Dashboards

---

## ETL (n8n)

A total of **5 n8n workflows** were designed and implemented:

### Raw Layer – Data Ingestion (3 workflows)

Three workflows ingest raw CSV data into PostgreSQL without transformations:

* `appointments`
* `slots`
* `patients`

This layer preserves the original structure of the data.

---

### Staging Layer (1 workflow)

The staging workflow is responsible for:

* data cleansing and standardization
* joining raw tables
* creating a unified **master dataset**

This layer prepares data for analytical modeling.

---

### 🔹 Data Warehouse Layer (1 workflow)

The final workflow builds a **dimensional (star schema) model** optimized for analytics.

#### Fact Table

* `fact_appointments`

#### Dimension Tables

* `dim_patient`
* `dim_insurance`
* `dim_status`
* `dim_date`
* `dim_time`

---

## 🗄️ Database

* **PostgreSQL** was used as the primary database for raw, staging, and warehouse layers.

---

## 📊 Data Visualization

* **Power BI** was used to create interactive dashboards.
* Visualizations focus on appointment trends, status and time-based analysis.

<img width="447" height="358" alt="image" src="https://github.com/user-attachments/assets/c4ea7f8e-5299-43be-a33b-b61203a032ed" />
<img width="413" height="350" alt="image" src="https://github.com/user-attachments/assets/29bdc0b0-78f6-4da7-8005-6144740b7bc5" />
<img width="688" height="337" alt="image" src="https://github.com/user-attachments/assets/962895e2-0efa-4c44-afca-29627a1d388e" />

---

## 📂 Data Source

* Dataset sourced from **Kaggle**
  https://www.kaggle.com/datasets/carogonzalezgaltier/medical-appointment-scheduling-system

---

## 🧰 Tech Stack

* **n8n** – ETL workflow 
* **PostgreSQL** – relational database & transformations
* **Power BI** – reporting and analytics
* **CSV / Kaggle dataset** – data source
