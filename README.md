# Lab Submission: SQL Data Selection and Transformation with Python

This repository contains my completed submission for the Module 9 Lab: SQL SELECT Statements. The goal of this lab is to demonstrate my ability to retrieve and transform data from a SQLite database using SQL queries embedded in Python via the `pandas.read_sql()` method. I followed all lab steps and used feature branches and Pull Requests for each step to ensure clean, testable commits.

## Features

- Connection to `data.sqlite` using `sqlite3` and `pandas`.
- SQL queries for:
  - Selecting specific columns and filtering results.
  - Aliasing and using `CASE` for conditional logic.
  - Using SQL built-in string and numeric functions like `LENGTH()`, `SUBSTR()`, and `SUM()`.
  - Parsing date values using `STRFTIME()` into day, month, and year components.
- Each transformation is assigned to a clearly named variable (e.g., `df_executive`, `sum_total_price`) in `main.py`.
- All tests in `test_main.py` pass successfully using `pytest`.

## Environment

- Python 3.8.x (tested locally with 3.8.13)
- macOS terminal using `pipenv` for virtual environment and dependency management

## Setup

Clone the repo and navigate to the project directory:

```bash
git clone <https://github.com/walbeck85/se_sql_select_lab>
cd se_sql_select_lab
```

Install dependencies and activate the shell:

```bash
pipenv install
pipenv shell
```

If you don’t have `pipenv` installed, you can install it globally with:

```bash
pip install pipenv
```

## File structure

```
.
├── Pipfile
├── Pipfile.lock
├── README.md
├── data.sqlite
├── main.py
└── test_main.py
```

## How to run the file

Use `python3 main.py` to print preview data from the database:

```bash
python3 main.py
```

This prints:
- A full table preview of all employees (Step 1)
- Other debug print statements as needed for step validation (may be commented out for cleanliness)

## How to run tests

Use `pytest` to validate each step:

```bash
pytest
```

Or stop after the first failure:

```bash
pytest -x
```

You should see 9 tests pass, confirming that all steps have been implemented correctly.

## Rubric alignment

- **SQL connection and selection**: Successfully connected to the database using `sqlite3`.
- **Querying specific columns**: Used `SELECT` with column filtering (`employeeNumber`, `lastName`, etc.).
- **Aliasing**: Applied `AS` to rename columns (e.g., `employeeNumber AS ID`).
- **CASE statements**: Correctly used to define executive roles.
- **String functions**: `LENGTH(lastName)` and `SUBSTR(jobTitle, 1, 2)` used correctly.
- **Numeric aggregation**: Used `SUM(ROUND(priceEach * quantityOrdered))` to compute order totals.
- **Date parsing**: Used `STRFTIME('%d', orderDate)` and similar for `day`, `month`, and `year`.

## Branch and PR Workflow

All work was performed in isolated feature branches (e.g., `alias-employee-id`, `exec-case-role`, `extract-day-month-year`), and merged to `main` only after successful local testing.

Each PR included:
- Step-specific code
- Verified test pass before merge
- Clean up of debug output when appropriate

## Instructor checklist

- Clone the repo and install with `pipenv`.
- Run `python3 main.py` to confirm the SQLite connection and optional data previews.
- Run `pytest` to confirm all 9 steps are passing.
- Optional: Review SQL queries and transformation logic in `main.py`.