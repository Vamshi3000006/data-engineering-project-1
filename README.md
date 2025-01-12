Here is the entire information formatted neatly for a GitHub README file:

---


## **Acknowledgments**
This capstone project was developed under the guidance of **DataTalksClub**. A special thanks to the instructors:
- **Alexey Grigorev**
- **Sejal Vaidya**
- **Victoria Perez Mola**
- **Ankush Khanna**

Your time, effort, and expertise are deeply appreciated!

🟢 Learn Data Engineering at your own pace with [DataTalksClub's video lectures on YouTube](https://www.youtube.com).

---

## **Problem Statement**
The objective of this project is to create a system that tracks historical US employment data (1990–Present) using datasets from the **Bureau of Labor Statistics (BLS)**. The data provides granular insights down to the county level across the US, making it a valuable resource for individuals researching job market trends in specific regions—especially useful when considering relocation.

---

## **Technologies Used**
This project utilized the following tools and technologies:
- **Google Cloud Platform (GCP)**: Main cloud provider
  - **Google Cloud Storage (GCS)**: Data lake storage
  - **BigQuery**: Data warehouse
- **Python**: Main programming language
- **Docker**: Containerization (via Docker Compose)
- **Apache Airflow**: Workflow orchestration
- **Terraform**: Infrastructure-as-Code (IaC)
- **Apache Spark**: Data processing and transformation
- **Google Data Studio**: Dashboard visualization

---

## **Steps to Reproduce**

### **1. GCP Account Setup**
1. Sign up for a free GCP account (includes $300 credit or 90 days of free usage).
2. Set up a service account:
   - Generate a JSON key file for the service account.
   - Save it to your local directory.
3. Install and configure Google Cloud CLI:
   ```bash
   export GOOGLE_APPLICATION_CREDENTIALS=<path/to/service/key>.json
   gcloud auth application-default login
   ```
   A browser window will prompt you to authenticate.

4. Assign permissions to the service account:
   - Navigate to **IAM & Admin > IAM** in the GCP console.
   - Add the following roles:
     - **Storage Admin** (for bucket management)
     - **Storage Object Admin** (for object-level operations)
     - **BigQuery Admin** (for data warehouse management)

5. Enable required APIs:
   - [IAM API](https://console.cloud.google.com/apis/library/iam.googleapis.com)
   - [IAM Credentials API](https://console.cloud.google.com/apis/library/iamcredentials.googleapis.com)

---

### **2. Infrastructure Setup with Terraform**
1. Download and install [Terraform](https://www.terraform.io/downloads).
2. Initialize your Terraform configuration:
   - Create a directory with a `main.tf` file for your configuration.
   - Run the following commands:
     ```bash
     terraform init
     terraform plan
     terraform apply
     ```
3. Optionally, use a `variables.tf` file to store configuration variables.

---

### **3. Set Up Apache Airflow with Docker**
1. Install Docker and Docker Compose.
2. Set up the necessary `Dockerfile` and `docker-compose.yml` files to run Airflow.
3. Follow the [Apache Airflow installation guide](https://airflow.apache.org/docs/apache-airflow/stable/installation/index.html) for configuration steps.

---

### **4. Run Data Pipelines**
1. Use the Airflow web interface to execute the following DAGs:
   - **`data_ingestion_gcp_dag`**: Ingests data into GCS. Run this first and wait for it to complete.
   - **`gcs_to_bq_dag`**: Loads data from GCS into BigQuery.
2. Monitor the task progress for both DAGs to ensure successful execution.

---

### **5. Create a Dashboard in Google Data Studio**
1. Open [Google Data Studio](https://datastudio.google.com/).
2. Create a new data source:
   - Select **BigQuery** as the source.
   - Connect to your project, dataset, and table.
3. Use the imported data to create interactive visualizations.
4. To optimize performance, uncheck blank values in dropdowns for "State" and "Year."

---

## **Project Outcomes**
This project provides a robust system to analyze historical employment data at a granular level, enabling users to make informed decisions about the job market. Below is a snapshot of the dashboard showcasing key metrics and trends.

![Dashboard Preview](#)

---

## **Contact and Feedback**
For questions, feel free to:
- Open a pull request (PR) on this repository.
- Send an email.

Thank you for your support and interest in this project! 🚀

---
