[[- FCC Python]]

`raise`
- custom error message
- ex: `raise ValueError("Invalid value")`
	       exception   custom message

`try/except`
- `try` - encapsulate code that might raise exception
- `except` - alternative code if exception occurs

```python
try:
    <code>
except:
    <code>
```

Specify exception type (good practice)

```python
try:
	<code>
except ValueError:
	<code>
```