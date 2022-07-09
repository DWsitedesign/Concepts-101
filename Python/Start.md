# Introduction

This file is for those who are brand new or need a refresh on the fundamentals of programming. It will be split up into sub sections each containing a little snippet of Python code, a short decription, and possible links.

The link to the official Python website is [www.python.org](https://www.python.org/).

## Data Types

Before we start with what variables are, and how we use them. I will first list out some of the most basic data types or variable types. In Python you don't have to declare the type of a variable, because the compiler will be *smart* and figure it out for you.

### The basic types

- bool (a true or false value)
- char (characters: think letters on a keyboard)
- int (the same as in math: numbers which can be specified by a ratio of two other ints)
- float (decimal numbers: usually to x7 accuracy)
- string (a list of chars)
- list (a collection of items)
- dictionary (a collection of items with key => value pairs)


For a closer look at types in C look [here](tutorialspoint.com/cprogramming/c_data_types.htm), and [here for python](https://www.tutorialspoint.com/python/python_variable_types.htm)


## Variables

What are variables? How do I use variables? Here we will answer these questions and more.

Variables are a way to record or *save* data for later. In order to fully maximize variables you should know scope and the basics of how variables work.

### Scope

Most errors dealing with variables will either be scope releated or data type errors. A variable's scope is where it can be called on.

```
somevar = 2
def myFunction():
    scopedvar=2

print(scopedvar) # <-- Won't work because scopedvar is in the scope of the function not the file.
print(somevar)
```

In this instance the scope of `scopedvar` is only inside the function `myFunction`. A general rule is you can access vars from your level or what is passed to your level.

### What?

How I like to think of variables is that it consists of three different parts: 
1. the variable name,
1. the memory address,
1. the data at the address.

To set a variable we use the convention of `variable name = desired value`

Your variable name shouldn't contain any special symbols or spaces. The value you set the var to can be practically anything: normal data types, class instances, functions.

```
# Setting myvar to the integer of 2
myvar = 2 # A singluar = means when you call the left the right value will show up.

# Set multiple variables to the same thing
var1 = var2 = var3 = 2 # All three variables are set to 2

# Set multiple variables to diffrent values

var1 = 2
var2 = 3
var3 = 1

# Or

var1, var2, var3 = 2, 3, 1
```

We now know how to set variables, so how do we use them in our scripts? We are going to call the variable name and it will return the value we last stored at the location.

To call a variable you merely write the variable's name.
```
myvar = 1
print(myvar) # prints 1
myvar = 2
print(myvar) # prints 2
myvar = 3
print(myvar) # prints 3

# We can also change the value of variable based off of the previous value
myvar = 1
myvar = myvar + 1
print(myvar) # prints 2
myvar = myvar + 1
print(myvar) # prints 3
myvar = myvar + 1
print(myvar) # prints 4
```

### Variable interactions with each other

There are several special symbols that will do certain things given two variables and the data types.

Earlier you may have seen the `+` between an int var and the int 1. The basic operators for two numeric variables are:
- `+` simply adds the two numbers together
- `-` acts like normal subtraction
- `*` multiplies
- `/` divides
- `**` raises to the power of
- `%` returns the remainder when x is divided by y in case `x%y`

However, if the variables aren't numeric it might error out.
The `+` for strings will concatinate them. To concatinate means put a and b together.
You can also put these symbols right before the `=` when setting a value and it will do the current operation with the last set data of the current variable. `myvar += 1` is equal to `myvar = myvar + 1`.

## Conditionals

Before we start talking about several statements we are going to take a moment and talk about booleans.
A boolean is something which has a value of True or False, and they make up the foundation for conditionals. A True value in Python is also represented by a 1, and False by a 0.

```
# Both conditions evaulate to true resulting in words being printed to the console.
if True == 1:
    print("True")

if False == 0:
    print("False")
```

However, you can switch the value of a boolean by putting `not` in front of it: your just doing the opposite of the given value.

```
print(not True) # False
print(not False) # True
```

There are two ways to get a boolean value. The first is to manually set it.

```
myvar = True
falsevar = False

# Or

myvar = 1
falsevar = 0
```

The other way is to use a condition to dynamically resolve the value.
Here are some of the common comparisions in the format of `y sign x` e.g. `y == x`.

- `==` y is equal to x
- `!=` y is not equal to x
- `<` and `>` y is less than x
- `=<` and `>=` or `<=` and `=>` y is less than or equal to x
- `is` y is an x object (same type of object)
- `in` y is an element of x

These comparisions can be strung together with `and` or `or`. 

```
print(True and 1+1 == 2) # True
print(True and 1+2 == 2) # False
print(True or 1+2 == 2) # True
print(False or 1+2 == 2) # False
```

You can also enclose smaller conditionals with `()` to create a more indepth conditional.

```
print(True and (1+2 == 2 or True) ) # True
print(True or (1+2 == 2 and True) ) # True
```

In general, think of `or` as adding the truth values together and `and` as multipling the values together. For more reading look [here](https://realpython.com/python-boolean/).

## Code Blocks

Here I will talk about the most common code blocks/snippets.

### If Statement

The If statement is a fundamental of coding given a certain check do the following code.

```
#if condition:
    # Do code

if True:
    # Will print hello since the condition is true
    print('Hello')

if 1+1=3:
    # Won't print anything since 1+1 is not equal to 3
    print('equal')
```

The If Statement can be paired with an `else` for both cases the true and the false.

```
if 1+1=3:
    # Won't print anything since 1+1 is not equal to 3
    print('equal')
else:
    # Will print not equal since original condition was false
    print('not equal')
```

Some things to keep in mind about If Statements is to 

1. Keep nesting of If's to a minimum.
1. Don't have an empty main if body and go straight to the else. If this is the case change your condition.

You can write the if statement in shorthand like `true code if condition else false code`.
### For loop

If you can understand the for loop the rest of the loops should come easily to you. For loops in Python are diffrent than for loops in other lower level languages (PHP, C++, C#).