# First Steps

It's time for your first Husky binary program. This program will read a name
off the command line and then print a greeting. Create a file ending in `main.hsy` and
type the following text:

```python
main:
    args = std::env::get_args()
    print("Hello," + args[0])
```

as compared with the original haskell program

```haskell
module Main where
import System.Environment
main :: IO ()
main = do args <− getArgs
        putStrLn ("Hello," ++ args !! 0)
```
