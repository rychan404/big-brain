[[- FCC Python]]

python modules
- file w/ code for tasks
- import library
	- order alphabetically
- access utilities thru dot notation
- ex: `string.ascii_lowercase()`

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

char class
- matches 1 char specified b/w brackets
- ex: `ma[dnt]` matches either mad, man, or mat

