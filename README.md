import csv
import pandas as pd
import matplotlib.pyplot as plt
from datetime import datetime

FILENAME = "family_expenses.csv"


def add_expense():
    date = input("Enter date (YYYY-MM-DD): ") or datetime.now().strftime("%Y-%m-%d")
    person = input("Enter name of family member: ")
    category = input("Enter category (Food, Rent, Transport, etc.): ")
    amount = float(input("Enter amount: "))
    
    with open(FILENAME, 'a', newline='') as file:
        writer = csv.writer(file)
        writer.writerow([date, person, category, amount])
    print("\n✅ Expense added successfully!\n")


def view_expenses():
    try:
        df = pd.read_csv(FILENAME)
        print("\nAll Expenses:\n", df)
    except FileNotFoundError:
        print("No expenses recorded yet!")


def summary():
    try:
        df = pd.read_csv(FILENAME)
        print("\nTotal Expenses: ₹", df['Amount'].sum())
        print("\nCategory-wise Spending:\n", df.groupby('Category')['Amount'].sum())
    except FileNotFoundError:
        print("No data available yet!")


def visualize_expenses():
    try:
        df = pd.read_csv(FILENAME)
        plt.figure(figsize=(6,4))
        df.groupby('Category')['Amount'].sum().plot(kind='bar', color='skyblue')
        plt.title("Family Expense by Category")
        plt.xlabel("Category")
        plt.ylabel("Amount (₹)")
        plt.tight_layout()
        plt.show()
    except FileNotFoundError:
        print("No data available to visualize!")


def initialize_file():
    try:
        open(FILENAME, 'x').write("Date,Person,Category,Amount\n")
    except FileExistsError:
        pass


def main():
    initialize_file()
    while True:
        print("\n===== Family Expense Tracker =====")
        print("1. Add Expense")
        print("2. View All Expenses")
        print("3. Summary Report")
        print("4. Visualize Expenses")
        print("5. Exit")
        
        choice = input("Enter choice (1-5): ")
        
        if choice == '1':
            add_expense()
        elif choice == '2':
            view_expenses()
        elif choice == '3':
            summary()
        elif choice == '4':
            visualize_expenses()
        elif choice == '5':
            print("👋 Exiting... Have a great day!")
            break
        else:
            print("❌ Invalid choice. Try again!")


if __name__ == "__main__":
    main()
