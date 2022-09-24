# Loops Cheat Sheet

Check out below for a run down of the syntax for while loops and for loops.

__While Loops__
A while loop executes the body of the loop while the condition remains True.

Syntax:
```python
while condition:
    body
```

Things to watch out for!

- __Failure to initialize variables.__ Make sure all the variables used in the loop’s condition  are initialized before the loop.
- __Unintended infinite loops.__ Make sure that the body of the loop modifies the variables used in the condition, so that the loop will eventually end __for all possible values of the variables__.

Typical use:

While loops are mostly used when there’s an unknown number of operations to be performed, and a condition needs to be checked at each iteration.

__For Loops__

A for loop iterates over a sequence of elements, executing the body of the loop for each element in the sequence.

Syntax:
```python
for variable in sequence:
    body
```

The __range()__ function:

__range()__ generates a sequence of integer numbers. It can take one, two, or three parameters:
- __range(n)__: 0, 1, 2, ... n-1
- __range(x,y)__: x, x+1, x+2, ... y-1
- __range(p,q,r)__: p, p+r, p+2r, p+3r, ... q-1 (if it's a valid increment)

__Common pitfalls:__

- __Forgetting that the upper limit of a range() isn’t included.__
- __Iterating over non-sequences.__ Integer numbers aren’t iterable. Strings are iterable letter by letter, but that might not be what you want.

Typical use:

For loops are mostly used when there's a pre-defined sequence or range of numbers to iterate.

__Break & Continue__
You can interrupt both while and for loops using the break keyword. We normally do this to interrupt a cycle due to a separate condition.

You can use the continue keyword to skip the current iteration and continue with the next one. This is typically used to jump ahead when some of the elements of the sequence aren’t relevant.

If you want to learn more, check out this [wiki page on for loops](https://wiki.python.org/moin/ForLoop).