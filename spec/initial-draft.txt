$$ .----------------. .----------------. .----------------. .-----------------.
$$| .--------------. | .--------------. | .--------------. | .--------------. |
$$| |  ____  ____  | | |      __      | | |     ____     | | | ____  _____  | |
$$| | |_  _||_  _| | | |     /  \     | | |   .'    `.   | | ||_   \|_   _| | |
$$| |   \ \  / /   | | |    / /\ \    | | |  /  .--.  \  | | |  |   \ | |   | |
$$| |    \ \/ /    | | |   / ____ \   | | |  | |    | |  | | |  | |\ \| |   | |
$$| |    _|  |_    | | | _/ /    \ \_ | | |  \  `--'  /  | | | _| |_\   |_  | |
$$| |   |______|   | | ||____|  |____|| | |   `.____.'   | | ||_____|\____| | |
$$| |     YET      | | |    ANOTHER   | | |    OBJECT    | | |   NOTATION   | |
$$| '--------------' | '--------------' | '--------------' | '--------------' |
$$ '----------------' '----------------' '----------------' '----------------'


$$ double dollar commenting because YAON is money!

$$ key vale
prop | val

$$ multiple key/values on line breaks

name | nick
age  | 28
rank | overlord

$$ multiple key/vals on the same line using a comma
name | nick, age | 28, rank | inline-overlord

$$ map key to list, use ",,," instead of pipe

prop | val
prop,,,
 val
 val2
 val3

prop,,, val1, val2, val3,,, nextProp | val $$ inline versoin
prop,,, val1, val2, val3, nextProp | val $$ also valid. `nextprop` automatically detected as key

$$ properties and values can have white space
prop | valid
this is a valid prop name | this is a valid

this prop is valid | this value is valid $$ in JSON: {"this prop is valid": "this value is valid"}

$$ yaon inside yaon, add a guy streatching!

yaon \o/ inner prop | inner value \o/ $$ { yaon: { "inner prop": "inner value" } }


$$ below, yoan in all its greatness

simple | foo
number | 23
with whitespace | so valid brah
as a list,,,
  item1
  item2
  item3
yaon \o/
  i love inner-yaons | why is that?
  let me tell you why,,, more complex data, you get to use the little "yaon"ing guy
  \o/
comments | (( inline comments are ignored )) where?
escape slach enabled | \(( this will be rendered )) was that a comment?
? | wait... you can use "?" as the key? God save the person maintaining your code...
