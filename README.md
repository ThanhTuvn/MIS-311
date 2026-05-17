# Assignment #2: Porfolio Site_ NAME: LE THANH TU_ IRN: 1832300420
## 1.	Data Overview:
The data is about the information on sales transactions at a supermarket. Which included: comprises branch, customer type, product category, sales volume, and total transaction value across different local supermarkets. 
This useful applications for analyzing customer purchasing behavior to improve the supermarket's future sales performance.

This dataset includes 253 rows and 8 columns of data. The variables include:

      • Sale_id (object): Unique identifier
      • Branch (object): Supermarket brand
      • City (object): Supermarket city
      • Customer_type (object): Customer type
      • Product_name (object): Product name
      • Product_category (object): Product category
      • Quantity (integer): Quantity sold
      • Total_price (real number): Total revenue in USD

## 2.	Data Cleaning:
<img width="400" height="167" alt="image" src="https://github.com/user-attachments/assets/726085f4-403c-4cf3-b1eb-8250dad4678a" />

 
This step are checking the data to identify missing or duplicate values before analyzing and building the table in subsequent steps. After checking, the result is that discovered 3 missing data points in the 'customer_type' field; 6 missing data points in the 'product_category' field and 3 missing data points in the 'quantity' field. In total, there are 12 missing values in this dataset. Additionally, we found 3 duplicate data rows, which have been removed.

Firstly, to address the missing values in the 'customer_type': to slove 3 out of 253 data points were missing values. According to the data table, it can be seen that the frequency of Member type customers (131) is higher than that of Regular type customers (119), so the Mode Imputation method was applied to clean up the missing data, which was replaced with "Member" to preserve the dataset size without significantly affecting the overall distribution.

Secondly, inconsistencies and value loss in the “'product_category'” were identified between product_name and product_category. For example: “shampoo” was inconsistently classified as both stationery, personal care, and household goods; “orange juice” was incorrectly classified as “household goods” instead of “beverages”; The term "detergent" was misclassified as "beverage" in some entries. Therefore, a new field, Cleaned_Product_Category, was created to ensure data integrity, which was designed for more logical classification so that each product fits its category according to the following rules: Apple: Fruits; Orange Juice: Beverages; Detergent: Household Shampoo; Personal Care Notebook: Stationery.

=> Applied the excel function: =IFS(E3="Apple","Fruits", E3="Orange Juice","Beverages", E3="Detergent","Household", E3="Shampoo","Personal Care", E3="Notebook","Stationery") to automate classification this process. This helped to make the classification data more consistent and logistic. Thirdly, three values were missing in the "quality", which should be represented as integers in a supermarket retail context. This is because the quantity should represent the units of goods sold.

=> A median value method had to be applied. The values selected to fill these gaps were replaced with 11, with all missing records being replaced by the value 11. The reason because the consistency of integers must be ensured. The average value of the dataset is approximately 10.6, using this value would result in non-integer entries (e.g., 10.6 units), which is inconsistent with retail practices where products are sold in whole units. In summary, cleaning data step helps to avoid a single transaction being counted multiple times and 239 unique values remaining after data cleaning. Moreover, the missing figures were discovered in the data that needed cleaning because columns and rows with missing information would negative affect other items such as quantity or total_price. This steps will help produce more accurate output based on complete and reliable transactions and ready for descriptive statistics and correlation analysis, if any, in subsequent steps.

## 3.	Descriptive Statistics:


<img width="955" height="492" alt="image" src="https://github.com/user-attachments/assets/7a588a2e-33e6-4008-ba45-b48a5b98d324" />

 
#### •	Quantity:
    o	Mean: 10.616
    o	Standard Error: 0.378904275
    o	Median: 11
    o	Mode: 2
    o	Standard Deviation: 5.991002625
    o	Sample Variance: 35.89211245
    o	Kurtosis: -1.258270857
    o	Skewness: -0.072603433
    o	Range: 19
    o	Minimum: 1
    o	Maximum: 20
    o	Sum: 2654
    o	Count: 250
#### •	Total price:
    o	Mean: 124.18512
    o	Standard Error: 6.513332297
    o	Median: 95.43
    o	Mode: 212.82
    o	Standard Deviation: 102.9848261
    o	Sample Variance: 10605.8744
    o	Kurtosis: 0.05172233
    o	Skewness: 0.913516111
    o	Range: 424.96
    o	Minimum: 2.18
    o	Maximum: 427.14
    o	Sum: 31046.28
    o	Count: 250
#### •	Revenue
    o	Mean: 1761.784
    o	Standard Error: 123.7544
    o	Median: 1065.185
    o	Mode: #N/A
    o	Standard Deviation: 1956.729
    o	Sample Variance: 3828790
    o	Kurtosis: 1.261353
    o	Skewness: 1.350208
    o	Range: 8538.44
    o	Minimum: 4.36
    o	Maximum: 8542.8
    o	Sum: 440445.9
    o	Count: 250
What's unusual is that the revenue section has a #N/A mode, meaning there's no "most frequently appearing" value. More specifically, the mode reflects the value that appears with the highest frequency. And in Revenue, all values are unique; no value is repeated, so the Revenue mode is N/A. This isn't an error, but a normal occurrence when processing revenue data.
### 3.1 Comparison of Total Revenue and Total Sales Value by City


  <img width="273" height="74" alt="image" src="https://github.com/user-attachments/assets/f2d91e1f-16b4-44bb-855a-b08dbfa630cf" />

<img width="559" height="373" alt="image" src="https://github.com/user-attachments/assets/7a7f8413-cfe0-4589-9b9e-68fbefe54223" />

The bart chart compares the total sales value of supermarkets with total revenue across three cities Chicago, Los Angeles and New York.

#### Data analysis: 
It can clearly seen that Chicago has the highest revenue about $166,484.58.The amount of money in New York’s revenue is next with $148,536.85.Finally, Los Angeles has the lowest revenue among the three cities, at $125,424.50. 
The next term that is Total price. At frist Chicago also has the highest sales value at approximately $11,133.05, slightly higher than New York ($10,964.42) and Los Angeles ($8,948.81). This suggests a trend that cities with better total revenue tend to have higher sales.
#### Insight 1:
Customer demand is stronger and transactions are more frequent in Chicago. Therefore, supermarkets should invest more in this location, considering marketing campaigns and ensuring a good supply of goods and programs for customers in Chicago to increase revenue, instead of focusing on less-consumer locations.
#### Insight 2:
On the other hand, Los Angeles is a profit-friendly market in terms of sales prices and revenue. Therefore, supermarkets need to improve promotional activities, diversify products, or understand customer data in this market to increase economic revenue.
### 3.2 The Sum of Revenue by customer type

 <img width="253" height="70" alt="image" src="https://github.com/user-attachments/assets/888cfb2c-302c-4d64-bf92-69505c960781" />

<img width="559" height="373" alt="image" src="https://github.com/user-attachments/assets/e9aa75cf-c1b6-4df5-8152-d4716e98b18c" />

   
The two bar chart presented about compares the sum of revenue value between Member and Normal customers.

#### Data analysis: Membership customers generate higher revenue than regular customers (approximately $261 > $179), and the total revenue of both customer types across the entire supermarket reached approximately $440,445.93. This is because membership customers more frequently and have higher spending levels by effect of exclusive loyalty programs.

#### Insight: This result shows that Member customers tend to spend more per transaction than Normal customers. It can be seen that the loyalty program, with its attractive offers or higher level of engagement, has brought clear economic value, which encourages higher spending behavior at the supermarket. Therefore, supermarkets should continue to develop member benefits, focusing on marketing strategies targeting "regular" customers to upgrade them to "members," and promotional programs aimed at increasing customer loyalty and improving overall revenue. This would be the most effective solution for rapid and sustainable long-term revenue growth.

### 3.3. Revenue Distribution by Product Category Analysis

   <img width="194" height="89" alt="image" src="https://github.com/user-attachments/assets/b4c6bac4-e3bc-4da3-a5e3-3174260b1a85" />

<img width="656" height="295" alt="image" src="https://github.com/user-attachments/assets/862a7792-2b98-4b93-92a9-c3f6539509e7" />

The graph indicates the total revenue of 5 product categories in the supermarket.

Data analysis:  it is clear from the chart that among 5 business categories, Fruits generated the highest revenue (approximately $6,463.17), followed by Stationery and Beverages, ranking respectively. Finally, the lowest revenue was Personal Care category ($4,598.06).

Insight: The results show that Fruits are the supermarket's main "attractive" items with high demand (a core category), contributing the most to the supermarket's cash flow. Soo the supermarket should maintain appropriate inventory levels and implement promotional programs for well-performing product groups such as Fruits and Stationery. In the other hand,the Personal Care product group has a lower average order value, suggesting that the supermarket needs to reconsider its pricing strategy or enhance combo packages for this category to increase the value of the shopping cart and improve sales.

