
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

