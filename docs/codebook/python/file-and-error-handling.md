# File Handling

File handling is an important part of any web application.
Python has several functions for creating, reading, updating, and deleting files.

The `open()` function takes two parameters; _filename_, and _mode_.

There are *four different methods (modes) for opening a file*:
- `"r"` - Read - Default value. Opens a file for reading, error if the file does not exist
- `"a"` - Append - Opens a file for appending, creates the file if it does not exist
- `"w"` - Write - Opens a file for writing, creates the file if it does not exist
- `"x"` - Create - Creates the specified file, returns an error if the file exists

```python
f = open("demofile.txt", "rt")
# Because `"r"` for read, and `"t"` for text are the default values, you do not need to specify them.
```
## Create a new file
To create a new file in Python, use the `open()` method, with one of the following parameters:

`"x"` - Create - will create a file, returns an error if the file exists

```python
f = open("myfile.txt", "x")
```
## read a file
The `open()` function returns a file object, which has a `read()` method for reading the content of the file:

```python
f = open("demofile.txt", "r")  
print(f.read())
```

```python
f = open("demofile.txt", "r")  
print(f.read(5)) # specify how many characters you want to return 
```

You can return one line by using the `readline()` method:

```python
f = open("demofile.txt", "r")  
print(f.readline())
```

## close files
It is a good practice to always close the file when you are done with it.

```python
f = open("demofile.txt", "r")  
print(f.readline())  
f.close()
```

## Write Files
To write to an existing file, you must add a parameter to the `open()` function:

`"a"` - Append - will append to the end of the file
`"w"` - Write - will overwrite any existing content

```python
f = open("demofile2.txt", "a")  
f.write("Now the file has more content!")  
f.close()  

# or 
f = open("demofile3.txt", "w")  
f.write("Woops! I have deleted the content!")  
f.close()

#open and read the file after the appending:  
f = open("demofile2.txt", "r")  
print(f.read())
```

the `with` statement helps work with resources like file steams, it handles exceptions and ensure the stream is closed when no longer needed.

```python
# write the file
with open('mission_journal.txt', 'w') as f:
    f.write('Its my first day on the space mission!')

# read the file
with open('mission_journal.txt', 'r') as f:
    file = f.read()

print(file)
```

## Delete a File
To delete a file, you must import the OS module, and run its `os.remove()` function:

```python
import os  
os.remove("demofile.txt")
```

To avoid getting an error, you might want to *check* if the file exists before you try to delete it:

```python
import os  
if os.path.exists("demofile.txt"):  
  os.remove("demofile.txt")  
else:  
  print("The file does not exist")
```

- delete folder

```python
import os  
os.rmdir("myfolder")
```


# Syntax Errors
Syntax Errors, also known as parsing errors, are perhaps the most common kind of complaint you get while you are still learning python:

```python
while True print(`hello world`)  # get syntax error
```

## Exceptions
Even if a statement or expression is syntactically correct, it may cause an error when an attempt is made to execute it. 

Errors detected *during execution are called exceptions* and are not unconditionally fatal.

```python
# other errors
10 * (1/0) # ZeroError
4 + spam*3 # NameError
'2' + 2 # TypeError
```

## Handling Exceptions
It is possible to write programs that handle selected exceptions.

- The `try` block lets you test a block of code for errors.
- The `except` block lets you handle the error.
- The `else` block lets you execute code when there is no error.
- The `finally` block lets you execute code, regardless of the result of the try- and except blocks.

```python
try:  
  print(x)  
except:  
  print("Something went wrong")  
finally:  
  print("The 'try except' is finished")
```

you can choose to throw an exception if a condition occurs. To throw (or raise) an exception, use the `raise` keyword.

```python
# raising exceptions
x = -1  
  
if x < 0:  
  raise Exception("Sorry, no numbers below zero")
```

We use assert to test conditions and display a message *if the condition is false*.

```python
assert condition, message
```

```python
# Assertions
name = "Mohit"
assert(name == 'Sohil'), f'name is {name}, it should be Sohil'

print(f'My Name is {name}')
```

## try/except

```python
try:
    new_set = {1,2,3,4,5}
    print(new_set[0]) # indexing not work in set, so TypeError.

except Exception as e:
    print(e) # print the error
    print('kya kar rha hai?, error aa rha hai sahi kar')
```

```python
# try - code to attempt running.
# except - execute this code if there is an exception generated.
x = 0
try:
    answer = 1/x

## You can define as many exception blocks as you want.
except ZeroDivisionError:
    answer = 'undefined'

except TypeError:    
    answer = 'use numbers instead of using string'

print(f'The answer is {answer}')
```

```python
# An except clause may name multiple exceptions as a parenthesized tuple, for example:
except (RuntimeError, TypeError, NameError):
    pass
```



