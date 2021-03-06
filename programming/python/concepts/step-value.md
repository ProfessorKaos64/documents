<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [About](#about)
- [Concept](#concept)
- [Example](#example)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# About

Notes using step values

# Concept

```
step = 2
for i in range(0, 100, step):
     print i
```

The above will print 0 to 100 in steps of 2. ie 0,2,4,6 etc...

# Example
```
def ask_number(question, low, high, step = 1):
     """Ask for a number within a range."""
     response = None
     while response not in range(low, high, step):
         response = int(input(question))
     return response
```

The trick is, you have to include the argument in the function parameter 
list, AND give it a value. The part "step=1" inside the parentheses of 
the "def" line does exactly that.

```
def ask_number(question, low, high, step=1):
....................................^^^^^^
```

Suppose you call the function like this:

```
ask_number("hello", 1, 10)
```

Python takes the arguments you give from left to right and assigns them 
to the function parameters:

```
question = "hello"
low = 1
high = 10
step = ??? no value given
```

Because you haven't supplied a value for step, Python next looks for a 
default, and finds the value 1, so it uses that instead of raising an 
exception (and error message).
