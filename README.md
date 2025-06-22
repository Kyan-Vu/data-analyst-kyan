# data-analyst-kyan
# Streamlining the Recruitment Process to Reduce Time-to-Hire

## Project Description
This project is a descriptive analysis of the recruitment process using internal HR datasets. The objective is to identify key factors that contribute to long time-to-hire, uncover bottlenecks in the recruitment pipeline, and generate insights that support strategies to streamline hiring workflows and reduce overall recruitment time.

---

## Project Title
**Streamlining the Recruitment Process to Reduce Time-to-Hire**

---

## Objective
The primary goal of this project is to conduct a descriptive analysis of the recruitment process using internal HR datasets. Through this analysis, we aim to identify key factors that contribute to long time-to-hire, uncover bottlenecks in the recruitment pipeline, and generate insights that can support strategies to streamline hiring workflows and reduce overall recruitment time.

---

## Dataset
The dataset includes HR recruitment data collected from the company’s internal systems, focusing on the applicant journey from job posting to hiring. It contains the following three key components:

### Recruitment Applications
- Application ID: Unique identifier for each job application  
- Candidate ID: Identifier for the candidate  
- Position ID: Identifier for the job posting  
- Application Date: Date the application was submitted  

### Interview Feedback
- Feedback ID: Identifier for each feedback entry  
- Candidate ID: Identifier for the interviewed candidate  
- Interviewer ID: Identifier for the interviewer  
- Feedback Score: Quantitative rating of the candidate's performance  

### Hiring Timeline Records
- Timeline ID: Unique identifier for each hiring process record  
- Position ID: Associated job posting  
- Posted Date: Date the job was posted  
- Hire Date: Date the candidate was officially hired  

---

## Methodology

### Data Collection and Preparation
- Loaded the HR datasets (Recruitment Applications, Interview Feedback, and Hiring Timeline Records) using Excel and AWS services such as S3.
- Cleaned and transformed data using AWS Glue DataBrew, including:
  - Removing null values  
  - Trimming whitespace in key fields (e.g., CandidateID, PositionID)  
  - Ensuring correct data types (e.g., converting date fields for calculations)  
  - Removing duplicates and aligning schemas for joins  
- Used Glue Crawlers and the AWS Glue Data Catalog to catalog and prepare datasets for analysis in Athena.

### Descriptive Statistics
Calculated key recruitment performance metrics using Amazon Athena, such as:
- Average time-to-hire across all job postings  
- Time-to-hire by feedback score to reveal candidate quality vs. processing time  
- Predicted time-to-hire after automation  

### Data Visualization
Created visual representations to illustrate findings:
- Draw.io diagram illustrating the ETL pipeline from data ingestion (S3) to final querying in Athena  
- Tables from Athena output showing statistical breakdowns  
- Excel-based charts and tables showing:  
  - Time-to-hire by feedback score  
  - Distribution of applications per position  
  - Summary metrics for each stage of the recruitment process  

### Candidate Segmentation
Segmented candidates based on key behavioral and outcome variables:
- Feedback score tiers (e.g., 1–2, 3–4, 5)  
- Duration of time-to-hire (fast hires vs. delayed)  
- Compared recruitment efficiency across job roles and feedback profiles  
- Identified potential "fast track" patterns based on positive feedback or timing  
- Grouped candidates by feedback score and time-to-hire  
- Analyzed variation across job roles and departments  

---

## Insights and Findings
Key insights derived from Athena query results:
- Feedback score is positively correlated with faster hiring decisions  
- Process delays often occur post-interview, due to missing or delayed feedback  
- Simulated automation (e.g., removing 2 days from the timeline) could significantly reduce average time-to-hire  

---

## Recommendations
Based on findings, the following improvements are recommended:
- Automate repetitive steps such as interview scheduling and follow-ups  
- Enforce time standards for interviewers to submit feedback  
- Use real-time monitoring of time-to-hire metrics in Athena and CloudWatch  
- Implement fast-track protocols for candidates with high feedback scores  

---

## Tools and Technologies

- **AWS S3 (Simple Storage Service)**  
  Used as the central data lake to store raw HR datasets, including recruitment applications, interview feedback, and hiring timeline records. S3 provides scalable, durable storage that integrates seamlessly with other AWS analytics services.

- **AWS Glue & AWS Glue Data Catalog**  
  Employed to automate ETL (Extract, Transform, Load) processes. AWS Glue crawlers and the Glue Data Catalog were used to infer schema, index datasets, and prepare them for querying in Athena.

- **AWS Glue DataBrew**  
  Enabled visual, code-free data preparation. Tasks such as removing null values, standardizing data types (e.g., date formats), deduplicating entries, and cleaning fields (e.g., trimming whitespace in IDs) were handled using DataBrew recipes.

- **AWS Athena**  
  Used to perform SQL-like queries directly on data stored in S3. Athena was essential for calculating performance metrics like average time-to-hire, feedback score distributions, and identifying delays across recruitment stages.

- **Amazon EC2**  
  Provided on-demand compute resources during prototype testing and when running more intensive data transformation scripts that exceeded Glue's interactive limits.

- **Excel**  
  Supplemented AWS services by creating pivot tables, ETL documentation, and summarizing Athena outputs in dashboard-ready formats. Used extensively
