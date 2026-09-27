# 📊 Customer Shopping Behavior Analysis — End-to-End Data Analytics Project

## Overview
This project analyzes customer shopping behavior using transactional data from 3,900 purchases to uncover insights into spending patterns, customer segments, product preferences, and subscription behavior. It covers the full analytics pipeline — data loading and cleaning in Python, exploratory data analysis, SQL-based business querying, an interactive Power BI dashboard, and a final report/presentation — to guide strategic business decisions around retention, pricing, and merchandising.

## Dataset
- **Size:** 3,900 rows × 18 columns
- **Key features:**
  - **Customer demographics:** Age, Gender, Location, Subscription Status
  - **Purchase details:** Item Purchased, Category, Purchase Amount, Season, Size, Color
  - **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method
- **Data quality:** 37 missing values in the Review Rating column, imputed using the median rating per product category
- **Coverage:** 25 products across 4 categories (Clothing, Accessories, Footwear, Outerwear), sold across 50 locations

## Tools & Technologies
| Category | Tools Used |
|---|---|
| Data Loading & Cleaning | Python (Pandas) |
| Exploratory Data Analysis | Python (Pandas, `.info()` / `.describe()`) |
| Database & Querying | PostgreSQL |
| Dashboarding | Power BI |
| Reporting | PDF Report |
| Presentation | Gamma (AI-generated executive deck) |

## Project Steps

### 1. Data Loading
- Imported the dataset into Python using Pandas.
- Ran `.info()` and `.describe()` to check structure and summary statistics.

### 2. Data Cleaning & Feature Engineering
- Checked for null values and imputed the 37 missing `Review Rating` entries using each product category's median rating.
- Renamed columns to snake_case for readability and documentation.
- Engineered an `age_group` column by binning customer ages, and a `purchase_frequency_days` column from purchase data.
- Verified `discount_applied` and `promo_code_used` were redundant and dropped `promo_code_used`.
- Connected Python to PostgreSQL and loaded the cleaned DataFrame into the database.

### 3. SQL Analysis (PostgreSQL)
Answered 10 key business questions with SQL, including:
1. **Revenue by gender** — Male customers generated $157,890 vs. $75,191 from female customers.
2. **High-spending discount users** — 839 customers used a discount but still spent above the $59.76 average.
3. **Top 5 products by rating** — Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78).
4. **Shipping type comparison** — Express shipping orders averaged $60.48 vs. $58.46 for Standard.
5. **Subscribers vs. non-subscribers** — 1,053 subscribers (avg. spend $59.49, total revenue $62,645) vs. 2,847 non-subscribers (avg. spend $59.87, total revenue $170,436).
6. **Discount-dependent products** — Hat (50%), Sneakers (49.7%), Coat (49.1%), Sweater (48.2%), Pants (47.4%) of unit sales were discounted.
7. **Customer segmentation** — Loyal: 3,116 · Returning: 701 · New: 83.
8. **Top 3 products per category** — e.g., Jewelry/Sunglasses/Belt (Accessories), Blouse/Pants/Shirt (Clothing), Sandals/Shoes/Sneakers (Footwear), Jacket/Coat (Outerwear).
9. **Repeat buyers & subscriptions** — 958 subscribers vs. 2,518 non-subscribers among repeat buyers (>5 purchases).
10. **Revenue by age group** — Young Adult ($62,143), Middle-aged ($59,197), Adult ($55,978), Senior ($55,763).

### 4. Power BI Dashboard
Built an interactive **Customer Behavior Dashboard** with:
- KPI cards: 3,900 customers, 3.75 average review rating, $59.76 average purchase amount
- Filters/slicers: Subscription Status, Gender, Category, Shipping Type
- Sales by Category and Revenue by Category bar charts
- Revenue by Age Group bar chart
- % of Customers by Subscription Status donut chart (1K subscribed vs. 3K not)

### 5. Report & Presentation
- Compiled a written project report covering methodology, EDA, SQL findings, dashboard, and business recommendations.
- Created an executive summary presentation in Gamma ("Customer Shopping Behavior — Executive Growth Readout") framing the findings around three growth levers: subscription monetization, discount/margin protection, and merchandising top-rated products.

## Results & Key Insights
- **Clothing drives the business:** ~$90K revenue and ~1,800 units sold, more than double the next category (Accessories, ~$70K / ~1,200 units). Footwear (~$30K) and Outerwear (~$15K) trail well behind.
- **Loyalty is high, but subscriptions aren't moving spend:** 79.9% of customers are "Loyal," yet subscribers ($59.49 avg spend) and non-subscribers ($59.87 avg spend) spend almost identically — the subscription program isn't currently driving incremental value.
- **Discount dependency risk:** Nearly 50% of purchases in Hats, Sneakers, Coats, Sweaters, and Pants are discounted, raising the question of whether these sales are incremental or just margin given away on demand that would have converted anyway.
- **Young Adults lead revenue** ($62,143) but the gap across age cohorts is narrow (Middle-aged $59,197, Adult $55,978, Senior $55,763) — spend is fairly balanced across life stages, so marketing shouldn't skew exclusively toward younger shoppers.
- **Top-rated products** (Gloves, Sandals, Boots, Hat, Skirt) all sit only slightly above the 3.75 catalog-average rating, giving a modest but usable proof-point set for campaigns.

## Business Recommendations
- **Boost subscriptions** — Promote exclusive subscriber benefits, since the current program shows no spend lift.
- **Strengthen loyalty programs** — Reward repeat buyers to convert more of the "Returning" and "New" segments into "Loyal."
- **Review discount policy** — Audit the five most discount-dependent products to separate incremental demand from margin loss.
- **Product positioning** — Feature top-rated and best-selling products (Clothing, Accessories) in campaigns.
- **Targeted marketing** — Focus on high-revenue age groups (Young Adult, Middle-aged) and Express-shipping users.

## Repository Structure
├── data/
│ └── customer_shopping_behavior.csv
├── notebooks/
│ └── eda_and_cleaning.ipynb
├── sql/
│ └── analysis_queries.sql
├── dashboard/
│ ├── Customer_Behavior_dashboard.pbix
│ └── Customer_Behavior_dashboard_picture.pdf
├── report/
│ └── Customer_Shopping_Behavior_Analysis.pdf
├── presentation/
│ └── Customer-shopping-behavior-analysis-presentation.pdf
└── README.md


## How to Run
1. Clone this repository:
```bash
   git clone <repo-link>
```
2. Install required Python libraries:
```bash
   pip install pandas numpy
```
3. Run the Jupyter notebook in `notebooks/` to reproduce data cleaning, feature engineering, and EDA on `customer_shopping_behavior.csv`.
4. Load the cleaned data into PostgreSQL and execute the queries in `sql/analysis_queries.sql` to reproduce the 10 business-question results.
5. Open `dashboard/Customer_Behavior_dashboard.pbix` in Power BI to explore the interactive dashboard.
6. Refer to `report/Customer_Shopping_Behavior_Analysis.pdf` for the full write-up and `presentation/Customer-shopping-behavior-analysis-presentation.pdf` for the executive summary deck.

## Author
**Abhishek Kumar**
B.Tech CSE, IIMT College of Engineering (AKTU)
[LinkedIn](https://www.linkedin.com/in/abhishek-kumar-428532331/) 
[GitHub](https://github.com/Abhishekkumarranjan123)
