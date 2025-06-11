[[- FCC Python]]

python modules
- file w/ code for tasks
- import library
	- order alphabetically
- access utilities thru dot notation
- ex: `string.ascii_lowercase()`

```python
# Prevent code from running when imported as module
if __name__ == '__main__':
	pass
```

## Random

`random.random()`
- num b/w 0.0 (inclusive) & 1.0 (exclusive)

`random.choice('')`
- takes sequence & returns rand item

## Secrets

`secrets.choice('')`
- same as `random.choice('')`
- secured randomness

## Regex

re
- pattern to match specific char combo
- alternative to if/else when matching/finding str patterns

`re.search('')`
- looks for 1st place where regex matches str

`re.compile('')`
- compiles str to regex
- `re.compile('i+')`
		+ = quantifier (specify num of times char is repeated)
		ex: + means repeat 1 or more times

`re.search(pattern, '')`
- combination of `re.search('')` & `re.compile('')`

`re.findall(pattern, '')`
- same as `re.search('')` but all occurrences

`re.sub(pattern, replacement, string)`
- replace text inside string based on regex pattern
- arguments: 
	- regex pattern to match
	- replacement
	- string you want to perform replacement

```python
verse = 'Always look on the bright side of life'
spam = re.sub('bright', 'spam', verse)
spam == 'Always look on the spam side of life' # True
```

- Lookaround: assertion that matches pattern w/o consuming characters in string
	- Lookbehind (positive or negative)
		- `?<=... and ?<!...` (respectively)
	- Lookahead (positive or negative)
		- `?=... and ?!...` (respectively)
		- match pattern if followed by certain sequence of chars

```python
# Lookbehind

spam = 'black back bat'
re.sub('(?<=l)a', 'o', spam) == 'block back bat' # True (match 'a' char only preceded by 'l') - positive
re.sub('(?<!l)a', 'o', spam) == 'black bock bot' # True (match 'a' char if not preceded by 'l') - negative
```

```python
# Lookahead

spam = 'black back bat'
re.sub('a(?=t)', 'o', spam) == 'black back bot' # True (match 'a' char only when followed by a 't') - positive
re.sub('a(?!t)', 'o', spam) == 'block bock bat' # True (match 'a' char if not followed by a 't') - negative
```
### Char Class

- matches 1 char specified b/w brackets
- ex: `ma[dnt]` matches either mad, man, or mat

- indicate range with hyphen (-)
- ex: `[a-z]t` matches with at, bt, ct, etc.

- ^ matches all chars except specified in class (like a not)
- ex: `[^a-z]t` matches with only ' t'

- combine multiple ranges
- ex: `[a-d3-6]` is the same as combining `[a-d]` & `[3-6]`

- dot char (.): matches any char in string except newline char
- ex: `'.+'`

- match special meaning chars using escape chars (backslash)
- ex: `'\+'`

- `\d` = `[0-9]`
- `\D` = `[^0-9]`
- `\w` = alphanumeric chars & underscore
- `\W` = non-alphanumeric chars & underscore
### Raw Strings

- backslashes are treated as real chars, not escape chars
- prefix w/ r
- ex: `print(r'\')`
