# Strings

string are combination of number, symbols and letters, enclosed inside quotation ('').

## Creating String

```python
# Creation of string
str1 = 'hello world!!'
str2 = "What's your name?"
str3 = '''Hello this is 
        triple quotes'''

print(str1)
print(str2)
print(str3)
```

## String Method

```python
# Length
a = "hello world"
print(len(a))
```

```python
# Count
a = "hello world"
print(a.count('l'))
```

```python
# Upper and Lower
a = "hello world"
print(a.upper())
print(a.lower())
```

```python
# index - to find the object between the range 
# (if not present it give error)
a = "hello world"
print(a.index('o'))
```

```python
# Find - same to index but if not present it return 1(True).
a = "hello world"
print(a.find('l'))
```

```python
# Capitalize
a = "hello world"
print(a.capitalize())
```

```python
# Casefold
a = "HELLO WORLD"
print(a.casefold())
```

```python
# Center  - it fills the characters and centeralizes a string
a = "hello world"
print(a.center(20, '*'))
```

```python
# rindex - searches the string for a specified value and returns
a = "hello world"
print(a.rindex('hello'))
```

```python
# replace - replace the value
a = "hello world"
print(a.replace('hello', 'dream'))
```

### More String Function

```python
# Boolean function for string
a = "hello world"
print(a.startswith('h'))
print(a.endswith('d'))

print(a.swapcase()) # upper to lower and lower to upper
print(a.strip()) # remove white and other trim

b = "#OOFD#BRB#OMW"
print(b.split('#')) # split the string

print(a.isalnum())  # alphanumeric
print(a.isalpha())  # alphabet
print(a.isdecimal())
print(a.isdigit())
print(a.isnumeric())
print(a.islower())
print(a.isupper()) # upper case
print(a.istitle()) # follow the rules of a tittle
print(a.isspace()) # string are whitespaces


print(a.ljust(20, '*')) # left justify
print(a.rjust(20, '*')) # right justify
```

## String Slicing
you can return a range of characters by using the `slice` syntax.
Specify the *start index and the end index*, separated by a colon, to return a part of the string.

```python
# string slicing
a = "hello world"

print(a[0]) # indexing
print(a[0:5]) # index 0 to 5
print(a[0:5:2]) # index 0 to 5 with step 2
print(a[::3]) # with step 3
```

```python
# negative indexing
print(a[-1])
print(a[-5:-1]) # index -5 to -1
print(a[-5:-1:2]) # index -5 to -1 with step 2
```

#### reverse the string

```python
print(a[::-1])
```

## Formatting String
The `format()` method formats the specified value(s) and insert them inside the string's placeholder.

The placeholder is defined using curly brackets: {}. The `format()` method returns the formatted string.

```python
# string formating - important
name = "John"
age = 36
txt = "My name is {} and I am {} years old"
print(txt.format(name, age))
```

```python
# Basic usage of the str.format() method looks like this:
print('We are the {} who say "{}!"'.format('knights', 'Ni'))

age = 22
name = "Sohil Sisodiya"

print("My Name is {}, I am {} year old!".format(name,age))
```

```python
# OR
print("{0} is {1} year old".format(name, age))
print("{1} year old, Which name is {0}".format(name, age))

print('{name} was {age} years old when he wrote this book'.format(name=name, age=age))
print('Why is {name} playing with that python?'.format(name=name))
```

```python
# using f flag
print(f'{name} was {age} years old when he wrote this book') 
# notice the 'f' before the string

print(f'Why is {name} playing with that python?') 
# notice the 'f' before the string
```

```python
name + ' is ' + str(age) + ' years old'  # another format method
```

>A *single backslash* at the end of the line indicates that the string is continued in the next line.

```python
"This is the first sentence. \
This is the second sentence."
```

`{Value:flags}` - Format the value based on what flags are inserted.

```python
# decimal (.) precision of 3 for float '0.333'
print('{0:.3f}'.format(1.0/3))


# fill with underscores (_) with the text centered
# (^) to 11 width '___hello___'
print('{0:_^11}'.format('hello'))


# keyword-based 'Swaroop wrote A Byte of Python'
print('{name} wrote {book}'.format(name='Swaroop', book='A Byte of Python'))
```

> Note - that print always ends with an invisible "new line" character ( `\n` ) so that repeated calls to print will all print on a separate line each.

```python
print('a', end='')
print('b', end='')
```

`:.number()f` = round to that many decimal places(fixed point)

```python
price1 = 30193.1445
print(f"price 1 is {price1:.2f}")

# :number() = allocate that many space
print(f"price 1 is {price1:10}")

# :03 - allocate and zero pad that many spaces
print(f"price 1 is {price1:010}")

# <number - left justify
print(f"price 1 is {price1:<10}")

# >number - right justify
print(f"price 1 is {price1:>10}") # default

# coma separated
print(f"price 1 is {price1:,}")
```

Access the Function and method of the collection and description of that function.

```python
char = 'hello'
print(dir(char)) # access all the function and method
print(help(str))
```
