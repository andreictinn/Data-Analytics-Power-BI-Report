# Power BI Data Transformation Project

## Overview

This repository documents the steps and procedures for a Power BI data analysis project aimed at replicating a realistic scenario. The project's objective is to extract and transform data before setting up a business report for presentation at a board meeting for a medium-sized international retailer.

## Project Steps

### Task 1: Import Orders Table - Select your respective data source

Connect to the Azure SQL Database using the provided credentials and import the Orders table into Power BI using the Get Data option.

### Task 2: Data Cleaning and Transformation in Power Query Editor

#### 2.1 Split Date and Time in Orders Table

- Use the Power Query Editor to split the `Order Date` and `Shipping Date` columns into date and time components.
- Filter out and remove any rows where the `Order Date` column has missing or null values to maintain data integrity.

#### 2.2 Clean and Transform Weight Column in Products Table

- Download the `Products.csv` file and import it into Power BI in the same way as before.
- Utilize the Remove Duplicates function on the `product code` column to ensure each product code is unique.
- Rename the columns in the dataset to match Power BI naming conventions for consistency and clarity.

#### 2.3 Connect to Azure Blob Storage for Stores Table
- Use Power BI's Get Data option to connect to Azure Blob Storage.
- Import the `Stores` table into the project using your provided credentials.
- Rename the columns in the dataset to align with Power BI naming conventions for clarity and consistency.

#### 2.4 Import Customers Data from Folder

- Download the `Customers.zip` file and unzip it on your local machine.
- Use the Get Data option in Power BI to import the Customers folder into your project.
- Utilize the Folder data connector to combine and transform the data from the three CSV files.
- Create a Full Name column by combining the [First Name] and [Last Name] columns.
- Delete any obviously unused columns (e.g., index columns) and rename the remaining columns to align with Power BI naming conventions.

#### 2.5 Remove Sensitive Column in Orders Table (if any)

- In the Power Query Editor, delete the column named [Card Number] to ensure data privacy.

#### 2.6 Additional Data Transformations (if any)

- Perform any additional data cleaning and transformation steps as needed for specific requirements.

### Task 3: Create a Data Model

- Create relationships between tables as necessary to establish a comprehensive Star Schema data model for using Time Intelligence analysis. 

#### 3.1 Create a Continuous Date Table

To leverage Power BI's time intelligence functions, create a continuous date table covering the entire time period from the earliest date in `Orders['Order Date']` to the latest date in `Orders['Shipping Date']` using your preferred DAX formula.

#### 3.2 Add Columns to Date Table

Use DAX formulas to add the following columns to your date table:

- Day of Week
- Month Number (Jan = 1, Dec = 12, etc.)
- Month Name
- Quarter
- Year
- Start of Year
- Start of Quarter
- Start of Month
- Start of Week

#### 3.3 Create Relationships in Star Schema

Form relationships between tables to create a star schema:

- `Products[product_code]` to `Orders[product_code]`
- `Stores[store code]` to `Orders[Store Code]`
- `Customers[User UUID]` to `Orders[User ID]`
- `Date[date]` to `Orders[Order Date]`
- `Date[date]` to `Orders[Shipping Date]`

Ensure the relationship between `Orders[Order Date]` and `Date[date]` is the active relationship, with one-to-many relationships.

### Task 4: Measures Table

#### 4.1 Create Measures Table

Create a separate table named "Measures Table" in Power Query Editor or DAX to manage measures effectively.

#### 4.2 Create Key Measures

Create key measures:

- Total Orders
- Total Revenue
- Total Profit
- Total Customers
- Total Quantity
- Profit YTD
- Revenue YTD

### Task 5: Hierarchies

#### 5.1 Create Date Hierarchy

Create a date hierarchy with levels:

- Start of Year
- Start of Quarter
- Start of Month
- Start of Week
- Date

#### 5.2 Create Geography Hierarchy

Create a geography hierarchy with levels:

- World Region
- Country
- Country Region

Create calculated columns for full country and geography names in the Stores table based on specific schemes.

Ensure correct data categories for columns.

### Task 6: Report Pages and Styling

#### 6.1 Create Report Pages

Create four report pages and name them as follows:

- Executive Summary
- Customer Detail
- Product Detail
- Stores Map

#### 6.2 Choose Color Theme

Decide on a color theme for your report. Power BI has pre-defined themes, which you can find in the Ribbon under the View tab. You can explore more about Power BI themes [here](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-report-themes).

#### 6.3 Design Executive Summary Page

On the Executive Summary page:

- Add a rectangle shape covering a narrow strip on the left side of the page.
- Set the fill color to a contrasting color of your choice. This will be the sidebar for navigation.

#### 6.4 Duplicate Rectangle Shape

Duplicate the rectangle shape on each of the other pages in your report.

### Task 7: Understandging Reports in Power BI

Power BI is an extremely versatile and customisable tool capable of creating tailored visuals and analysis for your professional needs. For a successful presentation, it is of paramount importance to understand what your report is meant to achieve before setting up the report to ensure you are showcasing the relevant performance indicators for your company's priorities. Displaying the wrong data can make even the most impressive report fall flat, thus choose your visuals wisely. 

### Task 7.1: Report Visuals

After ascertaining which data is relevant to your report, you can build the report. Determining the correct visuals will depend on a lot of factors and industry standards. Familiarise yourself with PowerBI reports here.  


## Contributors

- [Andrei Constantin]

Feel free to contribute or provide feedback!

