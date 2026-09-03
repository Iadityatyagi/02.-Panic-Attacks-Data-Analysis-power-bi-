🚨 **Panic Attacks Data Analysis — Power BI**

**📌 Project Overview**

Panic Attacks Data Analysis is a data analytics project developed using Snowflake and Power BI.

The project analyzes a Panic Attack dataset containing patient information, age, gender, medical history, trigger reasons, symptoms, and panic attack scores.

The data was first loaded into Snowflake, where SQL was used for database creation, table creation, data loading, and data understanding. The Snowflake data was then connected to Power BI for data transformation, DAX calculations, visualization, and dashboard development.

🎯 Project Objectives
The main objectives of this project are:

- Load the dataset into Snowflake
- Create database and tables using SQL
- Load CSV/Excel data into Snowflake
- Understand the dataset using SQL queries
- Connect Snowflake with Power BI
- Transform and prepare data in Power BI
- Create Panic Score categories
- Analyze patient medical conditions
- Analyze patients by age group and gender
- Analyze trigger reasons and medical history
- Create DAX calculations
- Build interactive Power BI dashboards

🛠️ Tools & Technologies

Tool	Purpose

Snowflake	Data storage and data analysis

SQL	Database, table, and data operations

Power BI	Data visualization and dashboard development

DAX	Calculations and analytical logic

CSV / Excel	Source data

Power BI Visuals	Interactive analysis

🔄 **Project Workflow**
```powerquery
Local CSV / Excel File
        ↓
Snowflake
        ↓
Create Database
        ↓
Create Table
        ↓
Load Data
        ↓
SQL Data Understanding
        ↓
Connect Snowflake to Power BI
        ↓
Load Data into Power BI
        ↓
Data Transformation
        ↓
Conditional Columns
        ↓
Panic Score Classification
        ↓
DAX Calculations
        ↓
Power BI Visualizations
        ↓
Interactive Dashboard

```

❄️ **Snowflake Data Preparation**

**1. Create Database**
 
Created a database in Snowflake to store the panic attack dataset.

```powerquery
CREATE DATABASE <DATABASE_NAME>;
```

**2. Create Table**
Created a table to store the panic attack data.

```powerquery
CREATE TABLE <TABLE_NAME> (
    ...
);
```
The table contains patient-related information such as:

- Patient ID
- Age
- Gender
- Medical History
- Medical Conditions
-Trigger Reason
- Panic Score
- Symptoms
- Dizziness
- And other relevant attributes
- 
**3. Load Data into Snowflake**
The local CSV/Excel panic attack dataset was loaded into Snowflake.

The data-loading process was:

1. Create database
2. Create table
3. Prepare the local dataset
4. Upload the data file
5. Load data into the Snowflake table
6. Verify the loaded data

🔎 **Data Understanding in Snowflake**

After loading the dataset, SQL queries were used to understand the data.

The analysis included:

- Checking the table structure
- Understanding columns
- Checking data types
- Exploring patient information
- Analyzing panic attack scores
- Understanding medical history
- Analyzing trigger reasons
- Reviewing patient symptoms
- Checking demographic information
  
This helped prepare the dataset before connecting it to Power BI.

🔗 Connecting Snowflake to Power BI

After completing the initial data preparation in Snowflake, the Snowflake database was connected to Power BI.

Connection Workflow
```powerquery
Snowflake
    ↓
Power BI Snowflake Connector
    ↓
Select Database
    ↓
Select Table
    ↓
Load Data
    ↓
Power BI Data Model
```


The required dataset was then loaded into Power BI for further analysis.

**🧹 Power BI Data Transformation**

After loading the data into Power BI, additional data transformations were performed.


The transformations included:


- Understanding the imported data
- Checking column names
- Checking data types
- Creating conditional columns
- Creating Panic Score categories
- Creating Age Groups
- Preparing fields for visualization
- Preparing the final dataset for dashboard development
  
🚨 Panic Score Classification

A Conditional Column was created in Power BI to classify patients according to their Panic Score.


The score was categorized into:


🟢 Low

🟡 Medium

🔴 High

This classification makes it easier to analyze patients according to panic attack severity.

**📊 Power BI Dashboard**

The Power BI report was developed using multiple pages.


**📄 Page 1 — Panic Attack Analysis**

The first page provides an overall analysis of the panic attack dataset.


It focuses on the overall patient and panic attack information and provides a high-level view of the data.


**📄 Page 2 — Patients with Medical Conditions**

The second page focuses on patients with different medical conditions.


**Visualization Used**
- Chart: Stacked Bar Chart
- X-Axis: Count of Patient ID
- Category: Medical Condition / Disease
The chart helps analyze the number of patients associated with different medical conditions.

📄 Page 3 — Detailed Patient Analysis
The third page provides detailed and interactive analysis.

🎛️ Slicers Used
- Panic Score: Low / Medium / High
- Gender
- Trigger Reason
- Medical History
These slicers allow users to dynamically filter the dashboard.



**🧮 DAX Calculations**

DAX was used to create additional calculations for the dashboard.


1. % Patients with Dizziness
   
This measure calculates the percentage of patients who experienced dizziness.

```powerquery
% Patients Dizziness =
DIVIDE(
    COUNTROWS(
        FILTER(
            'PANIC_ATTACK_DATA',
            'PANIC_ATTACK_DATA'[DIZZINESS] = TRUE()
        )
    ),
    COUNTROWS('PANIC_ATTACK_DATA'),
    0
) * 100
```

**Calculation Logic**
1. Filter patients where Dizziness is TRUE().
2. Count the filtered patients.
3. Divide by the total number of patients.
4. Multiply by 100 to calculate the percentage.

 
2. Age Group Using IF
3. 
An Age Group calculated column was created using nested IF statements.

```powerquery
Age Group =
IF(
    'PANIC_ATTACK_DATA'[AGE] <= 17,
    "Child",
    IF(
        'PANIC_ATTACK_DATA'[AGE] <= 24,
        "Adolescent",
        IF(
            'PANIC_ATTACK_DATA'[AGE] <= 64,
            "Adult",
            "Senior"
        )
    )
)
```


3. Age Group Using SWITCH
   
The same age-group logic was also implemented using SWITCH(TRUE()).
```powerquery
Age Group Switch =
SWITCH(
    TRUE(),
    'PANIC_ATTACK_DATA'[AGE] <= 17, "Child",
    'PANIC_ATTACK_DATA'[AGE] <= 24, "Adolescent",
    'PANIC_ATTACK_DATA'[AGE] <= 64, "Adult",
    "Senior"
)
```

Using SWITCH(TRUE()) provides a cleaner approach for handling multiple conditions.


**🎛️ Interactive Dashboard Filters**

The dashboard provides interactive slicers for:

- Panic Score Category
- Gender
- Trigger Reason
- Medical History
Users can select different values and dynamically explore the patient data.

**🔍 Key Analysis Areas**

The dashboard allows analysis of:


- Panic attack severity
- Patient demographics
- Age groups
- Gender distribution
- Medical conditions
- Medical history
- Trigger reasons
- Patient symptoms
- Dizziness percentage
- Patient distribution
  
**💡 Key Skills Demonstrated**

This project demonstrates practical experience in:


- Snowflake
- SQL
- Power BI
- DAX
- Data Loading
- Data Cleaning
- Data Transformation


 ## 📊 Interactive Dashboard

<p align="center">

🔗 **[🚀 View Interactive Power BI Dashboard](https://app.powerbi.com/groups/me/reports/6b922715-c035-4ef0-b07c-1dc0dc5099ee?ctid=fa19b9df-6609-4051-89e2-8018d6fb81b4&pbi_source=linkShare)**

</p>

## 📊 Dashboard Preview
 <img src="fielding.png" alt="Fielding  " width="900">
</p>




