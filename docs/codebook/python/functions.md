# Functions 
Functions are reusable pieces of programs. 

They allow you to give a name to a block of statements, allowing you to run that block using the specified name anywhere in your program and any number of times. This is known as calling the function. 

function define using `def` keyword.

```python
def say_hello():
	# block belonging to the function
	print('hello world')

# End of function
say_hello() # call the function
say_hello() # call the function again
```

```python
# Function Parameter
def print_max(a, b):
    if a > b:
        print(a, 'is maximum')
    elif a == b:
        print(a, 'is equal to', b)
    else:
        print(b, 'is maximum')


# directly pass literal values
print_max(3, 4)

# pass variables as arguments
x = 5
y = 7
print_max(x, y)
```

## scope of variables
- Local Variable
- global Variable

### Local Variable 
variable names are local to the function. This is called the scope of the variable.

```python
# local variable
x = 50
def func(x):
 print('x is', x)
 x = 2
 print('Changed local x to', x)
func(x)
print('x is still', x)
```

### Global Variable
If you want to assign a value to a name defined at the top level of the program (i.e. not inside any kind of scope such as functions or classes), then you have to tell Python that the name is not local, but it is global.

It is impossible to assign a value to a variable defined outside a function without the `global` statement.

```python
x = 50  # global variable

def func():
    global x    # global Keyword inside the function
    print('x is', x)
    x = 2
    print('Changed global x to', x)
    
func()
print('Value of x is', x)
```

## Arguments
_Arguments_ are specified after the function name, inside the parentheses. You can add as many _arguments_ as you want, just separate them with a comma.

### Default arguments value
You can specify default argument values for parameters by appending to the parameter name in the function definition the assignment operator `( = )` followed by the default value.

```python
def say(message, times=1): # default argument -- times=1
    print(message * times)
    
say('Hello')
say('World ', 5)
```

### Keyword Arguments
If you have some functions with many parameters and you want to specify only some of them, then you can *give values for such parameters by naming them* - this is called keyword arguments.

we use the name (keyword) instead of the position (which we have been using all along) to specify the arguments to the function.

```python
def space_suit(color='blue'):
    print('My space suit color is {}'.format(color))
space_suit() # print color is blue
space_suit(color = 'red') # print color is red


def func(a, b=5, c=10): # keyword arguments
    print('a is', a, 'and b is', b, 'and c is', c)
    
func(3, 7)
func(25, c=24)
func(c=50, a=100)
```

- when passing through arguments, positional arguments need to be passed through FIRST (and in order), followed by keyword arguments.
- positional arguments order is important but not in keyword arguments.

```python
def space_suit_welcome(name,space_ship,color='blue'):
    return 'Welcome {} to the {}, your suit color is {}'.format(name, space_ship, color)

names = ['sohil', 'mohit', 'rohit']
space_ships = ['apollo 8', 'One8', 'apollo One']

for idx, name in enumerate(names):
    ships = space_ships[idx]
    print(space_suit_welcome(name, ships))
```

### `VarArgs` parameters
Sometimes you might want to define a function that can take any number of parameters, i.e. variable number of arguments

```python
# *param

def print_sum(*num):
    sum = 0
    for i in num:
        sum = i+sum
    return sum

ans = print_sum(3,4,4,2,5,6,2,4,4)
print(ans)
```

```python
# **param

def print_sum(**num):
    sum = 0
    for i in num:
        sum = num[i]+sum
    return sum
    
ans = print_sum(num1 = 4, num2 = 5, num3 = 9)
print(ans)
```

```python
# use together

def total(a=5, *numbers, **phonebook):
    print('a', a)

 #iterate through all the items in tuple
    for single_item in numbers:
        print('single_item', single_item)

# get the value
    for i in phonebook:
        print('Value is',phonebook[i])      
# get the index like jack, john
    for i in phonebook:
        print('Key is',i)
        
 #iterate through all the items in dictionary
    for first_part, second_part in phonebook.items():
        print(first_part,second_part)

total(10,1,2,3,Jack=1123,John=2231,Inge=1560)
```

When we declare a starred parameter such as `*param` , then all the **positional arguments** from that point till the end
are collected as a tuple called 'param'.

Similarly, when we declare a double-starred parameter such as `**param` , then all the **keyword arguments** from that point till the end are collected as a dictionary called 'param'.

### The return statement
The `return` statement is used to return from a function i.e. break out of the function. 
We can optionally return a value from the function as well.

```python
def maximum(x, y):
    if x > y:
        return x
    elif x == y:
        return 'The numbers are equal'
    else:
        return y

print(maximum(2, 3))
```

## lambda function
A lambda function is a small anonymous function.
A lambda function can take any number of arguments, but can only have one expression.

```
# syntax
lambda _arguments_ : _expression_
```

```python
# how to use lamda function - lambda _arguments_ : _expression_
x = lambda a, n: a ** n
print(x(2,9))

ans = lambda x: x*3.14
print(ans(23))


# The power of lambda is better shown when you use them as an anonymous function inside another function.
def myfunc(n):  
  return lambda a : a * n  
  
mydoubler = myfunc(2)   
print(mydoubler(11))
```






