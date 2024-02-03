# Power BI Data Transformation Project

## Overview

This repository contains the steps and procedures for a Power BI data analysis project to replicate a realistic scenario. The goal is to extract, explore, clean and transform the data before setting-up a business report to present in front of a board meeting for a medium-sized international retailer. 


## Project Steps

### Task 1: Import Orders Table

### Task 2: Data Cleaning and Transformation in Power Query Editor

#### 2.1 Split Date and Time in Orders Table

- Use the Split Column feature to separate the `Order Date` and `Shipping Date` columns into date and time components.
- Remove any rows with missing or null values in the `Order Date` column.

#### 2.2 Clean and Transform Weight Column in Products Table

- Download the `Products.csv` file and import it into Power BI.
- Use the Remove Duplicates function on the `product_code` column.
- Create new columns for weight values and units using the Column From Examples feature.
- Replace blank entries in the units column with "kg."
- Convert the data type of the values column to a decimal number.
- If errors occur during conversion, replace them with the number 1.
- Create a calculated column to convert weights to kilograms if the unit is not "kg."

#### 2.3 

#### 2.4

#### 2.5 

#### 2.6 

#### 2.7 

#### 3.0 



## Contributors

- [Andrei Constantin]

Feel free to contribute or provide feedback!

