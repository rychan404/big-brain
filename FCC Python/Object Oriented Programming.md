[[- FCC Python]]

## Classes

- blueprint for creating objects (instances of class)

```python
class ClassName: # use PascalCase!
    pass
```

Methods of a class

```python
class ClassName:
    def method_name(self):
        pass
```

Instantiate an object to customized state

```python
def __init__(self):
	pass
	
def __init__(self, board): # example
	self.board = board
```

Dot notation to access instance variable

```python
print(gameboard.board)
```

`__str__` method
- modify what's printed when object is printed
