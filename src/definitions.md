# Definitions

In Husky, one can define

- `package`
- `type`
- `module`
- `form`

## package

A package is obviously a package.

## module

A module is obviously a module.

```rust
mod haha
```

## types

A `type` is a whatever.

There are five ways of defining types:

- `struct` define a new type

```rust
struct A:
    x: i32
    y: i32
```

- `enum` define a new type

- `monad` define

```rust
monad struct A
```

- `structure` define a new concept

- `inductive` define a new type

```Lean
inductive Nat
| Zero
| Succ Nat
```

Generic types

## forms

A `form` is a function, method or feature defined by stmts and exprs.

- function
- method
- feature. This is equivalent to constants by default. However, this can be much more ...

In Husky, there are multiple paradigms for defining a form:

- `proc` eager procedural. Like Rust.

```rust
proc haha(a: i32) -> i32:
    let b = 1
    var c = 1
    c++
    return b
```

- `func` eager functional. Like Ocaml.

```rust
func haha(a: i32) -> i32:
    b = 1
    c = 1
    b
```

- `def` lazy functional ascended. Like Haskell but more.

```python
# placeholder x

def b -> i32:
    x + 1

def a -> i32:
    # integrate b against x
    integrate b
```

- `fn` ffi.

```
#[rust_ffi(do_something)]
fn do_something();
```
