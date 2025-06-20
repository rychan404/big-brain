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

`__dict__` method
- dictionary storing obj attributes
- `vars()` - takes obj as argument & returns `__dict__` attribute

`getattr(obj, str)`
- takes obj & string attribute name
- dynamically access attributes

`__repr__` method
- return string needed to instantiate object

`__class__.__name__`
- access name of class

``__getattribute__`` method
- attempting to access instance attribute
- `__getattr__` called the same if defined in class

`__add__` method
- change what happens by default when 2 objects are added w/ +

`__sub__` method
- change what happens by default when 2 objects are subtracted w/ -

`__mul__` method
- change what happens by default when 2 objects are multiplied w/ *

`__eq__` method
- change what happens by default when 2 objects are compared w/ ==

`__ne__` method
- change what happens by default when 2 objects are compared w/ !=

`__lt__` method
- change what happens by default when 2 objects are compared w/ <

`__gt__` method
- change what happens by default when 2 objects are compared w/ >

`__le__` method
- change what happens by default when 2 objects are compared w/ <=

`__ge__` method
- change what happens by default when 2 objects are compared w/ >=

`__init_subclass__` method
- defined class is subclassed & enables customizability to child classes
- takes parameter cls (class) - new child class

`hasattr()`
- check if object has specific attribute
- returns True or False

`isinstance()`
- returns boolean
- obj (1st argument) is instance of class passed on 2nd argument
- ex: `isinstance(7, int) # True`

`__slots__`
- assigning sequence of strings restricts creation of attributes to only sequence
- prevent `__dict__`creation

```python
class Projectile:
    __slots__ = ('__speed', '__height', '__angle')
    def __init__(self, speed, height, angle):
        self.__speed = speed
        self.__height = height
        self.__angle = math.radians(angle)
```

## Inheritance

Example

```python
class Tree:
    def sprout(self):
        print('Making new leaves!')

class Oak(Tree):
    pass
    
Oak().sprout() # Output: Making new leaves!
```

super()
- refer implicitly to parent class
- ex: `super().__init__(x, y)`

keyword only argument (`*`)
- additional argument
- enforce keyword only arguments

```python
class R2Vector:
    def __init__(self, *, x, y):
        self.x = x
        self.y = y

    def norm(self):
        return (self.x**2 + self.y**2)**0.5
        
    def __str__(self):
        return f'{self.x, self.y}'
        
class R3Vector(R2Vector):

    def __init__(self, *, x, y, z):
        super().__init__(x=x, y=y)
        self.z = z

v1 = R2Vector(x=2, y=3)
print(v1.norm())
print(v1)
v2 = R3Vector(x=2, y=2, z=3)
```

## Interfaces

- Blueprint for a class
- Set of methods & properties a class should implement
- Define using abc module - `import abc`
	- Abstract base classes
	- Turn regular class to abstract - acts as blueprint for concrete classes
	- `@abstractmethod` decorator
		- modify behavior of function

```python
@spam
def foo():
    pass
```

```python
from abc import ABC

class Equation(ABC):
    def solve(self):
        pass

    def analyze(self):
        pass
        
class LinearEquation(Equation):
    pass

eq = Equation()
lin_eq = LinearEquation()
```

## Getters

- Get values from outside
- Define w/ `@property`

```python
class Nest:
    ...
    @property
    def number_of_eggs(self):
        return self.__number_of_eggs

n = Nest()
print(n.number_of_eggs)
```

## Setters

- Set values indirectly
- Define w/ `@method.setter`

```python
class Nest:
    @number_of_eggs.setter
    def number_of_eggs(self, new_value):
        self.__number_of_eggs = new_value

nest = Nest()
nest.number_of_eggs = 12
```