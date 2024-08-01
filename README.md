# python-challenge-1
Module 2 Challenge 1 - Python Challenge-PseudoCode

# Variety Food Truck Order System

## Overview

This project is an order system for a variety food truck. Customers can place orders from a predefined menu, and the system will print an itemized receipt at the end of the transaction. The program uses Python to handle input validation, order processing, and receipt printing.
'''
Args:
        None

    Returns:
        None

    Raises:
        None

    Examples:
      <div style="text-align: center;">  
        Welcome to the variety food truck.
From which menu would you like to order?
1: Drinks
2: Snacks
Type menu number: 1
You selected Drinks
Item # | Item name                | Price
-------|--------------------------|-------
1      | Coffee                   | $1.50
2      | Tea                      | $1.20
Type item number: 1
You selected Coffee for $1.5
How many Coffee would you like to order? 2
Would you like to order anything else? (Y/N): n
Thank you for your order.
This is what we are preparing for you.

Item name                 | Price  | Quantity
--------------------------|--------|----------
Coffee                    | $1.5   | 2
Total price: $3.0.


    Note:
        Ensure to run this function in an environment where input() is supported.
    """


## Features

- User-friendly menu selection
- Input validation for menu and quantity selection
- Continuous ordering until the customer decides to stop
- Itemized receipt printing with total cost calculation

## Requirements

- Python 3.6 or later

## Setup

1. Clone this repository to your local machine:
    ```sh
    git clone https://github.com/sack2116/python-challenge-1.git
    ```
2. Navigate to the project directory:
    ```sh python-challenge-1
    cd python-challenge-1
    ```

## Usage

To run the order system, execute the following command in your terminal:
```sh
python menu.py
```

## Example
Welcome to the variety food truck.
From which menu would you like to order?
1: Drinks
2: Snacks
Type menu number: 1
You selected Drinks
Item # | Item name                | Price
-------|--------------------------|-------
1      | Coffee                   | $1.50
2      | Tea                      | $1.20
Type item number: 1
You selected Coffee for $1.5
How many Coffee would you like to order? 2
Would you like to order anything else? (Y/N): n
Thank you for your order.
This is what we are preparing for you.

Item name                 | Price  | Quantity
--------------------------|--------|----------
Coffee                    | $1.5   | 2
Total price: $3.0

## PseudoCode

1. Initialize an empty list to store orders.
2. Display menu categories and prompt user to select a category.
3. Display items in the selected category and prompt user to select an item.
4. Ask user for quantity and validate the input.
5. Add the selected item, price, and quantity to the order list.
6. Continue ordering until user decides to stop.
7. Print itemized receipt with total cost.

## How it Works

1. Initialization: The program initializes an empty order list.
2. Menu Display: The program displays menu categories and items.
3. Order Processing: The user selects an item and quantity, which is validated and added to the order list.
4. Receipt Printing: After finalizing the order, the program prints an itemized receipt with the total cost.


