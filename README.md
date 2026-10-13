# Inventory-or-stock-manager

stock = {}

def add_item():
    name = input("Enter item name: ").title()
    quantity = int(input("Enter quantity: "))
    price = float(input("Enter price: "))

    if quantity < 0 or price < 0:
        print("Invalid quantity or price!")
        return

    stock[name] = {"quantity": quantity, "price": price}
    print("Item added!")

def update_stock():
    name = input("Enter item name: ").title()

    if name in stock:
        quantity = int(input("Enter new quantity: "))

        if quantity < 0:
            print("Invalid quantity!")
            return

        stock[name]["quantity"] = quantity
        print("Stock updated!")
    else:
        print("Item not found!")

def show_stock():
    for name, details in stock.items():
        print(name, "Quantity:", details["quantity"],
              "Price:", details["price"])

while True:
    print("\n1. Add Item")
    print("2. Update Stock")
    print("3. Show Stock")
    print("4. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        add_item()
    elif choice == "2":
        update_stock()
    elif choice == "3":
        show_stock()
    elif choice == "4":
        break
    else:
        print("Invalid choice!")
        
