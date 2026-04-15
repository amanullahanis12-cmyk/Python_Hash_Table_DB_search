# Python_Hash_Table_DB_search

**Author:** Amanullah Anis  
**Version:** 1.0  

---

## Overview

This program loads charity organization data from a CSV file, stores it in a hash table, and provides a graphical user interface (GUI) using Tkinter. Users can:

- Filter charities by category
- View charities sorted in descending order by charitable commitment percentage
- Search for specific organizations by name

The project includes hash table operations (insert, get, remove, contains) and an insertion sort algorithm.

---

## Technologies Used

- Python 3.x
- Tkinter – GUI framework
- Pandas – CSV data processing
- Unittest – Testing framework (see `testers.py`)

---

## Features

### Hash Table Implementation (`class Hash`)
- `insert(key, value)` – adds a new key-value pair
- `get(key)` – retrieves a value by key
- `contains(key)` – checks if a key exists
- `remove(key)` – deletes a key-value pair
- `get_length()` – returns the number of elements
- `print()` – formats the hash table as a string for GUI output
- `sort()` – sorts the hash table by charitable commitment percentage (descending) using insertion sort

### Sorting Algorithm (`class Sorter`)
- Insertion sort implementation that sorts in descending order
- Used by the hash table's `sort()` method

### GUI Application (`class Preferance`)
- Category buttons – click to filter charities by category
- Search bar – look up a specific charity by name
- Text output area – displays charity data

### Data Source
- Reads from `charities.csv`

---

## CSV File Format

The program expects a file named `charities.csv` in the same folder as `main.py` with the following columns:

| Column Name |
|-------------|
| rank |
| name |
| category |
| private donations |
| total revenue |
| fundraising efficiency % |
| charitable commitment % |
| headquarter |
| total_expense |
| tot_exp_char_service |
| tot_exp_management & general |
| tot_exp_fundraising |
| surplus_loss |
| Net_Assets |
| Donor_Dependency |
| Highest_Compensation |

**Categories used in the code:**
- Domestic Needs
- International Needs
- Medical
- Youth
- Environment & Animals
- Health
- Religious
- Public Affairs
- Education
- Cultural

---

## How to Run

### Prerequisites

```bash
pip install pandas

Step 1: Clone the repository
bash

git clone https://github.com/amanullahanis12-cmyk/Python_Hash_Table_DB_search.git
cd Python_Hash_Table_DB_search

Step 2: Ensure charities.csv is in the same directory
Step 3: Run the application
bash

python main.py

Step 4: Run tests (optional)
bash

python testers.py

How It Works

    Load CSV – Pandas reads charities.csv

    Filter by category – User clicks a category button

    Group and extract – Program groups charities by category and extracts the selected one

    Build hash table – Each charity's name becomes a key, and its metrics become a list of (column, value) tuples as the value

    Sort – The sort() method extracts charitable commitment percentages and runs insertion sort (descending)

    Display – The GUI shows the sorted charities

Testing

The testers.py file contains unit tests for:

    test_Hash – tests insert, get, contains, remove, get_length, print, and sort methods

    test_Sorter – tests insertion sort in descending order

Run tests with:
bash

python testers.py

File Structure
text

Python_Hash_Table_DB_search/
├── main.py          # Main application
├── testers.py       # Unit tests
├── charities.csv    # Data file
└── README.md        # This file

Academic Honesty Statement
text

This is my own original work based on specifications issued by my instructor.
I have not used unauthorized source code, either modified or unmodified, nor used generative AI as a final draft.
I have not given other fellow student(s) access to my program.
— Amanullah Anis

Known Limitations

    Sorting only works on the charitable commitment % field

    CSV file must be named exactly charities.csv and located in the same directory

Future Improvements

    Add ability to sort by other metrics

    Allow user to choose ascending or descending order

    Add export functionality

    Improve error handling for missing files or columns
