# Expense-Tracker-
 
expenses = []


def add_expense():
    name = input("Enter expense name: ").strip()

    if not name:
        print("Expense name cannot be empty.")
        return

    try:
        amount = float(input("Enter amount: ₹"))

        if amount <= 0:
            print("Amount must be greater than zero.")
            return

    except ValueError:
        print("Please enter a valid number.")
        return

    expense = {
        "name": name,
        "amount": amount
    }

    expenses.append(expense)
    print("Expense added successfully!")


def view_expenses():
    if not expenses:
        print("No expenses recorded yet.")
        return

    print("\n--- Your Expenses ---")

    for number, item in enumerate(expenses, start=1):
        print(
            f"{number}. {item['name']} - "
            f"₹{item['amount']:.2f}"
        )


def show_total():
    total = sum(item["amount"] for item in expenses)
    print(f"Total expenses: ₹{total:.2f}")


while True:
    print("\n===== SK197Coding Expense Tracker =====")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. Show Total")
    print("4. Exit")

    choice = input("Choose an option: ").strip()

    if choice == "1":
        add_expense()
    elif choice == "2":
        view_expenses()
    elif choice == "3":
        show_total()
    elif choice == "4":
        print("Thank you for using SK197Coding!")
        break
    else:
        print("Invalid option. Try again.")
