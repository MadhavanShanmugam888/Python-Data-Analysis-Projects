Project: Amazon Electronics Sales Analysis
This project performs a comprehensive Data Analysis on Amazon Electronics sales data. The goal is to understand customer satisfaction, product popularity, and category performance to provide actionable business insights.

Project Overview
The analysis explores user ratings, product categories, and temporal trends in the electronics market. By cleaning and visualizing the dataset, we identify high-demand items, customer sentiment trends, and specific products that require quality improvements.

Dataset Information
The dataset contains information about various electronics items sold on Amazon, including:

User Ratings: Customer scores ranging from 1 to 5.

Product Categories: Groups like Laptops, Cameras, Phones, etc.

Timestamps: Sale dates used for time-series analysis.

Brand & User Attributes: Metadata for deeper segmentation.

Source: Kaggle - Electronics Dataset

Tech Stack
Language: Python

Libraries:

Pandas: Data manipulation and cleaning.

NumPy: Numerical operations.

Matplotlib & Seaborn: Statistical data visualization.

Key Analysis & Workflow
1. Data Cleaning & Preprocessing
Missing Value Treatment: Standardized missing brand and user attributes as "Unknown".

Data Formatting: Converted timestamps to datetime objects and extracted features like Month and Year.

Integrity Checks: Removed duplicates and validated rating ranges (1-5).

Exporting Clean Data: Saved the processed dataset as Electronics_Cleaned.csv for further reporting.

2. Exploratory Data Analysis (EDA)
Rating Distribution: Analyzed the spread of customer satisfaction across all products.

Category Performance: Evaluated which product categories drive the highest engagement and ratings.

Trend Analysis: Investigated how sales and ratings fluctuate over different months and years.

3. Business Insights
Customer Satisfaction: The overall average product rating is 4.05, indicating high general satisfaction.

Product Popularity: Identified "Hero Products" that have both high review volumes and high ratings.

Quality Alert: Highlighted popular products with consistently low ratings, signaling an urgent need for quality control or feature updates.

Business Summary
Promote Heavily: Products that are both popular and highly rated are prime candidates for marketing campaigns.

Fix Urgently: High-volume products with poor ratings represent a risk to brand reputation and should be prioritized for quality improvements.

Author
Madhavan Shanmugam Data Analyst | Python | Power BI | SQL | Advanced Excel

How to Run
Ensure you have Python installed.

Install dependencies: pip install pandas matplotlib seaborn.

Place electronics.csv in the project directory.

Run the Jupyter Notebook: Interactive - Product_Sales.py.ipynb.
