# Data Analyst Project | Correlation in Python

This project aims to demonstrate how to analyze the correlation between different numeric variables in a dataset using Python. The dataset used in this project contains movie information, and the analysis focuses on exploring relationships between various numeric features such as budget and gross earnings.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [License](#license)

## Project Overview

In this project, we perform the following tasks:
1. Load and preprocess the dataset.
2. Identify and handle missing values.
3. Convert columns to appropriate data types.
4. Calculate and visualize the correlation matrix using a heatmap.

## Technologies Used

- Python
- Pandas
- Seaborn
- Matplotlib

## Installation

To run this project locally, you need to have Python installed. Then, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/Data-Analyst-Project-Correlation-Python.git
    cd Data-Analyst-Project-Correlation-Python
    ```

2. Create a virtual environment:
    ```bash
    python -m venv env
    source env/bin/activate  # On Windows, use `env\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Make sure your dataset (movies.csv) is in the project directory.
2. Run the Python script:
    ```bash
    python main.py
    ```

The script will load the dataset, preprocess the data, calculate the correlation matrix, and display a heatmap.

### Sample Code

Here is a snippet of the main analysis code:

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the data
df = pd.read_csv('movies.csv')

# Handle missing values
df['budget'] = df['budget'].fillna(0).astype('int64')
df['gross'] = df['gross'].fillna(0).astype('int64')

# Select numeric columns
numeric_df = df.select_dtypes(include=['int64', 'float64'])

# Calculate the correlation matrix
correlation_matrix = numeric_df.corr()

# Create a heatmap
plt.figure(figsize=(12, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.show()
