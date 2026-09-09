# 💰 Expense Tracker CLI

A simple, no-frills command-line tool for tracking personal expenses. Logs
data to a local SQLite database and generates monthly spending summaries,
including bar and pie charts.

## Features

- Add expenses with amount, category, and description
- List and filter expenses by category or month
- View monthly and category-based spending totals
- Generate visual charts (bar chart of spending by month, pie chart by category)
- Delete expenses by ID
- Zero external dependencies except `matplotlib` (only needed for charts)

## Setup

```bash
git clone <your-repo-url>
cd expense-tracker-cli
pip install -r requirements.txt
```

## Usage

**Add an expense:**
```bash
python expense_tracker.py add 45.50 Food "Groceries at Whole Foods"
python expense_tracker.py add 1200 Rent
```

**List expenses:**
```bash
python expense_tracker.py list
python expense_tracker.py list --category Food
python expense_tracker.py list --month 2026-09
```

**View a summary:**
```bash
python expense_tracker.py summary
python expense_tracker.py summary --chart   # also generates expense_summary.png
```

**Delete an expense:**
```bash
python expense_tracker.py delete 3
```

## How it works

- All data is stored in `expenses.db`, a local SQLite file created automatically
  on first run — no database server needed.
- The `summary --chart` command uses `matplotlib` to render:
  - A bar chart of total spending per month
  - A pie chart of spending distribution by category

## Possible extensions

- Add a budget limit per category with warnings when exceeded
- Export to CSV/Excel
- Add recurring expense support
- Wrap in a simple Flask web UI
