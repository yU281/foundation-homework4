# foundation-homework4
	# H1 Homework

 Git is an example of a distributed version control system.

Q2 Github

Modified Staged Committed

 PR stands for Pull Request Repo is short for Repository

git pull

git fetch

git push


class InsufficientFundsError(Exception):
    pass

def simulate_shop():
    items = {
        'item1': 50,
        'item2': 80,
        'item3': 120
    }
    customer_money = 100

    try:
        print("Welcome to the shop!")
        print("Here are the available items and their prices:")
        for item, price in items.items():
            print(f"{item}: £{price}")
        print("Enter 'exit' to leave the shop.")

        while True:
            option = input("Enter the item you want to purchase: ")

            if option == 'exit':
                print("Thank you for visiting the shop. Goodbye!")
                break

            try:
                price = items[option]
                if customer_money >= price:
                    customer_money -= price
                    print(f"Here's your {option}!")
                else:
                    raise InsufficientFundsError

            except KeyError:
                print("Invalid item! Please enter a valid item from the list.")

            except InsufficientFundsError:
                print("You do not have enough money to purchase this item.")
                additional_money = input("Do you have more money? Enter the amount: ")
                try:
                    additional_money = float(additional_money)
                    customer_money += additional_money
                except ValueError:
                    print("Invalid amount entered. Exiting the shop.")
                    break

