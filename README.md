# 🛒 Online Retail Exploratory Data Analysis & Pipeline

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Focus](https://img.shields.io/badge/Focus-EDA%20%26%20Visualization-success)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> An end-to-end transactional data analysis pipeline on the UCI Online Retail dataset, covering data cleaning, multi-level feature engineering, statistical profiling, and 8 visualizations using NumPy, Pandas, Matplotlib, and Seaborn.

---

## 📌 Project Overview

What shopping patterns, seasonal trends, and customer segments drive real-world e-commerce revenue? This project analyzes over 500,000 real-world transnational transactions from a UK-based online retail store (UCI Machine Learning Repository) to clean raw transactional records, engineer business attributes, and uncover operational insights.

**What it does**
- 📋 Loads and inspects multi-variable transaction records (`InvoiceNo`, `StockCode`, `Quantity`, etc.)
- 🧹 Eliminates missing customer identifiers, drops duplicate records, and filters negative returns and invalid prices
- ⚙️ Engineers operational metrics: `TotalPrice`, temporal fields (`Hour`, `Month`, `DayType`), `OrderSize`, and `CustomerSegment`
- 📐 Computes core statistical indicators: central tendency (mean, median, mode) and dispersion (std dev, variance, IQR)
- 📊 Generates 8 data visualizations across Matplotlib and Seaborn (trends, distributions, boxplots, heatmaps, and pairplots)
- 💡 Synthesizes actionable business insights on geographic markets, peak shopping hours, and high-value customer cohorts

---

## 📂 Repository Contents

| File | Description |
|---|---|
| `notebooks/online_retail_eda.ipynb` | Main Jupyter Notebook with all 9 assignment tasks executed with outputs |
| `data/online_retail.xlsx` | Raw and preprocessed UCI Online Retail dataset |
| `requirements.txt` | Core library dependencies and version specifications |
| `README.md` | Complete project documentation and findings overview |

---

## 🧰 Concepts Demonstrated

`pandas` · `numpy` · `matplotlib` · `seaborn` · `data wrangling` · `missing value handling` · `feature engineering` · `datetime extraction` · `quantile binning` · `groupby aggregations` · `parametric & non-parametric statistics` · `interquartile range (IQR)` · `multi-variable visualization`

---

## 🧩 Tasks Covered

| # | Task | Technique |
|---|---|---|
| 1 | Data import & setup | `pd.read_excel()`, `.shape`, `.info()`, `.head()`, `pd.to_datetime()` |
| 2 | Data cleaning | `dropna(subset=['CustomerID'])`, `drop_duplicates()`, filtering `Quantity > 0` & `UnitPrice > 0` |
| 3 | Feature engineering | `TotalPrice = Quantity * UnitPrice`, `dt.hour`, `dt.day_name()`, `pd.cut()`, quantile spend segmentation |
| 4 | Data exploration | `.describe()`, `.value_counts()`, grouping by `Country`, `Month`, and `Description` |
| 5 | Data wrangling | Multi-level `.groupby()`, revenue aggregation, sorting top customers and markets |
| 6 | Statistical analysis | Distribution profiling: Mean, Median, Mode, Std Dev, Variance, and IQR calculation |
| 7 | Data visualization | 4 Matplotlib plots (Line, Bar, Hist, Box) + 4 Seaborn plots (Count, Violin, Heatmap, Pairplot) |
| 8 | Business insights | Synthesis of geographic demand, seasonal surges, and inventory drivers |
| 9 | GitHub repository setup | Structured directory layout, commit history, dependencies, and documentation |

---

## 📊 Results

Processed **541,909 raw records**, filtered down to **397,884 clean, authenticated transactions** across 4,338 unique customers and 37 countries.

### Top Countries by Revenue

| Rank | Country | Total Revenue (£) | % of Total Spend |
|---|---|---|---|
| 1 | **United Kingdom** | ~£6.76M | > 80% |
| 2 | **Netherlands** | ~£285k | ~3.4% |
| 3 | **EIRE (Ireland)** | ~£250k | ~3.0% |
| 4 | **Germany** | ~£221k | ~2.6% |
| 5 | **France** | ~£197k | ~2.3% |

### Key Insights
- 🇬🇧 **Geographic Concentration:** The domestic UK market generates over 80% of aggregate revenue, while European wholesale hubs (Netherlands, EIRE, Germany) lead international sales.
- ⏰ **Peak Shopping Window:** Transaction frequency peaks sharply between **11:00 AM and 2:00 PM**, identifying optimal deployment windows for promotional announcements.
- 📅 **Q4 Seasonal Surge:** Monthly gross revenue expands steadily through autumn, peaking dramatically in **November** due to holiday inventory restocking.
- 👥 **High-Value Cohort Leverage:** The top tier (*Gold* customer segment) drives the vast majority of total sales margin despite representing an equal partition of unique buyer accounts.
- 📦 **Order Composition:** Top-selling inventory items consist of low-unit-price giftware and novelty household goods purchased in bulk quantities.

---

## 📈 Visualizations Implemented (8 Plots)

| Visual | Library | Plot Type | Metric / Variable Analyzed |
|---|---|---|---|
| **Plot 1** | Matplotlib | Line Chart | Monthly sales revenue trajectory across time |
| **Plot 2** | Matplotlib | Bar Chart | Top 10 customer countries ranked by total spend |
| **Plot 3** | Matplotlib | Histogram | Transaction value distribution (`TotalPrice < £100`) |
| **Plot 4** | Matplotlib | Box Plot | Outlier detection and spread for item `UnitPrice` |
| **Plot 5** | Seaborn | Count Plot | Transaction volume distribution across days of the week |
| **Plot 6** | Seaborn | Violin Plot | Order value density across `Bronze`, `Silver`, and `Gold` segments |
| **Plot 7** | Seaborn | Heatmap | Cross-tabulated shopping density (`DayOfWeek` vs. `Hour`) |
| **Plot 8** | Seaborn | Pair Plot | Multi-variable correlations (`Quantity`, `UnitPrice`, `TotalPrice`, `Hour`) |

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone [https://github.com/hasanulazad-cloud/Data-Scientist-DS-Module---2-Module-End-Assignment.git](https://github.com/hasanulazad-cloud/Data-Scientist-DS-Module---2-Module-End-Assignment.git)
cd Data-Scientist-DS-Module---2-Module-End-Assignment

# 2. Create and activate a virtual environment
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# 3. Install required packages
pip install -r requirements.txt

# 4. Launch Jupyter Notebook
jupyter notebook notebooks/online_retail_eda.ipynb
ℹ️ The dataset can be loaded directly from data/online_retail.xlsx or downloaded directly from the UCI Machine Learning Repository via the fallback URL in the script.

⚠️ Known Limitations
Dropped Unregistered Users: Approximately 135,000 transactions without a CustomerID were omitted to preserve user-level tracking integrity, slightly depressing total reported volume.

Cancelled Orders: Cancelled orders (indicated by invoices beginning with 'C' and negative quantities) were removed rather than paired with original sales, prioritizing positive purchase behavior over return-rate modeling.

Geographic Bias: Domestic UK transactions heavily dominate the dataset, requiring logarithmic scaling or sub-sampling when analyzing non-UK international cohorts.

🔮 Future Improvements
Implement complete RFM (Recency, Frequency, Monetary) customer segmentation modeling

Build an item-based collaborative filtering recommendation engine using StockCode co-purchases

Develop a predictive classification model to forecast customer churn based on purchase interval patterns

Deploy an interactive Streamlit or Dash web dashboard for real-time exploratory slicing

👤 Author
Hasanul H Azad

Revenue Cycle Management / Healthcare Analytics Professional upskilling in Data Science, AI, and Machine Learning

GitHub: @hasanulazad-cloud

⭐ If you found this useful, consider starring the repo.
