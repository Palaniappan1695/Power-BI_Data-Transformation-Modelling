# Power BI – Data Transformation & Data Modelling

## 📌 Project Overview

This project demonstrates data transformation, data cleaning, data aggregation, and data modelling using **Microsoft Power BI and Power Query**. The objective is to prepare raw order and sales target data for meaningful analysis by improving data quality, creating calculated columns, combining datasets, and establishing relationships between tables.

The project follows a step-by-step workflow, covering essential data preparation techniques used in real-world data analytics.

## 🎯 Project Objectives

- Import multiple CSV files into Power BI.
- Clean and transform data to improve consistency and usability.
- Create custom columns for location and profit margin analysis.
- Classify transactions into Profit, Loss, and Break-Even categories.
- Merge order details with order information using Order ID.
- Identify blank rows and evaluate duplicate records.
- Filter and sort data for focused analysis.
- Aggregate profit by category and sales targets by month.
- Establish relationships between order data and sales target tables.

## 📂 Dataset Description

The project uses three CSV data sources, as documented in the project screenshots.

| Dataset | Description |
|---|---|
| Order Details | Contains order-level details such as Order ID, product category, sub-category, quantity, amount, and profit. |
| List of Orders | Contains order information, including Order ID, order date, customer details, city, and state. |
| Sales Target | Contains monthly sales targets associated with product categories. |

*Note: The original CSV download URL was not available in the PDF. Dataset descriptions above are based on the fields and tables shown in the project documentation.*

## 🛠️ Tools & Technologies

- **Microsoft Power BI Desktop** – Data analysis and modelling.
- **Power Query Editor** – Data cleaning and transformation.
- **DAX** – Creating measures for analysis.
- **CSV files** – Source data format.

## 🔄 Project Workflow

### 1. Data Import
- Imported CSV files using the Text/CSV connector.
- Loaded the datasets into Power BI.

### 2. Row Limiting & Data Types
- Removed rows after the 500th row as part of the documented exercise.
- Converted Order Date into the Date data type.
- Changed Amount and Target columns to Fixed Decimal Number.

### 3. Text Formatting
- Applied Capitalize Each Word formatting to customer names for consistent presentation.

### 4. Custom Column Creation
Created two calculated columns in Power Query:

**Location**

```powerquery
[City] & ", " & [State]
```

Combined city and state into one column.

**Profit Margin**

```powerquery
[Profit] / [Amount]
```

Calculated profit margin and formatted the column as a percentage.

### 5. Conditional Column
Created a Profit Status column using the following conditions:

| Condition | Classification |
|---|---|
| Profit < 0 | Loss |
| Profit = 0 | Break-Even |
| Profit > 0 | Profit |

This classification helps distinguish profitable and loss-making records.

### 6. Data Merging
- Merged Order Details and List of Orders using Order ID.
- Expanded the merged columns.
- Renamed the resulting table to **Orders Data**.

### 7. Missing Data & Duplicate Handling
- Removed blank rows using Power Query.
- Checked for complete duplicate records.
- Identified that Order ID appears repeatedly in the dataset.
- Retained repeated Order IDs because other attributes, such as date, amount, quantity, category, and sub-category, can differ between records.

This step highlights the importance of distinguishing legitimate repeated values from completely identical rows.

### 8. Sorting & Filtering
- Sorted Order Date in descending order.
- Applied a state filter to examine records associated with Tamil Nadu.

### 9. Grouping & Aggregation
Performed the following operations:

**Order ID Count**

Created a DAX measure:

```dax
Count_of_order_id =
COUNT('Order Data (2)'[Order ID])
```

Displayed the measure using a Card visual.

**Average Profit by Category**

- Duplicated the Order Data table.
- Used Power Query's Group By feature to calculate average profit by category.

**Monthly Sales Target**

Grouped the Sales Target data by Month of Order Date and calculated the sum of Target, creating a new column named `Monthly_Target`.

### 10. Data Modelling
- Created a `Category_id` column to support matching category values between the order data and sales target tables.
- Established a relationship between the category identifiers.
- Examined the relationship between Order ID fields, noting that a new identifier was unnecessary where Order ID was already unique.

These relationships help organize the data for subsequent analysis.

## 📊 Key Learning Outcomes

Through this project, I gained practical experience in:

- Importing and preparing multiple datasets in Power BI.
- Using Power Query for data cleaning, text formatting, and data type conversion.
- Creating custom and conditional columns.
- Merging tables using common keys.
- Handling blank rows and evaluating duplicate records.
- Applying sorting, filtering, grouping, and aggregation.
- Creating basic DAX measures.
- Building relationships between tables for data modelling.
- Understanding the importance of data quality before analysis.

## 🚀 Conclusion

This project strengthened my foundational understanding of Power BI data preparation and modelling. It demonstrates how raw CSV datasets can be transformed into structured, analysis-ready tables through systematic cleaning, calculated columns, aggregation, and relationship creation.

The techniques learned in this exercise provide a foundation for developing interactive dashboards and performing more advanced business and sales analysis.

## 👤 Author

**Palaniappan**

Aspiring Data Analyst | Finance & MIS Professional

**Skills Practiced:** Power BI, Power Query, DAX Basics, Data Cleaning, Data Transformation, Data Aggregation, and Data Modelling.
