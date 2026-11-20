# Retail Sales, Customer Segmentation & Promotional ROI Analysis

## 📌 Project Overview
An end-to-end data analytics project evaluating **3,900 retail customer transactions ($233.1K total revenue)** to uncover what drives repeat purchases, whether promotional discounts increase average order value, and how subscription perks impact customer loyalty.

* **Tech Stack:** Python (Pandas, NumPy, Matplotlib, seaborn), MySQL, Microsoft Power BI (DAX)
* **Key Focus Areas:** Data Wrangling, Feature Engineering, Relational Querying, Customer Segmentation, and Executive Dashboarding

---

## 🛠️ Methodology & Workflow

### 1. Data Cleaning & Feature Engineering (Python)
* **Missing Value Imputation:** Identified missing entries in `review_rating` and imputed them using category-level medians to preserve rating distributions.
* **Redundancy Removal:** Verified that `promo_code_used` duplicated `discount_applied` across 100% of records and removed the redundant field.
* **Custom Feature Engineering:**
  * Engineered generational cohorts (`Gen-Z`, `Millennials`, `Gen X`, `Boomers`) using `pd.cut()`.
  * Created custom business value tiers (`High-Value Loyal`, `Standard Regular`, `At-Risk`, `Discount-Driven`) using `np.select()` based on spend and purchase history.

### 2. Business Analysis (MySQL)
Executed 10 analytical queries using CTEs, `CASE` logic, and window functions (`RANK()`, `DENSE_RANK()`) to evaluate seasonal product demand, state-level discount dependency, payment preferences across generations, and high-LTV subscription upsell segments.

### 3. Interactive Executive Dashboard (Power BI)
Built a 2-page interactive report featuring explicit DAX measures (`Total Revenue`, `Average Order Value`, `Discount Usage %`, `Subscriber Rate %`), dynamic slicers (`Season`, `Gender`, `Category`), and conditional formatting.

---

## 📊 Dashboard Preview

### Page 1: Executive Revenue & Seasonal Overview
![Executive Overview](executive_overview.png)

### Page 2: Customer Segmentation, Loyalty & Promotional ROI
![Customer & Promo Insights](customer_promo_insights.png)

---

## 💡 Key Findings & Business Recommendations

1. **Tighten Promotional Eligibility (Margin Recovery):**
   * **Finding:** **43.0%** of all orders use a discount, yet discounted orders yield a slightly lower Average Order Value (**$59.28**) than full-price orders (**$60.13**).
   * **Recommendation:** Introduce a **$75 minimum cart threshold** for promo codes to protect profit margins while incentivizing larger basket sizes.
2. **Convert High-Value Non-Subscribers:**
   * **Finding:** Only **27.0%** of customers are subscribed, leaving a large pool of repeat buyers (*High-Value Loyal* accounts for **$98K** in revenue) outside the membership program.
   * **Recommendation:** Launch targeted membership campaigns offering exclusive **Express / Next-Day shipping perks** to frequent non-subscribers.
3. **Optimize Seasonal Inventory Allocation:**
   * **Finding:** *Clothing* (**$104.3K**) and *Accessories* (**$74.2K**) generate over **76%** of total revenue, with peak demand occurring in **Fall ($60.0K)** and **Winter ($58.6K)**.
   * **Recommendation:** Prioritize inventory stocking and marketing spend on high-velocity sizes and colors ahead of Q3/Q4 peak seasons.
