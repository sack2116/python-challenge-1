# python-challenge-1
Module 2 Challenge 1 - Python Challenge-PseudoCode

# Order System

def order_system():
    """
    Order system for a variety food truck.

    This function sets up a system for taking customer orders, validates inputs,
    and prints a receipt at the end of the order process.

    Args:
        None

    Returns:
        None

    Raises:
        None

    Examples:
        The function runs interactively, so no examples are provided.

    Note:
        Ensure to run this function in an environment where input() is supported.
    """

    # Step 1: Initialize an empty order list.
    order = []

    # Step 2: Greet the customer.
    print("Welcome to the variety food truck.")

    # Step 3: Start the order loop.
    place_order = True
    while place_order:
        # Step 4: Display menu categories and get customer selection.
        print("From which menu would you like to order?")
        i = 1
        menu_items = {}
        for category in menu.keys():
            print(f"{i}: {category}")
            menu_items[i] = category
            i += 1

        # Step 5: Get customer's menu category selection.
        menu_category = input("Type menu number: ")

        # Step 6: Validate menu category input.
        if menu_category.isdigit():
            menu_category = int(menu_category)
            if menu_category in menu_items.keys():
                menu_category_name = menu_items[menu_category]
                print(f"You selected {menu_category_name}")

                # Step 7: Display items in the selected menu category.
                i = 1
                menu_items = {}
                print("Item # | Item name                | Price")
                print("-------|--------------------------|-------")
                for item, value in menu[menu_category_name].items():
                    if isinstance(value, dict):
                        for sub_item, price in value.items():
                            print(f"{i}      | {item} - {sub_item}{' ' * (24 - len(item + sub_item) - 3)}| ${price}")
                            menu_items[i] = {"Item name": f"{item} - {sub_item}", "Price": price}
                            i += 1
                    else:
                        print(f"{i}      | {item}{' ' * (24 - len(item))} | ${value}")
                        menu_items[i] = {"Item name": item, "Price": value}
                        i += 1

                # Step 8: Get customer's item selection.
                menu_selection = input("Type item number: ")

                # Step 9: Validate item selection input.
                if menu_selection.isdigit():
                    menu_selection = int(menu_selection)
                    if menu_selection in menu_items.keys():
                        item_name = menu_items[menu_selection]["Item name"]
                        price = menu_items[menu_selection]["Price"]
                        print(f"You selected {item_name} for ${price}")

                        # Step 10: Ask for quantity.
                        quantity = input(f"How many {item_name} would you like to order? ")
                        if not quantity.isdigit():
                            quantity = 1
                        else:
                            quantity = int(quantity)

                        # Step 11: Add item to the order list.
                        order.append({"Item name": item_name, "Price": price, "Quantity": quantity})
                    else:
                        print("Invalid item selection.")
                else:
                    print("You didn't select a valid item number.")
            else:
                print("You didn't select a valid menu option.")
        else:
            print("You didn't select a valid menu number.")

        # Step 12: Ask if the customer wants to continue ordering.
        while True:
            keep_ordering = input("Would you like to order anything else? (Y/N): ").lower()
            match keep_ordering:
                case 'y':
                    place_order = True
                    break
                case 'n':
                    place_order = False
                    print("Thank you for your order.")
                    break
                case _:
                    print("Invalid input. Please type (Y)es or (N)o.")

    # Step 13: Print the order receipt.
    print("This is what we are preparing for you.\n")
    print("Item name                 | Price  | Quantity")
    print("--------------------------|--------|----------")
    for item in order:
        item_name = item["Item name"]
        price = item["Price"]
        quantity = item["Quantity"]
        print(f"{item_name}{' ' * (26 - len(item_name))} | ${price}{' ' * (6 - len(str(price)))} | {quantity}")

    # Step 14: Calculate and print the total price.
    total_price = sum(item["Price"] * item["Quantity"] for item in order)
    print(f"Total price: ${total_price}")

if __name__ == "__main__":
    order_system()
