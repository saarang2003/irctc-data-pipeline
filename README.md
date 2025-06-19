# 🚄 IRCTC Real-Time Data Pipeline using Google Cloud (GCP)

## 📢 Overview
The **IRCTC Real-Time Data Pipeline** is a cloud-native, real-time streaming architecture designed to simulate and process live passenger data from IRCTC (Indian Railway Catering and Tourism Corporation). It leverages key **Google Cloud Platform (GCP)** services like **Pub/Sub**, **Dataflow (Apache Beam)**, **BigQuery**, and **Cloud Storage** to ingest, process, transform, and store high-velocity data for advanced analytics.

---

## 📁 Architecture Overview

### 🔹 Data Flow Pipeline

1. **Data Ingestion**: Simulated IRCTC mock data is published to **Google Pub/Sub** topics.
2. **Data Processing**: A streaming pipeline built with **Apache Beam (Python SDK)** and deployed via **Dataflow** reads and transforms data using Python UDFs.
3. **Data Storage**: Transformed records are persisted into **Google BigQuery** for analytics and reporting.
4. **UDF Registration**: Custom UDFs stored in **Google Cloud Storage** are registered and used within BigQuery SQL queries.

---

## ⚙️ Tech Stack

| Technology             | Purpose                                 |
|------------------------|------------------------------------------|
| Google Cloud Pub/Sub   | Real-time message ingestion              |
| Google Dataflow        | Serverless data processing with Apache Beam |
| Google BigQuery        | Cloud-native data warehouse              |
| Google Cloud Storage   | Storing UDF files & pipeline artifacts   |
| Python                 | UDF and pipeline development             |
| SQL                    | Data transformation & querying           |
| Terraform (Optional)   | Infrastructure provisioning (IaC)        |

---

## 🚀 Features

- ✅ Real-time data ingestion via **Pub/Sub**
- ✅ Serverless, scalable processing with **Dataflow**
- ✅ Custom **Python UDFs** for data enrichment and transformation
- ✅ Built-in **fault tolerance** and retry logic
- ✅ Advanced data warehousing using **BigQuery**
- ✅ Optimized SQL queries for **real-time reporting & dashboarding**

---

## 📊 Project Flowchart

![IRCTC Data Pipeline Flowchart](./IRCTC%20Flowchart.png)

---

## 🗄️ BigQuery Schema

| Column Name       | Data Type  | Description                          |
|-------------------|------------|--------------------------------------|
| `row_key`         | STRING     | Unique identifier for each record    |
| `name`            | STRING     | Passenger's name                     |
| `age`             | INT64      | Passenger's age                      |
| `email`           | STRING     | Passenger's email address            |
| `join_date`       | DATE       | Date when the passenger joined       |
| `last_login`      | TIMESTAMP  | Last login timestamp                 |
| `loyalty_points`  | INT64      | Loyalty points earned                |
| `account_balance` | FLOAT64    | Account balance in INR               |
| `is_active`       | BOOL       | Whether the account is active        |
| `inserted_at`     | TIMESTAMP  | Record insertion timestamp           |
| `updated_at`      | TIMESTAMP  | Last record update timestamp         |
| `loyalty_status`  | STRING     | Loyalty membership tier/status       |
| `account_age_days`| INT64      | Number of days since account creation|

---

## 🎯 Use Cases

- 📊 **Passenger Behavior Analysis**: Understand trends using historical and real-time data.
- 🎁 **Loyalty Program Optimization**: Design personalized loyalty programs using insights.
- 🔍 **Operational Monitoring**: Monitor user activity status in real-time.
- 📈 **Business Trend Analysis**: Perform strategic analysis using BigQuery dashboards.

---

## 🛠️ How to Run

### Prerequisites:
- GCP Project with billing enabled
- `gcloud` CLI configured
- Python 3.8+
- Apache Beam SDK (`pip install apache-beam[gcp]`)
- Service Account with Dataflow, BigQuery, and Pub/Sub permissions

### Deployment Steps:
1. **Set up Pub/Sub topics and subscriptions**
2. **Upload UDFs to Google Cloud Storage**
3. **Deploy Dataflow Pipeline** using Apache Beam
4. **Create BigQuery Dataset & Table** with defined schema
5. **Start publishing mock data** to Pub/Sub

---

## 📝 Future Enhancements

- ✅ Integrate **Cloud Functions** for reactive event-driven workflows
- ✅ Use **Dataflow Streaming Engine** for enhanced real-time analytics
- ✅ Implement **cost-optimized BigQuery queries**
- ✅ Extend schema for train details, booking status, and delays
- ✅ Build a **Looker Studio Dashboard** for live monitoring

---