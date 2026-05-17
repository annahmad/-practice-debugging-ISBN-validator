# ISBN Validator

A Python project that validates ISBN-10 and ISBN-13 codes by checking their format, length, and check digit. Built as a debugging lab to identify and fix common Python errors such as `IndentationError`, `IndexError`, `TypeError`, and `ValueError`.

## What It Does

- Prompts the user to enter an ISBN code and its length
- Validates the format and length of the entered ISBN
- Calculates the expected check digit and compares it with the given one
- Handles all invalid inputs gracefully with descriptive error messages

## How to Run

```bash
python isbn_validator.py
```

Then enter the ISBN and length in this format:

```
Enter ISBN and length: 1530051126,10
```

## Input Format

- Enter the ISBN code **without hyphens**, followed by a comma, then the length (`10` or `13`)
- Example: `1530051126,10` or `9781530051120,13`

## Valid Test Inputs

| ISBN | Length | Expected Output |
|---|---|---|
| `1530051126` | `10` | Valid ISBN Code. |
| `9971502100` | `10` | Valid ISBN Code. |
| `080442957X` | `10` | Valid ISBN Code. |
| `9781530051120` | `13` | Valid ISBN Code. |
| `9781947172104` | `13` | Valid ISBN Code. |

## All Possible Messages

| Situation | Message |
|---|---|
| Valid ISBN | `Valid ISBN Code.` |
| Wrong check digit | `Invalid ISBN Code.` |
| Wrong length for ISBN-10 | `ISBN-10 code should be 10 digits long.` |
| Wrong length for ISBN-13 | `ISBN-13 code should be 13 digits long.` |
| Non-numeric characters in ISBN | `Invalid character was found.` |
| Length is not 10 or 13 | `Length should be 10 or 13.` |
| Non-numeric length entered | `Length must be a number.` |
| No comma in input | `Enter comma-separated values.` |

## Bugs Fixed

| Bug | Location | Description |
|---|---|---|
| `TypeError` | `validate_isbn` | `len(isbn, length)` → fixed to `len(isbn)` |
| Off-by-one error | `validate_isbn` | Wrong slice indexes for main digits and check digit |
| `ValueError` | `validate_isbn` | `int('X')` crashes on valid ISBN-10 check digit |
| `IndentationError` | `main` | `if/else` block was not indented correctly |
| `IndexError` | `main` | Missing comma in input caused a crash |
| `ValueError` | `main` | Non-numeric length caused a crash |

## Functions

| Function | Description |
|---|---|
| `validate_isbn(isbn, length)` | Validates the ISBN format, length, and check digit |
| `calculate_check_digit_10(digits)` | Calculates the expected check digit for ISBN-10 |
| `calculate_check_digit_13(digits)` | Calculates the expected check digit for ISBN-13 |
| `main()` | Handles user input and calls the validator |

## Technologies Used

- Python 3
- Exception handling (`try/except`)
- String slicing and list comprehensions

  ## Author
  Ann Ahmad
