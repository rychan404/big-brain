[[- FCC Python]]
## Conditional Statements

`if condition:`

`elif condition:`

`else:`

ternary syntax
- concise way to write if/else conditionals
- ex: `val_1 if condition else val_2`

Difference between `is` and `==`
- ``is`` - check if 2 variables point to same object in memory
- `==` - check if 2 variables have the same value

## Loops

`for i in str:`
- i sequentially takes values of elements in str
- use _ as a placeholder

`while condition:`

## Structural Pattern Matching

- enables matching pattern w/ subject value

```python
match value:
    case x:
        <code>
    case y:
        <code>
```

- enables verification of subject having specific structure
- binds names in pattern to elements of subject

```python
match my_list:
    case [a]:
        print(a)
    case [a, b]:
        print(a, b)
```