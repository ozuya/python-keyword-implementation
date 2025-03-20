# Importing modules using 'import' and 'as'
import math as m
from math import sqrt  # 'from' keyword to import a specific function

# Defining a class using 'class'
class MathOperations:
    def __init__(self, number):
        self.number = number  # Assigning instance variable

    # Function to check if a number is even or odd using 'if', 'else', and 'return'
    def is_even_or_odd(self):
        if self.number % 2 == 0:
            return True  # Using 'True' keyword
        else:
            return False  # Using 'False' keyword

    # Function using 'try', 'except', 'finally' for exception handling
    def safe_divide(self, divisor):
        try:
            result = self.number / divisor
        except ZeroDivisionError:  # Handling division by zero
            return "Cannot divide by zero"
        finally:
            print("Division attempt completed.")  # 'finally' always executes
        return result

    # Function using 'lambda' to return the square of a number
    def square(self):
        return (lambda x: x ** 2)(self.number)

# Using 'assert' to check a condition
assert sqrt(16) == 4, "Assertion Failed: The square root of 16 should be 4"

# Creating an instance of 'MathOperations'
operation = MathOperations(4)

# Using 'if', 'elif', 'else' statements
if operation.is_even_or_odd():
    print(f"{operation.number} is even")
elif operation.number == 0:
    print(f"{operation.number} is zero")
else:
    print(f"{operation.number} is odd")

# Using 'for' loop and 'in' keyword
for i in range(3):
    print(f"Iteration {i}: {operation.square()}")

# Demonstrating 'global' keyword
total = 0
def update_total(value):
    global total
    total += value

update_total(5)
print(f"Global total is: {total}")

# Demonstrating 'nonlocal' keyword
def outer():
    count = 0
    def inner():
        nonlocal count  # Modifying 'count' from the enclosing scope
        count += 1
        print(f"Nonlocal count is: {count}")
    inner()
outer()

# Using 'del' to delete a variable
del total
try:
    print(total)  # This will raise an error since 'total' is deleted
except NameError:
    print("Variable 'total' has been deleted.")

# Using 'while' loop with 'break' and 'continue'
counter = 0
while counter < 10:
    counter += 1
    if counter == 5:
        continue  # Skips printing 5
    if counter == 8:
        break  # Exits loop when counter reaches 8
    print(counter)

# Using 'with' for safe file handling
with open("sample.txt", "w") as file:
    file.write("Hello, Python!")
    print("File is written successfully.")

# Using 'yield' in a generator function
def generate_numbers():
    for i in range(3):
        yield i  # Returns value while maintaining state

for num in generate_numbers():
    print(f"Yielded value: {num}")

# Using 'pass' as a placeholder
def placeholder_function():
    pass  # Placeholder for future code

# Using 'raise' to manually trigger an exception
def check_positive_number(number):
    if number < 0:
        raise ValueError("Number must be positive")  # Raising an error
    return number

try:
    check_positive_number(-5)
except ValueError as e:
    print(f"Error: {e}")

# Using 'in' to check membership
sample_list = [1, 2, 3, 4, 5]
if 3 in sample_list:
    print("3 is in the list")

# Using 'is' to check object identity
a = [1, 2, 3]
b = a
if a is b:
    print("a and b refer to the same object")

# Using 'or' and 'and' logical operators
if (5 > 3 and 2 > 1) or (4 < 3):
    print("Logical condition is true")

# Using 'not' to negate a condition
if not (5 < 3):
    print("5 is not less than 3")

# Using 'None' to represent a null value
x = None
if x is None:
    print("x is None")
    
