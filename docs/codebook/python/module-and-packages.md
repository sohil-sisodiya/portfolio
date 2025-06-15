# Module
You have seen how you can reuse code in your program by defining functions once. What if you wanted to reuse a number of functions in other programs that you write? As you might have guessed, **the answer is modules**.

```python
import sys # import the module
print('The command line arguments are:')

for i in sys.argv:
    print(i)
print('\n\nThe PYTHONPATH is', sys.path, '\n')
```

`from-import` statement

```python
from math import sqrt
print("Square root of 16 is", sqrt(16))
```

### Create Own Modules
Creating your own modules is easy, you've been doing it all along! This is because every Python program is also a m0odule. You just have to make sure it has a `.py` extension

```python
def say_hi(): # save this function as a mymodule.py
    
    print('Hi, this is mymodule speaking.')
__version__ = '0.1'
```

```python
# then import mymodule
import mymodule
mymodule.say_hi()
```

# Packages
Python Packages are a way to organize and structure your Python code into reusable components. 
Think of it like a *folder* that contains *related Python files* (modules) that work together to provide certain functionality.

> download and explore packages here -- https://pypi.org/

### How to Create Package in Python?
Creating packages in Python allows you to organize your code into reusable and manageable modules. Here’s a brief overview of how to create packages:

- **Create a Directory:** Start by creating a directory (folder) for your package. This directory will serve as the root of your package structure.

- **Add Modules:** Within the package directory, you can add Python files (modules) containing your code. Each module should represent a distinct functionality or component of your package.

- ***Init File:*** Include an __init__.py file in the package directory. This file can be empty or can contain an initialization code for your package. It signals to Python that the directory should be treated as a package.

- ***Subpackages:*** You can create sub-packages within your package by adding additional directories containing modules, along with their own __init__.py files.

- ***Importing:*** To use modules from your package, import them into your Python scripts using dot notation. For example, if you have a module named module1.py inside a package named mypackage, you would import its function like this: from mypackage.module1 import greet.

- ***Distribution:*** If you want to distribute your package for others to use, you can create a setup.py file using Python’s setuptools library. This file defines metadata about your package and specifies how it should be installed.

```
pip install package_name
```

```
pip list 
# to get the install packages
```

### Python Packages for Web scraping
Web scraping, the process of extracting data from websites, has emerged as a powerful technique to gather information from the vast expanse of the internet.

#### API 
API stands for application programming interface. you'll frequently have to interact with APIs to grab data or work with system. 
- here we can use the packages name - `Requests` [https://pypi.org/project/requests/]

```
pip install requests
```

```python
import requests

# use the method - module_nname.method()
requests.get()
```

Python *requests module* has several built-in methods to make HTTP requests to specified URI using GET, POST, PUT, PATCH, or HEAD requests. 
A HTTP request is meant to either retrieve data from a specified URI or to push data to a server. 
The `GET` method is used to retrieve information from the given server using a given URI.


##### Codes related to "GET" request:
- ***200 OK***: The server successfully processed the request, and the requested data is returned.
- ***201 Created***: A new resource is created on the server as a result of the request.
- **204 No Content**: The request is successful, but there is no additional data to return.
- ***300 Multiple Choices***: The requested resource has multiple representations, each with its own URL.
- ***302 Found (Temporary Redirect)***: The requested resource is temporarily located at a different URL.
- ***304 Not Modified***: The client's cached copy of the resource is still valid, and no re-download is necessary.
- ***400 Bad Request***: The request has malformed syntax or contains invalid data, making it incomprehensible to the server.
- ***401 Unauthorized***: Authentication is required, and the client's credentials (e.g., API key) are missing or invalid.
- ***500 Internal Server Error***: An unexpected server error occurred during request processing.
- ***502 Bad Gateway***: Acting as a gateway or proxy, the server received an invalid response from an upstream server.

#### working with packages

```python
import requests

# how to fetch data from APIs
joke_url = 'https://icanhazdadjoke.com/'
iss_url = 'https://api.wheretheiss.at/v1/satellites/25544'

# this is setting up a header - metadata or API request
my_header = {'Accept': 'application/json'}

  
# API call
joke_result = requests.get(joke_url, headers=my_header)
  
# print(result)
json_joke_result = joke_result.json()

print(json_joke_result['joke'])
print(type(json_joke_result)) # return the type


# same for ISS
iss_result = requests.get(iss_url, headers=my_header)
print(iss_result) # check the http response  

json_iss_result = iss_result.json()
print(json_iss_result)
```