🧾 Family Expense Tracker (Python CLI)

A simple command-line based Family Expense Tracker built using Python.
This tool allows you to add, view, summarize, and visualize household expenses stored in a CSV file.

✨ Features
Function	Description
Add Expense	Record a new expense entry with date, person, category, and amount.
View Expenses	Display all expense records in a table format.
Summary Report	View total spending and category-wise expense breakdown.
Visual Charts	Generate a bar chart of spending by category.
Automatic File Setup	Automatically creates family_expenses.csv if not present.
🛠️ Tech Used

Python 3.x

Pandas for data handling

Matplotlib for plotting charts

CSV for storing expense data

📦 Installation

Clone the repository:

git clone https://github.com/PalashMandot/Family-Expense-Tracker family-expense-tracker


Install the required Python libraries:

pip install pandas matplotlib

▶️ How to Run

Run the Python file:

python family_expense_tracker.py


You will see:

===== Family Expense Tracker =====
1. Add Expense
2. View All Expenses
3. Summary Report
4. Visualize Expenses
5. Exit


Just enter the number of the option you want to use.

📊 Example Chart Output

The Visualize Expenses option generates a bar graph showing category-wise total spending:

Food   ███████
Rent   ██████████████
Travel ████
...

🗂️ File Structure
family_expense_tracker.py
family_expenses.csv   (auto-created after first run)
README.md

🤝 Contributing

Feel free to contribute by:

Adding new features (e.g., deleting or updating entries)

Improving UI

Enhancing data analysis or visualization

Fork → Modify → Pull Request ✅
