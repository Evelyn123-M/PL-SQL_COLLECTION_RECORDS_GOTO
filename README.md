
# PL-SQL_COLLECTION_RECORDS_GOTO

# Overview

This project demonstrates the practical use of PL/SQL advanced features — specifically Collections, Records, and GOTO statements — using a simple Employee Management scenario.
The project is designed to help understand how PL/SQL structures can be used to handle complex data operations inside the Oracle Database.

# Objectives

To apply PL/SQL Collections such as Associative Arrays, VARRAYs, and Nested Tables.

To practice the use of Records — %ROWTYPE, user-defined, and cursor-based records.

To demonstrate GOTO statements for control flow (for learning purposes only).

To integrate all these features into a clean, executable PL/SQL package.

To document and execute the project in an organized repository for future reference.

Database Schema

# Table: EMPLOYEES

Stores employee data used for testing PL/SQL operations.
| Column          | Data Type    | Description                        |
| --------------- | ------------ | ---------------------------------- |
| `EMPLOYEE_ID`   | NUMBER       | Unique identifier (auto-generated) |
| `FIRST_NAME`    | VARCHAR2(50) | Employee first name                |
| `LAST_NAME`     | VARCHAR2(50) | Employee last name                 |
| `DEPARTMENT_ID` | NUMBER       | Department identifier              |
| `SALARY`        | NUMBER(10,2) | Employee salary                    |
| `HIRE_DATE`     | DATE         | Employment start date              |


# Project Structure

PLSQL_Collections_Records_GOTO_Repo/
├── README.md                  ← Project overview (this file)

├── DOCUMENTATION.md           ← Detailed explanation & assessment checklist

├── sql/
│   ├── create_schema.sql      ← Creates employees table

│   ├── seed_data.sql          ← Inserts test data

│   └── cleanup.sql            ← Drops objects after demo

├── plsql/

│   ├── examples_collections.sql ← Demonstrates arrays and bulk collect

│   ├── examples_records.sql     ← Demonstrates various record types

│   ├── examples_goto.sql        ← Shows safe GOTO usage

│   └── package_demo.sql         ← Combines logic into one package

├── tests/

│   ├── run_examples.sql        ← Runs all scripts sequentially

│   └── expected_output.txt     ← Expected DBMS_OUTPUT results

└── docs_assets/ (optional)

    └── diagrams.png
    
# Run setup scripts in order:

@sql/create_schema.sql

@sql/seed_data.sql

@plsql/examples_collections.sql

@plsql/examples_records.sql

@plsql/examples_goto.sql

@plsql/package_demo.sql

# View results:

Make sure output is enabled:

SET SERVEROUTPUT ON;

Expected outputs are stored in:

tests/expected_output.txt

# Cleanup (optional):

@sql/cleanup.sql


# Key Learning Outcomes
| PL/SQL Concept            | Demonstrated In          | Description                              |
| ------------------------- | ------------------------ | ---------------------------------------- |
| **Associative Arrays**    | examples_collections.sql | Key-value storage with string indexes    |
| **VARRAY**                | examples_collections.sql | Fixed-size, ordered collection           |
| **Nested Tables**         | examples_collections.sql | Unbounded collection supporting deletes  |
| **BULK COLLECT / FORALL** | examples_collections.sql | Efficient multi-row processing           |
| **Records (%ROWTYPE)**    | examples_records.sql     | Table-based record handling              |
| **User-defined Records**  | examples_records.sql     | Custom record structure                  |
| **Cursor-based Records**  | examples_records.sql     | Fetching data row by row                 |
| **GOTO Statements**       | examples_goto.sql        | Control flow jumps (educational purpose) |
| **Packages**              | package_demo.sql         | Encapsulation and modular design         |

# Sample Output

Assoc array - Kigali pop: 1200000

VARRAY total = 60

Nested table original elements:

  nt(1) = 5
  
  nt(3) = 15
  
BULK_COLLECT fetched 2 salary rows for dept 1

Table-based record: Alice Mugisha salary=5000

Cursor row: id=1 name=Alice salary=5000

Counter reached 3, jumping to skip_message label

Arrived at skip_message label. counter = 3

hr_demo_pkg.demo_all -> Pkg Employee salaries count=3


## ⚠️ Notes

GOTO is used here only for demonstration — avoid it in real production code.

All logic is self-contained and runs entirely inside the database (no external dependencies).

The repository can be cloned and reused for any future PL/SQL learning or demonstration tasks.

## Author & Course

## Student: Mutuyimana Evelyne
## ID:27701

## Course: PL/SQL Programming – INSY 8311

## Instructor: Mr. Eric Maniraguha

## Institution: Adventist University of Central Africa (AUCA)

## Year: 2025
