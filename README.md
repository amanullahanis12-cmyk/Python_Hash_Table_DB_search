Python_Hash_Table_DB_search

Author: Amanullah Anis
Version: 1.0
Course: Data Structures – Des Moines Area Community College (DMACC)
Overview

This program loads charity organization data from a CSV file, stores it in a custom hash table implementation (without using Python's built-in dictionary for the core structure), and provides a graphical user interface (GUI) using Tkinter. Users can:

    Filter charities by category (Domestic Needs, Medical, Youth, Education, etc.)

    View charities sorted in descending order by charitable commitment percentage

    Search for specific organizations by name

The project demonstrates hash table operations (insert, get, remove, contains) and a custom insertion sort algorithm.
Technologies Used

    Python 3.x

    Tkinter – GUI framework

    Pandas – CSV data processing

    Unittest – Testing framework (see testers.py)

Features
Hash Table Implementation (class Hash)

    Custom hash table using a dictionary backend

    insert(key, value) – adds a new key-value pair

    get(key) – retrieves a value by key

    contains(key) – checks if a key exists

    remove(key) – deletes a key-value pair

    get_length() – returns the number of elements

    print() – formats the hash table as a string for GUI output

    sort() – sorts the hash table by charitable commitment percentage (descending) using insertion sort

Sorting Algorithm (class Sorter)

    Insertion sort implementation that sorts in descending order

    Used by the hash table's sort() method to reorder charities by their charitable commitment percentage

GUI Application (class Preferance)

    Category buttons – click to filter charities by category

    Search bar – look up a specific charity by name

    Text output area – displays sorted charity data

    Displays each charity with all its metrics (fundraising efficiency, charitable commitment, etc.)

Data Source

    Reads from charities.csv (expected columns: name, category, fundraising efficiency %, charitable commitment %, etc.)

How to Run
Prerequisites
bash

pip install pandas

(Note: Tkinter comes pre-installed with most Python distributions on Windows)
Step 1: Clone the repository
bash

git clone https://github.com/amanullahanis12-cmyk/Python_Hash_Table_DB_search.git
cd Python_Hash_Table_DB_search

Step 2: Ensure charities.csv is in the same directory

The program expects a CSV file named charities.csv with the following structure (example):
name	category	fundraising efficiency %	charitable commitment %	...other columns...
Red Cross	Medical	85	90	...
Salvation Army	Religious	78	88	...
Step 3: Run the application
bash

python main.py

Step 4: Run tests (optional)
bash

python testers.py

How It Works
Data Flow

    Load CSV – Pandas reads charities.csv

    Filter by category – User clicks a category button

    Group and extract – Program groups charities by category and extracts the selected one

    Build hash table – Each charity's name becomes a key, and its metrics become a list of (column, value) tuples as the value

    Sort – The sort() method:

        Extracts all charitable commitment percentages

        Runs insertion sort (descending) on them

        Rebuilds the hash table in sorted order

    Display – The GUI shows charities ranked by charitable commitment

Example Output in GUI
text

American Red Cross- [('fundraising efficiency %', 85), ('charitable commitment %', 90), ...]

Doctors Without Borders- [('fundraising efficiency %', 82), ('charitable commitment %', 88), ...]

Sample GUI Walkthrough

    Launch the program – A window appears with category buttons, a search bar, and an output area.

    Click "Medical" – The program displays all medical charities sorted by charitable commitment (highest first).

    Search for "Red Cross" – Type the name and click "Search" to see that specific charity's full data.

    Invalid search – If the name isn't found, a popup says "Not an organization in the database."

Testing

The testers.py file contains unit tests for:

    test_Hash – verifies insert, get, contains, remove, get_length, print, and sort methods

    test_Sorter – verifies insertion sort works correctly in descending order

Run tests with:
bash

python testers.py

Expected output:
text

..
----------------------------------------------------------------------
Ran 2 tests in 0.001s

OK

What I Learned

    Implementing a hash table from scratch (collisions handled via dictionary, but logic written manually)

    Writing an insertion sort algorithm and adapting it to sort complex data structures

    Integrating Pandas with custom data structures

    Building a Tkinter GUI with buttons, text widgets, and message boxes

    Writing unit tests with Python's unittest framework

    Processing CSV data and converting it into hash table-friendly formats

    Maintaining academic honesty – no unauthorized code or generative AI for final draft

Known Limitations

    The hash table uses a Python dictionary internally – a pure implementation would use a list of lists for buckets

    Sorting only works on the charitable commitment % field (hardcoded)

    CSV file must be named exactly charities.csv and located in the same directory

    No input validation for empty CSV or missing columns

Future Improvements

    Implement true hash table with buckets (list of lists) and hash function

    Add ability to sort by other metrics (fundraising efficiency, etc.)

    Allow user to choose ascending or descending order

    Add export functionality (save filtered results to CSV)

    Improve error handling for missing files or malformed data

    Add scrollbar to output text area for large result sets

File Structure
text

Python_Hash_Table_DB_search/
├── main.py          # Main application with Hash, Sorter, and GUI classes
├── testers.py       # Unit tests for Hash and Sorter
├── charities.csv    # Data file (you must provide this)
└── README.md        # This file

Academic Honesty Statement

    This is my own original work based on specifications issued by my instructor.
    I have not used unauthorized source code, either modified or unmodified, nor used generative AI as a final draft.
    I have not given other fellow student(s) access to my program.
    — Amanullah Anis

License

This project was created for academic purposes at DMACC. Please contact the author for permission before using or distributing.
## Required CSV File Format

Create a file named `charities.csv` in the same folder as `main.py` with the following columns:

| Column Name | Data Type | Example |
|-------------|-----------|---------|
| name | string | "American Red Cross" |
| category | string | "Medical" |
| fundraising efficiency % | integer | 85 |
| charitable commitment % | integer | 90 |
| (any other columns) | any | ... |

**Valid categories in the code:**
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

**Example row:**
"Feeding America","Domestic Needs",92,95
"Red Cross","Medical",85,90
"World Wildlife Fund","Environment & Animals",88,93
