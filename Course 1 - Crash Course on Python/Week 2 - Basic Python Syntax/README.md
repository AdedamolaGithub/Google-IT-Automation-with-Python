# Conditionals Cheat Sheet

In earlier videos, we took a look at some of the built-in Python operators that allow us to compare values, and some logical operators we can use to combine values. We also learned how to use operators in if-else-elif blocks. 

It’s a lot to learn but, with practice, it gets easier to remember it all. In the meantime, this handy cheat sheet gives you all the information you need at a glance.

__Comparison operators__

- __a == b__: a is equal to b
- __a != b__: a is different than b
- __a < b__: a is smaller than b
- __a <= b__: a is smaller or equal to b
- __a > b__: a is bigger than b
- __a >= b__: a is bigger or equal to b

__Logical operators__
- __a and b__: True if both a and b are True. False otherwise.
- __a or b__: True if either a or b or both are True. False if both are False.
- __not a__: True if a is False, False if a is True.

__Branching blocks__

In Python, we branch our code using if, else and elif. This is the branching syntax:
```python
if condition1:
	if-block
elif condition2:
	elif-block
else:
	else-block
```

Remember: The if-block will be executed if condition1 is True. The elif-block will be executed if condition1 is False and condition2 is True. The else block will be executed when all the specified conditions are false.