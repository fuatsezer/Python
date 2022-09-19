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







