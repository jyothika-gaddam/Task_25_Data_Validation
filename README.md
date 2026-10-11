# Task 25 - Basic Data Validation

Data Analytics track | Tools: Excel (also works in Google Sheets)

## What this is

A data-entry sheet for employee records where wrong values are blocked at the time of typing. I used synthetic (made up) employee data, so none of the records are real people.

The goal of the task was to improve spreadsheet data quality, so instead of cleaning bad data later, the sheet stops it from getting in.

## Files

| File | What it has |
|------|-------------|
| `Employee_Data_Validation.xlsx` | The main workbook |
| `sample_entries.csv` | The same 15 sample rows in CSV form |
| `README.md` | This file |

## Sheets inside the workbook

- **Read_Me_First** - short instructions and a table of every rule
- **Lists** - the values used by the dropdowns (change them here to change the dropdown options)
- **Template** - empty entry sheet (200 rows) with all the validation applied
- **Sample_Entries** - 15 filled rows to show how the sheet should look

## Columns and validation rules

| Column | Rule | Validation type |
|--------|------|-----------------|
| Employee ID | Format `EMP-###`, no duplicates | Custom formula |
| Full Name | 3 to 50 characters | Text length |
| Gender | Male / Female / Other | Dropdown |
| Age | Whole number 18 to 60 | Whole number |
| Department | 6 departments | Dropdown |
| Job Role | Depends on the department chosen | Dependent dropdown (INDIRECT + named ranges) |
| Employment Type | Full-time / Part-time / Contract / Intern | Dropdown |
| Joining Date | Between 01-Jan-2015 and today | Date |
| Monthly Salary (INR) | 10,000 to 3,00,000 | Whole number |
| Email | Needs `@` and a dot, no spaces | Custom formula |
| Phone | 10 digits, starts with 6-9 | Whole number |
| Work Location | Dropdown list | Dropdown |
| Status | Active / On Leave / Resigned | Dropdown |
| Row Check | Shows Complete or Missing fields | Normal formula |

Every input cell also has an input message (shows when you click the cell) and a Stop-style error message if something invalid is typed.

## How to use

1. Open `Employee_Data_Validation.xlsx`
2. Go to the **Template** sheet
3. Fill the yellow cells - choose from dropdowns where available
4. Try entering a wrong value (like age 5 or an email without @) to see the error message

## Things I learned / notes

- Data validation only checks what is typed. If someone copy-pastes over a cell, the rule can be bypassed.
- The dependent dropdown (Job Role) works using named ranges like `Roles_HR` and the `INDIRECT` function. If the Department is empty, the Job Role dropdown will not show anything.
- Custom formulas are useful for things that have no built-in option, like unique IDs and email format.
- In Google Sheets the dropdowns and number/date rules should carry over, but the dependent dropdown may need to be set up again.

## Why use data validation? (interview answer)

It improves data quality by stopping wrong or inconsistent values at the entry point. This means less cleaning later, consistent categories (no "HR" / "hr" / "Human Resources" mix), and fewer errors in pivot tables and reports.
