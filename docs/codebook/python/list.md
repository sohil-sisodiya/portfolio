# Lists in Python
Lists are the *collection of ordered and mutable data means once created*, they can be changed. 

Multiple datatypes can be written inside a list.

```python
# writing a list
a = [1, 2, 3, 4, 5]
print(a)

# Mutliple datatype inside a list
b = [1, 2, 3, 4, 5, 'hello', 'world']
print(b)

print(type(a))
print(type(b))
```

```python
num_lst = [1,3,4,2,5]

# The built-in function dir() is used to find out which names a module defines. It returns a sorted list of strings
print(dir(num_lst))
print(help(num_lst)
```

```python
# 2D List
num1 = [1,2,2,3]
num2 = [5,6,7]

num = [num1, num2]

print(num)
print(num[1][0])
```

## List Slicing
The format for _list slicing_ is `[start:stop:step]`. start is the index of the _list_ where _slicing_ starts. stop is the index of the _list_ where _slicing_ ends.

```python
#indexing
a = [1, 2, 3, 4, 5]
print(a[0])
```

```python
# slicing
print(a[0:3]) # index 0 to 3
print(a[0:3:2]) # index 0 to 3 with step 2
print(a[:2]) # with start
print(a[::2]) # with step
```

```python
# negative slicing
print(a[-1])
print(a[-3:-1])
print(a[-3:-1:2])
```

==reverse== using slicing.

```python
a = [1, 2, 3, 4, 5]
print(a[::-1])
```

## List Iteration

```python
# using for loop
a = [1, 2, 3, 4, 5]
for i in a:
    print(i)
```

```python
# using for loop with range and length funtion
a = [1, 2, 3, 4, 5]
for i in range(len(a)):
    print(a[i])
```

```python
# using while loop
a = [1, 2, 3, 4, 5]
i = 0
while i < len(a):
    print(a[i])
    i += 1
```

```python
# using short-hand for loop
a = [1, 2, 3, 4, 5]
[print(i) for i in a]

# using short-hand for loop with range and length funtion
[print(a[i]) for i in range(len(a))]
```

## List Functions

```python
# find length of a list
a = [1, 2, 3, 4, 5]
print(len(a))
```

```python
# to count an occurance of a paricular elements
a = [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
print(a.count(1))
```

```python
# append function - to add to the list
a = [1, 2, 3, 4, 5]
a.append(6)
print(a)
```

```python
# insert function - to add to a specific location
a = [1, 2, 3, 4, 5]
a.insert(0, 0)
print(a)
```

```python
# to remove from a list
a = [1, 2, 3, 4, 5]
a.remove(1) # remove function
print(a)
```

```python
# pop function - to remove from a certain location using index
a = [1, 2, 3, 4, 5]
a.pop(0) # pop on index 0
print(a)
```

```python
# copy()- to creat a copy of a list
a = [1, 2, 3, 4, 5]
b = a.copy()
print(b)
```

```python
# index()- to access an element
a = [1, 2, 3, 4, 5]
print(a.index(3))
```

```python
# to extend the list
a = [1,2,3,4,5]
b = [6,7,8,9,10]
print(a)
a.extend(b)
print(a) # after extend method
```

```python
# to reverse the list
a = [1,2,3,4,5]
a.reverse()
print(a)

# by using slicing
b = [6, 7, 8, 9, 10]
print(b[::-1])
```

```python
# sort() returns None because it modifies the original list in-place.
# sorted(), on the other hand, returns a new sorted list.

# to sort the list
a = [1, 2, 4, 6, 2, 3, 5, 7]
a.sort()
print(a)

# by using sorted function
b = [1, 2, 4, 6, 2, 3, 5, 7]
print(sorted(b))
print(b)
```

```python
# clear() - to clear all the data from the list
a = [1, 2, 3, 4, 5]
a.clear()
print(a)
```

## List Comprehension
List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list.

```python
l1 = [1, 2, 3, 4, 5]
l2 = [i for i in l1]
print(l2)
```

```python
# with conditional statement
a = [1, 2, 3, 4, 5]
b = [i for i in a if i % 2 == 0]
print(b)
```

```python
[(x, y) for x in [1,2,3] for y in [3,1,4] if x != y] 
# metrix using list comprehension
```

### Loop Techniques
- loop over *a sequence in reverse*, first specify the sequence in a forward direction and then call the `reversed()`function.

```python
for i in reversed(range(1, 10, 2)):
    print(i)
```

- To loop over *a sequence in sorted order*, use the `sorted()` function which returns a new sorted list while leaving the source unaltered.

```python
basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
for i in sorted(basket):
    print(i)
```

- Using `set()` on a sequence eliminates duplicate elements. The use of `sorted()` in combination with `set()` over a sequence is an idiomatic way to loop over unique elements of the sequence in sorted order.

```python
basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
for f in sorted(set(basket)):
    print(f)
```
