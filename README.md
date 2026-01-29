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

<img width="1041" height="357" alt="Screenshot 2026-01-29 215454" src="https://github.com/user-attachments/assets/b3119c98-0c9b-4b09-9717-b733dc543436" />
<img width="1183" height="344" alt="Screenshot 2026-01-29 215521" src="https://github.com/user-attachments/assets/1e51d681-d7e8-449a-ba36-d2eb9eb8c357" />
<img width="1137" height="334" alt="Screenshot 2026-01-29 220225" src="https://github.com/user-attachments/assets/ebe15d63-1519-4e8e-a41c-097af842201d" />

---

### Staging Layer (1 workflow)

The staging workflow is responsible for:

* data cleansing and standardization
* joining raw tables
* creating a unified **master dataset**

This layer prepares data for analytical modeling.

<img width="1293" height="188" alt="Screenshot 2026-01-29 220239" src="https://github.com/user-attachments/assets/b970ec20-95e5-4ae6-b63a-76159259575c" />

---

### Data Warehouse Layer (1 workflow)

The final workflow builds a **dimensional (star schema) model** optimized for analytics.

<img width="1266" height="152" alt="Screenshot 2026-01-29 220255" src="https://github.com/user-attachments/assets/3f63289c-3001-4bb5-8513-aeddb09164b0" />


#### Fact Table

* `fact_appointments`

#### Dimension Tables

* `dim_patient`
* `dim_insurance`
* `dim_status`
* `dim_date`
* `dim_time`

<img width="968" height="646" alt="Screenshot 2026-01-28 204128" src="https://github.com/user-attachments/assets/b8e67ee9-5641-431c-b8dc-2110693ddf46" />

---

## Database

* **PostgreSQL** was used as the primary database for raw, staging, and warehouse layers.

---

## Data Visualization

* **Power BI** was used to create interactive dashboards.
* Visualizations focus on appointment trends, status and time-based analysis.

<img width="447" height="358" alt="image" src="https://github.com/user-attachments/assets/c4ea7f8e-5299-43be-a33b-b61203a032ed" />
<img width="413" height="350" alt="image" src="https://github.com/user-attachments/assets/29bdc0b0-78f6-4da7-8005-6144740b7bc5" />
<img width="688" height="337" alt="image" src="https://github.com/user-attachments/assets/962895e2-0efa-4c44-afca-29627a1d388e" />

---

## Data Source

* Dataset sourced from **Kaggle**
  https://www.kaggle.com/datasets/carogonzalezgaltier/medical-appointment-scheduling-system

---

## Tech Stack

* **n8n** – ETL workflow 
* **PostgreSQL** – relational database & transformations
* **Power BI** – reporting and analytics
* **CSV / Kaggle dataset** – data source
