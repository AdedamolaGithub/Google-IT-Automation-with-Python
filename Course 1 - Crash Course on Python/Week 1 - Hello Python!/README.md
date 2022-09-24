# First Programming Concepts Cheat Sheet

__Functions and Keywords__

Functions and keywords are the building blocks of a language’s syntax.

Functions are pieces of code that perform a unit of work. In the examples we've seen so far, we've only encountered the print() function, which prints a message to the screen. We'll learn about a lot of other functions in later lessons but, if you're too curious to wait until then, you can discover all the functions available [here](https://docs.python.org/3/library/functions.html).

Keywords are reserved words that are used to construct instructions. We briefly encountered for and in in our first Python example, and we'll use a bunch of other keywords as we go through the course. For reference, these are all the reserved keywords:

|        |          |         |          |        |
---------|----------|---------|----------|--------|
| False  | class    | finally | is       | return |
| None   | continue | for     | lambda   | try    |
| True   | def      | from    | nonlocal | while  |
| and    | del      | global  | not      | with   |
| as     | elif     | if      | or       | yield  |
| assert | else     | import  | pass     |
| break  | except   | in      | raise

You don't need to learn this list; we'll dive into each keyword as we encounter them. In the meantime, you can see examples of keyword usage [here](https://www.programiz.com/python-programming/keyword-list).

__Arithmetic operators__
Python can operate with numbers using the usual mathematical operators, and some special operators, too. These are all of them.

- __a + b__ = Adds a and b
- __a - b__ = Subtracts b from a
- __a * b__ = Multiplies a and b
- __a / b__ = Divides a by b
- __a ** b__ = Elevates a to the power of b. For non integer values of b, this becomes a root (i.e. a**(1/2) is the square root of a)
- __a // b__ = The integer part of the integer division of a by b
- __a % b__ = The remainder part of the integer division of a by b