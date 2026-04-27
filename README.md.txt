# 📊 Data Warehouse & ETL Pipelines using SSIS

This project demonstrates the implementation of multiple data warehousing scenarios using **SQL Server Integration Services (SSIS)** as part of a Data Warehouse course at Cairo University (Faculty of Computers and Artificial Intelligence).

The assignment focuses on building real-world ETL pipelines, handling data quality issues, and applying advanced data warehousing concepts.

---

## 🚀 Project Objectives

- Integrate data from multiple heterogeneous sources
- Clean and standardize inconsistent datasets
- Implement Slowly Changing Dimensions (Type 6)
- Design version-controlled data loading
- Apply business rules on transactional data
- Generate aggregated analytical outputs

---

## 🛠️ Tools & Technologies

- Microsoft SQL Server
- SQL Server Integration Services (SSIS)
- T-SQL
- REST API integration
- XML & CSV data sources

---

## 📂 Project Structure
📁 Q1_Data_Integration
📁 Q2_SCD_Type6
📁 Q3_Versioning_Load
📁 Q4_Trading_Analytics

Each folder contains SSIS packages, scripts, and resources related to the specific problem.

---

## 🔹 Q1 – Data Integration Pipeline

### 📌 Description
Built an ETL pipeline to integrate air quality data from multiple sources:
- XML file
- CSV file
- REST API

### ⚙️ Key Features
- Unified schema:
  - `sensor_id, city, timestamp, pm25, pm10`
- Data cleaning:
  - Handled missing and empty values
  - Removed invalid/negative pollution readings
- Added a `source` column to track data origin

### 🧠 Techniques Used
- Data Flow Tasks
- Derived Column
- Conditional Split
- Union All

---

## 🔹 Q2 – SCD Type 6 Implementation

### 📌 Description
Implemented **Slowly Changing Dimension Type 6** without using the built-in SCD transformation.

### ⚙️ Key Features
- Tracks both historical and current values
- Supports incremental data loading
- Handles updates in:
  - Name
  - Budget

### 🧠 Techniques Used
- Lookup Transformation
- Conditional Split
- Derived Column
- OLE DB Command (for updates)

---

## 🔹 Q3 – Versioning Data Load

### 📌 Description
Designed a version-controlled loading mechanism for device status data.

### ⚙️ Key Features
- On each run:
  - Previous records are closed (`Active_Flag = 0`)
  - New records inserted with incremented `Version_No`
- Daily reset of version numbering
- Supports multiple runs per day

### 🧠 Techniques Used
- Lookup
- Conditional Split
- Derived Column
- Sequence Containers

---

## 🔹 Q4 – Trading Data Processing

### 📌 Description
Processed raw trade transactions into clean, aggregated trading metrics.

### ⚙️ Key Features
- Standardized trade actions (`BUY`, `SELL`)
- Handled negative quantities:
  - Converted to opposite action
- Business validation:
  - SELL allowed only if a previous BUY exists
- Invalid transactions excluded

### 📊 Output
Generated a summary table:
- `Trader_ID`
- `Trade_Date`
- `Total_Buy`
- `Total_Sell`

### 🧠 Techniques Used
- Conditional Split
- Sorting & Aggregation
- Derived Column
- Lookup (for validation logic)

---

## 📈 Key Learnings

- Building end-to-end ETL pipelines using SSIS
- Handling real-world data quality issues
- Implementing SCD logic manually
- Designing versioned and time-aware datasets
- Applying complex business validation rules in data flows

---

## 📸 Screenshots (Optional)


<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1613a8f4-1429-4fe5-99db-910af46017de" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8d13243b-f8b5-46c7-9645-bb697aa6495c" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2b0fef55-a690-4e32-aca6-0d8a9a565974" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9e617b66-2ea3-43b5-bb00-6c952caf18fe" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7206c907-68c3-4d14-bb2c-18f005a41449" />
<img width="1364" height="326" alt="image" src="https://github.com/user-attachments/assets/27a16a22-f28a-47bd-9986-19922c7c0303" />


---

## 🧑‍💻 Author

- Mohand Badway

---

## 📌 Notes

This project was developed as part of an academic assignment.  
All implementations were built from scratch without using automated SCD components to demonstrate a deeper understanding of ETL logic.

---