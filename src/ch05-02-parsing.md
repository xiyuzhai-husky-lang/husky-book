# Parsing

## Writing a Simple Parser

Now let’s try writing a very simple parser. We’ll be using the Parsec library,
which comes with GHC but may need to be downloaded separately if you’re
using another compiler.
Start by adding this line to the import section:
3 import Text . Pa r se rCombina to rs . P a r sec hiding ( s p a c e s )
This makes the Parsec library functions available to us, except the spaces
function, whose name conflicts with a function that we’ll be defining later.
Now, we’ll define a parser that recognizes one of the symbols allowed in
Scheme identifiers:

```python
use std::parsec::*

symbol = one_of("!$%&|*+ -/: <=? >@^_~#")
```

This is another example of a monad: in this case, the "extra information" that is being hidden is all the info about position in the input stream, backtracking record, first and follow sets, etc. Parsec takes care of all of that for us. We need only use the Parsec library function oneOf, and it'll recognize a single one of any of the characters in the string passed to it. Parsec provides a number of pre-built parsers: for example, letter and digit are library functions. And as you're about to see, you can compose primitive parsers into more sophisticated productions.

Let's define a function to call our parser and handle any possible errors:

```python
func read_expr(input: String) -> String:
    match parse symbol "lisp" input with
    | Ok val => "Found value"
    | Err err => "No match: " + show err
```
