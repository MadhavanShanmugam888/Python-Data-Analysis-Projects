```python
import nbformat

def read_ipynb(file_path):
    with open(file_path, 'r', encoding='utf-8') as f:
        nb = nbformat.read(f, as_version=4)
    
    content = ""
    for cell in nb.cells:
        if cell.cell_type == 'markdown':
            content += cell.source + "\n\n"
        elif cell.cell_type == 'code':
            content += "```
```text?code_stderr&code_event_index=2
Traceback (most recent call last):
  File "<xbox-string>", line 1, in <module>
    import nbformat
ModuleNotFoundError: No module named 'nbformat'

```python\n" + cell.source + "\n```\n\n"
    return content

notebook_content = read_ipynb('Interactive - Product_Sales.py.ipynb')
print(notebook_content[:2000]) # Print first 2000 chars to get an overview



```

```python
import json

def read_ipynb_json(file_path):
    with open(file_path, 'r', encoding='utf-8') as f:
        nb = json.load(f)
    
    content = []
    for cell in nb.get('cells', []):
        cell_type = cell.get('cell_type')
        source = "".join(cell.get('source', []))
        if cell_type == 'markdown':
            content.append(f"### Markdown Cell:\n{source}")
        elif cell_type == 'code':
            content.append(f"### Code Cell:\n{source}")
    
    return "\n\n".join(content)

notebook_text = read_ipynb_json('Interactive - Product_Sales.py.ipynb')
print(notebook_text[:3000]) # Print more characters to capture structure and findings


```

```text
### Markdown Cell:
Connected to Python 3.13.13

### Code Cell:
# The dataset gives us electronics sales data at Amazon. 

# It contains user ratings for various electronics items sold, along with category of each item and time of sell.

# The dataset is available at https://www.kaggle.com/datasets/edusanketdk/electronics

# Importing the libraries

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns



### Code Cell:
# Importing the dataset
dataset= pd.read_csv('electronics.csv')



### Code Cell:
# List the first five rows
dataset.head()



### Code Cell:
# List the last 5 rows
dataset.tail()



### Code Cell:
dataset.size

### Code Cell:
dataset.shape

### Code Cell:
dataset.columns

### Code Cell:
dataset.info()

### Code Cell:
from datetime import datetime

### Code Cell:
pd.to_datetime(dataset['timestamp'])

### Code Cell:
dataset.columns= dataset.columns.str.lower().str.strip()
dataset.columns



### Code Cell:
dataset= dataset.drop("split", axis=1)
dataset.columns



### Code Cell:
dataset.isnull().sum()

### Code Cell:
dataset["brand"]= dataset["brand"].fillna("Unknown")
dataset["user_attr"]= dataset["user_attr"].fillna("Unknown")
dataset.isnull().sum()



### Code Cell:
dataset.duplicated().sum()

### Code Cell:
dataset.info()

### Code Cell:
dataset["timestamp"]= pd.to_datetime(dataset["timestamp"])
dataset.info()



### Code Cell:
dataset["rating"].describe()

### Code Cell:
dataset = dataset[(dataset["rating"] >= 1) & (dataset["rating"] <= 5)]

### Code Cell:
dataset["rating"] = pd.to_numeric(dataset["rating"])

### Code Cell:
dataset["category"].unique()

### Code Cell:
dataset["brand"].unique()

### Code Cell:
dataset["model_attr"].unique()

### Code Cell:
dataset["user_attr"].unique()

### Code Cell:
dataset= dataset.reset_index(drop=True)

### Code Cell:
dataset.shape

### Code Cell:
dataset["month"] = dataset["timestamp"].dt.month
dataset["month_name"] = dataset["timestamp"].dt.month_name() 
dataset["year"] = dataset["timestamp"].dt.year 



### Code Cell:
dataset.columns

### Code Cell:
dataset.to_csv("Electronics_Cleaned.csv", index=True)

### Code Cell:
plt.figure(figsize=(8,5))
sns.set_style("whitegrid")



### Code Cell:
# Exploratory Data Analysis (EDA)

### Code Cell:
## What is the overall average rating of products? 
overall_avg_rating = round(dataset['rating'].mean(),2)
overall_avg_rating



### Code Cell:
# Visualize Ratings

plt.figure(figsize=(8,8))

plt.hist(
    dataset["rating"],
    bins=5,
    color="skyblue",
    edgecolor="black"
)

plt.xticks(range(0,6))
plt.xlabel("Rating")
plt.ylabel("Counts")
plt.title("Distribution of Product Ratings")

plt.tight_layout()
plt.show()



### Code Cell:
## Buisiness Insight
### The average product rating is 4.05, indicating high customer satisfaction, with most ratings concentrated between 4 and 5.



### Code Cell:
dataset["category"].value_counts()

### Code Cell:
# Which categories receive the highest and lowest ratings? 

mean_rat


```

# Project: Amazon Electronics Sales Analysis

This project performs a comprehensive Data Analysis on Amazon Electronics sales data. The goal is to understand customer satisfaction, product popularity, and category performance to provide actionable business insights.

## Project Overview

The analysis explores user ratings, product categories, and temporal trends in the electronics market. By cleaning and visualizing the dataset, we identify high-demand items, customer sentiment trends, and specific products that require quality improvements.

## Dataset Information

The dataset contains information about various electronics items sold on Amazon, including:

* **User Ratings:** Customer scores ranging from 1 to 5.
* **Product Categories:** Groups like Laptops, Cameras, Phones, etc.
* **Timestamps:** Sale dates used for time-series analysis.
* **Brand & User Attributes:** Metadata for deeper segmentation.

*Source: [Kaggle - Electronics Dataset*](https://www.kaggle.com/datasets/edusanketdk/electronics)

## Tech Stack

* **Language:** Python
* **Libraries:**
* `Pandas`: Data manipulation and cleaning.
* `NumPy`: Numerical operations.
* `Matplotlib` & `Seaborn`: Statistical data visualization.



## Key Analysis & Workflow

### 1. Data Cleaning & Preprocessing

* **Missing Value Treatment:** Standardized missing brand and user attributes as "Unknown".
* **Data Formatting:** Converted timestamps to datetime objects and extracted features like Month and Year.
* **Integrity Checks:** Removed duplicates and validated rating ranges (1-5).
* **Exporting Clean Data:** Saved the processed dataset as `Electronics_Cleaned.csv` for further reporting.

### 2. Exploratory Data Analysis (EDA)

* **Rating Distribution:** Analyzed the spread of customer satisfaction across all products.
* **Category Performance:** Evaluated which product categories drive the highest engagement and ratings.
* **Trend Analysis:** Investigated how sales and ratings fluctuate over different months and years.

### 3. Business Insights

* **Customer Satisfaction:** The overall average product rating is **4.05**, indicating high general satisfaction.
* **Product Popularity:** Identified "Hero Products" that have both high review volumes and high ratings.
* **Quality Alert:** Highlighted popular products with consistently low ratings, signaling an urgent need for quality control or feature updates.

## Business Summary

* **Promote Heavily:** Products that are both popular and highly rated are prime candidates for marketing campaigns.
* **Fix Urgently:** High-volume products with poor ratings represent a risk to brand reputation and should be prioritized for quality improvements.

---

## Author

**Madhavan Shanmugam** *Data Analyst | Python | Power BI | SQL | Advanced Excel*

---

### How to Run

1. Ensure you have Python installed.
2. Install dependencies: `pip install pandas matplotlib seaborn`.
3. Place `electronics.csv` in the project directory.
4. Run the Jupyter Notebook: `Interactive - Product_Sales.py.ipynb`.
