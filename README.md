#  Diabetes Diagnosis and Doctor Followup Analysis

A1C and glucose levels play vital roles in diagnosing and managing diabetes by providing insights into blood sugar levels over time, and doctors must communicate with patients who are categorized as pre-diabetic and diabetic for prevention and treatment. With this need in mind, I devised a SQL project that sources data from the National Health and Nutrition Examination Survey to analyze patients' A1C and fasting plasma glucose levels, diagnose patients with either non-diabetes, prediabetes, or diabetes, and notify doctors who need to follow up with patients who fall in the last two categories. 

### A1C (Glycated Hemoglobin) Levels:
- **Measure**: Reflects average blood sugar levels over the past two to three months by measuring the percentage of hemoglobin coated with sugar.
- **Diagnostic criteria**:
  - Non-diabetic: Below 5.7%
  - Prediabetes: 5.7% to 6.4%
  - Diabetes: 6.5% or higher

### Fasting Plasma Glucose (FPG) Levels:
- **Measure**: Glucose concentration in the blood after fasting for at least eight hours.
- **Diagnostic criteria**:
    - Non-diabetic: Below 100 mg/dL
    - Prediabetes: 100 mg/dL to 125 mg/dL
    - Diabetes: 126 mg/dL or higher on two separate tests

## Project Overview

The main steps:

1. **Data Import and Preparation**:
   - Import data from SAS files (`P_GHB.XPT` and `P_GLU.XPT`).
   - Set up a working directory and read the files into Pandas DataFrames.
  
2. **Database Operations**:
   - Establishing a connection to an SQLite database named `Lab Records.db`.
   - Moving the imported tables (`ghb` and `fast_gluc`) to the SQLite database.
  
3. **Data Manipulation and Analysis**:
   - Performing SQL operations on the database:
     - Full joining of the fasting glucose and ghb tables to create `lab_records`.
     - Create a new table, `diabetes, ' with columns for diagnosis and doctor followup based on specific A1C and glucose levels.
  
4. **Data Retrieval and Export**:
   - Executing SQL queries to retrieve data from the `diabetes` table.
   - Fetching data from SQL into Pandas DataFrame.
   - Exporting the DataFrame to a CSV file named `diabetes_data.csv.`
