# US County Unemployment Rate Analysis

An exploratory data analysis of monthly unemployment rates for US counties from 1990 to 2016, done in Python with Pandas. The goal was to see how unemployment changed over time and how much it varied between states, counties, months and recession periods.

## Dataset

The data comes from a nested JSON file (`result.json`) organised by year, month, state and county. The file is too large for this repository, so it is hosted on Kaggle: [US Unemployment Rate Analysis dataset](https://www.kaggle.com/datasets/manishamali/us-unployment-rate-analysis). After flattening it there are 885,548 monthly records covering 2,885 counties in 47 states. Alaska, Florida and Georgia are not part of the dataset.

## Data Cleaning

* Flattened the JSON into a table and skipped the yearly averages
* Trimmed extra spaces and fixed data types
* Checked for missing values, invalid months, rates outside 0 to 100 and exact duplicate rows (none were found)
* Created a proper date column and kept months in calendar order
* Kept the very high and zero rates since they are real values from small counties
* Counted records that are missing from the source (about 49,000 county months, mostly in Louisiana and Texas). These were not imputed because most of them are full missing years.

## What I Looked At

* Data coverage by state
* Average unemployment over time with recession periods highlighted
* States with the highest and lowest average unemployment
* Monthly seasonality
* Top 15 highest county unemployment rates
* Gap between the highest and lowest county rates within each state

## Key Findings

* Nebraska had the lowest average unemployment (3.11%) and Arizona the highest (9.27%)
* January had the highest average rate (7.22%) and October the lowest (5.47%)
* The highest monthly average was 10.6% in January 2010, right after the Great Recession, and the lowest was 3.76% in October 2000
* San Juan County, Colorado hit 58.4% in January 1992, the highest value in the data, and Starr County, Texas stayed above 40% for much of 1990 to 1993
* Differences between counties were widest in 1992 and narrowest in 2007
* 41 of the 47 states have complete data, while Louisiana only has about 31% coverage

## Tools

Python, Pandas, Matplotlib, Seaborn, Jupyter Notebook

## How to Run

Download `result.json` from the Kaggle link above, install `pandas`, `matplotlib` and `seaborn`, update the file path in the first code cell, then run the notebook. You can also run it directly on Kaggle by adding the dataset to a notebook there.
