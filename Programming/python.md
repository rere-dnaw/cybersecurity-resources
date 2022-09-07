# General
---
## Create venv:
```bash
python3 -m venv venv/
source ./venv/bin/activate
```
##### Note: flag `-m` is used for running modules

## Get info about module:
- start python interpreter and import module which we want to inspect 
```code
python
import http
help(http)
```
- to get info about methods and attributes use `dir`
```code
python
import http
dir(http)
```

## Requirements:
```bash
pip freeze > requirements.txt
pip install -r requirements.txt
pip list --outdated
```

# Naming convention
| **Type**    |  **Public** |  **Internal** |
|:--------------|:-----------|:-----------|
| Packages | `lower_with_under` ||
| Modules | `lower_with_under` |`_lower_with_under`|
| Classes | `CapWords` |`_CapWords`|
| Exceptions | `CapWords` ||
| Functions | `lower_with_under()` |`_lower_with_under()`|
| Global/Class Constant | `CAPS_WITH_UNDER` |`_CAPS_WITH_UNDER`|
| Global/Class Variable | `lower_with_under` |`_lower_with_under`|
| Instance Variable | `lower_with_under` |`_lower_with_under`|
| Method Name | `lower_with_under()` | `_lower_with_under()`|
| Function/Method Parameters | `lower_with_under` ||
| Local Variables | `lower_with_under` ||

# Quick
- use contex manager when managing resources
#### e.g
```python
with open(text.txt, 'r') as f:
	content = f.read()
```
- to loop over two (or more) lists at once  use `zip`
```python
for item1, item2 in zip(list1, list2):
```
##### Note 1: if lists are different length, the `zip` will stop after the shortest list is exhausted.
##### Note 2: if return only one value form this type of iteration, the returned value will be a tuple data type
- to ignore unnecessary variable use `_`
```python
a, _ = (a, b)
print(a)
```
##### Unpack tuple and use only `a` variable.
```python
a, *_ = (a, b, c, d)
print(a)
```
##### Unpack tuple and use only `a` variable.
- setting dynamically attributes to class
```python
setattr(objectName, attribute, value)
```
- getting value for attribute 
```python
first = getattr(objectName, attribute)
```
- use `getpass` function  for credentials input from user 
```python
username = getpass('Username: ')
userpass = getpass('Password: ')
```
- create one dimensional list from multi dimension `from itertools import chain`
```python
list1 =  [a,b,[c,d]]
print(list(chain.from_iterable(list1)))
```
- revers string
```python
test = "example"
print(test[::-1])
```
- calculate item occurrence with `from collections import counter`
```python
list1 = [a,b,c,a,b,b,d,d,d,d]
counting = COunter(list1)
print(counting)
print(dict(counting.most_common()))
```
- remove duplicates
```python 
list1 = [a,b,c,a,b,c,a,a]
print(list(set(list1)))
```
##### Note: keep in mind that elements order is not preserved
```python
from collections import OrderedDict

list1 = [a,b,c,a,b,c,a,a]
print(list(OrderedDict.fromkeys(list1).keys()))
```
##### Note: this method will preserve elements order
- `_` is used to separate large number to make it more readable 
```python
a = 1000000000000
b = 1_000_000_000_000
```
- list comprehensions 
```python
list1 = [1,2,3,4,5]
result_list_1 = [el * 2 if el % 2 == 0 else el for el in list1]
print(result_list_1)
# [1,4,3,8,5]

result_list_2 = [el * 2 for el in list1 if el % 2 == 0]
print(result_list_2)
# [4,8]

results_list_3 = [(lambda el: el*2)(el) for el in list1]
print(list(results))
# [2, 4, 6, 8, 10]
```
- lambda function
```python
add = lambda x,y: x * y
```
- `map` return a list of the results of applying the function to the items of the argument sequence(s). 
```python
triple = lambda x: x * 3
list1 = [1,2,3]
result = map(triple, list1) 
```
##### Note: Slower than list comprehension which evaluate function
- dictionary comprehension 
```python
users = [(1, "Adam", 34),
		(2, "Tom", 30),
		(3, "Dan", 28),]

username_dict = {user[1]: user for user in users} 

print(username_dict)
# {'Adam': (1, 'Adam', 34), 'Tom': (2, 'Tom', 30), 'Dan': (3, 'Dan', 28)}
```
- unpacking arguments `*args`
```python
def multiple_all(times, *args):
	return [arg * times for arg in args]
	
print(multiple_all(2,3,4,5,6))
# [6, 8, 10, 12]
```
or
```python
def multiple_all(times, a, b, c):
	return [el * times for el in [a, b, c]]

print(multiple_all(2,*[3,4,5]))
# [6, 8, 10]
```
- unpacking key arguments `**kwargs`. 
```python 
from cmath import sqrt

def calc_unit_vector(**kwargs):
	m = abs(sqrt(kwargs['x']**2 + kwargs['y']**2 + kwargs['z']**2))
	return {'x': kwargs['x']/m, 'y': kwargs['y']/m, 'z': kwargs['z']/m}

print(calc_unit_vector(x=2, y=4, z=2))
# {'x': 0.4082482904638631, 'y': 0.8164965809277261, 'z': 0.4082482904638631}
```
##### Note: **Parameter name** needs to be the same as a **key name** 
```python 
from cmath import sqrt

def calc_unit_vector(x, y, z):
	m = abs(sqrt(x**2 + y**2 + z**2))
	return {'x': x/m, 'y': y/m, 'z': z/m}

vector1 = {'x': 2, 'y':4, 'z':2}

print(calc_unit_vector(**vector1))
# {'x': 0.4082482904638631, 'y': 0.8164965809277261, 'z': 0.4082482904638631}
```