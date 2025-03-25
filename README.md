                                         Cloud Computing Portfolio
					 
⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

Author: Muhammad Zulqarnain Shahzad (2306553)

Course: BUSI 653 - Cloud Computing Technologies

Professor: Dr. Mahmood Mortazavi Dehkordi

Institution: University Canada West

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

This portfolio was prepared as part of the MBA Cloud Computing project at University Canada West, under the distinguished mentorship and insightful guidance of **Dr. Mahmood Mortazavi Dehkordi**.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

Table of Contents

	.	Introduction
	.	Overall Portfolio Overview
 
Project A: UCW HR Professional Development

	•	Project Description
	•	Project Title
	•	Objective
	•	Datasets
	•	Architecture Diagram
	•	Methodology
	•	Implementation Steps
	•	Tools and Technologies
	•	Deliverables

Project B: City of Vancouver (Consulting & Management Services)

	•	Project Description
	•	Project Title
	•	Objective
	•	Datasets
	•	Architecture Diagram
	•	Methodology
	•	Implementation Steps
	•	Tools and Technologies
	•	Deliverables
 
In-Class Participation & Business Questions
 
	8.	Conclusion

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

1. Introduction

During our BUSI 653 Cloud Computing course at University Canada West, we undertook two significant cloud-based data analytics projects on AWS:

	1.	UCW HR Professional Development
	•	I handled the “Professional Development” subset within the HR Department.
	2.	City of Vancouver
	•	Specifically, I worked on the Consulting & Management Services data from the City of Vancouver open data portal.

Both projects required end-to-end design of a Data Analytic Platform (DAP) using AWS services for ingestion, transformation, security, cost analysis, and more.
We also addressed exploratory, descriptive, and diagnostic analytics, along with data wrangling and data quality controls.

Additionally, we participated in in-class activities, answering business questions about best practices, naming conventions, cost optimization, and data security. This README is a single comprehensive portfolio bringing together all that work.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

2 .  Overall Portfolio Overview

	•	Project A: UCW HR (Professional Development)
	•	Focus: building an AWS-based pipeline for professional development data (employees, activities, financial support).
	•	Emphasis: S3 folder structures (raw/transform/curated), AWS Glue, DataBrew, cost optimization, user logs, etc.
	•	Project B: City of Vancouver (Consulting & Management Services)
	•	My personal portion from a group of four. Others used different Vancouver data, but I used the business-licenses CSV focusing on consulting/management businesses.
	•	Steps: ingestion, cleaning, transformations, analytics, plus advanced AWS security and data governance features.

Throughout both, we adhered to the professor’s instructions to incorporate:

	•	Exploratory Data Analysis (EDA)
	•	Descriptive Analysis
	•	Diagnostic Analysis
	•	Data Wrangling
	•	Data Quality Control
	•	Security (KMS, IAM, versioning, replication)
	•	Cost Optimization (Lifecycle policies, CloudWatch alerts, minimal scanning in queries)

We also used SQL queries (e.g., in Athena) for final analysis, rather than Python/Pandas.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

3. Project A: UCW HR Professional Development

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

3.1. Project Description (UCW HR)

This initiative targeted the Professional Development domain within UCW’s HR Department. We developed a robust data pipeline to ingest, store, and analyze professional development records—such as training sessions, finance approvals, and employee logs.

3.2. Project Title (UCW HR)

“Implementing a Cloud-Based Data Analytics Platform for HR Professional Development at UCW”

3.3. Objective (UCW HR)

	•	Goal #1: Centralize all professional development data (activities, employees, financial support) in a secure, scalable AWS environment.
	•	Goal #2: Deliver insights on training frequency, cost distribution, employee feedback, and anomalies.
	•	Goal #3: Incorporate advanced security (KMS, IAM), cost management, and data quality checks.

3.4. Datasets (UCW HR)

	1.	Professional_Development_Activities.csv
	2.	Employees-List.csv
	3.	Financial_Support-List.csv

Fields typically include:

	•	Employees: EmployeeID, Name, Department, Role, etc.
	•	Activities: ActivityID, ActivityName, Date, Cost, Type, etc.
	•	Financial: SupportID, ApprovedAmount, SupportStatus, etc.

All uploaded initially to an S3 “raw” bucket.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

3.5. Architecture Diagram (UCW HR)

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

<img width="1512" alt="Screenshot 2025-03-25 at 2 30 52 PM" src="https://github.com/user-attachments/assets/2ce8e5fc-07f9-4d0a-a09e-4a7414caea1e" />

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

The final draw.io screenshot from Week 9:

	•	S3 (raw → transform → curated)
	•	AWS Glue DataBrew/ETL
	•	KMS, IAM roles, cross-region replication
	•	EC2 or Beanstalk reference.

3.6. Methodology (UCW HR)

According to the professor’s instructions, we implemented:

	1.	Exploratory Data Analysis: Identify missing values, outliers, distribution.
	2.	Descriptive Analysis: Summarize training sessions by cost, frequency, time.
	3.	Diagnostic Analysis: Investigate lower training uptake in certain quarters.
	4.	Data Wrangling: Merge employee + activities + financial data, fix data type issues, remove duplicates.
	5.	Data Quality Control: Evaluate completeness, uniqueness, date freshness (some tasks done in AWS Glue).

3.7. Implementation Steps (UCW HR)

Data Ingestion

	•	Created three S3 buckets: ucw-hr-zul-raw, ucw-hr-zul-transform, ucw-hr-zul-curated.
	•	Placed 3 CSVs in the they are respective folders inside raw bucket.
 
 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="image" src="https://github.com/user-attachments/assets/562d044b-e7bd-472c-967f-9ffe301aa2b2" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

Data Profiling (DataBrew)

	•	Built a DataBrew project.
	•	Verified missing data, textual anomalies.
⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="image" src="https://github.com/user-attachments/assets/3746ac34-2832-4135-80c1-459669fad9bb" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
 
Data Cleaning & Transformation

	•	Used DataBrew recipes: remove punctuation, fix date columns, fill missing cost with 0 or “N/A.”
	•	Output to the transform S3 bucket.
 
 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 20 15 PM" src="https://github.com/user-attachments/assets/de75770f-3fe8-4ee3-a7e2-8a890e193134" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
Glue Crawler & Catalog

	•	Created a crawler (“HR-ZUL-crawler”) to scan the transform bucket.
	•	Verified the schema in AWS Glue Data Catalog.
 
 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="image" src="https://github.com/user-attachments/assets/196fc0e5-63e8-4136-ba4f-7f50e5c9ac00" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
 
Join

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="image" src="https://github.com/user-attachments/assets/b21dfb51-e67f-495d-a9a1-dcb6c1c0845d" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
 
Glue ETL Job

	•	Visually mapped columns from employees/activities/financial to produce a curated, merged table.
	•	Summarized or aggregated cost totals per employee or per month.
	•	Output to ucw-hr-zul-curated.
 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 21 02 PM" src="https://github.com/user-attachments/assets/1dbfa345-b550-4c85-943c-6f6741fa577b" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
 
 Analytics (SQL in Athena)
 
	•	Ran queries such as SELECT department, COUNT(*) FROM hr_training GROUP BY department;
	•	Explored cost patterns or monthly participation rates.
 
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="Screenshot 2025-03-25 at 3 22 28 PM" src="https://github.com/user-attachments/assets/8c774f2b-437c-4920-a14b-69bfe687ae33" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
 
Security & Replication

	•	Created a KMS CMK to encrypt S3 objects by default.
	•	Enabled versioning and cross-region replication from ucw-hr-zul-raw to a backup bucket (e.g., “ucw-hr-backup”).
 
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 23 37 PM" src="https://github.com/user-attachments/assets/035235ad-ddd8-4990-b936-c99960d417b8" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 22 49 PM" src="https://github.com/user-attachments/assets/d9f08556-6707-47ba-8d30-24cddd9ab3fc" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 23 04 PM" src="https://github.com/user-attachments/assets/20c6c8dd-da62-467a-9dd9-8202869dca4b" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  
Data Quality

	•	Employed Glue data quality rules for checking no cost < 0, ensuring valid date ranges.
	•	“Pass” vs. “Fail” routing to separate subfolders.
 
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 24 11 PM" src="https://github.com/user-attachments/assets/594cead6-615e-4c8b-a8b6-4f090f0d1b41" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="Screenshot 2025-03-25 at 3 24 02 PM" src="https://github.com/user-attachments/assets/434e9a2a-73eb-4336-8e2b-2eeaba794588" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  
Cost Optimization

	•	Activated S3 lifecycle policies to move older data to infrequent access or Glacier.
	•	Monitored usage with CloudWatch alarms.
 
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

 <img width="1512" alt="image" src="https://github.com/user-attachments/assets/95bc33b7-6bed-40e7-a3aa-78d57dc5589e" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

CloudWatch Monitoring
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

<img width="1512" alt="Screenshot 2025-03-25 at 3 24 20 PM" src="https://github.com/user-attachments/assets/70816831-5abb-4a9b-a058-6aae59e023e6" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  
3.8. Tools and Technologies (UCW HR)

	•	AWS S3 (raw/transform/curated), versioning, replication
	•	AWS Glue (DataBrew, crawler, ETL)
	•	AWS KMS (encryption) + IAM (role-based security)
	•	AWS Athena for SQL analytics
	•	draw.io for architecture diagram

3.9. Deliverables (UCW HR)

	1.	HR draw.io diagram
	2.	Cleaned & merged dataset in curated
	3.	DataBrew job screenshots showing transformations
	4.	Glue ETL script or job definitions
	5.	SQL queries run in Athena, plus a summary of findings
	6.	Data Quality pass/fail outputs
	7.	CloudWatch cost/logs monitoring setup

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

4. Project B: City of Vancouver (Consulting & Management Services)

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

4.1. Project Description (City VAN)

As part of a 4-person group, each member tackled a different Vancouver dataset. My subset was the “Consulting & Management Services” business license data. The aim was to build a scalable AWS pipeline for ingestion → cleaning → summarization → analysis.

4.2. Project Title (City VAN)

“Advanced AWS Data Analytics for Vancouver’s Consulting & Management Services Business Licenses”

4.3. Objective (City VAN)

	•	Centralize “Consulting & Management Services” licensing data from Vancouver’s open data, ensuring it’s consistent and up-to-date.
	•	Provide descriptive metrics (license counts, statuses, issuance trends) and diagnostic insight into anomalies or sudden changes.
	•	Maintain data security, data quality, and cost-effective operations.

4.4. Datasets (City VAN)

	•	Business Licences - Consulting and Management Services.csv
	•	Typical fields: LicenseNumber, BusinessName, BusinessType, IssuedDate, Status, etc.
	•	Possibly up to a few thousand records.

(Other team members used different data, e.g., Animal Control, 3-1-1 metrics. My portion is specifically Consulting & Management.)

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

4.5. Architecture Diagram (City VAN)

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/3c1151ca-45e2-493d-b4c1-8ca562e229c5" />

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻


My final draw.io that references:

	•	S3 buckets (raw, transform, curated) named “city-van-zul-raw,” etc.
	•	DataBrew for cleaning, AWS Glue crawler for catalog, ETL for summarization
	•	KMS encryption, versioning, cross-region replication

4.6. Methodology (City VAN)

Following professor’s instructions:

	1.	Exploratory Data Analysis: Found missing fields, invalid statuses, date anomalies.
	2.	Descriptive Analysis: Summarized total active licenses, monthly issuance patterns.
	3.	Diagnostic Analysis: Explored potential cause of unexpected spikes or dips in license issuance.
	4.	Data Wrangling: DataBrew transformations (removing duplicates, normalizing date formats to “YYYY-MM-DD,” etc.).
	5.	Data Quality: Checking that each license has a valid number, consistent status, and non-empty business name.

4.7. Implementation Steps (City VAN)

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

Data Ingestion
 
	•	Created S3 buckets: city-van-zul-raw, city-van-zul-transform, city-van-zul-curated.
	•	Placed the CSV in a subfolder “consulting-management” under raw.
 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
 
<img width="1512" alt="image" src="https://github.com/user-attachments/assets/b7d11d5b-1bbe-4d73-ae2d-1cc670969b50" />

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

Data Profiling

	•	Used DataBrew to create a project, e.g. “ConsultingMgmtProjectZUL.”
	•	Found missing license fees or “IssuedDate” issues.
 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/c5fa7d67-4faa-4007-8a38-c7e0dc1e107d" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
Data Cleaning

	•	DataBrew recipe: remove special characters from “BusinessName,” unify date formats, fill missing license fees as “N/A.”
	•	Output to the transform bucket.
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/87fc253a-8750-413e-9681-b0583c5f5135" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
  
 
AWS Glue Crawler & Catalog

	•	Created a crawler “CityVanConsultingCrawler” pointing to transform bucket.
	•	Verified table schema in AWS Glue data catalog.
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/7e2ac21c-663e-42b5-9976-c57fdcb61b5d" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
ETL & Summaries

	•	Potentially joined with a small reference table for “Business Type” if available.
	•	Aggregated license counts by “Status,” “IssuedYear,” etc.
	•	Output curated summary to city-van-zul-curated.
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/6ed53b60-e48f-4ad1-a15d-2feec105db42" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
Analysis

	•	Used AWS Athena queries, e.g. SELECT Status, COUNT(*) FROM consulting_management GROUP BY Status;
	•	Studied monthly issuance for descriptive/diagnostic insights.
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/e1118d6b-54cd-4c90-9a7d-8f63a5483c44" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
Security / Replication

	•	KMS encryption, IAM roles limiting who can read the curated bucket.
	•	Bucket versioning + cross-region replication to “city-van-zul-backup.”
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/0b3d614c-27bb-4d85-878a-966a8a771691" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/fc87c3c7-467a-493c-ad08-9a70d523e43b" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
Data Quality

	•	Glue data quality checks for valid (non-empty) LicenseNumber, date being in a plausible range.
	•	Separated “passed” vs. “failed” records to different transform subfolders.
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/3f2eb3ab-5a14-4b80-8d2d-7209dca85ba2" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/25799529-9ee6-46c4-9f40-5f531e107c18" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/938a4ecf-a67c-4aa7-ac10-56006a5ff239" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
KMS Key Setup
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/a013e43c-26af-473e-9e3e-75c97681cb51" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻
CloudWatch Monitoring
  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/eaf0a9a5-b9b6-4111-9c09-9c0f186dc632" />

  ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

4.8. Tools and Technologies (City VAN)

	•	AWS S3 (raw → transform → curated)
	•	AWS Glue (DataBrew, crawler, ETL)
	•	IAM, KMS for security & encryption
	•	Athena for SQL analytics
	•	CloudWatch for cost & usage monitoring

4.9. Deliverables (City VAN)

	1.	draw.io architecture diagram
	2.	S3 folder structure with final curated dataset
	3.	DataBrew job recipes & cleaning steps
	4.	Glue crawler + ETL definitions
	5.	Athena queries and results
	6.	Data Quality pass/fail outputs
	7.	Cost analysis or lifecycle policies for older data

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

8. Conclusion

We successfully built two end-to-end cloud data analytics solutions:

	1.	UCW HR Professional Development – Showcasing how AWS S3, Glue, DataBrew, and Athena can unify staff training data for in-depth analytics, with robust security and cost controls.
	2.	City of Vancouver – Consulting & Management Services – Handling business license data by cleaning, profiling, and analyzing to derive valuable descriptive and diagnostic insights.

Key Achievements:

	•	Exploratory & Descriptive: We used DataBrew and Athena queries to discover data distributions and patterns.
	•	Diagnostic: Investigated root causes of anomalies in training usage or license issuance.
	•	Data Wrangling: Detailed cleaning steps for missing values, date normalization, duplicate removal.
	•	Data Quality Control: Employed Glue job rules to classify “passed” vs. “failed” records.
	•	Security & Replication: Deployed KMS encryption, IAM policies, versioning, cross-region replication.
	•	Cost Optimization: Created lifecycle rules, set up CloudWatch alarms to watch usage, and minimized data scanning.

 ⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

This project is a small reflection of a big journey, made possible through kindness, patience, and the guidance of those I deeply admire especially **Dr. Mahmood Mortazavi Dehkordi**, whose mentorship has been truly invaluable.
