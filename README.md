# ✈️ Airlines Data Pipeline

[![Python](https://img.shields.io/badge/Python-3.13%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-green.svg)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## 📋 Project Overview

A complete ETL (Extract, Transform, Load) data pipeline for airline operations analytics. This project demonstrates a production-ready data engineering solution with:

- **3-Layer Medallion Architecture** (Bronze → Silver → Gold)
- **Data Quality Validation** with quarantine handling
- **PII Protection** using SHA-256 hashing and masking
- **Star Schema** for business intelligence
- **Comprehensive KPIs** for airline analytics

## 🚀 Quick Start

### Prerequisites
Python 3.13+
Jupyter Notebook
Installation
# Clone or download the project
git clone <repository-url>
cd airlines-pipeline

# Install dependencies
pip install -r requirements.txt
Run the Pipeline
bash
jupyter notebook
# Open Use_Case_Airlines.ipynb
# Run all cells sequentially
📊 Key Results
Metric	Value
Total Revenue	$7,385,142.98
Average Ticket Price	$8,009.92
Cancellation Rate	30.46%
Total Flights	272
Average Duration	164.62 mins (2.74 hrs)
Data Quality	97.3% clean records
🏗️ Architecture
text
┌─────────────────────────────────────────────────────────────────┐
│                       Medallion Architecture                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  📥 BRONZE LAYER        🔄 SILVER LAYER       📊 GOLD LAYER    │
│  ┌─────────────┐       ┌─────────────┐       ┌─────────────┐  │
│  │ Raw Data    │ ────► │ Cleaned     │ ────► │ Business    │  │
│  │ + DQ Flags  │       │ Data        │       │ Ready Data  │  │
│  │ + Errors    │       │ + PII       │       │ + KPIs      │  │
│  └─────────────┘       └─────────────┘       └─────────────┘  │
│                                                                 │
│  Validation Engine    Transformation Engine   Star Schema      │
│  - PK Checks          - Duration Calc        - Dimensions     │
│  - Type Checks        - Overnight Handling   - Fact Table     │
│  - Rule Checks        - Airline Imputation   - Aggregations   │
│                       - PII Masking                            │
└─────────────────────────────────────────────────────────────────┘

## 📁 Project Structure

### Core Files
- `Use_Case_Airlines.ipynb` - Main pipeline notebook
- `UseCase - Airlines.xlsx` - Source data
- `requirements.txt` - Python dependencies
- `README.md` - Project documentation
- `LICENSE.txt` - MIT License

### Documentation
- `Documentation/Airlines_Data_Pipeline_Documentation.docx`

### Storage Layers
- `storage/bronze/` - Raw validated data
- `storage/silver/` - Cleaned masked data
- `storage/gold/` - Business ready data
- `storage/quarantine/` - Invalid records

### Dashboards
- `Dashboards/1.Duration_analysis.png`
- `Dashboards/2.Route_performance.png`
- `Dashboards/3.Airline_Trends.png`
- `Dashboards/4.Delay&Anamoloy.png`



🔒 Privacy & Security
PII Protection Methods
Field	Protection	Method
Email	Masking	j****e@domain.com
Phone	Masking	****3210
Aadhaar ID	Hashing	SHA-256
Passport	Hashing	SHA-256
Access Control
Bronze Layer: Data Engineering Team
Silver Layer: Analytics Team

Gold Layer: Business Users
## 📈 Business KPIs

### Route Performance

| Route | Bookings | % of Total |
|-------|----------|------------|
| CCU → DEL | 267 | 20.86% |
| DEL → BOM | 210 | 16.41% |
| MAA → BOM | 187 | 14.61% |
| BOM → CCU | 172 | 13.44% |
| DEL → HYD | 104 | 8.13% |
| Others | 340 | 26.55% |
| **Total** | **1,280** | **100%** |
Payment Distribution
UPI: Highest Usage

CARD: Medium Usage

NETBANKING: Lowest Usage

🛠️ Technology Stack
Component	Technology
Language	Python 3.13+
Data Processing	Pandas, NumPy
Storage	CSV Files
PII Protection	hashlib (SHA-256)
Development	Jupyter Notebook
Documentation	Markdown/Word



## 📊 Data Quality Summary

| Entity | Total | Clean | Quarantined | Quality Rate |
|--------|-------|-------|-------------|--------------|
| Flights | 1,020 | 1,020 | 0 | 100% |
| Bookings | 1,000 | 970 | 30 | 97% |
| Passengers | 1,039 | 1,039 | 0 | 100% |
| Payments | 1,000 | 922 | 78 | 92.2% |
| **Total** | **4,059** | **3,951** | **108** | **97.3%** |
🔄 Data Flow
text
Source Excel → Bronze (DQ) → Silver (Transform) → Gold (Model) → BI
📝 Assumptions
Data Quality Assumptions
Flight IDs are unique identifiers

Airline names can be inferred from flight ID prefixes

Overnight flights exist (arrival < departure)

All timestamps are in same timezone

Booking status values are standardized

Business Logic Assumptions
Cancellation Rate = (Cancelled / Total) × 100

Total Revenue = Sum of all payments

Average Ticket Price = Total Revenue / Number of Bookings

Market Share = (Airline Flights / Total Flights) × 100

Reference Date for Age = 2026-09-05

🧪 Testing
Run the pipeline and verify:

Bronze layer has 4 CSV files with validation flags

Quarantine folder contains invalid records

Silver layer has masked PII fields

Gold layer has star schema tables

KPIs match expected values

🚧 Future Enhancements
□ Apache Spark integration for scalability
□ Real-time streaming with Kafka
□ Automated data quality monitoring
□ Interactive dashboards with Power BI/Tableau
□ Machine learning for demand forecasting
□ Dynamic pricing optimization
□ Customer segmentation analysis
📄 License
This project is for educational and demonstration purposes.

🤝 Contributing
Please read CONTRIBUTING.md for details on our code of conduct and the process for submitting pull requests.


Documentation: See /Documentation/Airlines_Data_Pipeline_Documentation.docx

Version: 1.0
Last Updated: September 6, 2026
Status: Production Ready 

⭐ Quick Links
Architecture Diagram

Data Flow Diagram

Star Schema

Full Documentation

Source Code
