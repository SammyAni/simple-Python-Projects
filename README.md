# Python-Projects
def calculator():
    print("Welcome to the Basic Calculator!")
    while True:
        operation = input("Choose operation (+, -, *, /) or 'exit' to quit: ")
        if operation == 'exit':
            break
        if operation in ('+', '-', '*', '/'):
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))
            if operation == '+':
                print(f'Result: {num1 + num2}')
            elif operation == '-':
                print(f'Result: {num1 - num2}')
            elif operation == '*':
                print(f'Result: {num1 * num2}')
            elif operation == '/':
                if num2 != 0:
                    print(f'Result: {num1 / num2}')
                else:
                    print("Error: Division by zero.")
        else:
            print("Invalid operation. Please try again.")

if __name__ == '__main__':
    calculator()
