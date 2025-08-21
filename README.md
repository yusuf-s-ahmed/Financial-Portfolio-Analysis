# Portfolio Analysis

This project analyses financial data from various sources, including stock prices, economic indicators, and portfolio metrics. The data is processed and visualized to provide insights into market trends, portfolio performance, and economic conditions.

## Example Data Visualisation

This is a sample dashboard using the cleaned data in the `output-data` folder.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Data Sources](#data-sources)
- [Technology Stack](#technology-stack)
- [Quick Start Guide](#quick-start-guide)
- [Sample SQL Queries](#sample-sql-queries)
- [Key Insights](#key-insights)
- [Challenges and Solutions](#challenges-and-solutions)
- [Impact](#impact)

## Overview

This project processes and analyses financial data from multiple sources, including stock prices, economic indicators, and portfolio metrics. The data is cleaned, transformed, and stored in a structured format for analysis and visualisation.

## Features

- **Data Cleaning**: Processes raw CSV files into cleaned datasets
- **Data Analysis**: SQL-based queries for financial insights
- **Visualisation**: Graphs and charts for market trends and portfolio performance
- **Automation**: Python scripts for data processing and analysis

## Data Sources

The following datasets are used in this project:

1. **Stock Prices**:
   - S&P 500: `output-data/S_and_P_500_cleaned.csv`
   - FTSE 100: `output-data/FTSE_100_cleaned.csv`
   - Barclays: `output-data/Barclays_cleaned.csv`
   - HSBC: `output-data/HSBC_cleaned.csv`
   - Shell: `output-data/Shell_cleaned.csv`

2. **Economic Indicators**:
   - UK CPI: `output-data/uk_cpi_cleaned.csv`
   - UK GDP: `output-data/uk_gdp_cleaned_usd.csv`
   - UK Unemployment: `output-data/uk_unemployment_cleaned.csv`

3. **Portfolio Metrics**:
   - `output-data/portfolio_metrics_cleaned.csv`

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
| Large Datasets                   | Optimized data processing with Pandas                          |
| Visualization                    | Created clear and informative charts                           |

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