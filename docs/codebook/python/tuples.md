# Tuples
tuple are the collection of *ordered and un-mutable data* (Faster). <br>
once created, tuples cannot be changed, multiple datatypes can be written inside a tuples.

### create a tuple

```python
a = (1, 2, 3, 4, 5) # brackets are not mandatory.
print(a)
print(type(a))

# if one elements in tuple
b = (1,) # use comma
print(b)
print(type(b))
```

```python
# nested tuples
nested_tuples = (1,2,3,(2,3))
nested_tuples
```

all method of tuple with the description.

```python
dir(a)
help(a)
```

## Slicing and Iteration in Tuples

```python
# slicing
a = ("One Plus", "Vivo", "Redmi", "SumSung", "RealMe")

print(a[0]) # index
print(a[0:3])
print(a[0:3:2]) # index 0 to 3 with step 2
print(a[:2]) # start with 2
print(a[::3]) # with step 2

# Negative Slicing
print(a[-1])
print(a[-3:-1])
print(a[-3:-1:2])
```

```python
# for reverse the tuple using slicing
print(a[::-1])
```

```python
# Iteration in tuple
a = ("One Plus", "Vivo", "Redmi", "SumSung", "RealMe")

# using for loop
for i in a:
    print(i)

# using for loop using range and length function
for i in range(len(a)):
    print(a[i])

# using while loop
i = 0
while i < len(a):
    print(a[i])
    i += 1
```

```python
# short-hand for loop
a = ("One Plus", "Vivo", "Redmi", "SumSung", "RealMe")
[print(i) for i in a]

# short-hand for loop using range and length function
[print(a[i]) for i in range(len(a))]
```

## Tuple Conversion and Functions

```python
 # conversion of tuple
a = ("One Plus", "Vivo", "Redmi", "SumSung", "RealMe")
b = list(a)
print(b)
print(type(b))
```

```python
# Function using in tuples
a = ("One Plus", "Vivo", "Redmi", "SumSung", "RealMe")
print(len(a))
print(a.count("Vivo"))
print(a.index("Redmi"))
```
