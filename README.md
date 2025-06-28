# Sales_DashBoard

## 📊 Project Overview

This Power BI dashboard analyzes **food item sales across various cities** using the following dataset components:

- `DAX Customers.xlsx`: Contains customer demographic and location data.
- `DAX Orders.xlsx`: Contains transactional order data, including product names, quantities, sales, and costs.
- `DAX.pbix`: The main Power BI report file with visualizations, DAX calculations, and dashboard elements.

The dashboard provides clear visibility into the most profitable products, sales distribution by city, and customer behavior.

---

## 🧾 Key Data Fields

- **City** (from `DAX Customers.xlsx`)
- **Product Name** (from `DAX Orders.xlsx`)
- **Sales**
- **Quantity Sold**
- **Order ID**
- **Cost** (used to compute Profit)

---

## 🔍 Calculated Measures (DAX)

### Total Sales
```DAX
Total Sales = SUM(Orders[Sales])
```

### Total Orders
```DAX
Total Orders = DISTINCTCOUNT(Orders[Order ID])
```

### Total Quantity Sold
```DAX
Total Quantity = SUM(Orders[Quantity])
```

### Profit
```DAX
Profit = SUM(Orders[Sales]) - SUM(Orders[Cost])
```

### Maximum Sales by Product
```DAX
Max Sales Product = 
CALCULATE(
    MAXX(
        VALUES(Orders[Product Name]),
        CALCULATE(SUM(Orders[Sales]))
    )
)
```

---

## 📈 Visualizations Used

- **Bar Charts**:
  - Product-wise Total Sales
  - Top 5 Selling Items

- **Pie Charts**:
  - Product Category Contribution

- **Map Chart**:
  - Sales Distribution by City

- **Cards**:
  - Total Sales  
  - Total Profit  
  - Total Orders  
  - Quantity Sold

- **Slicers**:
  - Product Name  
  - City  
  - Date

---

## 🎯 Key Insights

- Identified the **most profitable products** and **cities with high sales density**
- Highlighted peak sales volume by **product category**
- Enabled **dynamic filtering** and **interactive drilldowns**
- Supports **data-driven decision-making** for pricing and inventory planning

---

## 🛠️ Tools Used

- **Power BI Desktop (.pbix)** for dashboard creation
- **DAX** for business metric calculations
- **Excel (.xlsx)** for data input and preprocessing

---

## 📂 Folder Structure

```
/Sales_DashBoard/
├── DAX.pbix
├── DAX Customers.xlsx
├── DAX Orders.xlsx
└── README.md
```

---

## 📌 Notes

- Data must be refreshed if Excel files are updated.
- Slicers allow for **customizable views** by City and Product.
- Measures are optimized for clarity and performance.
