# Meta Capstone Project: Little Lemon Restaurant Database Schema and Entity Relationship Modeling

Welcome to the readme file for the Meta Capstone Project, focused on building the Little Lemon restaurant database schema and entity relationship modeling. This document provides an overview of the project and the systems used, as well as the steps to complete the project.

## Systems Used

The following systems are utilized in the project:

1. **Git**: Version control system for tracking changes and enabling collaboration.
   - Download Git from: [https://git-scm.com/downloads](https://git-scm.com/downloads)
   - Refer to subsequent readings for installation and usage instructions.

2. **MySQL**: Database management system for storing and accessing information.
   - MySQL Workbench, command-line interface, or application clients can be used.
   - Download MySQL from: [https://dev.mysql.com/downloads/](https://dev.mysql.com/downloads/)

3. **Python**: Programming language used for communicating with the database.
   - Python is the preferred method for interacting with the MySQL database.
   - Download Python from: [https://www.python.org/downloads/](https://www.python.org/downloads/)

4. **Tableau**: Business intelligence tool for analyzing and visualizing data.
   - Tableau is used for extracting and displaying meaningful information.
   - Visit [https://www.tableau.com/](https://www.tableau.com/) for more information.

## Project Steps

Follow these steps to complete the Little Lemon Restaurant Database Schema and Entity Relationship Modeling project:

1. Set up a Git repository to manage the project code and track changes.
2. Design the database schema for the Little Lemon restaurant, considering tables, relationships, and attributes.
3. Create the necessary SQL statements to create the database and tables in MySQL.
4. Implement the database schema by executing the SQL statements in MySQL.
5. Develop a Python application to communicate with the MySQL database.
6. Write code to handle user input and update the database based on bookings and guest visits.
7. Test the Python application to ensure it correctly interacts with the database.
8. Explore the data using Tableau to extract meaningful information and generate visualizations.
9. Analyze the data in Tableau and identify patterns or trends relevant to the restaurant's operations.
10. Document the project, including the schema, SQL statements, Python code, and Tableau visualizations.
11. Update the Git repository with all project files and changes made during the development process.
12. Collaborate with others by sharing the Git repository and allowing them to review and contribute to the code.

## Exploratory Data Analysis

**Readme File - Exploratory Data Analysis for Little Lemon Sales Data**

## Introduction

In this document, we will explore the steps taken to perform an exploratory data analysis (EDA) on the Little Lemon sales data. The goal is to understand the data provided by the restaurant and prepare the data for building an Entity Relationship Model (ERM). The analysis is carried out using Python programming language and the pandas library to manipulate and analyze the data.

## Step 1: Loading the Data

The first step in the analysis is to load the data from the provided Excel file ('LittleLemon_data.xlsx') into a pandas DataFrame. The pandas library is imported at the beginning of the script to handle data manipulation.

```python
import pandas as pd
import mysql.connector

# Load data
df = pd.read_excel('LittleLemon_data.xlsx')
```

## Step 2: Initial Data Inspection

After loading the data, the next step is to perform an initial inspection to understand the structure and contents of the DataFrame.

```python
# Check for nan and attributes type
df.info()
```

The `df.info()` method provides a summary of the DataFrame, including the total number of non-null values, data types of columns, and memory usage. In this case, there are no null values in any column of the DataFrame, which is a good sign.

## Step 3: Displaying the Data

The `df.head()` method is used to display the first few rows of the DataFrame, giving us a glimpse of the data.

```python
df.head()
```

The displayed data shows the first five rows of the DataFrame, with columns representing attributes such as 'OrderID', 'OrderDate', 'DeliveryDate', 'CustomerID', 'CustomerName', 'City', 'Country', 'PostalCode', 'CountryCode', 'Cost', 'Sales', 'Quantity', 'Discount', 'DeliveryCost', 'CourseName', 'CuisineName', 'StarterName', 'DesertName', 'Drink', and 'Sides'. These attributes correspond to the features of the sales data.

## Step 4: Cleaning and Preparing the Data

### Column Name Cleaning

To ensure consistency and avoid potential issues during data processing, the column names are cleaned by removing any leading/trailing white spaces and replacing spaces with underscores.

```python
df.columns = [column.strip().replace(' ', '') for column in df.columns]
```

This step helps in accessing columns using clean, standardized names.

## Step 5: Understanding the Data's Uniqueness

To gain insights into the uniqueness of data in each column, we can use the `df.nunique()` method. This will provide the count of unique values in each column.

```python
df.nunique()
```

The output of the above code snippet gives us the count of unique values for each column in the DataFrame. For example, 'OrderID' has 1000 unique values, 'OrderDate' has 700 unique values, 'DeliveryDate' has 666 unique values, and so on. This information helps us understand the cardinality of each attribute and will be useful while designing the Entity Relationship Model.

## Conclusion

In this exploratory data analysis, we successfully loaded the Little Lemon sales data, inspected its structure, cleaned the column names, and explored the uniqueness of each attribute. This preliminary analysis prepares us for the next steps, such as building an Entity Relationship Model (ERM) and conducting further data analysis and visualization to gain deeper insights from the data.

The cleaned and analyzed data can be used for various purposes, including business intelligence, data mining, and machine learning tasks, to drive better decision-making and understand customer behavior and preferences. The cleaned dataset is now ready for further data modeling and analysis.

## Entity-Relationship Diagram (ERD) Analysis

Based on the provided sales data, we can define the columns and possible data types for the entity relation diagram (ERD) for the "littleLemon" project. Below is the description of the columns and their respective data types:

1. Order ID (Data Type: String)
   - Unique identifier for each order.

2. Order Date (Data Type: Date)
   - The date when the order was placed.

3. Delivery Date (Data Type: Date)
   - The date when the order was delivered.

4. Customer ID (Data Type: String)
   - Unique identifier for each customer.

5. Customer Name (Data Type: String)
   - The name of the customer who placed the order.

6. City (Data Type: String)
   - The city where the customer is located.

7. Country (Data Type: String)
   - The country where the customer is located.

8. Postal Code (Data Type: String)
   - The postal code of the customer's location.

9. Country Code (Data Type: String)
   - The country code of the customer's location.

10. Cost (Data Type: Decimal)
    - The cost of the order.

11. Sales (Data Type: Decimal)
    - The sales amount for the order.

12. Quantity (Data Type: Integer)
    - The quantity of items ordered.

13. Discount (Data Type: Decimal)
    - The discount applied to the order.

14. Delivery Cost (Data Type: Decimal)
    - The cost of delivery.

15. Course Name (Data Type: String)
    - The name of the course item ordered (e.g., "Greek salad", "Bean soup").

16. Cuisine Name (Data Type: String)
    - The name of the cuisine associated with the ordered item (e.g., "Greek", "Italian", "Turkish").

17. Starter Name (Data Type: String)
    - The name of the starter item ordered.

18. Dessert Name (Data Type: String)
    - The name of the dessert item ordered.

19. Drink (Data Type: String)
    - The name of the drink ordered.

20. Sides (Data Type: String)
    - The name of the side dish ordered.

Now, let's build the Entity Relationship Diagram (ERD) for the "littleLemon" sales data: 

In the above ERD:
- The "Orders" table represents information about each order made by customers.
- The "Customers" table stores information about the customers who placed the orders.
- The "Course", "Starter", "Desert", "Drink", and "Sides" tables store information about different types of items that can be ordered as part of a course, starters, desserts, drinks, and side dishes, respectively.
- The "Course" table is related to the "Orders" table through the "CourseName" column.
- Each item in the "Course" table has a name that corresponds to the "CourseName" column in the "Orders" table.
- The other item tables ("Starter", "Desert", "Drink", and "Sides") follow a similar relationship pattern with the "Orders" table.

Please note that the ERD provided here assumes a one-to-many relationship between orders and the course, starters, desserts, drinks, and sides. It also assumes that each order is associated with a single customer. The ERD can be expanded or modified based on additional requirements and relationships present in the data.