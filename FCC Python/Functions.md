 [[- FCC Python]]
## Defining & Calling Functions

`def function_name():`

`def function_name(a, b, c=value):`
- set default values for parameters (c=value)

`function_name()`
- call func

keyword arguments
- explicitly show what value is assigned to parameter

```python
def add(x, y):
	return x + y

add(x=1, y=7) # 8
```
## Lambda

`lambda x: expr`
	x=parameter, expr=expression
- brief anonymous funcs
- simple 1 time tasks
- store in var
- call thru var(input)

`map(func, elements)`
- execute func (ex: lambda) for each element (ex: list)

`filter(func, list)`
- select items based on func output
- ex: elements of list when func is True

## All

`all()`
- returns True if all elements evaluate to True
- else return False
