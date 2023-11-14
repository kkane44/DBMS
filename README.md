# DBMS Project: ACID Transactions on Product, Depot, and Stock

This project implements transactions in a Database Management System (DBMS) to manipulate fictitious relations - Product, Depot, and Stock. The transactions are designed to ensure the ACID properties are maintained.

## Table of Contents

1. [Description](#description)
2. [Transactions](#transactions)
3. [Schema](#schema)
4. [Usage](#usage)
5. [Installation](#installation)
6. [Contributing](#contributing)
7. [License](#license)

## Description

This DBMS class project focuses on implementing transactions that adhere to the ACID properties. The transactions involve changing the depot name in the tables and adding a new depot.

## Transactions

1. **Transaction 1: Change Depot Name**
   - Description: This transaction updates the name of a depot in the 'Depot' table.
   - Example Usage:
     ```python
     # Python code for Transaction 1
     myproject.execute("UPDATE Depot SET did = 'dd1' WHERE did = 'd1'")
     project.commit()
     ```

2. **Transaction 2: Add New Depot**
   - Description: This transaction adds a new depot to the 'Depot' table and updates related entries in the 'Product' and 'Stock' tables.
   - Example Usage:
     ```python
     # Python code for Transaction 2
     myproject.execute("INSERT INTO Depot(did, addr, volume) VALUES ('d100', 'Chicago', 100)")
     myproject.execute("INSERT INTO Stock(pid, did, quantity) VALUES ('p1', 'd100', 100)")
     project.commit()
     ```
     
## Schema

The project works with the following relations:

- **Product**
  - Attributes:
    - pid (Product ID) [Primary Key]
    - pname (Product Name)
    - price (Product Price)

- **Depot**
  - Attributes:
    - did (Depot ID) [Primary Key]
    - addr (Depot Address)
    - volume (Depot Volume)

- **Stock**
  - Attributes:
    - pid (Product ID) [Foreign Key referencing Product.pid]
    - did (Depot ID) [Foreign Key referencing Depot.did]
    - quantity (Quantity in Stock)

## Usage

1. Install the required MySQL connector in Python.
   ```bash
   pip install mysql-connector-python
