# Customer Call List - Data Cleaning Project

This repository showcases data cleaning and preparation workflows for an unstructured customer call database using Python and Pandas inside a Jupyter Notebook environment.

The project pipeline converts a messy, raw customer contact log filled with duplicates, structural formatting issues, missing records, and non-standardized responses into a pristine, actionable call sheet.

## Raw Dataset Challenges Handled:
* **Duplicate Rows:** Multiple entries logged for identical customers (e.g., duplicate rows for Anakin Skywalker).
* **Corrupted Text Names:** Non-alphanumeric punctuation and structural notation mixed into strings (e.g., `/White`, `...Potter`, `Flenderson_`).
* **Non-Standard Phone Formats:** Mixed usage of string separators (`123-545-5421`, `123/643/9775`, `876|678|3469`).
* **Messy Address Strings:** Single-string entries compounding street address lanes, states, and postal zip codes together.
* **Ambiguous Values:** Mixed answers (`Yes`, `Y`, `No`, `N`, `N/a`) describing single attributes.

## Core Cleaning Pipeline Steps:
1. **Deduplication:** Dropped identical rows based on unique `CustomerID` tracking numbers.
2. **Feature Selection:** Erased background descriptive metrics like `Not_Useful_Column` to lower feature clutter.
3. **String Stripping:** Standardized columns using `.str.strip()` to clear leading slashes, dots, and trailing underlines from names.
4. **Regex Phone Extraction:** Implemented regular expression patterns (`r'\D'`) to scrub slashes and dashes out of call columns.
5. **Address Parsing:** Segregated complex single-string locations out into separate columns for `Street_Address`, `State`, and `Zip_code`.
6. **Value Re-mapping:** Standardized inconsistent flags uniformly to simple `Y` and `N` codes.
7. **Missing Value Resolution:** Filled trailing `NaN`, `pd.NA`, and `N/a` strings with a blank character to safeguard script runtime loops.
8. **Compliance Filtering:** Cleaned out rows tracking phone calls matching `Do_Not_Contact == 'Y'` or lacking a viable telephone number entirely.

## Project Technologies:
* **Python 3**
* **Pandas Data Library**
* **Jupyter Notebooks / Google Colab Environment**
