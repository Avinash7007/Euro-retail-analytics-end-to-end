# 📊 Euro Retail Analytics | Data Cleaning & Ingestion (Layer 1)

This project focuses on **data cleaning and ingestion using Python (Pandas)** for a retail dataset.  
It prepares raw data for further transformation in SQL Server and visualization in Power BI.

---

## 📁 Project Structure

Euro_Retail/  
├── notebooks/  
│   └── 01_data_cleaning_and_load.ipynb  (Layer 1: Data cleaning & ingestion)  
│  
├── data/  
│   └── raw/                            (Store raw CSV files here)  
│  
├── README.md                           (Project documentation)  
├── requirements.txt                    (pip install -r requirements.txt)  
├── .env.example                        (Connection string template)  
└── .gitignore                          (Ignore .env, raw data files)  

---

## ⚙️ What This Layer Does

- Handles missing values (null treatment)  
- Cleans inconsistent data  
- Standardizes formats (dates, columns)  
- Prepares structured datasets for SQL layer  

---

## 👤 Author

**Avinash Dubey**  
Data Analyst | 3+ Years Experience  
SQL | Python | Power BI | Data Modeling | ETL  

---

## 📌 Notes

- Put all CSV files inside: `data/raw/`  
- Raw data is not pushed to GitHub (ignored via `.gitignore`)  
- This is the first step of a larger data pipeline  

---

## 🚀 Setup

- Clone repo  
- Open project folder  
- Run: `pip install -r requirements.txt`  
- Open notebook and execute  

---

## 🏷️ Tech Stack

- Python (Pandas, NumPy)

---

## 📊 Next Steps

- SQL Server data modeling (Layer 2)  
- Power BI dashboard (Layer 3)  
