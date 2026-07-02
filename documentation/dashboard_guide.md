# ShopSphere Dashboard User Guide

## 🎯 Quick Start

### Opening the Dashboard

1. **Download Power BI Desktop** (if not already installed)
   - Visit: https://powerbi.microsoft.com/en-us/desktop/
   - Install the latest version

2. **Open the Dashboard File**
   - Navigate to `dashboard/ShopSphere_Dashboard.pbix`
   - Double-click to open in Power BI
   - Wait for data to load (~30-60 seconds)

3. **Start Exploring**
   - Use filters on the right side
   - Click on charts to drill down
   - Hover over data points for details

---

## 📊 Dashboard Pages Overview

### Page 1: Executive Summary

**Purpose:** High-level business health at a glance

**Key Components:**
- **KPI Cards** (Top): 4 critical metrics
  - Total Profit
  - Total Sales
  - Profit Margin %
  - Total Orders

**How to Use:**
- Check overall business performance daily
- Use as starting point for deeper analysis
- Compare against targets/benchmarks

**Interactions:**
- Click card to highlight related data
- Hover for detailed metrics

---

### Page 2: Category & Geographic Analysis

**Purpose:** Understand performance by product category and delivery geography

**Key Components:**

1. **Category Bar Chart** (Bottom Left)
   - Shows Total Profit (light blue) and Total Sales (dark blue)
   - Compares Electronics, Fashion, Home & Furniture
   - Reveals category profitability patterns

2. **Delivery Speed Donut Chart** (Right)
   - Shows distribution of delivery performance
   - Color-coded: Blue (Fast/Normal), Orange (Delayed)
   - Interactive percentages

3. **Detail Table** (Right)
   - Lists all sub-categories with metrics
   - Sortable and filterable
   - Shows individual product performance

**How to Use:**
- **Identify Top Performers:** Look for tallest bars in category chart
- **Spot Problem Areas:** Check delayed delivery percentage
- **Deep Dive:** Click on category to see sub-category details
- **Export Data:** Right-click table > Export

**Key Questions to Answer:**
- Which category is most profitable?
- What percentage of orders are delayed?
- Which sub-category underperforms?

---

### Page 3: Sales Channel Performance

**Purpose:** Analyze profitability and trends across sales channels

**Key Components:**

1. **Channel Profit Chart** (Left)
   - Horizontal bar chart
   - Compares Website, Mobile App, Marketplace
   - Quick profitability comparison

2. **Discount Impact Chart** (Top Right)
   - Shows loss vs. profit comparison
   - Discounted vs. Non-discounted analysis
   - Helps optimize discount strategy

3. **Monthly Trends** (Bottom Right)
   - Area chart showing 12-month trend
   - Sum of Profit (light area)
   - Sum of Sales (line overlay)
   - Identifies seasonality patterns

**How to Use:**
- **Channel Strategy:** Identify which channel drives most profit
- **Discount Analysis:** Evaluate if discounts hurt profitability
- **Trend Identification:** Look for seasonal peaks and troughs
- **Forecasting:** Use trend patterns for Q1-Q4 planning

**Key Questions to Answer:**
- Which sales channel is most profitable?
- Do discounts increase or decrease overall profit?
- What's the seasonal pattern?
- When should we ramp up inventory?

---

## 🔧 Using Filters

### Filter Panel (Right Side)

**Available Filters:**
- Category (Electronics, Fashion, Home & Furniture)
- Sub_Category (Individual products)
- Sales_Channel (Website, Mobile App, Marketplace)
- Delivery_Speed (Fast, Normal, Delayed)
- Month (January - December)
- Region/City (Geographic filters)

### How to Apply Filters

1. **Single Selection**
   - Click checkbox next to item
   - Dashboard updates automatically

2. **Multiple Selection**
   - Ctrl+Click (Windows) or Cmd+Click (Mac) multiple items
   - Or use "Select All/None" option

3. **Clearing Filters**
   - Click "X" on filter box
   - Or click "Clear All"

4. **Filter Combinations**
   - Use multiple filters together
   - Example: "Electronics" + "Website" = Electronics on Website

### Example Filter Scenarios

**Scenario 1: Website Performance**
1. Set Sales_Channel = "Website"
2. Review all metrics
3. Compare to other channels

**Scenario 2: Monthly Analysis**
1. Set Month = "March"
2. Analyze category performance for that month
3. Compare to other months

**Scenario 3: On-Time Delivery Focus**
1. Set Delivery_Speed = "Delayed"
2. Identify which categories/channels have issues
3. Take corrective action

---

## 📈 Reading the Visualizations

### KPI Cards

```
┌─────────────────────────┐
│     514.21M             │  ← Value (Total Sales)
│  Total sales            │  ← Label (Metric Name)
└─────────────────────────┘
```

**Interpretation:**
- Large number = High absolute value
- Compare to target/benchmark
- Track month-over-month change

### Bar Charts

```
  Sales (Dark Blue) | Profit (Light Blue)
  ─────────────────────────────────────
  Electronics:  ████████ | ██
  Fashion:      ████████ | ██
  Furniture:    ████████ | ██
```

**How to Read:**
- Taller bars = Higher values
- Stacked bars show composition
- Compare bar heights for ranking

### Area/Line Charts

```
  Profit & Sales Trend
  25M ┌─────────────
  20M │    ╱─╲   ╱─╲
  15M │   ╱   ╲ ╱   ╲
  10M │  ╱     ╲╱     ╲
   0M └─────────────────
       Jan Feb Mar Apr ...
```

**How to Read:**
- Y-axis = Value
- X-axis = Time period
- Rising line = Increasing trend
- Falling line = Decreasing trend

### Donut Charts

```
       22.3% (Fast)
      ╱───────────╲
    ╱               ╲
  Blue (Delayed)  Orange (Normal)
   10.92%  16.7%
```

**How to Read:**
- Each slice = Category percentage
- Size = Proportion of total
- Click to highlight/filter

---

## 💡 Tips & Tricks

### Navigation Tips

1. **Moving Between Pages**
   - Use tabs at bottom of dashboard
   - Or use navigation buttons if present
   - Bookmarks jump to specific states

2. **Drill-Down**
   - Double-click bar/point to zoom
   - Right-click for context menu
   - Use hierarchy to explore detail

3. **Cross-Filtering**
   - Click on any visual
   - Other visuals filter automatically
   - Click again to clear filter

### Analysis Tips

1. **Spot Trends**
   - Look at line charts for patterns
   - Identify peaks and valleys
   - Compare to previous periods

2. **Find Outliers**
   - Look for unusual bars or points
   - Hover to see exact values
   - Investigate anomalies

3. **Make Comparisons**
   - Use filters to compare groups
   - Side-by-side analysis
   - Percentage difference calculations

### Performance Optimization

1. **Faster Loading**
   - Close unnecessary visuals
   - Reduce filter range
   - Clear unused filters

2. **Mobile Viewing**
   - Use Power BI Mobile app
   - Adjust zoom for screen size
   - Swipe to navigate pages

3. **Exporting Data**
   - Right-click visual → Export
   - Download data for Excel analysis
   - Use "See data" option

---

## 🚨 Common Issues & Solutions

### Issue 1: Dashboard Won't Load

**Solution:**
1. Ensure Power BI Desktop is latest version
2. Check internet connection
3. Close other applications
4. Restart Power BI
5. Re-open the .pbix file

### Issue 2: Data Not Updating

**Solution:**
1. Check data source connection
2. Manually refresh: Ctrl+Shift+F9
3. Check data file hasn't moved
4. Verify file permissions

### Issue 3: Filters Not Working

**Solution:**
1. Clear all filters (click X)
2. Refresh the page
3. Check filter relationships
4. Restart Power BI

### Issue 4: Slow Performance

**Solution:**
1. Close other applications
2. Reduce active filters
3. Increase system RAM
4. Check for background processes
5. Consider breaking into smaller files

---

## 📊 Common Analysis Workflows

### Workflow 1: Monthly Performance Review

1. Open dashboard
2. Set Month filter to current month
3. Review 4 KPI cards
4. Check category performance
5. Analyze delivery metrics
6. Compare to previous month
7. Document findings

### Workflow 2: Category Deep Dive

1. Open Category Analysis page
2. Click on category of interest
3. Review sub-categories in detail table
4. Check profitability
5. Analyze delivery performance
6. Identify top products
7. Plan improvement actions

### Workflow 3: Channel Comparison

1. Go to Sales Channel page
2. Compare profit bar heights
3. Analyze discount impact
4. Review 12-month trend
5. Identify growth opportunities
6. Plan channel strategy

---

## 📤 Exporting & Sharing

### Export to PowerPoint

1. Click "File" menu
2. Select "Export"
3. Choose "PowerPoint" format
4. Select pages to export
5. Choose location and save

### Export Data

1. Right-click on visual
2. Click "Export data"
3. Choose Excel format
4. Save file

### Share Dashboard

1. Publish to Power BI Service
2. Share with colleagues
3. Set permissions
4. Create mobile layout
5. Monitor usage

---

## 🎓 Learning Resources

- **Power BI Documentation**: https://docs.microsoft.com/power-bi/
- **DAX Tutorial**: https://dax.guide/
- **Power BI Community**: https://community.powerbi.com/
- **YouTube Tutorials**: Search "Power BI Dashboard Tutorial"

---

## 📞 Support

For questions or issues:
1. Check this guide first
2. Review README.md
3. Open GitHub Issue
4. Contact project maintainer

---

**Last Updated:** July 2, 2024  
**Dashboard Version:** 1.0
