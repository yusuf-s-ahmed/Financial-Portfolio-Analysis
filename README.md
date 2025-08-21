## Analysing a portfolio of assets based in UK energy and financial markets with investment recommendations

This project evaluates a diversified investment portfolio consisting of UK energy and financial stocks (BP, Shell, HSBC, Barclays), ETFs (FTSE 100, S&P 500), and UK 10-year government bonds. Historical price data and macroeconomic indicators, including GDP, commodity prices were collected, cleaned, and queried using SQL for filtering.

### Table of Contents

- [Portfolio Simulation](#portfolio-weights-simulation)
- [Features](###features)
- [Data Sources](###data-sources)
- [Technology Stack](###technology-stack)
- [Quick Start Guide](###quick-start-guide)
- [Sample SQL Queries](###sample-sql-queries)
- [Key Insights](###key-insights)
- [Challenges and Solutions](###challenges-and-solutions)
- [Impact](###impact)

### Portfolio Weights Simulation

- UK Financial Markets (HSBC, Barclays) - 30%
- UK Energy Markets (BP, Shell) - 20%
- FTSE 100 - 10%
- S&P 500 - 40%

### Features

- **Data Cleaning**: Processes raw CSV files into cleaned datasets
- **Data Analysis**: SQL-based queries for financial insights
- **Visualisation**: Graphs and charts for market trends and portfolio performance
- **Automation**: Python scripts for data processing and analysis

### Data Sources

The following datasets are used in this project:

Stock Prices (sourced from Yahoo Finance):
- S&P 500
- FTSE 100
- Barclays
- HSBC
- Shell

Economic Indicators:

- UK Consumer Price Index (CPI) — Federal Reserve Economic Data (FRED)
- UK Unemployment Rate (FRED)
- UK GDP - World Bank

Portfolio Metrics:
- Calculated within this project based on stock and economic data

## Technology Stack

| Component            | Tools and Libraries                       |
|---------------------|--------------------------------------------|
| Data Processing      | Pandas, NumPy, Python                     |
| Data Storage         | CSV files                                 |
| Visualisation        | Excel                                     |
| Development          | Jupyter Notebook, Python virtual environment |

## Quick Start Guide

### Prerequisites

- Python 3.8+
- Jupyter Notebook
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/yusuf-s-ahmed/Financial-Portfolio-Analysis.git
cd portfolio-analysis
```

### 2. Create Virtual Environment

```bash
python -m venv venv
# On Windows
venv\Scripts\activate
# On Linux/Mac
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run Jupyter Notebook

```bash
jupyter notebook
```

## Sample SQL Queries

### 1. Average S&P 500 Price by Year

```sql
SELECT 
    strftime('%Y', date) AS year,
    AVG(price) AS avg_price
FROM sp500
GROUP BY year
ORDER BY year;
```

### 2. Monthly FTSE 100 Trends

```sql
SELECT 
    strftime('%Y-%m', date) AS month,
    AVG(price) AS avg_price
FROM ftse100
GROUP BY month
ORDER BY month;
```

### 3. Barclays Price Analysis

```sql
SELECT 
    date,
    price
FROM barclays
WHERE price > 150
ORDER BY date DESC;
```

### 4. Portfolio Metrics Summary

```sql
SELECT 
    AVG(metric1) AS avg_metric1,
    AVG(metric2) AS avg_metric2
FROM portfolio_metrics;
```

## Key Insights

| Dataset              | Key Insight                                |
|---------------------|--------------------------------------------|
| S&P 500             | Historical price trends over the years     |
| FTSE 100            | Monthly average price fluctuations         |
| Barclays            | Significant price movements                |
| Portfolio Metrics   | Summary statistics for portfolio performance |

## Challenges and Solutions

| Challenge                         | Solution                                                       |
|----------------------------------|----------------------------------------------------------------|
| Data Cleaning                    | Automated scripts for handling missing values and outliers     |
| Large Datasets                   | Optimised data processing with Pandas                          |
| Visualisation                    | Created clear and informative charts                           |

## Impact

This project provides a comprehensive analysis of financial data, enabling better decision-making and insights into market trends and portfolio performance.

## Troubleshooting

1. **Missing Dependencies**: Ensure all packages are installed in your virtual environment.
2. **Data File Issues**: Verify that all CSV files are in the `output-data` folder.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.