# shopping_behavior_analysis
shopping_behavior_analysis using Python and Pandas. Performed comprehensive data cleaning, missing value imputation, feature engineering, and exploratory data analysis on 3,900 e-commerce transactions. Delivered key business insights including revenue, discount effectiveness, customer segmentation, top-performing products, and category performance.

**Description:**
This Jupyter Notebook provides a comprehensive analysis of customer shopping behavior using transactional data. The project focuses on understanding purchase patterns, handling missing and categorical data, and identifying high-value customers. The analysis includes:

* **Data Exploration (EDA):** Inspect dataset structure, identify missing values, and summarize key statistics.
* **Data Cleaning & Preprocessing:** Standardize column names, handle missing values, encode categorical variables, and normalize textual data for analysis.
* **Aggregations & Insights:** Calculate total purchase amounts per customer, analyze discount usage, and identify customers exceeding average spending thresholds.
* **Analysis by Category & Ratings:** Explore review ratings across product categories to uncover patterns in customer feedback.

This notebook demonstrates professional data cleaning, preprocessing, aggregation, and exploratory analysis techniques, suitable for presentation in a corporate data analytics portfolio.

---

## 2️⃣ **Step-by-Step Detailed Description (for Notebook cells)**

1. **Data Loading & Initial Inspection**

   ```python
   df.info()
   df.isna().sum()
   ```

   *Perform initial data inspection to understand dataset structure and summarize missing values.*

2. **Column Name Standardization**

   ```python
   df.columns = df.columns.str.replace(' ', '_').str.lower()
   ```

   *Normalize column names by replacing spaces with underscores and converting to lowercase for consistency.*

3. **Handling Missing Values**

   ```python
   # For each product category and review rating
   ```

   *Handle missing values across product categories and review ratings to ensure data completeness for analysis.*

4. **Encoding Categorical Variables**

   ```python
   df['frequency_of_purchases'] = df['frequency_of_purchases'].map(mapping_dict)
   ```

   *Map categorical text values (e.g., purchase frequency) to numeric codes and standardize column names for analysis.*

5. **Aggregating Purchase Data**

   ```python
   g1 = df[df['discount_applied']=='Yes'] \
          .groupby('customer_id') \
          .agg(purchase_amount_sum=('purchase_amount','sum')) \
          .reset_index()
   m = df['purchase_amount'].mean()
   g1[g1['purchase_amount_sum'] > m]
   ```

   *Filter customers who applied discounts, aggregate total purchases per customer (handling multiple orders), and identify those exceeding the overall average purchase amount.*

6. **Analyzing Review Ratings by Category**

   ```python
   df.groupby('category')['review_rating'].mean()
   ```

   *Examine distribution of review ratings across categories to uncover customer feedback patterns.*

---
and more....
## 3️⃣ **Key Takeaways / Insights**

* High-value customers can be identified by aggregating total purchase amounts and comparing against the overall average.
* Discount usage impacts total spending patterns, helping inform marketing and loyalty strategies.
* Review ratings vary by category, providing insights into product performance and customer satisfaction.
