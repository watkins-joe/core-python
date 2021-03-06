table of contents

- [course overview](#course-overview)
- [installing and starting python](#installing-and-starting-python)
  - [intstalling python](#intstalling-python)
  - [interactive python](#interactive-python)
    - [typing in the command line](#typing-in-the-command-line)
    - [how to exit REPL](#how-to-exit-repl)
  - [significant whitespace](#significant-whitespace)
  - [python culture](#python-culture)
    - [moment of zen 1: readbility counts](#moment-of-zen-1-readbility-counts)
  - [using the standard library](#using-the-standard-library)
    - [using the `math` module](#using-the-math-module)
      - [`from module_name import attribute_name`](#from-module_name-import-attribute_name)
      - [`from math import factorial as fac`](#from-math-import-factorial-as-fac)
  - [summary](#summary)
- [scalar types, operators, and control flow](#scalar-types-operators-and-control-flow)
  - [scalar types](#scalar-types)
    - [`integers`](#integers)
    - [`float`](#float)
    - [`None`](#none)
    - [`bool`](#bool)
  - [relational operators](#relational-operators)
    - [control flow](#control-flow)
      - [if-statement syntax](#if-statement-syntax)
        - [else-clause](#else-clause)
      - [while-loops](#while-loops)
        - [`break`](#break)
  - [summary](#summary-1)
- [introducing strings, collectons, and iteration](#introducing-strings-collectons-and-iteration)
  - [`str`](#str)
  - [`string literals`](#string-literals)
    - [newline](#newline)
    - [escape sequences](#escape-sequences)
    - [string features](#string-features)
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

in most-widely used programming languages, we would need more complex code or more sophisticated mathematics merely to compute how many ways there are to draw 3 fruit from a set of 13 fruits. 

python encounters no such problems and can compute with arbitrarily large integers limited only by the memory in my computer.

how many different pairs of fruit can we pick from 100 fruit?

to emphasize how large 100 factorial is, we calculated it in our console:

```py
>>> from math import factorial as fac
>>> fac(100)
93326215443944152681699238856266700490715968264381621468592963895217599993229915608941463976156518286253697920827223758251185210916864000000000000000000000000
>>> 
```

we can convert this integer to a text string and count the number of characters in it:

```py
>>> len(str(fac(100)))
158
>>> 
```

158 digits! that's a lot.

## summary

we learned
* how to download and install python
* starting python REPL
* evaluating simple expressiona and mathematic calculations in REPL
* the role of underscore in the REPL
  * the value of `_` in REPL is the result of the last evaluated expression
* how to make basic use of the `print()` function
  * that the printed output is a **side effect**  of the function, **not** a return value
* how to exit REPL
  * using <kbd>CTRL</kbd> + <kbd>Z</kbd> on windows or <kbd>CTRL</kbd> + <kbd>D</kbd> on Linux and macOS
* how python uses significant whitespace
  * code blocks are initiated  with a colon and comprise consecutive lines at the same indentation level
  * advantages of significant whitespace
    * clarity
    * consistency
  * rules for indentations
* python culture
  * the zen of python
    * can be printed in REPL by typing `import this` in REPL
  * "readability counts"
* importing standard library modules
    1. `import from`
       - importing an entire module
    2. `from module import name`
       - importing selected/specific elements of a module
    3. `from module import name as name2`
       - renaming imported elements
* using python's help system
* learned how to use python's `factorial` function from python's standard math library

# scalar types, operators, and control flow
## scalar types

python comes with a number of built-in  data types

these include **primitive** scalar types like `integers` as well as **collection** types like `dictionaries`

| Data Type  | Description                     | Example            |
| ---------- | ------------------------------- | ------------------ |
| `int`      | arbitrary precision integer     | `42`               |
| `float`    | `64-bit` floating point numbers | `4.2`              |
| `NoneType` | the `null` object               | `None`             |
| `bool`     | `boolean` logical values        | `true` and `false` |


### `integers`

python integers are **signed** and have, for all practical purposes, unlimited precision, meaning they can contain as many digits as you need.

integer literals are specified in decimal:

```py
>>> 10
10
>>> 
```

they may also be specific in `binary` with the `0b` prefix:

```py
>>> 0b10
2
>>>
```

or `octal` with the `0o` prefix:

```py
>>> 0o10
8
>>> 
```

or in `hexadecimal` with the `Ox` prefix:

```py
>>> 0x10
16
>>>
```

can also create integers with the `int` constructor function

```py
>>> int(3.5)
3
>>> 
```

- this can convert from other numeric types (like floats) to integers
- the rounding of integers is always rounded down towards zero

can also convert `strings` to `integers`

```py
>>> int("496")
496
>>> 
```

you can supply an optional number base when converting from a `string`

```py
>>> int("10000", 3)
81
>>> 
```

### `float`

floating point numbers are supported in python by the `float` type

python floats are implemented as `IEEE-754 double-precision` with `53-bits of binary precision`
- this is equalivalent to between 15 and 16 significant digits in decimal

any literal number containing a decimal is interpreted by python as a `float`

```py
>>> 3.125
3.125
>>> 
```

scientific notation can also be used. an example being the speed of light in meters per second.

```py
>>> 3e8
300000000.0
>>> 
```

for small numbers, like Planck's constant, 1.616 times 10<sup>-35</sup>

```py
>>> 1.616e-35
1.616e-35
>>> 
```

notice how it switched the display representation, that is, the format it prints to the REPL, to the most readable form.

as with integers, convert to floats from other numeric or string stypes  using the float constructor function

we can pass int values to the float constructor:

```py
>>> float(1)
1.0
>>>
```

we can also pass strings:

```py
>>> float("1")
1.0
>>> 
```

this is also how  we create the special floating point values `nan` or `not a number`

```py
>>> float("nan")
nan
>>>
```

as well as positive infinity and negative infinity

```py
>>> float("inf")
inf
>>> float("-inf")
-inf
>>> 
```

**NOTE: the result of any calculation involving an `int` and a `float` is promoted to a `float`.**

```py
>>> 3.0 + 1
4.0
>>> 
```

### `None`

python has a special `null` value called `None`, spelled with a capital `N`.

`None` is frequently used to represent the absence of a value.

the python REPL **never** prints `None` results, so typing `None` into the REPL has no effect

```py
>>> None
>>>
```

`None` can be assigned to variables just like an other object

we can check whether an object is `None` by using python's `is` operator

```py
>>> a = None
>>> a is None
True
>>>
```

### `bool`

the `bool` type represents boolean logical values (`True` and `False`) and plays an important role in several of python's control flow structures

there are two `bool` values, `True` and `False`, both spelled with the first letter capitialized

```py
>>> True
True
>>> False
False
```

there is also a `bool` constructor that can be used to convert from other types to `bool`

for integers, `0` is considered `falsy` and all other values, including negative numbers, `truthy`

```py
>>> bool(0)
False
>>> bool(42)
True
>>> bool(-1)
True
>>> 
```

the same behavior applies to `float` types, again where only `0` is considered `falsy`

```py
>>> bool(0.0)
False
>>> bool(0.207)
True
>>> bool(-1.117)
True
>>> 
```

whenc converting from collections, such as strings or lists, only empty values are considered `falsy`

for lists, the empty list is falsy

```py
>>> bool([])
False
>>>
```

while any non-empty list is `truthy`

```py
>>> bool([1, 5, 9])
True
>>> 
```

similarly, empty `strings` are `falsy`

```py
>>> bool("")
False
>>> 
```

while any other string is `truthy`

```py
>>> bool("Spam")
True
>>> 
```

the `bool` constructor may not behave how you would expect when passing in the strings `"True"` and `"False"`

```py
>>> bool("True")
True
>>> bool("False")
True
>>> 
```

since both are non-empty `strings`, both result in `True`

## relational operators

`bool` values are commonly produced by python's relational operators which can be used for comparing objects

| Description                      | Example |
| -------------------------------- | ------- |
| value equality / equivalence     | `==`    |
| value inequality / inequivalence | `!=`    |
| less-than                        | `<`     |
| greater-than                     | `>`     |
| less-than or equal to            | `<=`    |
| greater-than or equal to         | `>=`    |

two of the most widely used relational operators are pythons equality (`==`) and inequality (`!=`) tests

these test whether two objects are equivalent or inequivalent -- whether one can be used in place of the other or not.

```py
>>> g = 20
>>> g == 20
True
>>> g == 13
False
>>> g != 20
False
>>> g != 13
True
>>> 
```

we can also compare the order of quantities using the rich comparison operators

```py
>>> g < 30
True
>>> g <= 20
True
>>> g > 30
False
>>> g >= 20
True
>>> 
```

### control flow

conditional statements allow us to branch execution of our code based on the value of an expression

#### if-statement syntax

the **form** of the statement is the `if` keyword, followed by an `expression`, terminated by a colon `:` to introduce a new code block

```py
if expression:
    block
```

at the REPL:

```py
>>> if True:
...     print("It's true!")
... 
It's true!
>>> 
```

remember to terminate the block of code with a blank line!

if false, the code does not execute.

```py
>>> if False:
...     print("It's true!")
... 
>>> 
```

the expression used with the if-statement will be converted to a `bool`, just if the `bool` constructor had been used

so explicitly constructing a `bool` in the if-statement is exactly equivalent to using a bare string.

```py
>>> if bool("eggs"):
...     print("Yes please!")
... 
Yes please!
>>> if "eggs":
...     print("Yes please!")
... 
Yes please!
>>> 
```

thanks to this useful shorthand, explicit conversion to `bool` using the `bool` constructor is rarely used in python.

##### else-clause

optional block that goes in a block introduced by th else keyword followed by a colon `:` which is indented to the same level as the `if` keyword

```py
>>> h = 42
>>> if h > 50:
...     print("Greater than 50")
... else:
...     print("50 or smaller")
... 
50 or smaller
>>> 
```

for the `else` keyword in this case, we just omit the indentation after the three dots.

for multiple conditions, use python's `elif` keyword, which is a combined else-if. the zen of python reminds us that flat is better than nested.

```py
>>> if h > 50:
...     print("Greater than 50")
... elif h < 20:
...     print("Less than 20")
... else:
...     print("Between 20 and 50")
... 
Between 20 and 50
>>> 
```

the above is much easier to read than this:

```py
>>> if h > 50:
...     print("Greater than 50")
... else:
...     if h < 20:
...         print("Less than 20")
...     else:
...         print("Between 20 and 50")
... 
Between 20 and 50
>>> 
```

#### while-loops

while loops in python are introduced by the `while` keyword, followed by a `boolean` expression

just like the condition for if-statements, the expression is implicitly converted to a boolean value as if had been passed to the `bool` constructor

the while statement is terminated by a colon because it introduces a new block

```py
while expression:
    block
```

example loop that counts down from 5 to 1

```py
>>> while c != 0:
...     print(c)
...     c -= 1
... 
5
4
3
2
1
>>> 
```

new language feature is the **augmented assignment operator**, a minus sign followed up an equal sign to subtract one from the value of `c` on each iteration.

because the expressions are implicitly converted to a bool, we can also write the loop this way:

```
>>> while c:
...     print(c)
...     c -= 1
... 
5
4
3
2
1
>>> 
```

why? because
* c is truthy when initialized at 5 because 5 is != 0. 0 is a falsy value and would terminate the while loop. this repeats until the value of `c` reaches 0.

however, doing this may be considered "unpythonic" because referring back to the zen of python, "explicit is better than implicit"

we place higher value on the readability of the first form over the consision of the second form.

while-loops are often used in python where an infinite loop is required.

we can create an infinite loop in REPL that will never end, but we can terminate it with CTRL+C on mac

```py
>>> while True:
...     pass
... 
^C
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
KeyboardInterrupt
>>> 
```

##### `break`

python requires you to use `while True`and `break` together with an early exit facilitated by the `break` statement

the `break` statement jumps out of the inner-most executing loop to the line immediately after it

example of break:

```py
>>> while True:
...     response = input()
...     if int(response) % 7 == 0:
...             break
... 
8
9
10
14
>>> 
```

1. we write an infinite loop that asks the user for input using the `input()` function
2. we assign the value that the user enters in that the input function returns to a variable called `response`
3. we write an if-statement that first converts the input in the response variable to an integer and checks if the input is divisible by  7 using the modulo operator (`%`)
   1. if it is, we break out of the loop
   2. if it is not, our program asks the user for another input.
4. the loop continues to ask for input until correct input is entered, or we terminate the program

## summary

we..
* looked at data types `int`, `float`, `None`, and `bool`
* reviewed relational operators for equivalence and ordering
* wrote conditional code containing if-elif-else statements
* used while-loops to ask the user for input with an infinite `while True:` loop
* learned that while-loop expressions, like if-statements, are converted to `bools`
* learned how interrupt/terminate infinite loops with <kbd>CTRL</kbd> + <kbd>C</kbd> on macOS and that doing this generates a `KeyboardInterrupt` exception
* learned how to break out of loops using the `break` statement
  * observed that `break` only exits the **inner-most executing loop**
  * and that it takes execution to the first statement following the loop that we broke out of
* looked at **augmented assignment operators** like `-=` and `+=` for modifying iterator/counter variables in-place
* requesting text input from the user with the `input()` function

# introducing strings, collectons, and iteration

## `str`

strings in python have the data type `str` and we have already been using them extensively.

strings are a **sequence of Unicode code points**. we can think of code points as being like characters, although they are not strictly equivalent.

the sequence of characters in a python string is **immutable**, meaning that once a string has been constructed, you cannot modify its contents.

`literal strings` in python are delimited by single quotes or double quotes.
 - this differs from `C` where `char`s can only be delimited by single-quotes (`'A'`) and `string`s can only be delimited by double quotes (`"This is a string"`)
   - and technically, `string` is not a data type in `C`, but is rather an array of `char`s terminated by the `null` character (`\0`) represented like so: 
        ```c
        char greetings[] = "Hello World!"
        ```

```py
>>> 'This is a string'
'This is a string'
>>> "This is also a string"
'This is also a string'
>>> 
```

no matter which type of quotes you decide to use for strings in python, you must be consistent

you can't use single quotes on one side and double quotes on the other, like below:

```py
>>> 'This is also a string"
  File "<stdin>", line 1
    'This is also a string"
                           ^
SyntaxError: EOL while scanning string literal
>>> 
```

this allows us to use single quotes where they apply in normal english in a string and avoids from having to escape characters.

```py
>>> "It's a good thing"
"It's a good thing"
>>> '"Yes!", he said, "I agree!"'
'"Yes!", he said, "I agree!"'
>>> 
```

## `string literals`

adjacent string literals are concatenated by the python compiler into a single string, which can be useful for nicely formatted code

```py
>>> "first" "second"
'firstsecond'
>>> 
```

### newline

if you want a string literal containing new lines, we have two options

1. use multi-line strings
    - spread the string literal across multiple lines

multi-line strings are delimited by three quote characters rather than one

```py
>>> """This is
... a multiline
... string"""
'This is\na multiline\nstring'
>>> 
```

when the string is echoed back to us in REPL, the new lines are represented by the `\n` escape character

we can also use three single-quotes

```py
>>> '''So 
... is
... this.'''
'So\nis\nthis.'
>>> 
```

2. use escape sequences
    - embed escape sequences in a single-line string literal

as an alternative, we can just embed the `\n` characters into the string literal ourselves

to get a better sense of what we are representing, we can use the print function to see the string

```py
>>> m = 'This string\nspans multiple\nlines'
>>> m
'This string\nspans multiple\nlines'
>>> print(m)
This string
spans multiple
lines
>>> 
```

python 3 translates `\n` to the appropriate, native newline sequence for your platform/OS

### escape sequences

we can use the escape sequence for other purposes, too like:

1. incorporating tabs with `\t`
2. allowing us to quote characters within strings
```py
>>> "This is a \" in a string"
'This is a " in a string'
>>> 'This is a \' in a string'
"This is a ' in a string"
>>> 
```

to put a backslash in a string, we escape the backslash with itself

to reassure ourselves that there really only is one backslash in that string, we can again use the print function

```py
>>> k = 'A \\ in a string'
>>> k
'A \\ in a string'
>>> print(k)
A \ in a string
>>> 
```

### string features

you can create a `raw string` in python, useful or things like regex patterns or file paths that use backslashes extensively

raw strings **don't support any escape sequences** and are essentially *what you see is what you get*

to create a raw string, prefix the opening quote with a lowercase `r`

```py
>>> path = r'C:\Users\Merlin\Documents\Spells'
>>> path
'C:\\Users\\Merlin\\Documents\\Spells'
>>> print(path)
C:\Users\Merlin\Documents\Spells
>>> 
```

we can use the string constructor to create string representations of other types, such as `integers` or `floats`

```py
>>> str(6.02e23)
'6.02e+23'
>>> 
```

strings in python are what are called sequence types, which means they support certain common operations for querying sequences

we can access individual characters using square bracket notation with an integer 0-based index

```py
>>> s = 'parrot'
>>> s[4]
'o'
>>> 
```

in contract to other programming languages, there is no separate character type distinct from the `string` type. for example, `C` has the `char` data type and while it doesn't technically have a `string` type, a `string` is an array of `char`s

```c
char greetings[] = "Hello World!";
```

this means that even though we are accessing only one character of a string in our example above, it is still of the `string` type. we can test this

```py
>>> type(s[4])
<class 'str'>
>>> 
```

string objects also support a  wide variety of operations/methods

we can list those methods using the help function on the string type

we will try the `capitalize` method

like other languages, we use object/dot notation to call methods on objects

```py
>>> c = "oslo"
>>> c.capitalize()
'Oslo'
>>> 
```

remember that strings are **immutable**, so the `capitalize` method didn't modify `c` in-place. rather, it returned a **new** string.

we can verify by this by displaying `c` again in REPL, which remains unchanged

```py
>>> c
'oslo'
>>> 
```

strings (`str`) are unicode-capable, meaning we can use them with international characters easily, even in string literals.

this is because the default source code for python 3 is `UTF-8`.

if we have access to Norwegian characters, we can store them in a string literal without issue

```py
>>> "Vi er s?? glad for ?? h??re og l??re om Python!"
'Vi er s?? glad for ?? h??re og l??re om Python!'
>>>
```

we can even write the hexadecimal representations of Unicode code poinst as an escape sequence prefixed by `/u`, such as:

```py
>>> "Vi er s\u00e5 glad for \u00e5 h\xf8re og l\u00e6re om Python!"
'Vi er s?? glad for ?? h??re og l??re om Python!'
>>> 
```

similarly, we can use thee `\x` escape sequence followed by aa two-character hexadecimal string or an escaped octal string to include Unicode characters in a string literal

```py
>>> '\xe5'
'??'
>>> '\345'
'??'
>>> 
```

there are no such Unicode capabilities in the otherwise similar `bytes` type
