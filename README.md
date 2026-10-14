# Nextgen-Learners-Data-Science-week1

# Applicant Data Cleaning & Preprocessing Pipeline 🚀

**Author:** Shiza Ali  
**Program:** NextGen Learners Data Science Internship Program  
**Milestone:** Week 1 — Foundations: Cleaning & Exploring the Applicant Dataset

---

## 📌 Project Overview
Real-world datasets are rarely clean. This project demonstrates foundational data wrangling and exploratory data analysis (EDA) techniques using **Python** and **Pandas**. The goal was to take a raw applicant dataset containing structural errors, missing values, duplicates, and inconsistent formatting, and transform it into a robust, analysis-ready dataset.

---

## 🛠️ Key Steps & Data Cleaning Pipeline

1. **Initial Exploration (`df.info()`, `df.describe()`):**
   - Assessed dataset shape (`80 rows, 7 columns`) and identified missing values, exact duplicates, and incorrect data types.

2. **Handling Missing Values:**
   - **Applicant Name:** Dropped rows missing names as they are critical identifiers.
   - **Email:** Imputed missing values with a placeholder (`"not_provided@example.com"`) to preserve sample size.
   - **University:** Imputed missing values with `"Not Specified"`.
   - **Status:** Filled missing entries with `"Under Review"` as a logical default state.

3. **Duplicate Detection:**
   - Identified and removed exact and near-duplicate applications (reducing dataset size from 78 to 73 records) using a unique cleaned `Email` identifier rather than prone-to-error names.

4. **Text Standardization:**
   - Standardized `Domain Applied` variations (e.g., `web dev`, `webdev`, `WEB DEV`) into 5 clean core categories.
   - Standardized `Status` capitalization using string methods (`.str.strip().str.title()`).

5. **Data Type Correction & Imputation:**
   - Converted `Application Date` to proper `datetime64[ns]` format (handling overflow artifacts like `########`) and used forward fill (`.ffill()`) to resolve missing date values without dropping records.
   - Cleaned `Phone` numbers by stripping hyphens and spaces while maintaining string format to preserve crucial leading zeros.

---

## 📊 Final Dataset Summary
* **Starting Shape:** 80 rows, 7 columns
* **Final Shape:** 73 rows, 7 columns
* **Data Quality:** Zero missing values in critical fields, duplicates removed, and uniform formatting across all attributes.

---

## 🚀 Technologies Used
* **Python**
* **Pandas**
* **Jupyter Notebook**
