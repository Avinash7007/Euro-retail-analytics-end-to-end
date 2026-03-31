# 🛒 EuroRetail Insights Platform

End-to-end retail analytics pipeline: **Python → SQL Server → Power BI**

---

## 📐 Project Architecture

```
┌─────────────────────────────────────────────────────────────────────────┐
│                     EuroRetail — 3-Layer Pipeline                       │
│                                                                         │
│  ✅ Layer 1 — PYTHON          ⏳ Layer 2 — SQL        ⏳ Layer 3 — BI  │
│  ┌────────────────────┐       ┌──────────────────┐   ┌──────────────┐   │
│  │  Data Cleaning     │  ───► │  SQL Server      │ ► │  Power BI    │   │
│  │  + Load to SQL     │       │  Stored Procs    │   │  Dashboard   │   │
│  │  (DONE ✅)         │       │  Views / DDL     │   │  Reports     │   │
│  └────────────────────┘       └──────────────────┘   └──────────────┘   │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 📁 Repository Structure

```
Euro_Retail/
│
├── notebooks/
│   └── 01_data_cleaning_and_load.ipynb   ← Layer 1 (DONE ✅)
│
├── data/
│   └── raw/                              
│       ├── dim_customer.csv
│       ├── dim_date.csv
│       ├── dim_product.csv
│       ├── dim_store.csv
│       ├── fact_sales.csv
│       ├── fact_returns.csv
│       └── fact_shipments.csv
│
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

---

## ✅ Layer 1 — Python: Data Cleaning & SQL Load (COMPLETE)

**Notebook:** `notebooks/01_data_cleaning_and_load.ipynb`

### Tables Processed

| Table | Cleaning Applied |
|---|---|
| `dim_customer` | Null `customer_name` / `city` → filled with sentinel strings |
| `dim_date` | `date` column cast to `datetime64` |
| `dim_product` | No nulls — validated clean |
| `dim_store` | No nulls — validated clean |
| `fact_sales` | Dropped derived cols; rows with null `order_date` dropped |
| `fact_returns` | Rows with null `return_date` dropped; null `refund_amount` → 0 |
| `fact_shipments` | Null `ship_cost` imputed with mean; rows with null `ship_date` dropped |

### Flow
```
CSV Files → Load Raw → Clean Each Table → Load Clean Data to SQL Server
```

---

## ⚙️ Setup

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Configure environment
```bash
cp .env.example .env
# Edit .env — set DATA_FOLDER path and SQL Server connection string
```

### 3. Place raw CSVs in `data/raw/`

### 4. Open and run the notebook
```bash
jupyter notebook notebooks/01_data_cleaning_and_load.ipynb
```

---

## ⏳ Coming Next

- **Layer 2 — SQL Server:** DDL, stored procedures, views, star schema
- **Layer 3 — Power BI:** KPI dashboard, sales / returns / shipments reports

---

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| Data Cleaning | Python 3.x · pandas · Jupyter Notebook |
| Database | SQL Server · SQLAlchemy · pyodbc |
| Reporting | Power BI *(coming soon)* |

## 👤 Author

**Avinash Dubey**  
Data Analyst | 3+ Years Experience  
SQL | Python | Power BI | Data Modeling | ETL  
