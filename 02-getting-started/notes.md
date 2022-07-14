# course overview

the course is 100% applicable to python version `3.6` released in 2016.

it is not applicable to python version `3.7`  to `.10`

# installing and starting python

## intstalling python

use `python3` command on command line to launch python in your CLI

the triple arrow `>>>` displayed in the CLI means python is waiting for our input.

## interactive python

we can start using it immediately.

the interactive CLI environment is a `read, eval, print` loop

python will
1. **read** everything we type in
2. **evaluate** it 
3. **print** the result, and loop back to the beginning

this is also known as the `REPL` >>> the read, eval, print loop.

### typing in the command line

* can initialize variables in the cli and reference them
```py
>>> x = 5
>>> x
5
>>> 3 * x
15
```

* can use the `_` variable to reference the most recently printed value
```py
>>> 3 * x
15
>>> _
15
```

can also use the `_` variable in an expression
```py
>>> 3 * x
15
>>> _
15
>>> _ * 2
30
```
this is one of the very few obscure shortcuts in python

note: the `_` variable doesn't have any behavior in python scripsts or program. this functionality is only in the RE
some commands don't have return values

```py
>>> x = 5
```

we assigned the value of 5 to x and there was no return value from that command.

```py
>>> print('Hello, Python')
Hello, Python
```

this command printed the string `Hello, Python`

`print` is one of the biggest differences between Python 2 and Python 3.

- in Python 3, the parenthesis are **required**
  - `print("Python 3")`
  - this is because `print` in Python 3 is a function call

- in Python 2, the parenthesis are **not required**
  - `print "Python 2"`

### how to exit REPL

send the end-of-file control character, `CTRL-D` on mac/linux systems

`CTRL-Z`, then  `Enter` on windows systems

## significant whitespace

basic code structure

control flow structures
- for-loops
- while-loops
- if-statements

are all introducted by statements that are terminated by a **colon**, `:`

python will change the prompt to three dots `...` requesting that you provide the body of the for-loop.

example:

`for-loop`

```py
>>> for i in range(5):
...
```

leading whitespace is **syntactically significant** in python.

python uses **indentation levels** rather than curly braces `{}` to demarcate code blocks.

by convention, contemporary python code is indented by `4` spaces for each level. this can be accomplished by hitting the <kbd>Tab</kbd> key.

so, we provide those four spaces and a statement to form the body of our for loop.

```py
>>> for i in range(5):
...     x = i * 10
...     print(x)
```

our for-body is finished after our print(x)statement. to terminate our block of code, we must enter a blank line into REPL.

```py
>>> for i in range(5)
...     x = i * 10
...     print(x)
...
```

after doing do, our code is evaluated and executed and our prompt `>>>` returns after it is finished.

```py
>>> for i in range(5)
...     x = i * 10
...     print(x)
...
0
10
20
30
40
>>>
```

looking at more significant examples of code clearly demonstrate how indentation matters in differentiating different blocks of code.

![example](content/sigWhitespace.png)

the whitespace **must** match the structure of your program.

even with code removed, we can see different colored bars with different levels of indentation that visually help us see the levels of code.

![example2](content/sigWhitespaceNoCode.png)

each level of indentation is **typically** four spaces.

advantages to significant whitespace:

1. forces developers to write readable code 
2. no clutter with unnecessary braces
3. human and computer can't get our of sync

rules for indentation

1. prefer **four spaces**
2. **never** mix tabs and spaces
3. be **consistent** on consecutive lines
4. only deviate to **improve** readability

> "programming as Guido intended (or indented) it"

## python culture

development of python is managed thru PEPs, or `python enhancement proposals`

PEP 8 recommends we use four spaces for indentation of our code

PEP 20 describes the zen of python, the 20 aphorisms that describe the guiding principals of python, 19 of which are written down

it can also be access from the REPL by typing `import this`

```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

### moment of zen 1: readbility counts

Readability Counts
- Clarity matters
- So readability makes
- For valuable code

## using the standard library

the standard library contains modules

you gain access to standard library modules by uding the `import` keyword

the basic method of importing a module is this syntax:  `import module_name`

example:

using the standard library's `math` module to perform some calculations

we can access something inside of a module with the syntax `module.attribute_name`

```py
>>> math.sqrt(81)
9.0
>>> 
```

how do we know which modules have certain attributes or methods?

REPL has a built-in `help` function that can retrieve any embedded documentation form objects for which it has been provided

```
>>> help
Type help() for interactive help, or help(object) for help about object.
>>> 
```

### using the `math` module

```
>>> help(math)
```

prints this to the console:

```
Help on module math:

NAME
    math

MODULE REFERENCE
    https://docs.python.org/3.8/library/math
    
    The following documentation is automatically generated from the Python
    source files.  It may be incomplete, incorrect or include features that
    are considered implementation detail and may vary between Python
    implementations.  When in doubt, consult the module reference at the
    location listed above.

DESCRIPTION
    This module provides access to the mathematical functions
    defined by the C standard.

FUNCTIONS
    acos(x, /)
        Return the arc cosine (measured in radians) of x.
    
    acosh(x, /)
        Return the inverse hyperbolic cosine of x.
    
    asin(x, /)
        Return the arc sine (measured in radians) of x.
...
```

we can scroll thru the list using the arrow keys on mac/linux or <kbd>Spacebar<kbd> on windows

press <kbd>Q</kbd> to exit the `help` browser and return to REPL.

we can use help to look up specific functions in modules, too.

```
>>> help(math.factorial)
Help on built-in function factorial in module math:

factorial(x, /)
    Find x!.
    
    Raise a ValueError if x is negative or non-integral.
(END)
```

again, press <kbd>Q<kbd> to return to REPL.

it can be very verbose to reference the same math module each time a function or method is used from it.

our calculation calculates how many different ways we can choose `k` number of items from `n` number of total items

example:

```py
>>> n = 5
>>> k = 3
>>> math.factorial(n) / (math.factorial(k) * math.factorial(n-k))
10.0
>>>
```

we had to repeat using the `math` module each time we referenced the `factorial` function from `math`

#### `from module_name import attribute_name`

instead, we can import **specific** functions from modules into the current namespace with the syntax `from math import factorial`

example:

```py
>>> from math import factorial
>>> factorial(n) / (factorial(k) * factorial(n-k))
10.0
```

it's an improvement, but is still a lot of code for such a simple expression. 

#### `from math import factorial as fac`

a third form of the `import`  statement allows us to rename the imported function with the syntax `from math import factorial as fac`

example:

```py
>>> from math import factorial as fac
>>> fac(n) / (fac(k) * fac(n-k))
10.0
```

this can be used to make code more readable or to avoid name clashes

as useful as it is, this style of the import statement should be used infrequently and judiciously

remember that when we used `factorial` by itself, it returned an `integer`

but when we performed a division calculation with multiple factorials, it's returning a `floating point integer`

this is because we have used python's `floating point division operator`, and single forward-slash `/`

we can improve our expression since we know it will only ever return integral results.

we can do this by using python's `integer division operator`, which is a double forward-slash `//` 

example:

```py
>>> fac(n) // (fac(k) * fac(k-n))
10
>>>
```

most programming languages would fail on the above expression for even moderately high values of `n`

this is because in most programming languages, regular signed integers can only store values less than 2<sup>31</sup> - 1, which equals `2147483647`

however, factorials growso fastthat the largest factorial that you can fit into a 32-bit signed integer is 12 factorial, since 13 factorial is too large.

in most-widely used programming languages, we would need more complex code or more sophisticated mathematics merely to compute how many ways there are to 
