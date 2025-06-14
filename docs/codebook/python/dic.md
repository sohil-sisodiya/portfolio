# Dictionary

Dictionary allow user to write the data in the form of **Keys and Values**.
- Dictionaries are enclosed inside `{}`
- Keys and Values are Separated by `:`

```python
# create a dict
car_data = {"car1": "Honda", "Year": 2003}
print(car_data)

type(car_data)
```

```python
dir(car_data)
help(car_data)
```

### Nested Dictionary

```python
employees = {1:{'name':'John', 'age': 50}, 2:{'name':'Devil', 'age': 25}}
employees[1]['age'] # access the value in dict
```

## Iteration in Dictionary

```python
student = {'name':'John', 'class':'6th', 'roll_no':23}

# print all the key names one by one
for i in student:
    print(i)

# print all the value names one by one
for x in student:
    print(student[x])
    
# using value function
for x in student.values():
    print(x)
    
# using items function
for x,y in student.items():
    print(x,"-",y)
```

## Dictionary Functions

```python
student = {'name':'John', 'class':'6th', 'roll_no':23}

# adding the new key value pair
student['marks'] = 100

# get
x = student.get("name")
print(x)

# item
x = student.items()
print(x)

# Keys
x = student.keys()
print(x)

# values
x = student.values()
print(x)

# Copy the entire dictionary
copy_dic = student.copy()
print(copy_dic)
```

```python
#setdefault
x = student.setdefault("roll_no", 24)
print(x)

#update
student.update({"gender": "M"})

#pop
student.pop("roll_no")
print(student)

#popitem
student.popitem()  # pop the lestest item of the dic

#clear
student.clear()
```

