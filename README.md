# 📊 Amazon Electronics Sales Analysis

## 📌 Project Overview

This project analyzes electronics sales data using **Python, Pandas, NumPy, Matplotlib, and Seaborn** to identify sales trends, product performance, customer purchasing behavior, and business opportunities.

The project follows a complete **Exploratory Data Analysis (EDA)** workflow, including data cleaning, transformation, statistical analysis, visualization, and business insight generation.

> **Dataset Note:** The dataset used in this project is synthetic/practice data created for learning and portfolio purposes. It is not official Amazon internal sales data.

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Analyze overall electronics sales performance
* Identify the highest-performing product categories
* Analyze monthly sales trends
* Compare regional sales performance
* Identify the top-performing products
* Understand customer purchasing behavior
* Analyze customer ratings
* Analyze payment-method preferences
* Study the relationship between discounts and sales
* Generate actionable business insights

---

## 🛠️ Technologies Used

| Technology           | Purpose                                   |
| -------------------- | ----------------------------------------- |
| **Python**           | Data analysis and programming             |
| **Pandas**           | Data cleaning, manipulation, and analysis |
| **NumPy**            | Numerical calculations                    |
| **Matplotlib**       | Data visualization                        |
| **Seaborn**          | Statistical visualization                 |
| **Jupyter Notebook** | Interactive analysis                      |
| **Excel**            | Dataset inspection and reporting          |
| **GitHub**           | Project version control and portfolio     |

---

## 📂 Project Structure

```text
amazon-electronics-sales-analysis/
│
├── data/
│   ├── amazon_electronics_sales.csv
│   ├── amazon_electronics_sales.xlsx
│   └── category_performance_summary.xlsx
│
├── notebooks/
│   └── amazon_electronics_sales_analysis.ipynb
│
├── visuals/
│   ├── sales_by_category.png
│   ├── monthly_sales_trend.png
│   ├── sales_by_region.png
│   ├── top_10_products.png
│   ├── customer_rating_distribution.png
│   ├── rating_vs_sales.png
│   ├── payment_method_analysis.png
│   ├── discount_vs_sales.png
│   └── quantity_by_category.png
│
├── README.md
└── requirements.txt
```

---

## 📊 Dataset

The dataset contains **2,500 electronics sales transactions**.

### Main Variables

| Column                 | Description               |
| ---------------------- | ------------------------- |
| `Order_ID`             | Unique order identifier   |
| `Order_Date`           | Date of the order         |
| `Region`               | Customer region           |
| `Category`             | Product category          |
| `Product`              | Product name              |
| `Unit_Price_INR`       | Original product price    |
| `Discount_Percent`     | Discount applied          |
| `Quantity`             | Number of units purchased |
| `Customer_Rating`      | Customer rating           |
| `Review_Count`         | Number of product reviews |
| `Payment_Method`       | Payment method used       |
| `Delivery_Time`        | Delivery duration         |
| `Discounted_Price_INR` | Price after discount      |
| `Sales_INR`            | Total transaction sales   |
| `Month`                | Order month               |
| `Month_Number`         | Numerical month           |

---

# 🔍 Analysis Process

## 1. Data Loading

The dataset was imported using Pandas:

```python
df = pd.read_csv("../data/amazon_electronics_sales.csv")
```

The dataset was then inspected using:

```python
df.head()
df.shape
df.columns
df.info()
df.describe()
```

---

## 2. Data Cleaning

The following preprocessing tasks were performed:

* Checked missing values
* Checked duplicate records
* Converted `Order_Date` into datetime format
* Handled missing customer ratings using the median
* Handled missing payment methods using the mode
* Verified the cleaned dataset

Example:

```python
df["Order_Date"] = pd.to_datetime(df["Order_Date"])

df["Customer_Rating"] = df["Customer_Rating"].fillna(
    df["Customer_Rating"].median()
)

df["Payment_Method"] = df["Payment_Method"].fillna(
    df["Payment_Method"].mode()[0]
)
```

---

# 📈 Exploratory Data Analysis

## Category Performance

The analysis found that **Laptops** were the highest-revenue category.

| Category    | Total Sales (INR) | Quantity | Avg. Rating | Orders |
| ----------- | ----------------: | -------: | ----------: | -----: |
| Laptops     |       ₹66,933,292 |    1,097 |        4.06 |    617 |
| Smartphones |       ₹51,610,268 |    1,173 |        4.09 |    674 |
| Monitors    |       ₹15,946,128 |      565 |        4.13 |    310 |
| Headphones  |       ₹12,292,342 |      943 |        4.09 |    514 |
| Accessories |        ₹2,843,750 |      680 |        4.10 |    385 |

### Key Findings

* **Laptops** generated the highest revenue at approximately **₹66.9 million**.
* **Smartphones** generated approximately **₹51.6 million** in sales.
* Smartphones had the highest number of orders (**674**).
* Smartphones also recorded the highest quantity sold (**1,173 units**).
* **Monitors** achieved the highest average customer rating at approximately **4.13/5**.
* Average discounts remained close to **15%** across categories.
* Accessories generated the lowest revenue, although they still contributed a significant number of transactions.

---

## 📅 Monthly Sales Analysis

Monthly sales were analyzed to identify:

* Peak sales periods
* Low-performing months
* Seasonal sales patterns
* Potential opportunities for promotional campaigns

A line chart was created to visualize the monthly sales trend.

---

## 🌎 Regional Sales Analysis

Sales were grouped by region to compare regional performance.

This analysis helps identify:

* High-performing markets
* Lower-performing regions
* Potential regional expansion opportunities
* Areas where marketing efforts could be increased

---

## 🏆 Top 10 Products

Products were ranked according to total sales.

This analysis helps identify products that could receive:

* Higher inventory priority
* Increased marketing exposure
* Promotional campaigns
* Cross-selling opportunities

---

## ⭐ Customer Rating Analysis

Customer ratings were analyzed using:

* Rating distribution
* Rating vs. sales scatter plot
* Correlation analysis

The correlation between customer ratings and sales was calculated using:

```python
df["Customer_Rating"].corr(df["Sales_INR"])
```

> Correlation indicates the strength of a linear relationship but does not establish causation.

---

## 💳 Payment Method Analysis

Customer payment preferences were analyzed by counting orders for each payment method.

This helps understand customer preferences and can support decisions related to:

* Payment options
* Checkout experience
* Digital payment adoption
* Customer convenience

---

## 🏷️ Discount Analysis

The relationship between discount percentage and sales was investigated using a scatter plot and correlation analysis.

```python
df["Discount_Percent"].corr(df["Sales_INR"])
```

This analysis helps evaluate whether higher discounts are associated with higher transaction sales.

> The correlation analysis should not be interpreted as proof that discounts directly cause higher sales.

---

# 📊 Visualizations

The project includes the following visualizations:

1. **Sales by Product Category**
2. **Monthly Sales Trend**
3. **Sales by Region**
4. **Top 10 Products by Sales**
5. **Customer Rating Distribution**
6. **Customer Rating vs. Sales**
7. **Orders by Payment Method**
8. **Discount Percentage vs. Sales**
9. **Quantity Sold by Category**

These visualizations were created using **Matplotlib and Seaborn**.

---

# 💡 Key Business Insights

Based on the analysis:

### 1. Laptops are the strongest revenue category

Laptops generated approximately **₹66.9 million**, making them the highest-revenue product category.

### 2. Smartphones show strong customer demand

Smartphones had the highest number of orders and the highest total quantity sold, indicating strong purchasing demand.

### 3. Monitors have the highest average rating

Monitors achieved an average rating of approximately **4.13/5**, indicating strong customer satisfaction.

### 4. Accessories have lower revenue

Accessories generated approximately **₹2.84 million**, making them the lowest-revenue category. However, they may provide opportunities for cross-selling with higher-value electronics.

### 5. Discounts are relatively consistent

Average discounts across categories were approximately **15%**, indicating a relatively consistent discounting strategy.

---

# 📌 Business Recommendations

Based on the findings, the following recommendations can be considered:

* Prioritize inventory planning for **laptops and smartphones**.
* Use high-performing products in targeted marketing campaigns.
* Explore cross-selling opportunities for **accessories**.
* Maintain strong product quality for highly rated categories such as monitors.
* Analyze peak sales months before planning promotional campaigns.
* Evaluate discount strategies using additional metrics such as profit margin and conversion rate.
* Monitor regional performance to identify markets with growth potential.

---

# 🚀 Skills Demonstrated

This project demonstrates practical skills in:

* Python programming
* Pandas
* NumPy
* Data cleaning
* Exploratory Data Analysis
* Data aggregation
* GroupBy operations
* Feature engineering
* Statistical analysis
* Correlation analysis
* Data visualization
* Business analysis
* Insight generation
* GitHub project organization

---

# ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the project

```bash
cd amazon-electronics-sales-analysis
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
notebooks/amazon_electronics_sales_analysis.ipynb
```

### 5. Run the notebook

Run the cells sequentially to reproduce the analysis and visualizations.

---

# 📚 Future Improvements

Possible improvements for a future version include:

* Build an interactive **Power BI dashboard**
* Add profit and profit-margin analysis
* Perform customer segmentation
* Analyze delivery performance
* Build sales forecasting models
* Perform statistical hypothesis testing
* Add interactive filters
* Develop machine-learning models for sales prediction

---

# 👨‍💻 Author

**Darshan Maurya**

B.Tech — Computer Science & Engineering

### Areas of Interest

* Data Analytics
* Business Intelligence
* Python
* SQL
* Power BI
* Excel
* Data Visualization

---

## ⭐ Project Objective

The goal of this project is to demonstrate how **Python-based data analysis can transform raw sales data into meaningful business insights and actionable recommendations.**
