# Financial Projection Tool

## Overview
This repository contains a Python script for projecting financial outcomes for retirement planning. The tool calculates the longevity of savings and IRA accounts, taking into account inflation, interest rates, Required Minimum Distributions (RMDs), and federal and state taxes.

## Project Details
**Author:** Ganga Singh

## Executive Summary
This project includes the following key components:

1. **User Inputs:** Collects user inputs using a GUI for start age, savings balance, IRA balance, annual spending, interest rates, retirement age, life expectancy, state, and additional income.
2. **Annual Spending Adjusted for Inflation:** Projects how spending power decreases over time due to inflation.
3. **Savings Account Growth:** Tracks the growth of the savings account based on the interest rate.
4. **IRA Account Growth and Withdrawals:** Tracks the growth of the IRA account, including the impact of RMDs starting at the specified age, and the option to withdraw more if necessary.
5. **Tax Calculations:** Calculates the tax impact on withdrawals from the IRA, considering the different tax structures of California and Massachusetts.
6. **Financial Projections:** Projects the longevity of the savings account and the IRA based on the above components.

## Project Components
- **Python Script:** `financial_projection.py`
- **Data Files:** No external data files required; all data is embedded within the script.

## Files
- **Python Script:** [financial_projection.py](path/to/financial_projection.py)

## Functions
### `calculate_rmd(ira_balance, age, rmd_table)`
Calculates the Required Minimum Distribution (RMD) based on the IRA balance and age.

### `calculate_federal_taxes(income, brackets)`
Calculates federal taxes based on the income and federal tax brackets.

### `calculate_state_taxes(income, state, ca_brackets, ma_rate)`
Calculates state taxes based on the income and state (California or Massachusetts).

### `calculate_taxes(income, brackets)`
Helper function to calculate taxes for a given income and tax brackets.

### `get_user_inputs()`
Collects user inputs using a GUI (Tkinter) for various financial parameters.

### `run_financial_projection(params)`
Runs the financial projection based on the user inputs and returns a DataFrame with the yearly financial data and a message indicating the longevity of funds.

## Usage
1. Ensure you have Python and the required libraries installed (`pandas`, `tkinter`).
2. Run the Python script:
    ```bash
    python financial_projection.py
    ```
3. Enter the required inputs in the GUI dialog boxes.
4. The script will output a year-by-year breakdown of the financial projection and indicate when funds are expected to be depleted.

## Example
Here is an example of running the financial projection:

```python
if __name__ == "__main__":
    user_inputs = get_user_inputs()
    projection_df, message = run_financial_projection(user_inputs)
    print(projection_df)
    print(message)
