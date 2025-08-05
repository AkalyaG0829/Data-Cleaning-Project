#  Data Cleaning: Layoffs Dataset Using SQL

This project focuses on cleaning and standardizing a raw dataset containing global tech company layoffs. Using SQL (MySQL), we handle duplicates, format inconsistencies, null values, and perform text standardization to prepare the data for analysis.

##  Dataset Overview
The dataset includes:
- Company names
- Location, industry, and country
- Number and percentage of layoffs
- Company stage and funds raised
- Layoff event dates

##  Goals
- Remove duplicates and inconsistencies
- Standardize text fields (industry, country, company)
- Convert date formats
- Handle missing or null values
- Prepare the data for further analysis or visualization

##  Tools Used
- MySQL
- SQL (CTEs, `ROW_NUMBER()`, `JOIN`, `TRIM`, `STR_TO_DATE`, etc.)

##  Key SQL Tasks Performed

### 1. Data Staging
- Created `layoffs_staging` and `layoffs_staging2` tables
- Copied raw data into staging tables for safe transformation

### 2. Removing Duplicates
- Used `ROW_NUMBER()` with `PARTITION BY` to find duplicates
- Deleted duplicate rows from staging tables

### 3. Data Standardization
- Trimmed spaces from text columns (e.g., `company`, `country`)
- Replaced inconsistent values (e.g., "Crypto & Blockchain" → "Crypto")
- Standardized country names (e.g., "United States.")

### 4. Date Formatting
- Converted date strings to proper `DATE` format using `STR_TO_DATE()`

### 5. Handling Nulls
- Replaced empty strings with NULL
- Inferred missing industry values by joining on company name
- Removed rows with no layoff data (`total_laid_off` AND `percentage_laid_off` both NULL)

### 6. Final Cleanup
- Dropped helper columns (`row_num`) after use

##  Files
`layoffs_cleaning.sql`: SQL script containing the full data cleaning process.

##  Final Result
A clean and standardized table `layoffs_staging2` ready for data analysis and visualization.





