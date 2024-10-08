# mexico-housing-in-pyspark
# Real Estate Analysis with PySpark

This project analyzes real estate data from Mexico using PySpark. The analysis includes data cleaning, exploratory data analysis, and visualization of relationships between property features such as area and price. The project focuses on data from different states in Mexico, with a special emphasis on areas like Morelos and Mexico City.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Key Steps](#key-steps)
- [Visualization](#visualization)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project performs data analysis on a dataset containing real estate information in Mexico. The analysis includes:
- Cleaning and preparing the dataset.
- Calculating correlations between property area and price.
- Visualizing data distributions and relationships.
- Filtering data to focus on specific regions such as Morelos and Mexico City.

## Dataset

The dataset used in this project consists of several CSV files containing real estate data. The key columns in the dataset include:
- `state`: The state in which the property is located.
- `area_m2`: The area of the property in square meters.
- `price_usd`: The price of the property in USD.

To run this project, you need to have PySpark and Matplotlib installed. You can install these dependencies using pip:

```bash
pip install pyspark matplotlib
```

You also need a Spark environment set up. Follow the [Github Docker Spark documentation](https://github.com/josephmachado/efficient_data_processing_spark) to install PySpark.

## Usage

1. Clone the repository to your local machine:

```bash
git clone https://github.com/KaranjaNjiyo24/mexico-housing-in-pyspark.git
```

2. Navigate to the project directory:

```bash
cd mexico-housing-in-pyspark
```

3. Run the PySpark script:

```bash
mexico-housing analysis.py
```

## Key Steps

### 1. Data Loading and Cleaning
- Load the CSV files into PySpark DataFrames.
- Drop missing values and clean columns, including converting prices to numeric values.

### 2. Exploratory Data Analysis
- Calculate the mean price per square meter (`price_per_m2`) by state.
- Identify correlations between property area and price.
- Filter data for specific regions like Morelos and Mexico City for focused analysis.

### 3. Visualization
- Create scatter plots to visualize the relationship between property area and price.
- Generate bar charts to compare average prices across different states.

Example of creating a scatter plot for Mexico City:

```python
import matplotlib.pyplot as plt

# Filter the DataFrame for Mexico City
df_mexico_city = df.filter(df["state"] == "Distrito Federal")

# Convert to Pandas for visualization
df_mexico_city_pd = df_mexico_city.select("area_m2", "price_usd").toPandas()

# Create a scatter plot
plt.scatter(x=df_mexico_city_pd["area_m2"], y=df_mexico_city_pd["price_usd"])
plt.xlabel("Area [sq meters]")
plt.ylabel("Price [USD]")
plt.title("Mexico City: Price vs. Area")
plt.show()
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with any improvements or suggestions.






