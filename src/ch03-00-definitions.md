# Definitions

In Husky, one can define

- `package`
- `type`
- `module`
- `form`

## package

A package is a minimal unit for ...

Let’s walk through what happens when we create a package. First, we enter the
command `corgi new`:

```console
$ corgi new my-project
     Created binary (application) `my-project` package
$ ls my-project
Corgi.toml
main.hsy
```

After we run `corgi new`, we use `ls` to see what Corgi creates. In the project
directory, there’s a *Corgi.toml* file, giving us a package. There’s also a
*src* directory that contains *main.rs*. Open *Corgi.toml* in your text editor,
and note there’s no mention of *src/main.rs*. Corgi follows a convention that
*src/main.rs* is the crate root of a binary crate with the same name as the
package. Likewise, Corgi knows that if the package directory contains
*src/lib.rs*, the package contains a library crate with the same name as the
package, and *src/lib.rs* is its crate root. Corgi passes the crate root files
to `rustc` to build the library or binary.

Here, we have a package that only contains *src/main.rs*, meaning it only
contains a binary crate named `my-project`. If a package contains *src/main.rs*
and *src/lib.rs*, it has two crates: a binary and a library, both with the same
name as the package. A package can have multiple binary crates by placing files
in the *src/bin* directory: each file will be a separate binary crate.

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

- `enum` allow you to define a type by enumerating its possible *variants*. It's more controllable than inheritance in object-oriented programming.

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

    ```rust
    #[rust_ffi(do_something)]
    fn do_something();
    ```
