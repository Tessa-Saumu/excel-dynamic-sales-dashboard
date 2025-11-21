# Excel Dynamic Sales Dashboard 📊

## 🎯 Project Overview
An interactive, dynamic sales dashboard for KicksHub that allows managers to instantly view sales rep performance metrics by simply selecting a sales rep and month from dropdown menus. Built entirely in Excel using advanced formulas and dynamic arrays.

## 💼 Business Problem
Sales managers need quick access to individual rep performance without navigating through static reports. This dashboard provides real-time insights into revenue, transactions, and commission tiers through an intuitive interface.

## ✨ Key Features

### Interactive Controls
- **Sales Rep dropdown** - Select any rep (Ana, Ben, Chloe, David)
- **Month dropdown** - Filter by October, November, or December
- **Auto-updating display** - All metrics update instantly based on selections

### Dynamic Metrics Calculated
- 💰 Total Revenue for selected rep/month
- 📈 Total number of transactions
- 📊 Average revenue per transaction
- 🏆 Count of "High" commission tier sales ($1000+)

### Advanced Components
- **Dynamic transaction table** - Automatically filters and displays individual sales with product names and commission amounts
- **Visual chart** - Bar chart showing transaction breakdown by commission tier (High/Medium/Low)
- **Smart data enrichment** - Commission tiers auto-assigned based on revenue thresholds

## 🛠️ Technical Implementation

### Excel Functions & Techniques Used
- **XLOOKUP** - Pull product prices and sales rep data across tables
- **FILTER with HSTACK** - Dynamic array formula to show filtered transactions
- **SUMIFS/COUNTIFS** - Multi-criteria calculations for metrics
- **SUMPRODUCT** - Alternative approach for complex conditional sums
- **IFS** - Nested logic for commission tier assignment
- **Data Validation** - Dropdown menus with dynamic ranges
- **Dynamic Named Ranges** - Support automatic updates
- **Conditional Formatting** - Visual hierarchy and data emphasis

### Formula Complexity Highlights
```excel
// Dynamic filtered transaction table
=FILTER(HSTACK(XLOOKUP(...), ...), 
  (Table1[Sales Rep ID]=...)*
  (MONTH(Table1[Date])=MONTH(...)))

// Multi-criteria revenue calculation
=SUMIFS(Table1[Total Revenue],
  Table1[Sales Rep ID], XLOOKUP(...),
  Table1[Month], MONTH(...))
```

## 📂 Data Structure

**3 interconnected tables:**
1. **Raw Sales Data** (50+ transactions across 3 months)
   - Transaction ID, Date, Sales Rep ID, Product ID, Units Sold
   
2. **Product Master**
   - Product details, pricing, commission rates
   
3. **Sales Rep Master**
   - Rep ID to name mapping

## 🎨 Dashboard Design
- Clean, professional layout
- Color-coded sections (orange theme)
- Automatic header updates ("Summary for [Rep] during [Month]")
- Hidden helper calculations for chart data
- Single-sheet interface for easy navigation

## 💡 Skills Demonstrated
- Advanced Excel formula nesting
- Data modeling and table relationships
- Dynamic array formulas (FILTER, UNIQUE)
- Multi-criteria data aggregation
- Interactive dashboard design
- Business intelligence principles
- User experience design

## 📸 Dashboard Preview
<img width="1468" height="694" alt="dashboard-ben-december" src="https://github.com/user-attachments/assets/db3dee39-58ad-42d3-985a-d3c33bccdf46" />
<img width="1445" height="708" alt="dashboard-ana-february" src="https://github.com/user-attachments/assets/4cc98d4a-8498-4c25-a40a-9193a6535df8" />


## 🎓 Use Cases
- Sales performance tracking
- Commission calculation verification
- Monthly sales reviews
- Individual rep performance analysis
- Quick managerial insights

## 📊 Key Metrics
- Handles 4 sales reps across 3 months
- 50+ transactions with dynamic filtering
- Real-time calculations without VBA or macros
- Pure formula-driven solution

---

**Tools:** Microsoft Excel | Advanced Formulas | Data Validation | Dynamic Arrays

**Context:** Built as a mini-project demonstrating advanced Excel proficiency for business analytics applications.
```

---

## **GITHUB REPO STRUCTURE:**
```
excel-dynamic-sales-dashboard/
│
├── README.md                        
│
├── Excel-Dynamic-Sales-Dashboard.xlsx
│
├── screenshots/                       
│   ├── dashboard-ana-february.png     # Dashboard with Ana selected
│   ├── dashboard-ben-december.png     # Dashboard with Ben selected
│   ├── data-sheet.png                 # Data sheet view
│   └── product-sales-rep-tables.png   # Master tables view
|
└── project-requirements.pdf           
