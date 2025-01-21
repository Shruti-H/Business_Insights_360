## Project Overview

AtliQ Hardware, a growing consumer electronics company, encountered significant losses in Latin America due to reliance on surveys and intuition for expansion decisions. Their Excel-based analytics system proved inadequate for handling the increasing volume of data, resulting in poor decision-making. To stay competitive and enable better strategic decisions, AtliQ Hardware decided to embrace data analytics and replace Excel with more advanced tools.
This project is part of the Get Job Ready: Power BI Data Analytics for All Levels 3.0 course cum certification program from Codebasics, where I gained hands-on experience with Power BI and data analytics concepts. It aims to provide actionable insights for stakeholders across various dimensions, including finance, sales, marketing, supply chain, and executive decision-making.
### Objectives 
AtliQ wants to make data-driven decision-making a part of their work culture and is taking their first big step towards that by embedding a Power BI tool in the organization. The key objectives of this project are:
- Implement data analytics and provide actionable insights.
- Use Power BI to enable data-driven decision-making across AtliQ's operations.
- Enable quick insights for business across markets to drive strategic decisions.
### Data Sources

- **MySQL Database: gdb041**  
  Extracted data about customers, markets, products, monthly sales, and forecast data. Below are some important details about the tables present in this database:
  
  - **dim_customer**: Contains data about AtliQ’s customers such as their code, name, market, platform, and channel.  
    - 27 distinct markets (e.g., India, USA, Spain, etc.)  
    - 75 distinct customers (e.g., Walmart, BestBuy, Amazon, AtliQ Exclusive, etc.)  
    - 2 distinct platforms (Brick & Mortar, E-commerce)  
    - 3 distinct channels (Retailer, Direct, and Distributor)  

  - **dim_market**: Contains data about markets.  
    - 27 distinct markets  
    - 7 distinct sub-zones (e.g., LATAM, NE, etc.)  
    - 4 distinct regions (e.g., EU, APAC, etc.)  

  - **dim_product**: Contains data about products produced and sold by AtliQ such as their name, code, division, segment, category, product (name), and variant.  
    - 397 distinct products  
    - 3 distinct divisions (PC, N & S, P & A)  
    - 6 distinct segments (Peripherals, Accessories, Notebook, etc.)  
    - 14 distinct categories (Processors, MotherBoard, Mouse, etc.)  

  - **fact_sales_monthly**: Actual monthly sales data containing date, product details, customer details, and sold quantity. Data spans from 2017-09-01 to 2021-12-01.

  - **fact_forecast_monthly**: Similar to **fact_sales_monthly** but with forecast quantity instead of sold quantity. Data spans from 2017-09-01 to 2022-08-01.

- **MySQL Database: gdb056**  
  Extracted data about freight cost, gross price, manufacturing cost, post-invoice deductions, and pre-invoice deductions. Below are some important details about the tables present in this database:
  
  - **freight_cost**: Contains data about freight cost and other costs in percentage for markets in each fiscal year.
  
  - **gross_price**: Contains data about the gross price of each product in each fiscal year.
  
  - **manufacturing_cost**: Contains data about the manufacturing cost of each product in each fiscal year.
  
  - **post_invoice_deductions**: Contains data about discounts and other deductions in percentage.
  
  - **pre_invoice_deductions**: Contains pre-invoice deduction percentages for each customer in each fiscal year.
- **Other data sources:**  
  - **Excel file**: Extracted market share data, operational expenses and targets data.
  - **Operating-expenses-table-1.xlsx** : contains data about different operating expenses for markets in different fiscal years( such as ads/promotions and some other operational expenses in percentage)
  - **marketshare-v2022.xlsx**: contains market share data for AtliQ and its competitors for different category of products in different sub zones and fiscal year
  - **Targets.xlsx** : contains monthly Net Sales, Gross Margin and Net Profit targets for different markets. 

  **Note:** The fiscal year for AtliQ begins in September.
### Data Model
The data model for this Power BI project follows a **Hybrid Schema** that combines elements of both **Star** and **Snowflake** schemas. The core of the model is structured in a **Star Schema** for simplicity and efficient querying, while some of the dimension tables are further normalized in a **Snowflake Schema** to maintain data integrity and reduce redundancy.

Below is the visual representation of the data model in Power BI:

<img width="647" alt="Image" src="https://github.com/user-attachments/assets/b716fbbf-5a23-409e-b83c-ed3f375ecc81" />

### Data Transformation

In this section, I outline the key data transformation techniques I learnt and applied throughout the project. The transformations were crucial for cleaning, structuring, and enriching the data to enable actionable insights through Power BI.

#### Techniques learnt:
- **DAX Measures**: 
  - Created various DAX measures to calculate key business metrics, such as Net Sales, Gross Margin, Net Profit and other P & L values.
  
- **Calculated Columns**: 
  - Used DAX to create calculated columns, like gross_sales_amount,net_sales_amount etc to enhance the data model and support detailed analysis.
  
- **Creating Tables**:
  - Used DAX and PowerQuery to create new tables such as fiscal_year, dim_date table.
  
- **Merging and Appending Data**:
  - Merged and appended tables to consolidate information for analysis.
  
- **Data Cleaning**:
  - Performed basic data cleaning tasks such as correcting data types, removing trailing spaces, and standardizing spellings.
  

- **Pivoting and Unpivoting Data**:
  - Unpivoted columns of market share data in Power Query to calculate sales amount for each manufacturer

### Visualizations

The following dashboards were created in the final Power BI report to present insights clearly and effectively:

- **Home Page**: A landing page that provides a brief introduction to all the other pages. Users can click on buttons to navigate to each corresponding visual.
 <img width="666" alt="Image" src="https://github.com/user-attachments/assets/5b2664c9-2ef1-4dd2-ae38-98ceb926649f" />
  
- **Finance View**: 
  - Displays the overall P&L statement in a **matrix**.
  - Highlights top products and customers based on P&L values using a matrix.
  - Includes an **Area chart** to compare P&L values for the selected year against benchmark values (previous year values or target values).
 <img width="674" alt="Image" src="https://github.com/user-attachments/assets/1a342aa6-8326-4bb4-9c2d-e4a9ad078210" />
  
- **Sales View**:
  - A **Scatter plot** showing the performance matrix for markets and customers.
  - **Donut charts** displaying the breakdown of Net Sales and Gross Margin.
  - A matrix presenting product performance.
 <img width="673" alt="Image" src="https://github.com/user-attachments/assets/6c46cd9a-ea08-4727-b5a0-1a6b208e1dc1" />

- **Marketing View**:
  - Matrix visuals showing region, market, customer, and product performance.
  - A **Waterfall chart** comparing Gross Margin, Operational Expenses, and Net Profit.
 <img width="670" alt="Image" src="https://github.com/user-attachments/assets/faadd302-09c3-48e7-8820-52d3998c9f3d" />

- **Supply Chain View**:
  - **Line and Clustered Column charts** displaying forecast accuracy and Net Error trends.
  - Matrix visuals presenting key metrics by product and customer.
 <img width="675" alt="Image" src="https://github.com/user-attachments/assets/8c7e514c-0d62-43a5-9f89-d72850b9b604" />

- **Executive View**: 
  - A **100% Stacked Bar chart** showing revenue by division and channel.
  - A **Line and Clustered Column chart** displaying revenue, Gross Margin %, Net Profit %, and PC Market Share % for AtliQ.
  - A **Ribbon chart** illustrating Market Share trends for AtliQ and its competitors.
  - A **table** showing key metrics by sub-zone.
  - **Matrices** displaying the top 5 products and customers by revenue.
 <img width="677" alt="Image" src="https://github.com/user-attachments/assets/c8aa551a-7104-41de-bd74-b407f25e5d51" />
 
**Other Visuals and Techniques Learned**:
- Creating slicers for filtering and selection.
- Using **Card** visual to display KPIs.
- Adding buttons, page navigators, and bookmarks to toggle between visuals.
- Designing tooltips for additional insights.
- Creating and utilizing field parameters for dynamic data selection.

These transformations and visualizations helped convert raw data into actionable insights, enabling data-driven decisions at AtliQ Hardware.

### Key Learnings and Techniques
- Gained hands-on experience with advanced Power BI functionalities like **DAX**, **Power Query**, and **Data Modeling**.
- Learned how to create **interactive dashboards** that provide stakeholders with actionable insights.
- Improved skills in transforming raw data into meaningful metrics using **measures** and **calculated columns**.
- Mastered data transformation and cleansing techniques like **data type conversion**, **text manipulation**, and **removal of white spaces**.
### Conclusion
This Power BI project transformed AtliQ Hardware's data into actionable insights across multiple departments. By leveraging the capabilities of Power BI, I was able to provide stakeholders with interactive dashboards and detailed visualizations that support data-driven decisions, enhancing the overall business performance.






