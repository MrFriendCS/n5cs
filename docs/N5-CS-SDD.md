# Software Design and Development

## Notes

All the code examples use Python.

Python uses indentation (spaces at the beginning of a line) to show where code blocks are.

These notes are focused on N5 Computing Science so some terms are used differently.  Any reference to an `array` will actually use a `list`.

## Information

### Comments

Single line comment.

``` python
## This comment is not displayed
```

Multiline comment.

``` python
"""
This comment is not displayed
This comment is not displayed
"""
```

### Display information

``` python
print("Hello world")

print(3.14)
```

## Assign values

Variables are used to store values.  An assignment statement has 3 parts:

 1. **=** is the assignment operator (an equals sign in maths)
 2. The value to the right of the assignment operator
 3. The variable name to the left of the assignment operator

The value is assigned to (stored in) the variable.  The value *might* need to be calculated first before being assigned.

``` python
myInteger = 5
```

``` python
myReal = 3.14
```

``` python
myCharacter = "&"
```

``` python
myString = "Hello"
```

``` python
myBoolean = True
```

``` python
myArrayOfIntegers = [56, 34, 2, 85, 51]
```

``` python
myArrayOfStrings = [""] * 4
```

## Arithmetic operations

Addition
``` python
4 + 2
```

Subtraction
``` python
4 - 2
```

Multiplication
``` python
4 * 2
```

Division
``` python
4 / 2
```

Exponentiation (to the power of)
``` python
4 ** 2
```

### Examples

``` python
myMultiplication = 3 * 2
print(myMultiplication)

mySquare = 3 ** 2
print(mySquare)

myAge = 21
myAge = myAge + 1
print(myAge)
```

## Concatenation

Concatenate means to join together.

### Strings

A string can be concatenated with another string.

``` python
part1 = "Ho"
part2 = "use"

word = part1 + part2

print(word)
```

Be sure to include a space between words when concatenating.

``` python
word2 = "world"

phrase = word1 + " " + word2

print(phrase)
```

### Non-strings

To concatenate something that is not a string, it must be cast (converted) to a string.

``` python
age = 18

phrase = "I am " + str(age)

print(phrase)
```

### Arrays

An array can be concatenated with another array.

``` python
part1 = ["Ho", "Ho"]
part2 = ["Ho"]

combined = part1 + part2

print(combined)
```

### Non-arrays

To concatenate something that is not an array, it must be cast (converted) to an array.

``` python
myArray = []
myInt = 18

combined = myArray + [myInt]

print(combined)
```

## User input

### String input

**Note:** Anything from the keyboard is a *string*.

```python
word1 = input("Enter the first word: ")
word2 = input("Enter the second word: ")

phrase = word1 + " " + word2

print(phrase)
```

### Non-string input 

Values that have a different datatype must be cast from string to the correct datatype, using one of the following functions:

```python
myInt = int("42")
myReal = float("3.14")
myBool = bool("True")
```

#### Example

```python
value1 = int(input("Enter the first value: "))
value2 = int(input("Enter the second value: "))

addition = value1 + value2

print(addition)
```

## Selection - simple

### Comparison operators

Comparison operators are used to compare one value with another.   All of the following examples produce a Boolean answer of `True` or `False`.

Equality (the same as)
``` python
16 == 18
```

Inequality (not the same as)
``` python
16 != 18
```

Greater than
``` python
16 > 18
```

Greater than or equal to
``` python
16 >= 18
```

Less than
``` python
16 < 18
```

Less than or equal to
``` python
16 <= 18
```

### Selection

Selection makes use of a comparison operator to decide what to do.

Example 1.  Code is only run if the comparison is `True`.

``` python
age = 21

if age >= 18:
    print("You can go to the pub.")
```

Example 2.  One section of code is always run.

``` python
age = 16

if age >= 18:
    print("You can go to the pub.")
else:
    print("You can't go to the pub.")
```

Example 3.  Only the section of code for the first comparison that is `True` is run.  There can be multiple `elif` statements.

There can be multiple `elif` statements, and the `else` is optional.  Numerical values are compared in order: largest to smallest (_see below_), or smallest to largest.

``` python
score = 81

if score >= 80:
    print("Excellent score!")
elif score >= 50:
    print("Well done!")
else:
    print("Oh dear!")
```

## Logical operators

Compare more than one set of values to produce a Boolean answer of `True` or `False`.

### AND

Both comparisons must be `True` to produce a final answer of `True`.

| Comparison 1 | Comparison 2 | Result |
| ------------ | ------------ | ------ |
| False        | False        | False  |
| False        | True         | False  |
| True         | False        | False  |
| True         | True         | True   |

#### Example AND

``` python
myAnswer = 16 <= 18 and "Night" == "Day"

print(myAnswer)
```

### OR

One or both comparisons must be `True` to produce a final answer of `True`.

| Comparison 1 | Comparison 2 | Result |
| ------------ | ------------ | ------ |
| False        | False        | False  |
| False        | True         | True   |
| True         | False        | True   |
| True         | True         | True   |

#### Example OR

``` python
myAnswer = 16 <= 18 or "Night" == "Day"

print(myAnswer)
```

### NOT

Reverses the result of the comparison.

| Comparison | Result |
| ---------- | ------ |
| False      | True   |
| True       | False  |

#### Example NOT

``` python
myAnswer = not(16 <= 18)

print(myAnswer)
```

## Selection - complex

Complex selection uses of logical operators.

``` python
age = 21
banned = False

if age >= 18 and not(banned):
    print("You can go to the pub.")
```

##  Fixed and conditional loops

### Fixed loop (for)

Before a fixed loop starts, the number of times it will run ***is*** stated.

#### Example

Display the numbers 0 to 9, ten numbers in total.  The loop variable is `counter` and it holds the current value from the range function.

``` python
for counter in range(10):
    print(counter)
```

The range function produces a sequence of values.  The last value in the sequence is always one less than the `stop` value:

``` python
range(stop)  ## Starts from 0

range(start, stop)

range(start, stop, step)
```

#### Example

Display the numbers 1 to 9.

``` python
for counter in range(1, 10):
    print(counter)
```

#### Example

Display the odd numbers from 1 to 9.

``` python
for counter in range(1, 10, 2):
    print(counter)
```

### Conditional loop (while)

Before a conditional loop starts, the number of times it will run ***is not*** stated.

It only runs if the comparison is `True`.  Each time the code is completed the comparison is checked again.  If it is still `True` the code is run again.

``` python
value = int(input("Enter a value: "))

while value < 10:
    value = value + 1
    print(counter)
```

## Predefined functions

### Random

The code to produce a random number needs to be imported before it can be used.

The code can be used to produce a random integer, with the lowest and highest possible values specified.

``` python
import random

myDice = random.randint(1, 6)

print(myDice)
```

### Round

#### Decimal Places

The round function works with floating point values (decimals).  It returns (produces) a value that is rounded to a specified number of decimal places

``` python
myReal = 3.14159265359

myRound = round(myReal, 2)

print(myRound)
```

#### Whole number

**Note:** Python does not always round up when a value has 5 tenths.  Instead it rounds to the nearest even number!

The round function can also be used to return a value without any decimal places (integer).

The following example will return a value of 4.

``` python
myReal= 3.5

myRound = round(myReal)

print(myRound)
```

The following example will ***also*** return a value of 4.

``` python
myReal= 4.5

myRound = round(myReal)

print(myRound)
```

### Length

The length function works with strings and arrays.  It returns a number of characters in a string or the number of elements in an array.

#### String

``` python
myString = "Computing"

myLength = len(myString)

print(myLength)
```

#### Array

``` python
myArrayOfIntegers = [56, 34, 2, 85, 51]

myLength = len(myArrayOfIntegers)

print(myLength)
```

## Standard algorithms

### Input validation

User input can be checked using a conditional loop.  If the value entered is not acceptable an error message is displayed and the value re-entered until it is.

It can be done two different ways, initial input before the loop or within the loop.

#### Input before loop

The conditional loop is only entered if the value entered is invalid.

``` python
dice = int(input("Enter dice value: "))

while dice < 1 or dice > 6:
    print("Value must be from 1 to 6.")
    
    dice = int(input("Enter dice value: "))

print("You entered " + str(dice))
```

#### Input within loop

Variable is assigned a value that will cause the loop condition to be true.

``` python
dice = 0

while dice < 1 or dice > 6:
    dice = int(input("Enter dice value: "))
    
    if dice < 1 or dice > 6:
        print("Value must be from 1 to 6.")

print("You entered " + str(dice))
```

### Running total within a loop

#### Fixed loop

``` python
total = 0

for counter in range(4):
    age = int(input("Enter an age: "))

    total = total + age

print("The combined age is " + str(total))
```

#### Conditional loop

``` python
answer = ""
total = 0

while answer != "no":
    age = int(input("Enter an age: "))
    total = total + age

    answer = input("Enter another age? ")

print("The combined age is " + str(total))
```

### Traversing a 1-D array

Arrays store more than one value, called elements.  Each element has a position.  Python starts counting from zero.

#### Putting values in

``` python
heights = [0.0] * 5

for index in range(len(heights)):
    height = float(input("Enter a height: "))

    heights[index] = height

print(heights)
```

#### Getting values out

Method 1 - using a loop variable (`index`)

``` python
scores = [56, 34, 2, 85, 51]

for index in range(len(scores)):
    print(scores[index])
```

Method 2 - not using a loop variable

``` python
scores = [56, 34, 2, 85, 51]

for score in scores:
    print(score)
```

### Multiple arrays

A program can use more than one array, in the same way that a program can use multiple variables.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5Nzg0MzY2Miw3NjI0MDE5ODIsLTE0OT
g0NjEyNDAsLTc0MTk0NDkxNywtMjI5MzQ4MjAyLDE5Njg1ODUy
ODgsODE0Mzk0OTE5XX0=
-->