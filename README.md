# Project - finance calculator

This project is able to calculate the interest rate and/or monthly payment of a loan.
After downlaoding the python file just run it and follow the User instructions in the code. Depending on your choice (monthly payment or calculation of interest rate) it will ask you to provide necessary information for the calculation. 


# import the math module for the interest calculations
import math
# create the user menu
user_menu = input("investment - to calculate the amount of interest you'll earn on your investment" "\n"
                  "bond - to calculate the amount you'll have to pay on a home loan" "\n"

                  "\n" "Enter either 'investment' or 'bond' from the menu above to proceed: ").lower()

print(user_menu)

# User makes selections
if user_menu == "investment":
    P = int(input("Please enter the amount of you would like to deposit: "))
    r = int(input("Please enter interest rate (Only the number!!): "))
    t = int(input("Please enter number of years: "))
    interest = input(
        "Would you like a 'simple' or 'compound' interest: ").lower()
    # another if condition to check which interest the User is choosing (nested)
    if interest == "simple":
        A = P * (1+(r/100)*t)
        print("Your interests is: ", round(A, 2), "€")
    elif interest == "compound":
        A = P * math.pow((1+(r/100)), t)
        print("Your interests is: ", round(A, 2), "€")
    # in case no valid selection was made
    else:
        print("Sorry you have not selected a valid interest.")

elif user_menu == "bond":
    P = int(input("Please enter the present value of the house: "))
    i = int(input("Please enter interest rate (Only the number!!): "))
    n = int(input("Please enter number of months: "))

    repayment = ((i/100)/12) * P/(1 - (1 + (i/100))**(-n))
    # print with only tow decimal numbers
    print("Your monthly payment is: ", round(repayment, 2), "€")

# in case no valid selection was made
else:
    print("No valid selection made.")
