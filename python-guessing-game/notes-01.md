# Python Basics: Building a Guessing Game

## Part 1: Introduction

In this game, the computer will choose a secret number, and it'll be your job to guess it. We'll use some essential Python tools like loops, conditional statements (like if-else), and a special helper called the `random` module to make it all work."

## Part 2: Working with the random Module

*Giving the computer a way to think of a secret number*.
Python has a built-in module called `random` that provides functions for working with randomness. To use it, we start by writing import random at the beginning of our program."

```python
import random

random_number = random.randint(1, 10)  # Generates a random number between 1 and 10
print("The computer has chosen a secret number!") 
```

**Syntax**: In Python, code is organized into lines and blocks. Indentation (spaces before code) is crucial and defines code blocks.

**Importing Modules**: Python has a vast library of pre-written code called modules. The import statement allows us to access functions and variables from these modules. Here, we import the `random` module.

**`random.randint(a, b)` function**: This function generates a random integer between `a` (inclusive) and `b` (inclusive). In our case, it generates a number between 1 and 10 and stores it in the random_number variable.

### Take Note

- Importing a module that doesn't exist will result in an error.
- The `random.randint()` function can generate different random numbers each time you run the program.

## Part 3: Getting User Input

To play our guessing game, we need a way for the player (you!) to give the computer guesses. Here's where Python's `input()` function comes in. It allows us to ask the player a question and capture their answer as text.

```python
name = input("What's your name? ")
age = int(input("How old are you? "))  # Convert input to a number
print("Hello,", name, "! You are", age, "years old.")
```

**`input(message)` function**: This function displays the message in parentheses as a prompt for the user and then waits for their input. The user's answer is stored as a string (text) in the variable you specify (here, name).
**Casting (type conversion)**: In our example, we use `int(input())` to convert the user's age input (which is initially text) into a number before storing it in the `age` variable. This allows us to perform calculations with the age.
**String Concatenation**: The `print` statement combines text and variables using commas (,). In Python, this creates a single string for output.

### Take Note

If you don't use `int()` or a similar casting function for numerical input, Python will treat it as text, and calculations might not work as expected.

## Part 4: Conditional Statements

Now, we need to make our game smart! It should be able to tell the player if their guess is too high, too low, or just right. For this, we'll use conditional statements like `if` and `else`. These statements act like decision-makers in our code."

```python
number1 = 5
number2 = 10
if number1 > number2:
    print(number1, "is greater than", number2)
else:
    print(number1, "is not greater than", number2)
```

**`if` Statement**: The `if` statement checks a condition. If the condition is true, the code indented below the `if` will run.
**Comparison Operators**: We use these between values to create conditions:

- `>` (greater than), `<` (less than)
- `>=` (greater than or equal to), `<=` (less than or equal to)
- `==` (equal to), `!=` (not equal to)
- `els`e statement: This is an optional part of the decision structure. The code indented below `else` will run if the condition associated with the `if` was false.

### Take Note

**Indentation**: Indentation in Python defines code blocks. Indent code after `if` and `else` to indicate the code that runs in each case.

**`if-elif-else` Chain**: For multiple possibilities, we often use an `elif` to create a chain of conditions.  For example:

```python
score = 85 
if score >= 90:
    print("Grade is A")
elif score >= 80:
    print("Grade is B")
else:
    print("Grade is below B")
```

### Exercise

Write a python script that takes two numbers as input from the player. Use `if`, `elif`, and `else` statements to compare the numbers and print out which number is bigger, or if they are equal."

## Part 5: Loops

We need a way to let the player keep guessing in our game until they find the secret number. Loops let us repeat a section of code multiple times. We'll use a `while` loop for this.

```python
target_number = 5
guess = 0
while guess != target_number:
    guess = int(input("Guess a number: "))
print("You guessed it!")
```

**`while` loop**: The `while` statement checks a condition. The code indented below the `while` line will execute as long as that condition is true.
**Loop Initialization**: Before the loop, we usually initialize variables like `target_number` (the number to guess) and `guess` (initialized to something that doesn't match the target initially).
**Loop Body**: Inside the loop:

- `input("Guess a number: ")` prompts the user to guess a number.
- `int()` converts the user's input (which is initially text) into a number, allowing direct comparison with the `target_number`.

**Control Flow**: Each time through the loop, the computer asks for a guess and checks if it matches the `target_number`. When the player guesses correctly, the condition `guess != target_number` becomes false, and the loop stops.

### Take Note

**Infinite Loops**: If the condition inside a while loop is always true, you'll get an infinite loop (a program that never ends!). Ensure there's a way for the condition to become false.
Hands-on Practice:

### Exercise

Write a program using a while loop that keeps asking the player to enter their favorite word until they finally type the word 'stop'."

## Part 6: Putting It All Together

Now for the exciting part – building the core of our guessing game! Remember, it involves a random number, a loop for guesses, and feedback using 'if' and 'else' to tell the player if their guess is too high, too low, or correct.

```python
import random

secret_number = random.randint(1, 10)  
guess = 0

while guess != secret_number:
    guess = int(input("Guess a number between 1 and 10: "))
    if guess < secret_number:
        print("Too low!")
    elif guess > secret_number:
        print("Too high!")

print("You win! You guessed the secret number!") 
```

**Structure**: Notice how the elements we've learned fit neatly together:
**Import**: The `random` module.
**Setup**: Generate the `secret_number` and initialize a `guess`.
**Loop**: The `while` loop keeps the game going until the correct guess.
**Player Input**: `input()` and `int()` capture and convert the player's guess.
**Feedback**: `if`, `elif` provide feedback to the player.
**Victory**: Code outside the loop executes when the player wins.

It helps to outline the game's steps in plain language (look up **pseudocode**) to enhance your understanding of the logic.

## Part 7: Practice

Some exercises to take your game further! Choose one or more from these:

- **Change the range**: Can you make it guess between 1 and 100 instead?
- **Limited guesses**: Give the player only a few tries (hint: you'll need a counter!).
- **Bonus**: Can you make the computer tell you hints like 'warm' or 'cold' depending on how close you are?

## What Next?

You should now understand the `random` module, taking user input, `if` statements, and `while` loops. You've combined these to make the foundation of a Python game.

**Error Handling**: Consider adding ways to catch invalid input from the user (for example, if they type a letter instead of a number).
**Functions**: We'll begin working with functions, which are reusable blocks of code that help organize our programs, create reusable instructions.
