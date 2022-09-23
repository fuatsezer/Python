# Python
## Writing your own functions
### Defining a function
```python
def square(): # <- Function header
  new_value = 4 ** 2 # <- Function body
  print(new_value)

square()
>> 16

```

### Function parameters
```python
def square(value):
  new_value = value ** 2
  print(new_value)
  
square(4)
>> 16
```
### Return values from functions
```python
def square(value):
  new_value = value ** 2
  return new_value
  
num = square(4)
print(num)
>> 16
```
### Docstrings
* Docstring describe what your function does
* Serve as documentation for your function
* Placed in the immediate line after the function header
* In between triple double quotes """
```python
def square(value):
  """Return the square of a value."""
  new_value = value ** 2
  return new_value

```

### Multiple function parameters
```python
def raise_to_power(value1,value2):
  """Raise value1 to the power of value2"""
  new_value = value1** value2
  return new_value
  
result = raise_to_power(2,3)
print(result)
>> 8

```
### Returning multiple values 
```python
def raise_both(value1,value2):
  """Raise value1 to the power of value2 and vice varsa"""
  new_value1 = value1** value2
  new_value2 = value2** value1
  new_tuple = (new_value1,new_value2)
  return new_tuple
  
result = raise_both(2,3)
print(result)
>> (8,9)

```
### Scope and user-defined functions
### Global Scope
```python
new_val = 10

def square(value):
  """Returns the square of a number."""
  global new_val
  new_val = new_val ** 2
  return new_val
square(3)
>> 100
new_val
>> 100
```
## Default and flexible arguments
### Add a default argument
```python
def power(number, pow=1):
  """Raise number to the power of pow."""
  new_value = number ** pow
  return new_value
power(9,2)
>> 81
power(9,1)
>> 9
power(9)
>> 9
```

### Flexible arguments: *args
```python
def add_all(*args):
  """Sum all values in *args together."""
  
  # Initialize sum
  sum_all = 0
  
  # Accumulate the sum
  for num in args:
    sum_all += num
  return sum_all

add_all(1,2)
>> 3
```

### Flexible arguments: **kwargs
```python
def print_all(**kwargs):
  """Print out key-value pairs in **kwargs."""
  # Print out the key-value pairs.
  for key, value in kwargs.items():
    print(key + ":" + value)

print_all(name="dumbledore",job="headmaster")
>> job: headmaster
>> name: dumbledore
```

### Lambda Function
```python
raise_to_power = lambda x,y: x ** y
raise_to_power(2,3)
>> 8
```
### Ananymous functions
* Function map takes two arguments: `map(func, seq)`
* `map()` applies the function to ALL elements in the sqquence
```python
nums = [48,6,9,21,1]
square_all = map(lambda num: num ** 2, nums)

print(list(square_all))
>> [2304, 36, 81, 441, 1]
```

### Errors and exceptions
```python
def sqrt(x):
  """Returns the square root of a number."""
  try:
    return x ** 0.5
  except:
  print("x must be an int or float")

sqrt(4)
>> 2.0

sqrt("hi")
>> x must be an int or float
```

```python 
def sqrt(x):
  """Returns the square root of a number."""
  if x < 0:
    raise ValueError("x must be non-negative")
  try:
    return x ** 0.5
  except TypeError:
    print("x must be an int or float")
sqrt(-2)
>> ValueError: x must be non-negative
```

### Iterating over iterables: next()
```python
word = "Da"
it = iter(word)
next(it)
>> "D"
next(it)
>> "a"
next(it)
>> StopIteration
```

```python
word = "Data"
it = iter(word)
print(*it)
>> D a t a
```
```python
file = open("file.txt")
it = iter(file)
print(next(it))
>> This is the first line
print(next(it))
>> This is the second line.
```

### Using enumarate()
```python
avengers = ["hawkeye","iron man", "thor","quicksilver"]
e = enumarate(avengers)
list(e)
>> [(0,"hawkeye"), (1,"iron man"), (2,"thor"), (3,"quicksilver")]
for index,value in enumarate(avengers,start=10):
  print(index,value)
>> 10 hawkeye
>> 11 iron man
>> 12 thor
>> 13 quicksilver
```

### zip() and unpack
```python
avengers = ["hawkeye","iron man", "thor","quicksilver"]
names = ["barton", "stark", "odison", "maxinoff"]

for z1,z2 in zip(avengers,names):
  print(z1,z2)

>> hawkeye barton
>> iron man stark
>> thor odison
>> quicksilver maxinoff
```

## List Comphrension
```python
nums = [12,8,21,3,16]
new_nums = [num + 1 for num in nums]
print(new_nums)
>> [13, 9, 22, 4, 17]
```
## Nested loops
```python
pairs_2 = [(num1, num2) for num1 in range(0,2) for num2 in range(6,8)]
print(pairs_2)
>> [(0, 6), (0,7), (1, 6), (1,7)]
```
## Conditional Comphrension
```python
[num ** 2 for num in range(10) if num%2 == 0]
>> [0, 4, 16, 36, 64]
```

```python
[num ** 2 if num%2 == 0 else 0 for num in range(10)]
>> [0, 0, 4, 0, 16, 0, 36, 0, 64, 0]
```

## Dict comphrension
```python
pos_neg = {num: -num for num in range(3)}
>> {0:0, 1:-1, 2:-2}
```






