# Statements

## initialization statement

There are different ways to initialize a variable in different paradigms.

- `proc`

We need to specify whether a variable is mutable or not in a procedural paradigm.

Define an immutable.

```swift
let a = 1
```

Define a mutable variable.

```swift
var a = 1
```

- `func` | `def`

Everything is immutable, so we can initialize with a pythonic syntax

```swift
a = 1
```

## `if` statement

```rust
if true:
    a = 1
```

```rust
if true:
    a = 1
elif false:
    a = 2
```

```python
if true:
    a = 1
elif false:
    a = 2
else:
    b = 3
```

## `match` statement

```python
match a with
| 1 =>:
    something
| 2 =>:
    something
```

```ocaml
match a with
| 1 => something
| 2 => something
```

```ocaml
match a into
| 1 => something
| 2 => something
```

## loop statment

### `for`
```rust
for i < 10: // i=0, 1, 2, ... , 9
    ...
```

```rust
for i > -10: // i=0, -1, -2, ... , -9
    ...
```

```rust
for 3 <= i <= 9: // i = 3, 4, ... , 9
    ...
```

```rust
for 9 >= i > 2: // i = 9, 8, ... , 3
    ...
```

### `for in` 

```rust
for i in 1..10: // i = 1, 2, ... , 9
    ...
```

```rust
for i in a_list // i = 1, 2, ... , 9
    ...
```



### `while` 

```python
while i < 10:
    <do something>
```

### `forext` 

```rust
var i = 9
forext i > 0: // i = 9, 8, ..., 1
    <do something>
```

### `do while` 
```python
var i = 9
do while i > 0:
    <do something>
```
