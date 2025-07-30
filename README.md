# cafe-management-system
# IDEAS - ask for review and maybe add the option for menu acc to customer's mood

# Defining menu

def show_menu():
    print("\n--- Welcome to the Cafe ---")
    print("Here's our menu:")
    print("1. Coffee           - ₹70")
    print("2. Hot Tea          - ₹50")
    print("3. Boba             - ₹200")
    print("4. Lemon Tea        - ₹100")
    print("5. Ice Cream Coffee - ₹150")
 
# Menu and rate list

menu = {
    "coffee": 70,
    "hot tea": 50,
    "boba": 200,
    "lemon tea": 100,
    "ice cream coffee": 150
}

total_bill = 0  
ordering = True
ordered_items = []  
 
# Loops for the working

while ordering:
    show_menu()
    choice = input("What would you like to order? ").strip().lower()

    if choice in menu:
        total_bill += menu[choice]
        ordered_items.append(choice.title())
        print(f"{choice.title()} added to your order. ₹{menu[choice]}")

        more = input("Would you like to order something else? (yes/no): ").strip().lower()
        if more != "yes":
            ordering = False
    else:
        print("Sorry, we don't have that item. Please choose from the menu.")

#Ask for cookie 

cookie_offer = input("\nWould you like a complimentary cookie? (yes/no): ").strip().lower()
if cookie_offer == "yes":
    ordered_items.append("Complimentary Cookie")
    print("Great! A delicious cookie has been added to your tray.")

# Order Summary

print("--- Order Summary ---")
print("Items Ordered:")
for item in ordered_items:
    print(f" - {item}")
print(f"Total Bill: ₹{total_bill}")
print("Thank you for ordering! Your order will be here shortly.")
