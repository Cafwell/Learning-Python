## Using functions

In terms of *calling* functions, we have seen:
+ free functions like print() and range()
+ functions on objects (also called "methods") like my_list.append() and my_str.split()

There are also codes like:
+ data literals like 10, "hello" and [1, 2]
+ syntax like for house in town: and if height > 10:

There is a official web tells all those things:
https://docs.python.org -> 
1. [Library Reference](https://docs.python.org/3/library/index.html)
2. [Language Reference](https://docs.python.org/3/reference/index.html)

### Built-in functions


## Importing functions
### The math module
```Python
>>> import math
# the square root function
>>> math.sqrt(25)
5.0
```
You can also grab a single function from a module:
```Python
>>> from math import sqrt
>>> math.sqrt(25)
5.0
```
A import * way
```Python
>>> from math import *
>>> print(cos(pi))
-1.0
```

## Writing fuctions

```Python
>>> def o_to_g(o):
    if o > 0:
        g = o * 28.3495
        return g
    else:
        print("value is a negtive num")
        return("Try again")

>>> print(o_to_g(-1))
value is a negtive num
Try again
```

---
Exercise

Having a list like: my_list = [5, 7, 34, 5, 3, 545]
if num > 10, print them like [34, 545]

<details>
  <summary><b>Answer</b></summary>
  <pre><code> 
>>> def big(numbers):
    a = []
    for num in numbers:
        if num > 10:
            a.append(num)
    return a
>>> my_list = [5, 7, 34, 5, 3, 545]
>>> large_numbers = big(my_list)
>>> print(large_numbers)
[34, 545]
    </code></pre>
</details>
