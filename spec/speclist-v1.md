
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
