# Gathering Data

There are several type of method of gathering data
- Working with CSV files
- JSON/SQL
- fetch API
- Web Scraping and more...

## Working with CSV files
***CSV*** (Comma Separated Values) is a simple ***file format*** used to store tabular data, such as a spreadsheet or database. A CSV file stores tabular data (numbers and text) in plain text.

### Working with CSV files in Python
Below are some operations that we perform while working with Python CSV files in Python.

- importing pandas
```python
import pandas as pd
```

- Opening a Local CSV file
```python
df = pd.read_csv('data.csv')
```

- Opening a csv file from an URL
```python
import requests
from io import StringIO

url = "paste url here"
hearders = {'User-Agent': "Mozilla/5.0 (Mocintosh; Intel Mac OS X 10.14; rv: 66.0) Gecko/20100101 Firefox/66.0"}
req = requests.get(url, headers = headers)
data = StringIO(req.txt)

pd.read_csv(data)
```

- `sep` parameter
```python
# sep parameter
pd.read_csv('data.csv', sep='\t' )
```

- `name` parameter - if you do not have a column name, so you can pass a list of column using `name` parameter to make it column. 
```python
pd.read_csv('data.csv', names = ['country', 'capital', 'currency'])
```

- `index_col` parameter - change the default index to exist index
```python
pd.read_csv('data.csv', index_col = 'Sno')
```

-  `header` parameter - change the header to any other column
```python
pd.read_csv('data.csv', header = 1) # 1 iw index of the row
```

- `use_cols` parameter - `use_cols` is used to call specific column only in the data.
```python
pd.read_csv('data.csv', use_cols = ['Sno', 'country', 'capital'])
```

- `squeeze` Parameter - if you can only need the only one column of the dataset. so `squeeze` convert that column into the series not DataFrame.
```python
pd.read_csv('data.csv', use_cols = ['Sno'], squeeze = True)
```

- `skiprows/nrows` parameter - skip the rows of the data using index, list or even function. `nrows` used to display the only n number of rows in the data.
```python
pd.read_csv('data.csv', skiprows = [0,2])
pd.read_csv('data.csv', nrows = 100)
```

- `encoding` Parameter - if the data in different encoded, so we can use `encoding` parameter to skip the error and change the default character encoding,
```python
pd.read_csv('zomato.csv', encoding = 'latin-1')
```

- *skip bad lines* - skip the bad format row or incorrect data in rows like we have 8 columns in the data but some rows have 9 columns.
```python
pd.read_csv('data.csv', error_bad_lines = False)
```

- `dtype` parameter - change and assign the data type of any columns you want
```python
pd.read_csv('data.csv', dtypes = {'target': int}) # target is column name
```

- Handling Dates
```python
pd.read_csv('data.csv', parse_dates = ['date']) # date is column name
```

- Convertors
```python
def rename(name):
	if name == 'Royal Challenger Bangalore':
		return "RCB"
	else:
		return name

rename('Royal Challenger Bangalore')

pd.read_csv('data.csv', converters = {'team1': rename})
```

- `na_values` parameter
```python
pd.read_csv('data.csv', na_values = ['Male']) # all the values of male is repalce with NAN vlaue.
```

- Loading a *huge dataset in chunks*
```python
dfs = pd.read_csv('data.csv', chunksize = 5000) # split data into chunks (equal parts)
```

```python
for chunks in dfs:
	print(chunk.shape)
```

## Working with JSON/SQL
JSON is data markup format. You use it to define what the data is and means. eg: This car is blue, it has 4 seats.

```sql
{
    "colour": "blue",
    "seats": 4
}
```

SQL is a data manipulation language. You use it to define the operations you want to perform on the data. eg: Find me all the green cars. Change all the red cars to blue cars.

```sql
select * from cars where colour = 'green'
update cars set colour='blue' where colour='red'
```

### Working with JSON
[reference](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_json.html)
**JSON** provides a _standardized_ object notation/structure to talk to web services.

```python
pd.read_json('data.json')
```

```python
# fetch using url
pd.read_json('www.url.com/data.json')
```

### Working with SQL
- first go XAMPP software and live Apache and MySQL .
- go run the SQL query and create database in ` localhost/phpmyadmin/` website
- download the `mysql.connector` package

```
pip install mysql.connector
```

```python
import mysql.connector

# create a connection between mysql and python.
conn = mysql.connector.connect('localhost', user = 'root', password = '', database = 'world')
```

```python
pd.read_sql_query("SELECT * FROM city", conn) 

#Note - add any sql query to fetch data
pd.read_sql_query("SELECT * FROM country WHERE SurfaceArea > 2000 ", conn) 
```

### Fetch Data From API
An **API** (Application Programming Interface), a collection of protocols and subroutines that enable communication between programs.

- Connect to an API
```python
import requests
import json

response_API = requests.get('https://api.covid19india.org/state_district_wise.json')
```

- Get the Data From API
```python
data = response_API.text
```

- Parse the data into JSON format
```python
parse_json = json.loads(data)
```

- Extract the data and print it
```python
active_case = parse_json['Andaman and Nicobar Islands']['districtData']['South Andaman']['active']

print(active_case)
```

- Another way to get the data from API
```python
import requests
import json

response_API = requests.get('https://api.covid19india.org/state_district_wise.json')
# go to the website json viewer and paste link and check the data.

# print(response_API.status_code)
response_API.json()['results']

# convert the list into DataFrame
pd.DataFrame(response_API.json()['results'])

# get the specific column from the data
pd.DataFrame(response_API.json()['results'])[['column1', 'column2']]

# get the data from different different pages
df = pd.DataFrame()

for i in range(1, 429):
	requests.get('https://api.covid19india.org/state_district_wise.json'.format(i))
	temp_df = pd.DataFrame(response_API.json()['results'])[['column1', 'column2']]
	df = df.append(temp_df, ignore_index = True)

# convert into csv format
df.to_csv('movie.csv')
```

### Fetching data using Web Scraping
**Web** **scraping** is a technique to fetch data from websites. While surfing on the **web**, many websites prohibit the user from saving data for personal use.

```python
import requests
# Making a GET request
r = requests.get('https://www.geeksforgeeks.org/python-programming-language/')

# check status code for response received
# success code - 200
print(r)

# print content of request
print(r.content)
```