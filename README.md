# Toy Sales Data Analysis: Optimal Store Locations

## Project Overview

This project aims to identify the best possible locations to open new toy stores based on sales data analysis. The dataset includes sales information from various stores across different cities and locations, with the goal of predicting sales for potential new store locations to maximize revenue.

## Datasets

The dataset includes the following files:
- `inventory_data`
- `sales_data`
- `stores_data`
- `products_data`

## Schema

<img width="564" alt="Screenshot 2024-07-24 123004" src="https://github.com/user-attachments/assets/017cda08-c8ea-4843-9504-de0a3c3a9a15">

### Store Locations

Each city can have four types of store locations:
- Residential
- Commercial
- Downtown
- Airport

Currently, there are 50 stores, but the total number of possible store locations is 116 (29 cities * 4 locations).

## Project Steps

### 1. Data Merging
- **Merge Data Files**: Combined `inventory_data`, `sales_data`, `stores_data`, and `products_data` into a single DataFrame for analysis.

### 2. Data Cleaning
- **Identify Missing Values**: Checked for missing values in the dataset.
- **Remove Rows with Zero Stock**: Improved dataset quality by removing rows where stock on hand was zero.
- **Remove Special Characters and Convert to Numeric**: Removed "$" and spaces from `Product_Price` and `Product_Cost` columns to ensure accurate calculations.

### 3. Outlier Treatment
- **Normalize Product Cost**:
  - Calculated mean, standard deviation, and range for `Product_Cost`.
  - Applied L2 normalization to scale the `Product_Cost` values.
  - Added a new column `Product_Cost_Normalized` to the dataset.
- **Normalize Product Price**:
  - Calculated mean, standard deviation, and range for `Product_Price`.
  - Applied L2 normalization to scale the `Product_Price` values.
  - Added a new column `Product_Price_Normalized` to the dataset.
- **Normalize Units**:
  - Calculated mean, standard deviation, and range for `Units`.
  - Applied L2 normalization to scale the `Units` values.
  - Added a new column `Units_Normalized` to the dataset.

### 4. Feature Engineering
- **Month Column**: Extracted the month from the `Date` column and created a new column `Month`.
- **Sales Column**: Calculated `Sales` by multiplying `Units` and `Product_Price`, and added a new column `Sales`.

### 5. Univariate Analysis
- **Product Price Analysis**: Visualized the distribution of `Product_Price` using a boxplot.
- **Categorical Features**:
  - **Product Categories**: Analyzed unique product categories and aggregated sales data by category.
  - **Units Sold per Category**: Counted the number of units sold per product category.
  - **Average Sales per Category**: Calculated average sales for each product category.
  - **Total Sales per Category**: Calculated total sales for each product category.
  - **Visualizations**: Created bar plots to show average and total sales per product category.
- **Product Names**: Analyzed the uniqueness and distribution of `Product_Name`.
- **Store Locations**: Analyzed average sales at each store location and visualized it using a barplot.

### 6. Bivariate Analysis
- **Correlation Analysis**:
  - **Sales & Product Price**: Calculated Pearson correlation between `Sales` and `Product_Price`.
  - **Sales & Product Cost**: Calculated Pearson correlation between `Sales` and `Product_Cost`.
  - **Sales & Stock on Hand**: Calculated Pearson correlation between `Sales` and `Stock_On_Hand`.
  - **Sales & Month**: Calculated Pearson correlation between `Sales` and `Month`.
  - **Correlation Matrix**: Created a correlation matrix for `Units`, `Month`, `Stock_On_Hand`, and `Product_Price`, and visualized it using a heatmap and bar plots.
  
### 7. Hypothesis Testing
- **Correlation Between Stock on Hand and Sales Volume**:
  - Null Hypothesis: There is a strong correlation between Stock on Hand and Sales Volume.
  - Alternate Hypothesis: There is no strong correlation between Stock on Hand and Sales Volume.
  - Conclusion: No strong correlation found.
- **Influence of Store Location on Sales**:
  - Null Hypothesis: Store Location has a strong influence on Sales.
  - Alternate Hypothesis: Store Location does not have a strong influence on Sales.
  - Conclusion: Significant difference found using Kruskal-Wallis test.

### 8. Multiple Linear Regression Model
- **Feature Selection**: Selected relevant features for prediction.
- **Label Encoding**: Applied to categorical features.
- **Model Building**: Created a pipeline for encoding categorical variables and fitting the model.
- **Prediction Function**: Developed a function to predict sales for new city-location combinations.
- **Identify Missing Combinations**: Found city-location pairs not present in the data and predicted sales for these combinations.

### 9. Results Analysis
- **Predicted Sales for New Locations**: Calculated and compared predicted sales for new locations.
- **Visualizations**: Created bar charts to compare existing and predicted sales, focusing on top city-location combinations.

## Key Findings

- There is no strong correlation between Stock on Hand and Sales Volume.
- Store location has a significant impact on sales.
- Identified potential new store locations with high predicted sales increases.
- Visualized the comparison between existing and predicted sales for top city-location combinations.
- Univariate analysis shows that Toys category has the highest units sold and total sales, while Electronics has the highest average sales.
- Bivariate analysis reveals significant correlations between Sales and Product Cost and Price, while Stock on Hand and Month have lesser impacts.

## Contact

If you have any questions or would like to discuss any of the dashboards in more detail, feel free to reach out to me at [LinkedIn](https://www.linkedin.com/in/gagansays/).

---

Thank you for visiting this repository. I hope you find these dashboards informative and insightful!
