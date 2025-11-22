Customer Shopping Behavior Analysis* report:

---
Customer Shopping Behavior Analysis
1. Overview

This project analyzes customer shopping behavior using transactional data from **3,900 purchases** across multiple product categories.
It aims to uncover insights into **spending patterns, customer segmentation, product preferences, and subscription trends** to drive data-informed business strategies.

---

2. Dataset

**Source:** Internal retail transactions
**Size:** 3,900 rows × 18 columns

**Key Features:**

* **Demographics:** Age, Gender, Location, Subscription Status
* **Purchase Details:** Item Purchased, Category, Amount, Season, Size, Color
* **Behavioral Factors:** Discount Applied, Promo Code Used, Previous Purchases, Review Rating, Shipping Type

**Missing Data:**
37 missing values in *Review Rating* were imputed using median values by category.

---
 3. Tools Used

| Purpose             | Tool                                        |
| ------------------- | ------------------------------------------- |
| Data Cleaning & EDA | Python (Pandas, NumPy, Matplotlib, Seaborn) |
| Database & SQL      | PostgreSQL / MySQL Server                   |
| Dashboard           | Power BI                                    |
| Presentation        | Gamma App                                   |
| Documentation       | Markdown, Jupyter Notebook                  |

---

 4. Steps

 Data Preparation (Python)

* Imported dataset and standardized column names to `snake_case`
* Handled missing data using **median imputation**
* Created new features:

  * `age_group` (binned ages)
  * `purchase_frequency_days` (purchase frequency)
* Removed redundant fields (`promo_code_used` dropped after correlation check)
* Loaded cleaned data into PostgreSQL for SQL querying

---

SQL Analysis

Performed 10 key analyses in PostgreSQL:

| #  | Business Query                 | Insight                                                                            |
| -- | ------------------------------ | ---------------------------------------------------------------------------------- |
| 1  | Revenue by Gender              | Compared total spend by male vs female customers                                   |
| 2  | High-Spending Discount Users   | Found discount users who still spent above average                                 |
| 3  | Top 5 Products by Rating       | Gloves, Sandals, Boots, Hat, Skirt                                                 |
| 4  | Shipping Type Comparison       | Express users spent more (60.48 vs 58.46)                                          |
| 5  | Subscribers vs Non-Subscribers | 27% subscribed; subscribers spent marginally less per order but had higher loyalty |
| 6  | Discount-Dependent Products    | Identified products most bought with discounts                                     |
| 7  | Customer Segmentation          | Classified customers as New, Returning, or Loyal                                   |
| 8  | Top 3 Products per Category    | Example: Jewelry, Sunglasses, and Belt lead Accessories                            |
| 9  | Repeat Buyers & Subscriptions  | Repeat buyers (5+ purchases) more likely to subscribe                              |
| 10 | Revenue by Age Group           | Young Adults lead with $62K revenue, followed by Middle-aged                       |

*(See pages 4–6 in the PDF for visual SQL tables and rankings.)*

---

#Dashboard (Power BI)

Built an interactive dashboard to visualize:

* Revenue and sales by **category** and **age group**
* **Subscription** breakdown (27% Yes / 73% No)
* Average purchase amount ($59.76)
* Review rating distribution (Avg: 3.75)
* KPIs for top-performing segments and products

*(Dashboard screenshot available on page 7 of the report.)*

---

5. Results

* **Young Adults** and **Middle-aged** customers generate the most revenue.
* **Subscribers** show stronger long-term value despite lower average spend.
* **Express Shipping** correlates with higher spending.
* **Top-rated products** overlap with best-sellers — strong brand loyalty indicators.

---

6. Business Recommendations

* 💳 **Boost Subscriptions:** Offer exclusive benefits for subscribers.
* 🎁 **Customer Loyalty Program:** Reward repeat buyers to retain them.
* 💬 **Review Policy:** Encourage genuine reviews and balance discounts.
* 🌟 **Product Strategy:** Promote top-rated items like *Gloves* and *Sandals*.
* 🎯 **Marketing Focus:** Target *Young Adults* and *Express Shipping* users.

---

7. How to Run

1. Clone this repository
2. Install dependencies

   ```bash
   pip install pandas numpy matplotlib seaborn psycopg2
   ```
3. Load dataset into PostgreSQL (`customer_behavior` table)
4. Run the Python EDA script → `eda_customer_behavior.py`
5. Execute SQL queries from `analysis_queries.sql`
6. Open Power BI dashboard (`Customer_Behavior.pbix`)
7. Present summary deck (`Customer_Behavior_Presentation.gamma`)

---
8. Deliverables

* 🧾 Cleaned dataset (CSV/SQL)
* 📊 Power BI dashboard
* 📈 Gamma presentation deck
* 🗂️ Documentation (this README)

