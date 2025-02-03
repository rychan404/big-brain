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

```python
class Ocean:

    def __init__(self, sea_creature_name, sea_creature_age):
        self.name = sea_creature_name
        self.age = sea_creature_age
    
    def __str__(self):
        return f'The creature type is {self.name} and the age is {self.age}'

c = Ocean('Jellyfish', 5)

print(c) # returns 'The creature type is Jellyfish and the age is 5'
```

Helper methods (sometimes called private methods)
- denoted by an underscore next to method name
- used to complete one specific task & simplify code

```python
class BinarySearchTree:

    def __init__(self):
        self.root = None
        
    def _insert(self, node, key):
        if node is None:
            return TreeNode(key)
        if key < node.key:
            node.left = self._insert(node.left, key)
        elif key > node.key:
            node.right = self._insert(node.right, key)
        return node
        
    def insert(self, key):
        self.root = self._insert(self.root, key) # simplifies methods that are called outside of class
```