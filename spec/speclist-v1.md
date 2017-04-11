
## File naming

1.1 File ends in `.yaon`

```
CORRECT:
mydata.yaon
INCORRECT:
mydata.json
```

## File content

2.1. .yaon file allows any one of the following:

2.1.1. single yaon object without Yaon Guy
```
foo | bar
a | b
```

2.1.2. single yaon object wrapped in Yaon Guys
```
\o/
  foo | bar
  a | b 
\o/
```

2.1.3 multpile yaon objects seperated by Yaon Guys (new line independent)
```
obj | 1
\o/
obj | 2
\o/
obj | 3

$$ OR
obj | 1 \o/ obj | 2 \o/
```

2.1.4 muliple yaon objects with begining and terminating Yaon Guy.
```
\o/
obj | 1
\o/
obj | 2
\o/
obj | 3
\o/
```
2.1.5 a list of yaon objects, each must be wrapped in Yaon Guy
```
CORRECT:
,,,\o/ obj | 1 \o/, \o/ obj | 2 \o/,,,
,,,\o/ obj | 1 \o/, \o/ obj | 2 \o/  $$terminating list commas optional

INCORRECT:
,,, obj | 1, obj | 2 ,,, $$syntax error

,,, \o/ obj | 1 \o/,,, ,,,\o/ obj | 1 \o/,,,  $$two lists at root level
```

### Tokens

3.1. recognized tokens:

3.1.1. Yaon Guy
```
\o/
output: start of YAON object
```
3.1.1.1. Second Yaon Guy is recognized as terminator

3.1.2. Pipe
```
|
```
within yaon, parses value on left side to be key, right side to be value.

3.1.3 New line
```
\n (line return)
```
denotes end of one item and start of another (such as key value pair)

3.1.4. Comma
```
,
```
denotes end of one item and start of another (such as key value pair)

3.1.2. commalipse 
```
,,,
```
Represents start of List (XX)

3.1.2.1 terminating commalipse:
```
,,,
```
represents end of list

3.1.2.2. comma (within list)
```
,
```
seperates items in list.

3.1.2.3 comma, value, pipe (at end of list)
```
, key | val
```
Comma with this lookahead automatically recognizes itself as the list terminator (in lieu of terminating commalipse)
```
EG
,,,listItem1, listItem2, listItem3, notActuallyListItem | butAKeyValue
=> ["listItem1", "listItem2", "listItem3"], { notActuallyListItem: "butAKeyVaue"]
```
**3.1.3.** Double Dollar Sign
```
$$
```
Represents comment from starting point to end of line.

**3.1.4.** Double parenthesis
```
((
))
```
Represents the starting and closing of a block-level comment.

## Data Types (4)

**4.1** Object. Represented with Yaon Guys
```
\o/
\o/
```
```
\o/
key  | value
key2 | value
\o/
```
**4.2** List. Started with commalipses and optionally terminating with them.
```
,,,,,, $$empty list
,,,1,2,3,,,
,,,foo,bar,,,
,,,1,2, ,,,0,-1,,, ,3,4 $$nested list
,,,1,2, \o/ foo | bar \o/, 5, 6
```
**4.3** String. The standard interpretation of a value (from a key/value or list item). Interpreted with whitespace, quotes usually optional.
```
"" $$quotes required for empty string.
this is a string $$=> "this is a string"
"this is a string"
```
**4.4** Number. Automatically parsed when using ints.
```
0
-5
1.03
0.43
.5
```
**4.5** Boolean. True and false, with emoticon aliases
```
true
^_^ $$=> true
false
T_T $$=>false
```
**4.5** Null. No value.
```
null
```
**4.6** Empty. Automatically denotes an empty list, string, or object depending on context
```
\o/
empty object | \o/ -_- \o/ $$=> {}
empty list,,, -_-          $$=> []
empty string | -_-         $$=> ""
\o/
```


## Interpretation

**5.1** value interpretation



