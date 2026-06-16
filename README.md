# CodeVeda-Data-Science-Level-1
contains the completed Data Science projects and tasks for Level 1 of Codeveda Internship
# project overview
this project shows an end to end data engineering and analytics pipeline. the workflow is divided into two phase: first web scrapping and second, executing statistical data cleaning and exploratory data analysis(EDA) to surface actionable retail insights.
## Phase 1: web scrapping(Data Acquisition)

in  the first phase a python script was built to extract data  from an online bookstore 
## Key Features & Workflow
* **Automated Extraction:** Scraped essential book details across the website, including book titles, pricing,  and stock availability.
* **HTML Parsing:** Utilized Python libraries to navigate pagination and extract clean text from complex nested HTML tags and structures.
* **Data Storage:** Structured the unstructured web elements into a clean tabular format for future analytical use.

# tools used
beautiful soup/ request (for webscrapping and html parsing)
pandas (to save the data to csv)
jupyter notebook (use to write the code)

---


---

## Phase 2: Data Cleaning & Exploratory Data Analysis (EDA)
With the raw web data acquired, the dataset (containing over 11,000 records) underwent a strict data-scrubbing pipeline to ensure analytical integrity.

### 1. Handling Anomalies & Missing Values
* **Logical Imputation:** Handled 4,199 missing entries in the discount attribute by deducing that missing fields represented standard, full-paying transactions ($0$ discount).
* **Listwise Deletion:** Purged 604 rows where critical structural metrics (both quantity and total spent) were entirely absent.
* **Statistical Outlier Removal (IQR Method):** Employed the Interquartile Range (IQR) method to calculate upper and lower distribution boundaries, isolating and dropping **60 extreme outlier rows** that would otherwise distort business averages.

### 2. Schema Standardization
* **Temporal Formatting:** Transformed the `transaction date` feature from a raw text object into a standardized Pandas `datetime64[ns]` schema, enabling chronological sorting.
* **Categorical Auditing:** Standardized text alignment across structural features (`payment method` and `location`) to eliminate category duplication from casing variances.

### 3. Business Insights & Descriptive Analytics
* **Distribution Profile:** Discovered an average purchase size of **₦128.24** against a median of **₦108.50**. This positive right-skew indicates a steady baseline shopper profile elevated by a healthy cluster of high-value transactions.
* **Revenue Drivers:** Aggregated financial volumes to reveal that **Cash** serves as the enterprise's primary operational payment driver.

---

## Tech Stack & Core Libraries.
* **Pandas:** For matrix manipulation, boolean filtering, and structural aggregations.
* **Matplotlib & Seaborn:** For rendering polished, publication-ready statistical visualizations.

---

## Project Structure & Execution
1. **`scraped_data.ipynb` / Notebook:** Run this first to extract the raw data from the web source.
2. **`DataCleaning.ipynb`:** Run this notebook to process the raw output, eliminate outliers, and generate performance charts.
3. **`cleaned_retail_data.csv`:** The final, immaculate dataset ready for production or Power BI integration.