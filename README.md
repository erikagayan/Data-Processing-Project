# Data Processing Project

## Overview

This project demonstrates an application focused on SQL knowledge, data processing, and proficiency with the pandas library.

## Project Description

The main task of this project was to manipulate a .csv data file (db_table.csv), treating it as a database table for data processing. The focus was on query optimization and avoiding unnecessary database connections. Additional columns were added to the output data, adhering to the principle of not altering the original dataset.

## Technologies Used

- **Pandas**: For reading and processing data from the .csv file.
- **pandasql**: For executing SQL-like queries on DataFrames.

## Implementation

### Steps:

1. **Data Reading**: Utilizing `pandas.read_csv('db_table.csv')` to load data into memory.
2. **Data Processing**: Appending extra columns `bitCode` and `siCode` based on specific requirements.
3. **Query Formulation**: Developing functions for transforming input data into General code1 and General code2 formats.
4. **Response Generation**: Constructing dictionaries to catalogue possible query combinations and their respective data sources.

### Sample Code:

```python
import pandas as pd

# Reading and initial data processing
df = pd.read_csv("db_table.csv", index_col=[0])
df['bitCode'] = df['source'].apply(calculate_bitcode)
df['siCode'] = df.apply(lambda row: calculate_sicode(row['bitCode'], row['code3']), axis=1)

# Functions for code transformation and query creation
def transform_G_code1(G_code1):
    return G_code1

def transform_G_code2(G_code2):
    return G_code2.split("/")[0] if "/" in G_code2 else G_code2

# Generating responses
grouped_data_dict = {}
# [Continuation of code for processing requests]
