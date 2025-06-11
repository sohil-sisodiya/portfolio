# Basics of Python

## What is Python
Python is both compiled and interpreted, object-oriented, high level programming language with dynamic semantics.
- creator - **Guido Van Rossum (1991)**

## Comment in Python
python have two type of comments:
- single line
- multi line

```python
# this is single line comment

''' this is
		multi line comment.
'''
```

`docString`
docstring return the documentation of above program using `.__doc__` method.

```python
def print_max(x, y):
    '''Prints the maximum of two numbers.
The two values must be integers.'''
 # convert to integers, if possible
    x = int(x)
    y = int(y)
    if x > y:
        print(x, 'is maximum')
    else:
        print(y, 'is maximum')
        

print_max(3, 5)
print(print_max.__doc__) # docstring return the documention of above program

# shift + tab using to see the doc of a fuction in jupyter notebook
```

## Variables in Python
Rule of Writing a Variables:
1. Use `(_)` underscore to separate the names while writing a variable not space.
2. A variable name never start with a number or special symbols.

```python
# creating variable 

txt = 'hello'
print(txt) # retrun the output
```

```python
# creating multi line variable
number = (
    1 + 2 + 3 +
    4 + 5 + 6 +
    7 + 8 + 9
)

print(number)

# Assigning Mutliple Variable in same line
num1 = 10; num2 = 20; num3 = 30
print(num1, num2, num3)

var1 = var2 = var3 = 35
print(var1)
print(var2)
print(var3)

var_sum = var1 + var2 + var3

print(var_sum)

i = 5
print(i)
i = i + 1
print(i)

s = '''This is a multi-line string.
This is the second line.'''
print(s)
```

### Indentation
*Whitespace* is ==important== in python. Actually, whitespace at the beginning of the line line important. this is called Indentation.

```python
i = 5

# Error below! Notice a single space at the start of the line
 print('Value is', i)
print('I repeat, the value is', i)
```

## Data Types and User-Input
python has automatically assign data type of variable, you don't need to assign it.

```python
a = "hello"  # str

# numeric
b = 10  # int
c = 10.5  # float
d = 5+6j  # complex

# Boolean
e = True  # bool
f = False # bool

# Sequence
g = [1, 2, 3, 4]  # list
h = (1, 2, 3, 4)  # tuple
i = {1, 2, 3, 4}  # set
# set
o = frozenset({1, 2, 3, 4})  # frozenset

# Mapping
j = {1: 'one', 2: 'two', 3: 'three'}  # dict

# binary
k = b'hello'  # bytes
l = bytearray(5)  # bytearray
m = memoryview(bytes(4))  # memoryview

# None
n = None  # NoneType
```

### User Input
_Python_ allows for _user input_. That means we are able to ask the _user_ for _input_.

```python
# take input by user
name = input("Enter your name: ")
age = int(input("Enter your age: ")) # input convert into integer

print("Hello", name)
print(age)
```

### Type-Casting and subtype
Conversion of one data type to another is called type-casting.

Two type of type-casting:
1. **Implicit** Type Conversion: Where Python itself convert one to another datatype.

```python
# implicit type conversion
a = 23
b = 23.4

print(type(a))
print(type(b))
```

2. **Explicit** Type Conversion: Where the user converts one datatype to another.

```python
# Explicit Type Conversion
a = '200'
print(type(a))

b = int(a)
print(type(b))  # string to int
```

## Operators and Operands
*Operators* indicates what operations is to be performed.
*Operands* indicates on what the action or the operation should be performed.

> x + y = 10, here
> x, y and 10 are operands and + is operators

### type of operators
python divides the operators in the following groups:

- Arithmetic operators

```python
# Arithmetic Operators
a = 10
b = 3

print(a + b) # Addition
print(a - b) # Subtraction
print(a * b) # Multiplication
print(a / b) # Division
print(a % b) # Modulus
print(a ** b) # Exponentiation

# Note that if one of the values is a float, you'll get back a float.
print(a // b) # Floor division
```

- Assignment operators

```python
# Assignment Operators
a = 10
b = 3

a += b # a = a + b
print(a)

a -= b # a = a - b
print(a)

a *= b # a = a * b
print(a)

a /= b # a = a / b
print(a)
```

- Comparison operators

```python
# Comparison Operators
a = 10
b = 3

print(a == b) # Equal to
print(a != b) # Not equal to
print(a > b) # Greater than
print(a < b) # Less than
```

> The ***== operator (equal to)*** asks whether two values are the same as each other. 
> The ***= operator (assignment)*** puts the value on the right into the variable on the left.


- Logical operators

```python
# Logical Operators
a = True
b = False

print(a and b) # and - both conditions must be true
print(a or b) # or - at least one conditions must be true
print(not a) # not - inverts the condition
```

- Identity operators

```python
# Indentity Operators- used to check the indentity
a = 10
b = 3

print(a is b) # is
print(a is not b) # is not
```

- Membership operators

```python
# Membership Operators- used to check the presence of a sequance in an object
a = "Hello"
b = 'e'

print(b in a) # in
print(b not in a) # not in
```

- Bitwise operators

```python
# Bitwise Operators - difficult
a = 10
b = 2

print(a & b) # and
print(a | b) # or
print(a ^ b) # xor

print(~a) # not
print(a << b) # left shift - Shifts the bits of the number to the left by the number of bits specified.
print(a >> b) # right shift - same do for right
```

shortcut ==math expression==

```python
 a = 2 
 a*= 3 # it mean a = a * 3

print(a)
```

## Random Numbers
python has ability to generate random number using their random library.

```python
import random
dir(random) # all method show in random module
help(random) # description of the methods and functions in random module
```

```python
# rolling a dice 
number = random.randint(1,6) # random integer number
number
```

```python
# using variable
low = 1
high = 30

num = random.randint(low,high)
num
```

```python
# random float number
num_f = random.random() # return the float between 0 to 1
num_f
```

```python
# option which is randomly select 
options = ("rock", "paper", "scissors")

option = random.choice(options)
option
```

```python
cards = [2,3,4,5,6,7,8,9,10,'J','Q','K','A']
random.shuffle(cards) # shuffling the randoms

cards
```

## Conditional Statements
Conditional statements allows computer to execute a certain condition only if it is true.

### Type of conditional statements
1. if
2. if-else
3. if-elif-else
4. Nested statement

```python
# if
marks = 82

if marks >= 90:
    print("Grade A")

print("Other Rank")
```

```python
# if-else
age = 20
if age >= 18:
    print("You are eligible to vote")
else:
    print("You are not eligible to vote")
```

```python
# if-elif-else
marks = 76

if marks >= 90:
    print("Grade A")
elif marks >= 80:
    print("Grade B")
elif marks >= 70:
    print("Grade C")
else:
    print("Grade D")
```

```python
# nested statement
num = 10

if num >= 0:
    if num == 0:
        print("Zero")
    else:
        print("Positive number")
else:
    print("Negative number")
```

```python
# short hand if statement - one line statement
a = 10
b = 20

if a < b: print("a is less than b")
```

### short hand if-else statement
Conditional expression - A one line shortcut for the if-else statement(Ternary Operator).
here, X if condition else Y

```python
a = 10
b = 20

# body of if; if condition; else; body of else
print("a is less than b") if a < b else print("a is greater than b")
```

## Loops
A loop means to repeat something in the exact same way.

### types of loops are:
1. For
2. While
3. While True
4. Nested

```python
# for loop
for i in range(10): # range() means range between --> 1 to 10
    print(i)
```

```python
# while loop
i = 0 # start
while i < 10: # condition
    print(i)
    i += 1 # increment
```

```python
# while true -- not important, rarely use case
i = 0
while True:
    print(i)
    i += 1
    if i >= 100:
        break
```

```python
# nested loop - a loop inside a loop is called as nested loop.
for i in range(1,6):
    for j in range(1, i+1):
        print(j, end = ' ')
    print()
```

```python
# for loop with conditional statement
for i in range(1,10):
    if i % 2 == 0:
        print(i)

# conditional statement with and operator
for i in range(1, 101):
    if i % 2 == 0 and i % 3 == 0:
        print(i)
```

```python
num = [2,2,3,1,3,4,6]
# enumerate return value and index
for index, value in enumerate(num):
    print(index,value)
```

## Break and Continue Statement

### Continue Statement
Continue statement is used when you want to skip a particular condition.

```python
# Continue statement
for i in range(1, 10):
    if i == 5:
        continue
    print(i)
```

### Break Statement
Break statement is used when you want to destroy a loop at a certain condition and come out of the loop.

```python
# Break statement
for i in range(1, 10):
    if i == 5:
        break
    print(i)
```


