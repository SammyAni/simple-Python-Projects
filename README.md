# Python- Pi Calculator
#Python program that calculates and generates the digits of π (pi) up to a user-specified amount

import decimal

def pi_digits(precision):

    """ Calculates pi to the specified number of decimal places using the Chudnovsky algorithm """
    
    decimal.getcontext().prec = precision + 1 
    
    # Set the precision for decimal calculations
    
    C = 426880 * decimal.Decimal(10005).sqrt()
    L = 13591409
    X = 1
    M = 1
    K = 6
    S = L

    for i in range(1, precision):
        M = (K**3 - 16*K) * M // i**3
        L += 545140134
        X *= -262537412640768000
        S += decimal.Decimal(M * L) / X
        K += 12

    pi = C / S
    return pi
    
def main():
    # Get user input for the number of digits of pi to generate
    
    while True:
        try:
            precision = int(input("Enter the number of digits of pi to generate (up to 1,000,000): "))
            if 1 <= precision <= 1000000:
                break
            else:
                print("Please enter a number between 1 and 1,000,000.")
        except ValueError:
            print("Invalid input. Please enter a valid integer.")

    # Calculate pi to the specified precision
    pi_value = pi_digits(precision)

    # Output or save the calculated pi digits
    print(f"Pi to {precision} digits:")
    print(str(pi_value))

    # Optionally save the result to a text file
    with open("pi_digits.txt", "w") as f:
        f.write(str(pi_value))

    print(f"Pi digits saved to 'pi_digits.txt'.")
    if __name__ == "__main__":
    main()
    !python calculate_pi.py
  
