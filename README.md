# Task 4
This repo contains all the data necessary to get started on task 4, good luck!
# Shipping Data Processor

This project processes shipping data from multiple CSV files and populates a SQLite database with the extracted information.

## Features

- Reads shipping data from three CSV files:
  - `shipping_data_0.csv`
  - `shipping_data_1.csv`
  - `shipping_data_2.csv`
- Populates a SQLite database with:
  - Product information
  - Shipment details
- Ensures no duplicate products or shipments are inserted into the database.

## Prerequisites

- Python 3.6 or higher
- SQLite3
- Required Python packages:
  - `sqlite3` (built-in)
  - `csv` (built-in)

## Project Structure
data population task for the Walmart shipping database.

Part 1: Data Acquisition
I forked and cloned the repository containing all relevant shipping spreadsheets and the SQLite database from this link
.

Part 2: Database Population
I wrote a Python script to read, transform, and insert data from the spreadsheets into the SQLite database:

Each row from the spreadsheets was read and relevant data extracted.

Data was formatted to match the database schema.

Spreadsheet 0 was inserted directly into the database, as it was self-contained.

For spreadsheets 1 and 2, I combined rows based on the shipping identifier, calculated the quantity of goods per shipment, and added a row for each product with the corresponding origin and destination information.

All data was successfully inserted into the database, and the script handled interdependent spreadsheets correctly, ensuring the database is fully populated and consistent.
# Shipping Data Processor

This project processes shipping data from multiple CSV files and populates a SQLite database with the extracted information.

## Features

- Reads shipping data from three CSV files:
  - `shipping_data_0.csv`
  - `shipping_data_1.csv`
  - `shipping_data_2.csv`
- Populates a SQLite database with:
  - Product information
  - Shipment details
- Ensures no duplicate products or shipments are inserted into the database.

## Prerequisites

- Python 3.6 or higher
- SQLite3
- Required Python packages:
  - `sqlite3` (built-in)
  - `csv` (built-in)

## Project Structure

Workspace
(rerun without)
Still building the workspace index, response may be less accurate.

Here is a sample README.md for your project:

├── README.md
├── data
│   ├── shipping_data_0.csv
│   ├── shipping_data_1.csv
│   └── shipping_data_2.csv
├── script.py
├── shipment_database.db
└── venv
    ├── bin
    ├── include
    ├── lib
    └── pyvenv.cfg


## Usage

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>

python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

python script.py

The script will:

Read data from the data/ folder.
Populate the shipment_database.db SQLite database.
Database Schema
The database contains two tables:

product

id (INTEGER, Primary Key)
name (TEXT, Unique)


shipment

id (INTEGER, Primary Key)
product_id (INTEGER, Foreign Key to product.id)
quantity (INTEGER)
origin (TEXT)
destination (TEXT)

Example Output
inserted product 1 from shipping_data_0
inserted product 2 from shipping_data_0
inserted product 0 from shipping_data_1
inserted product 1 from shipping_data_1
