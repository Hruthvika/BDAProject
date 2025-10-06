# Student Midmarks Data Cleaning & Analysis using PySpark

## Overview
This project demonstrates data preprocessing and analysis using **Apache Spark (PySpark)**.  
The dataset (`MIDMARKS.csv`) contains student midterm marks across multiple subjects and sections.  
The notebook walks through the process of **loading, cleaning, transforming, and analyzing** the data using PySpark DataFrame operations.

---

## Features
- Initialize and configure a Spark session.
- Load CSV data into a Spark DataFrame.
- Handle **null and invalid values** in subject marks (e.g., "A", "AB", "MP").
- Perform **data type casting** for numeric fields.
- Standardize categorical data (e.g., fix misspelled section names like `GAMA` → `GAMMA`).
- Analyze records by section and subject using `groupBy()` and aggregation functions.

---

## Dataset
**File:** `MIDMARKS.csv`  
**Columns:**  
- `SECTION` – Represents student section (e.g., ALPHA, SIGMA, ZETA).  
- Subject columns – `DV`, `M-II`, `PP`, `BEEE`, `FL`, `FIMS` (subject marks).

Invalid entries such as `"A"`, `"AB"`, `"MP"`, and missing values are replaced with `0`.

---

## Technologies Used
- **Apache Spark (PySpark)**
- **Python 3**
- **Jupyter Notebook**

---

## Steps Performed
1. **Spark Initialization**
   ```python
   from pyspark.sql import SparkSession
   spark = SparkSession.builder.appName("Test").getOrCreate()
```

2. **Data Loading**

   ```python
   data = spark.read.csv("MIDMARKS.csv", header=True)
   data.show()
   data.printSchema()
   ```

3. **Data Cleaning**

   * Replace nulls and invalid marks with 0.
   * Fix inconsistent section names.
   * Fill missing section entries with `"ZETA"`.

4. **Data Transformation**

   * Convert columns to integer type.
   * Group and count records by section and subjects.

5. **Analysis**

   * Display the distribution of students per section.
   * Summarize mark counts per subject.

---

## Results

* Cleaned and standardized dataset ready for further analysis or visualization.
* Improved data quality by handling nulls and ensuring consistent categorical values.

---

## How to Run

1. Ensure you have **Python 3.x** and **Apache Spark** installed.
2. Install dependencies:

   ```bash
   pip install pyspark
   ```
3. Open the notebook:

   ```bash
   jupyter notebook SparkProject.ipynb
   ```
4. Run all cells sequentially to execute the full pipeline.

---

## Future Enhancements

* Add data visualization (e.g., bar charts for subject performance).
* Perform correlation analysis between subjects.
* Integrate machine learning for marks prediction or performance clustering.
