# Sales Data Filter & Report Engine

A beginner-friendly Python + NumPy project that simulates one year of sales for 10 stores across 12 months, then filters the data with queries and generates simple reports.

## Project Objective

Create a sales dataset, display it, slice it by quarter, filter it with Boolean masks, pick records with fancy indexing, and print four summary reports, all in a single Python file with no user input.

## Requirements

- Python 3.x
- NumPy (`pip install numpy`)

## How to Run

```bash
python sales_data_filter_report_engine.py
```

The program runs from start to finish and prints everything to the console.

## NumPy Topics Used

| Topic | Where it is used |
|---|---|
| `np.arange()` | Month numbers 1 to 12 |
| `np.linspace()` | Monthly sales targets (50,000 to 70,000) |
| `np.random` | Random sales values (fixed seed `42`, so output is repeatable) |
| `reshape()` | Turns 120 values into a 10 x 12 array (stores x months) |
| Boolean masking | Filtering sales by target, average, and ranges |
| `&`, `\|`, `~` | Combined AND, OR, and NOT conditions |
| Fancy indexing | Selecting Stores 2, 5, 8 and the top 3 months |
| 2D slicing | Quarterly data and a single store's record |

## Data Layout

- Rows are stores (Store 1 to Store 10).
- Columns are months (January to December).
- Sales values are random whole numbers between 30,000 and 89,999.
- Each month has one target, applied to every store.

## Program Steps

1. **Create the dataset:** month labels, random sales, reshape to 10 x 12, targets with `linspace`.
2. **Display the data:** month names, all store sales, monthly targets.
3. **2D slicing:** Q1 (Jan-Mar), Q2 (Apr-Jun), Q3 (Jul-Sep), Q4 (Oct-Dec), plus the full record of Store 3.
4. **Boolean masking queries:**
   - Records where sales exceed the monthly target
   - Stores with average sales below the overall average
   - AND: sales between 50,000 and 70,000
   - OR: sales below 35,000 or above 85,000
   - NOT: records that did not exceed the target
5. **Fancy indexing:**
   - Stores using index array `[1, 4, 7]` (zero-based, meaning Store 2, Store 5, Store 8)
   - Three best-performing months by total sales
6. **Reports:**
   - Monthly report: total sales, total target, achievement %
   - Store-wise report: annual sales and monthly average
   - Quarterly report: Q1 to Q4 totals
   - Growth target report: average sales per store vs target, with Target Met / Target Missed

## Functions

| Function | Purpose |
|---|---|
| `create_dataset()` | Builds months, sales array, and targets |
| `display_sales_data()` | Prints the dataset and targets |
| `perform_slicing()` | Quarterly slices and one store's record |
| `perform_boolean_masking()` | All five mask-based queries |
| `perform_fancy_indexing()` | Selected stores and top 3 months |
| `generate_reports()` | The four reports |
| `main()` | Runs every step in order |

## Notes

- No classes, pandas, Matplotlib, file handling, or other external libraries are used.
- The top 3 months are found with a simple loop; the result is then used as an index array.
- Change the seed in `create_dataset()` to get a different random dataset.
