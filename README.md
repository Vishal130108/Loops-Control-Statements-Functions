# While Loop, For Loop, Control Statements & Functions

## 📌 Assignment Overview

This assignment focuses on implementing loops, control statements, and functions in Python.

The objective is to develop an understanding of:

- Iteration using a `while` loop and a `for` loop
- Control statements such as `break`, `continue`, and `else`
- Function creation and usage
- User input and type conversion
- Logical problem-solving using practical examples

The assignment consists of three practical programs:

1. Number Guessing Game
2. Multiplication Table Generator
3. BMI Calculator

---

## 🛠️ Technologies Used

- Python
- Jupyter Notebook

---

# Task 1: While Loop & Control Statements – Number Guessing Game

## 📌 Problem Statement

Create a Python program that implements a simple number guessing game using a `while` loop.

The program should make use of control statements such as `else`, `break`, and `continue`.

---

## 🎯 Objectives

The program should:

- Generate a random number between 1 and 10
- Ask the user to guess the number
- Allow a maximum of 3 attempts
- Check whether the guess is within the valid range
- Provide feedback for each guess
- Use `continue` for invalid guesses
- Use `break` when the correct number is guessed
- Use `while...else` when the user runs out of attempts

---

## Step 1: Generate a Random Number

The `random` module is imported and the `randint()` function is used to generate a random number between 1 and 10.

### Code

```python
import random

secret_number = random.randint(1, 10)
```

### Output

There is no direct output because the generated number is stored in the `secret_number` variable.

For example:

```text
7
```

The generated number can be different each time the program is executed.

---

## Step 2: Set the Number of Attempts

The number of attempts is stored in a variable named `attempts`.

The user is allowed a maximum of 3 attempts.

### Code

```python
attempts = 3
```

### Output

```text
3
```

The value `3` represents the maximum number of attempts.

---

## Step 3: Get User Input

The `input()` function is used to ask the user to enter a number.

Since `input()` returns a string, the value is converted into an integer using `int()`.

### Code

```python
guess = int(input("Guess the number (between 1 and 10): "))
```

### Sample Output

```text
Guess the number (between 1 and 10): 5
```

---

## Step 4: Implement the While Loop

A `while` loop is used to continue the game as long as the user has attempts remaining.

### Code

```python
while attempts > 0:
    print("Attempts remaining:", attempts)
    break
```

### Sample Output

```text
Attempts remaining: 3
```

The condition `attempts > 0` ensures that the loop runs only while attempts are available.

---

## Step 5: Check Whether the Guess Is Within the Valid Range

The user should enter a number between 1 and 10.

If the entered number is outside this range, the program displays an error message and uses `continue` to return to the beginning of the loop.

### Code

```python
if guess < 1 or guess > 10:
    print("Your guess is out of range. Please guess a number between 1 and 10.")
    continue
```

### Sample Output

```text
Guess the number (between 1 and 10): 15
Your guess is out of range. Please guess a number between 1 and 10.
```

The `continue` statement skips the remaining code in the current iteration and starts the next iteration of the loop.

---

## Step 6: Compare the Guess with the Secret Number

The number of attempts is reduced after a valid guess.

The program then checks whether the guessed number is:

- Correct
- Greater than the secret number
- Less than the secret number

### Code

```python
attempts = 3

while attempts > 0:
    guess = int(input("Guess the number (between 1 and 10): "))

    if guess < 1 or guess > 10:
        print("Your guess is out of range. Please guess a number between 1 and 10.")
        continue

    attempts = attempts - 1

    if guess == secret_number:
        print("Congratulations! You guessed the correct number.")
        break
    elif guess > secret_number:
        print("Too high. Try again.")
    else:
        print("Too low. Try again.")
```

### Sample Output

```text
Guess the number (between 1 and 10): 5
Too low. Try again.

Guess the number (between 1 and 10): 9
Too high. Try again.

Guess the number (between 1 and 10): 7
Congratulations! You guessed the correct number.
```

---

## Step 7: Use While...Else

The `else` block associated with the `while` loop executes when the loop finishes normally without encountering a `break`.

In this program, it is used when the user runs out of attempts without guessing the correct number.

### Code

```python
else:
    print("Better luck next time!")
```

### Sample Output

```text
Better luck next time!
```

This message appears when all three valid attempts are used without guessing the secret number.

---

## Step 8: Final Number Guessing Game

The complete program combines all the concepts learned in the previous steps.

### Final Code

```python
import random

secret_number = random.randint(1, 10)
attempts = 3

while attempts > 0:
    guess = int(input("Guess the number (between 1 and 10): "))

    if guess < 1 or guess > 10:
        print("Your guess is out of range. Please guess a number between 1 and 10.")
        continue

    attempts = attempts - 1

    if guess == secret_number:
        print("Congratulations! You guessed the correct number.")
        break
    elif guess > secret_number:
        print("Too high. Try again.")
    else:
        print("Too low. Try again.")

else:
    print("Better luck next time!")
```

### Sample Output

```text
Guess the number (between 1 and 10): 2
Too low. Try again.

Guess the number (between 1 and 10): 9
Too high. Try again.

Guess the number (between 1 and 10): 7
Congratulations! You guessed the correct number.
```

The secret number is generated randomly, so the output may be different each time the program is executed.

---

## 🔑 Key Concepts Learned

- `import`
- `random.randint()`
- `while` loop
- `if`, `elif`, and `else`
- `break`
- `continue`
- `input()`
- `int()`
- `while...else`
- Variables
- Conditional logic

---

# Task 2: For Loop – Multiplication Table Generator

## 📌 Problem Statement

Create a Python program to generate the multiplication table of a number using a `for` loop.

The table should be generated from 1 to 10.

---

## 🎯 Objectives

The program should:

- Ask the user to enter a number
- Use a `for` loop
- Use `range()` to generate numbers from 1 to 10
- Calculate the multiplication result
- Display the multiplication table

---

## Step 1: Get the Number from the User

The `input()` function is used to get the number from the user.

The value is converted into an integer using `int()`.

### Code

```python
number = int(input("Enter the number for which you want the multiplication table: "))
```

### Sample Output

```text
Enter the number for which you want the multiplication table: 5
```

The entered value is stored in the `number` variable.

---

## Step 2: Use a For Loop with Range

The `range(1, 11)` function generates numbers from 1 to 10.

The ending value `11` is excluded.

### Code

```python
for i in range(1, 11):
    print(i)
```

### Output

```text
1
2
3
4
5
6
7
8
9
10
```

This demonstrates how a `for` loop works with `range()`.

---

## Step 3: Calculate the Multiplication Result

The number entered by the user is multiplied by each value generated by the `for` loop.

### Code

```python
for i in range(1, 11):
    result = number * i
    print(result)
```

### Sample Output

For the input `5`:

```text
5
10
15
20
25
30
35
40
45
50
```

The multiplication result is stored in the `result` variable.

---

## Step 4: Display the Multiplication Table

The program is modified to display the multiplication in a readable format.

### Code

```python
for i in range(1, 11):
    result = number * i
    print(number, "x", i, "=", result)
```

### Sample Output

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

---

## Step 5: Final Multiplication Table Program

The complete program combines user input, `for` loop, `range()`, multiplication, and output formatting.

### Final Code

```python
number = int(input("Enter the number for which you want the multiplication table: "))

for i in range(1, 11):
    result = number * i
    print(number, "x", i, "=", result)
```

### Sample Output

```text
Enter the number for which you want the multiplication table: 5

5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

---

## 🔑 Key Concepts Learned

- `for` loop
- `range()`
- `input()`
- `int()`
- Variables
- Arithmetic operators
- Multiplication
- `print()`
- Iteration

---

# Task 3: Functions – BMI Calculator

## 📌 Problem Statement

Create a Python program to calculate BMI using a user-defined function.

The program should accept the user's weight and height, calculate BMI using a function, and display the result.

### BMI Formula

```text
BMI = Weight (kg) / Height (m)²
```

---

## 🎯 Objectives

The program should:

- Create a function named `calculate_bmi()`
- Accept weight and height as parameters
- Calculate BMI
- Return the calculated BMI
- Accept user input
- Display the BMI rounded to two decimal places

---

## Step 1: Create the BMI Function

A function named `calculate_bmi()` is created.

The function accepts two parameters:

- `weight`
- `height`

The BMI is calculated using the formula and returned using the `return` statement.

### Code

```python
def calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    return bmi
```

### Output

There is no output because the function is only being defined.

The function can be called later when the required inputs are available.

---

## Step 2: Get Weight from the User

The user's weight is accepted using the `input()` function.

The value is converted into a decimal number using `float()`.

### Code

```python
weight = float(input("Enter your weight in kg: "))
```

### Sample Output

```text
Enter your weight in kg: 58
```

The entered value is stored in the `weight` variable.

---

## Step 3: Get Height from the User

The user's height is accepted using the `input()` function.

The value is converted into a decimal number using `float()`.

### Code

```python
height = float(input("Enter your height in meters: "))
```

### Sample Output

```text
Enter your height in meters: 1.62
```

The entered value is stored in the `height` variable.

---

## Step 4: Call the Function

The `calculate_bmi()` function is called using the values stored in `weight` and `height`.

The returned value is stored in the `bmi` variable.

### Code

```python
bmi = calculate_bmi(weight, height)

print(bmi)
```

### Sample Output

```text
22.10059171597633
```

The calculation is:

```text
58 / (1.62²) = 22.10059171597633
```

---

## Step 5: Format the BMI Output

The BMI value is formatted to two decimal places using an f-string.

The format specification `.2f` is used to display two digits after the decimal point.

### Code

```python
print(f"Your BMI is: {bmi:.2f}")
```

### Sample Output

```text
Your BMI is: 22.10
```

---

## Step 6: Final BMI Calculator Program

The complete program combines the function, user inputs, calculation, return value, and formatted output.

### Final Code

```python
def calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    return bmi


weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

bmi = calculate_bmi(weight, height)

print(f"Your BMI is: {bmi:.2f}")
```

### Sample Output

```text
Enter your weight in kg: 58
Enter your height in meters: 1.62

Your BMI is: 22.10
```

---

## 🔑 Key Concepts Learned

- Function creation using `def`
- Function parameters
- Function calling
- `return` statement
- `float()`
- `input()`
- Arithmetic operators
- Exponentiation using `**`
- Variables
- f-strings
- Decimal formatting using `.2f`

---

# 📚 Overall Learning Outcomes

After completing this assignment, I practiced the following Python concepts:

- While loops
- For loops
- `range()`
- Conditional statements
- `break`
- `continue`
- `while...else`
- Functions
- Parameters
- Return values
- User input
- Type conversion
- Arithmetic operations
- String formatting
- Decimal formatting
- Basic problem-solving

---

# 📂 Project Structure

```text
Python-Assignment-3/
│
├── Python_Assignment_3.ipynb
└── README.md
```

---

# 📝 Conclusion

This assignment provided practical experience with Python loops, control statements, and functions.

The three programs helped demonstrate different programming concepts:

1. The **Number Guessing Game** demonstrated `while` loops, `break`, `continue`, conditional statements, and `while...else`.
2. The **Multiplication Table Generator** demonstrated `for` loops and `range()`.
3. The **BMI Calculator** demonstrated user-defined functions, parameters, return values, arithmetic operations, and formatted output.

These concepts form an important foundation for writing Python programs and will be useful for further learning in Data Analytics.
