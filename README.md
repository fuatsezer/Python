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
