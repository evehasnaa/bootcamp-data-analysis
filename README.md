
# 📊 Power BI Customer & Sales Analysis Report

### 👩‍💻 Analyst: Hasnaa Ahmed  
### 🗓️ Project Scope: Customer Segmentation, CLV, Payment Behavior & Sales Insights

---

## 🔎 Overview

This report presents key insights extracted from three main tables: `Customers`, `Payments`, and `Shipping`. By leveraging Power BI, various visuals and DAX measures were applied to explore customer behaviors, classify them based on lifetime value, analyze payment trends, and track product performance across segments.

---

## 🧩 1. Customer Classification Overview

**Objective**: Segment customers into High, Medium, and Low value groups to tailor marketing strategies and business decisions.

- **Transformation**: Created a new column `Customer Classification` using behavioral and monetary rules.
- **Visual Used**: Donut Chart
- **Value**: Count of customers per class

**💡 Insight**: Most revenue is concentrated among High Value customers, highlighting the need for retention-focused efforts toward this segment.

---

## 💧 2. Customer CLV Contribution by Segment

**Objective**: Understand how each customer class contributes to total Customer Lifetime Value (CLV).

- **Visual Used**: Waterfall Chart  
- **Measure**:
```DAX
Customer CLV = 
CALCULATE(
    SUM('Fac Order Details'[Revenue]),
    FILTER('Fac Order Details', 'Fac Order Details'[order_id] = 'Dim Customers'[id])
)
````

**💡 Insight**: High-value customers contribute significantly to overall business revenue. Targeted loyalty programs are essential for this segment.

---

## 🔝 3. Top 10 Products by Revenue (Per Segment)

**Objective**: Identify the best-performing products across customer segments.

* **Visual Used**: Funnel Chart
* **Filter Applied**: Top 10 products by revenue within each segment

**💡 Insight**: Product preferences vary by customer type. Personalization and recommendation engines can benefit from this.

---

## 💳 4. Payment Method Preference by Segment

**Objective**: Visualize the preferred payment methods for each customer class.

* **Visual Used**: Donut Chart
* **Legend**: Payment Method
* **Filter**: Customer Classification

**💡 Insight**: Different segments prefer different payment methods. Optimize offerings based on usage trends.

---

## 💰 5. Total Payment Amount by Customer Class

**Objective**: Compare total amount paid by each customer class.

* **Visual Used**: Column Chart
* **Measure**:

```DAX
Total Amount = SUM(payments[amount])
```

**💡 Insight**: High-value customers, while fewer, contribute the majority of revenue. Focus retention and upsell efforts on them.

---

## 🧠 6. Customer Behavior Analysis Table

**Objective**: Deep-dive into individual customer profiles and behaviors.

* **Visual Used**: Table
* **Columns Included**:

  * Full Name (`first_name + last_name`)
  * Total Orders
  * Average Rating
  * Sum of CLV
  * Net Revenue
  * Total Amount Paid

**💡 Insight**: Enables tracking customer value, identifying top contributors, and spotting those with high potential but low activity.

---

## 📈 7. Customer Registration Trends

**Objective**: Analyze customer growth over time.

* **Visual Used**: Line Chart
* **Measure**: Count of Customer IDs
* **Axis**: Monthly aggregation of `registration_date`

**💡 Insight**: Helps identify peak sign-up periods and campaign effectiveness.

---

## 🚚 8. Shipping Company Distribution

**Objective**: Understand shipping carrier usage across orders.

* **Transformation**: Renamed `carrier` column to `Shipping Company`
* **Visual Used**: Donut Chart
* **Value**: Count of shipping records

**💡 Insight**: Useful for evaluating logistics partnerships and operational performance.

---

## 🥇 9. Top 10 Paying Customers

**Objective**: Highlight the most valuable customers in terms of payment.

* **Visual Used**: Clustered Column Chart
* **Axis**: Full Name
* **Value**: Total Amount Paid
* **Filter**: Top 10 by total amount

**💡 Insight**: These are the top VIP customers. Focus on retention, rewards, and proactive engagement.

---

## ✅ Business Recommendations

| Recommendation                 | Description                                                 |
| ------------------------------ | ----------------------------------------------------------- |
| 🎯 Retain High-Value Customers | Launch loyalty programs and personalized outreach.          |
| 💳 Optimize Payment Options    | Prioritize support for the most-used methods per segment.   |
| 📬 Personalized Campaigns      | Use customer classification for better targeting.           |
| 🛒 Product Positioning         | Promote top-performing products for each segment.           |
| 📈 Forecasting                 | Use registration trends to plan marketing and resourcing.   |
| 📊 Operational Review          | Re-evaluate underused or underperforming shipping carriers. |

---

> 📁 **Note**: This report is built using Power BI and connected to a SQL Server database. Measures are written in DAX. Visuals and transformations are designed to support data-driven decisions for marketing, product strategy, and customer success.

---

```

