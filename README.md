# SME Filtering Repository

This repository contains a Jupyter notebook that processes financial data from XHTML files and determines the size of a company based on UK Company House criteria.

## Notebook Overview

### 1. Imports
The notebook starts by importing necessary libraries and modules:
- `ixbrl_labels_2024_full` from `utils`
- `BeautifulSoup` from `bs4`
- `json`

### 2. Functions

#### `retrieve_all_ix_financial_data_minus(xhtml_content_path)`
This function retrieves financial values from an XHTML file, detects negative values, and adjusts for decimals.

- **Args:**
  - `xhtml_content_path` (str): The path to the XHTML file.
- **Returns:**
  - `dict`: A dictionary containing the financial values.

The function:
1. Reads the XHTML file.
2. Parses the content using BeautifulSoup.
3. Iterates over predefined labels to extract financial data.
4. Adjusts values based on attributes like `sign` and `decimals`.
5. Returns a dictionary of financial values.

#### `company_size(ixbrl_data)`
This function determines the size of a company based on the UK Company House criteria.

- **Args:**
  - `ixbrl_data` (dict): A dictionary containing the financial values extracted from the XHTML content.
- **Returns:**
  - `str`: The size of the company ('micro', 'small', 'medium', or 'large').

The function:
1. Defines criteria for different company sizes.
2. Extracts required data from the provided dictionary.
3. Calculates missing values if necessary.
4. Prints the financial data.
5. Determines the company size based on the criteria.

### 3. Company Size Criteria
The notebook outlines the criteria for classifying companies as micro, small, or medium-sized based on turnover, balance sheet total, and number of employees.

### 4. Load XHTML File and Retrieve iXBRL Labels
The notebook loads an XHTML file and retrieves iXBRL labels using the `retrieve_all_ix_financial_data_minus` function.

### 5. Calculate Company Size
The notebook calculates the size of the company using the `company_size` function and prints the result.

## Usage
1. Place your XHTML file in the appropriate directory.
2. Update the `file_path` variable with the path to your XHTML file.
3. Run the notebook to retrieve financial data and determine the company size.