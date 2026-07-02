# Data Dictionary - ShopSphere E-Commerce Dashboard

## Overview

This document provides detailed information about all data fields, dimensions, and measures used in the ShopSphere E-Commerce Analytics Dashboard.

---

## 📊 Dimensions (Descriptive Attributes)

### Date Dimensions

| Field | Type | Description | Example |
|-------|------|-------------|----------|
| **Date** | Date | Transaction date | 2024-01-15 |
| **Month** | Text | Month name | January, February, March |
| **Quarter** | Text | Quarter designation | Q1, Q2, Q3, Q4 |
| **Year** | Integer | Calendar year | 2024 |
| **Day of Week** | Text | Day name | Monday, Tuesday, etc. |
| **Week Number** | Integer | ISO week number | 1-52 |

### Product Dimensions

| Field | Type | Description | Example |
|-------|------|-------------|----------|
| **Category** | Text | Main product category | Electronics, Fashion, Home & Furniture |
| **Sub_Category** | Text | Product subcategory | Laptops, Men Wear, Sofa |
| **Product_ID** | Integer | Unique product identifier | 10001, 10002, 10003 |
| **Product_Name** | Text | Product description | Dell XPS 13 Laptop |
| **Brand** | Text | Product brand | Dell, HP, Lenovo |

### Geographic Dimensions

| Field | Type | Description | Example |
|-------|------|-------------|----------|
| **Region** | Text | Geographic region | North, South, East, West |
| **City** | Text | City name | New York, Los Angeles, Mumbai |
| **State** | Text | State/Province | California, Texas, Maharashtra |
| **Country** | Text | Country | United States, India |
| **Postal_Code** | Text | Postal code | 90210, 110001 |

### Customer Dimensions

| Field | Type | Description | Example |
|-------|------|-------------|----------|
| **Customer_ID** | Integer | Unique customer identifier | 50001, 50002, 50003 |
| **Customer_Name** | Text | Customer full name | John Smith |
| **Customer_Email** | Text | Customer email | john@example.com |
| **Customer_Segment** | Text | Customer classification | Premium, Standard, New |

### Sales Channel Dimensions

| Field | Type | Description | Example |
|-------|------|-------------|----------|
| **Sales_Channel** | Text | Channel of sale | Website, Mobile App, Marketplace |
| **Platform** | Text | Specific platform | iOS App, Android App, Web Browser |

### Operational Dimensions

| Field | Type | Description | Example |
|-------|------|-------------|----------|
| **Order_ID** | Integer | Unique order identifier | 100001, 100002, 100003 |
| **Delivery_Speed** | Text | Delivery performance | Fast, Normal, Delayed |
| **Order_Status** | Text | Current order status | Completed, Pending, Cancelled |
| **Payment_Method** | Text | Payment type | Credit Card, Debit Card, UPI |
| **Discount_Applied** | Boolean | Whether discount was used | Yes, No |
| **Discount_Type** | Text | Type of discount | Percentage, Fixed Amount, Coupon |

---

## 💰 Measures (Quantitative Metrics)

### Sales Measures

| Measure | Formula | Description | Unit |
|---------|---------|-------------|------|
| **Total Sales** | SUM(Sales) | Sum of all sales revenue | Millions ($) |
| **Net Sales** | SUM(Sales) - SUM(Returns) | Sales minus returns | Millions ($) |
| **Average Order Value (AOV)** | SUM(Sales) / COUNT(Orders) | Revenue per order | Thousands ($) |
| **Units Sold** | COUNT(Quantity) | Total items sold | Count |
| **Revenue per Unit** | SUM(Sales) / SUM(Quantity) | Average price per unit | Thousands ($) |

### Profit Measures

| Measure | Formula | Description | Unit |
|---------|---------|-------------|------|
| **Total Profit** | SUM(Revenue) - SUM(Costs) | Bottom-line profitability | Millions ($) |
| **Gross Profit** | SUM(Revenue) - SUM(COGS) | Profit before operating expenses | Millions ($) |
| **Profit Margin %** | (Profit / Sales) × 100 | Percentage of sales that is profit | Percentage (%) |
| **Profit per Order** | Total Profit / Total Orders | Average profit per transaction | Thousands ($) |

### Performance Measures

| Measure | Formula | Description | Unit |
|---------|---------|-------------|------|
| **Order Count** | COUNTA(Order_ID) | Total number of orders | Count |
| **Customer Count** | COALESCE(DISTINCT(Customer_ID)) | Unique customers | Count |
| **Return Rate %** | (Returned Orders / Total Orders) × 100 | Percentage of orders returned | Percentage (%) |
| **Conversion Rate %** | (Purchases / Visits) × 100 | Purchase conversion | Percentage (%) |
| **On-Time Delivery %** | (Fast + Normal) / Total Orders × 100 | Successful delivery rate | Percentage (%) |

### Discount Impact Measures

| Measure | Formula | Description | Unit |
|---------|---------|-------------|------|
| **Discounted Orders** | COUNT(Orders WHERE Discount = Yes) | Orders with discounts | Count |
| **Non-Discounted Orders** | COUNT(Orders WHERE Discount = No) | Orders without discounts | Count |
| **Total Discount Amount** | SUM(Discount Value) | Sum of all discounts given | Millions ($) |
| **Discount % of Sales** | (Total Discount / Total Sales) × 100 | Discount impact on revenue | Percentage (%) |
| **Loss Count** | COUNT(Orders WHERE Profit < 0) | Number of loss-making orders | Count |

---

## 🔢 Key Metrics Summary

### Executive KPIs

```
Total Sales:         $514.21M
Total Profit:        $39.71M
Profit Margin:       7.72%
Total Orders:        12,000
Average Order Value: $42,851 (calculated)
```

### By Category

| Category | Sales | Profit | Margin |
|----------|-------|--------|--------|
| Electronics | ~$171B | ~$42.15M | 7.7% |
| Fashion | ~$171B | ~$48.16M | 7.7% |
| Home & Furniture | ~$171B | ~$45.03M | 7.7% |
| **TOTAL** | **$514.21M** | **$39.71M** | **7.72%** |

### By Sales Channel

| Channel | Relative Contribution | Status |
|---------|----------------------|--------|
| Website | Highest | Primary |
| Mobile App | Medium | Growing |
| Marketplace | Medium-High | Established |

### By Delivery Speed

| Speed | Count | Percentage |
|-------|-------|------------|
| Fast | 5,350 | 22.3% |
| Normal | 4,030 | 16.7% |
| Delayed | 2,620 | 10.92% |

---

## 📈 Calculated Metrics

### DAX Formulas (Power BI)

```dax
-- Total Profit
TotalProfit = SUM(Orders[Profit])

-- Profit Margin %
ProfitMargin = DIVIDE(SUM(Orders[Profit]), SUM(Orders[Sales]), 0) * 100

-- Average Order Value
AOV = DIVIDE(SUM(Orders[Sales]), COUNTA(Orders[OrderID]))

-- On-Time Delivery %
OnTimeDelivery = 
    DIVIDE(
        COUNTIF(Orders[DeliverySpeed], "Fast") + 
        COUNTIF(Orders[DeliverySpeed], "Normal"),
        COUNTA(Orders[OrderID])
    ) * 100

-- Discount Impact
DiscountedOrders = COUNTIF(Orders[Discount], "Yes")
LossCount = CALCULATE(COUNTROWS(Orders), Orders[Profit] < 0)
```

---

## 📋 Data Quality Standards

### Validation Rules

1. **Sales Amount**
   - Must be positive (> 0)
   - Cannot exceed order capacity
   - Consistent with revenue records

2. **Profit Calculation**
   - Profit = Sales - Costs
   - Profit margin must be 0-100%
   - Must reconcile with accounting

3. **Order Data**
   - Order_ID must be unique
   - Order date must be within period
   - Delivery date >= Order date

4. **Geographic Data**
   - Valid state/country combinations
   - Postal codes match location
   - Coordinates valid if present

5. **Customer Data**
   - Email format valid
   - Customer_ID unique
   - No duplicate records

---

## 🔄 Data Refresh Schedule

| Component | Frequency | Window | SLA |
|-----------|-----------|--------|-----|
| Daily Transactions | Daily | 2:00 AM UTC | 99.9% |
| Weekly Reports | Weekly | Sunday Midnight | 99.5% |
| Monthly Aggregations | Monthly | Month-end | 99.0% |
| Historical Archive | Monthly | Last day | 95.0% |

---

## 🔐 Data Privacy & Security

- **PII Handling**: Customer names and emails are not exported
- **Data Masking**: Financial details masked in non-production environments
- **Access Control**: Role-based access to sensitive data
- **Audit Trail**: All data access logged for compliance

---

## 📞 Questions?

For questions about data definitions or calculations:
1. Check this dictionary first
2. Review the README.md file
3. Open a GitHub Issue
4. Contact the data team

---

**Last Updated:** July 2, 2024  
**Data Version:** 1.0
