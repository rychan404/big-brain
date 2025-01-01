[[- FCC Python]]
## Strings

```python
string = ''
string = ""
```

f-strings
- interpolate values in str
- placeholders that's replaced by values
- ex: `print(f'hi {name}) # same as 'hi ' + name`

`str[index]`
- access char at index
- last char at index -1
	- 2nd last is at index -2

`str[start:stop:step]` 
	start=inclusive, step=exclusive
- range of chars
- negative nums reverse order
- optional parameters

`len()`
- returns length

`str.lower()`
- returns lowercased str

`str.upper()`
- returns uppercased str

`str.find('')`
- finds index of char location
- returns -1 if not found

`str.index('')`
- same as `str.find('')`
- returns ValueError if not found

`str.maketrans({'a':'b', 'c':'d'})`
- creates translation table
- replace chars

`str.translate(translation_table)`
- str is translated w/ table

`str.join(list)`; str is a separator
- combine chars together

`str.strip('')`
- removes trailing/leading chars

## Lists

`list = [1, 2, 3...]`
- can have diff data types (ints, lists, etc.)

`list.append(item)`
- add item to end of list

`list.insert(index, item)`
- add item to the position of index

`list.pop(index)`
- removes last item of list (default)
- index specifies position to delete

list comprehension
- apply expressions to all items in list
- optional filter
- runs faster than writing out code

```python
span = [i * 2 for i in iterable]
span = [i * 2 for i in iterable if i > 0] # optional filter
span = [i * 2 if i > 0 else -1 for i in iterable] # optional filter with if/else in front of for
```

`range(start, stop, step)`
	start=inclusive, stop=exclusive, step=inclusive
	_     =optional (default: 0)                 = optional (default: 1)
- generate sequence of nums from start to stop every step

## Tuples

- like lists but immutable (unable to be changed)
- ex: `my_tuple = ('larch', 1, True)`

## Dictionaries

Syntax

```python
#             key   value        pairs
my_dict = {'amount':50.0, 'category':'Food'}
```

Access value through keys

```python
print(my_dict[amount]) # prints 50.0
```

