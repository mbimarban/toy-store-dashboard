# 🧸 Toy Store Business Intelligence Dashboard

## 📊 Professional Excel Dashboard System with Power Pivot & DAX

![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power Pivot](https://img.shields.io/badge/Power_Pivot-CA5010?style=for-the-badge&logo=microsoft&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

---

## 🎯 Project Overview

A comprehensive **Business Intelligence Dashboard System** built in Microsoft Excel featuring Power Pivot, DAX measures, and professional data visualization. This project demonstrates advanced Excel capabilities for sales and procurement analytics in a toy store retail context.

**Key Features:**
- ✅ **Dual Dashboard System** (Sales & Procurement perspectives)
- ✅ **Power Pivot Data Model** with 4 tables and relational integrity
- ✅ **8 Custom DAX Measures** for business metrics
- ✅ **Professional Design** with custom gradient color palette
- ✅ **Interactive Visualizations** (KPI cards, line charts, bar charts, donut charts)

---

## 📸 Dashboard Previews

### Sales Dashboard 2025
![Sales Dashboard](https://raw.githubusercontent.com/mbimarban/toy-store-dashboard/main/screenshots/sales_dashboard.png)

**Metrics Tracked:**
- 💰 Total Revenue: $9.86M
- 💵 Total Cost: $5.56M
- 📈 Total Profit: $4.31M
- 📊 Profit Margin: 43.7%

**Visualizations:**
- Monthly Revenue Trend (Line Chart)
- Top 10 Best-Selling Products (Horizontal Bar Chart)

---

### Procurement Dashboard 2025
![Procurement Dashboard](https://raw.githubusercontent.com/mbimarban/toy-store-dashboard/main/screenshots/procurement_dashboard.png)

**Metrics Tracked:**
- 📦 Total Stock Units: 339K
- 💰 Stock Value: $3.12M
- 📊 Stock-to-Sales Ratio: 59.8%
- ⏱️ Days of Inventory: 218 days

**Visualizations:**
- Stock Distribution by Category (Donut Chart)
- Top 10 Products by Stock Value (Horizontal Bar Chart)

---

### Data Model Architecture
![Data Model](https://raw.githubusercontent.com/mbimarban/toy-store-dashboard/main/screenshots/data_model.png)

**Star Schema Design:**
- 4 Tables: sales (fact), products (dim), stores (dim), inventory (fact)
- 4 Relationships: Product_ID, Store_ID connections
- Relational integrity maintained

---

## 🗂️ Dataset Overview

| Table | Records | Columns | Description |
|-------|---------|---------|-------------|
| **sales** | 245,800 | 6 | Transaction-level sales data with date, store, product, units |
| **products** | 180 | 5 | Product master data with category, price, cost |
| **stores** | 120 | 5 | Store locations with city, region, opening date |
| **inventory** | 14,143 | 3 | Current stock levels by store and product |

---

## 🧮 DAX Measures

### Sales Metrics
```dax
Total Revenue:=SUMX(sales, sales[Units] * RELATED(products[Product_Price]))

Total Cost:=SUMX(sales, sales[Units] * RELATED(products[Product_Cost]))

Total Profit:=[Total Revenue] - [Total Cost]

Margin %:=DIVIDE([Total Profit], [Total Revenue], 0)

Units Sold:=SUM(sales[Units])

Number of Transactions:=COUNTROWS(sales)
```

### Inventory Metrics
```dax
Total Stock Units:=SUM(inventory[Stock_On_Hand])

Stock Value:=SUMX(inventory, inventory[Stock_On_Hand] * RELATED(products[Product_Cost]))

Stock_to_Sales_Ratio:=DIVIDE([Total Stock Units], [Units Sold], 0)

Days_of_Inventory:=DIVIDE([Total Stock Units], [Units Sold], 0) * 365
```

---

## 🎨 Design System

### Color Palette - "Modern Kids"
Custom gradient palette inspired by toy store branding:

| Color | Hex Code | Usage |
|-------|----------|-------|
| 🔵 Blue 900 | `#1E3A8A` | Headers, primary text |
| 🔷 Blue 500 | `#3B82F6` | KPI cards, chart backgrounds |
| 🟣 Purple 500 | `#8B5CF6` | Secondary accents |
| 🌸 Pink 300 | `#F9A8D4` | Highlights, gradients |
| 🌟 Yellow 300 | `#FDE047` | Important values, alerts |
| ⬜ Slate 50 | `#F8FAFC` | Light backgrounds |

### Typography
- **Headings:** Segoe UI Bold, 16-24pt
- **KPI Labels:** Segoe UI Semibold, 10-12pt
- **KPI Values:** Segoe UI Bold, 18-24pt
- **Chart Labels:** Segoe UI Regular, 10pt

---

## 💡 Key Insights

### Sales Performance
- ✅ **Strong profitability:** 43.7% margin indicates healthy pricing strategy
- 📈 **Consistent revenue:** Monthly trend shows stability with minor fluctuations
- 🏆 **Top performer:** Mega Board Game ($231.9K revenue)
- 📊 **Revenue concentration:** Top 10 products account for $1.48M (15% of total)

### Inventory Management
- ⚠️ **Excess inventory:** 218 days of inventory (7+ months) is significantly high
- 💰 **Capital tied up:** $3.12M in stock value represents opportunity cost
- 📦 **Distribution:** 56% of stock in "Others" category shows fragmentation
- 🎯 **Focus areas:** Eco Art Kit ($53.4K), Pro Board Game ($50.7K), Mini Robot ($50.5K) hold most value

### Actionable Recommendations
1. **Reduce ordering cycles** - 218 days suggests over-purchasing
2. **Optimize product mix** - Focus on fast-moving, high-margin items
3. **Redistribute stock** - Consider inter-store transfers for balance
4. **Analyze slow movers** - Products in "Others" category may need discounting

---

## 🛠️ Technical Features

### Excel Techniques Applied
- ✅ **Power Pivot** - In-memory data model with relational tables
- ✅ **DAX (Data Analysis Expressions)** - Custom calculated measures
- ✅ **PivotTables** - Dynamic data aggregation from Power Pivot
- ✅ **Advanced Charting** - Custom formatted charts with gradients
- ✅ **Conditional Formatting** - Custom number formats for KPIs
- ✅ **Dashboard Design** - Separation of calculation and presentation layers

### Best Practices Implemented
- 📊 **Layered Architecture** - "Data" sheet for calculations, separate dashboards for presentation
- 🎨 **Consistent Design Language** - Unified color palette and typography
- 📈 **Data Storytelling** - Each dashboard answers specific business questions
- 🔄 **Scalable Structure** - Easy to add new measures or update data sources
- 📝 **Clear Naming Conventions** - Readable measure and field names

---

## 📂 Project Structure

```
toy-store-dashboard/
│
├── ToyStore_Dashboard_2025.xlsx       # Main Excel file with dashboards
│
├── data/                              # Source data files
│   ├── sales.csv                      # 245,800 transaction records
│   ├── products.csv                   # 180 product details
│   ├── stores.csv                     # 120 store locations
│   └── inventory.csv                  # 14,143 stock records
│
├── screenshots/                       # Dashboard previews
│   ├── sales_dashboard.png
│   ├── procurement_dashboard.png
│   └── data_model.png
│
└── README.md                          # Project documentation
```

---

## 🚀 How to Use

### Prerequisites
- Microsoft Excel 2016 or later (with Power Pivot enabled)
- Windows operating system (Power Pivot not available on Mac Excel)

### Setup Instructions

1. **Enable Power Pivot:**
   ```
   File → Options → Add-ins → Manage: COM Add-ins → Go
   ☑ Microsoft Power Pivot for Excel
   ```

2. **Open the Dashboard:**
   - Download `ToyStore_Dashboard_2025.xlsx`
   - Enable macros if prompted (for Power Pivot functionality)

3. **Navigate Dashboards:**
   - **Sales Dashboard** - Overview of sales performance
   - **Procurement Dashboard** - Inventory and procurement analytics
   - **Data** - Source PivotTables (hidden by default)

4. **Refresh Data (if updating source files):**
   ```
   Power Pivot → Manage → Refresh
   ```

---

## 📊 Use Cases

This dashboard system is ideal for:

- 🏪 **Retail Managers** - Track sales performance and identify best sellers
- 📦 **Procurement Teams** - Optimize inventory levels and purchasing decisions
- 💼 **Business Analysts** - Analyze trends and generate insights
- 📈 **Executive Leadership** - High-level KPIs for strategic planning
- 🎓 **Students/Learners** - Study advanced Excel and BI techniques

---

## 🎓 Learning Outcomes

By studying this project, you'll learn:

1. **Power Pivot Fundamentals**
   - Creating data models
   - Establishing table relationships
   - Managing large datasets in Excel

2. **DAX Proficiency**
   - Writing calculated measures
   - Using functions: SUM, SUMX, DIVIDE, RELATED, COUNTROWS
   - Understanding context and filter propagation

3. **Dashboard Design**
   - Visual hierarchy and layout principles
   - Color theory for business dashboards
   - Creating KPI cards and interactive charts

4. **Business Intelligence**
   - Defining meaningful KPIs
   - Data storytelling techniques
   - Translating data into actionable insights

---

## 🔄 Future Enhancements

Potential improvements for this project:

- [ ] Add date slicers for dynamic time filtering
- [ ] Create geographic analysis with store location maps
- [ ] Implement inventory turnover rate calculations
- [ ] Add customer segmentation analysis
- [ ] Build forecasting models for demand planning
- [ ] Export to Power BI for enhanced interactivity
- [ ] Add inventory alert thresholds with conditional formatting

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

Created as a demonstration of advanced Excel and Business Intelligence capabilities.

**Skills Demonstrated:**
- Advanced Excel (Power Pivot, DAX, PivotTables)
- Data Modeling & Relational Databases
- Business Intelligence & Analytics
- Dashboard Design & Data Visualization
- Data Storytelling

---

## 🙏 Acknowledgments

- Dataset inspired by retail toy store operations
- Color palette influenced by modern dashboard design trends
- DAX techniques based on Microsoft Power BI best practices

---

## 📧 Contact

For questions, feedback, or collaboration opportunities, please open an issue in this repository.

---

**⭐ If you found this project helpful, please consider giving it a star!**

---

*Last Updated: January 2025*
