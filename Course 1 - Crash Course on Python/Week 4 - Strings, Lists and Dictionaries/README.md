# String Reference Cheat Sheet

In Python, there are a lot of things you can do with strings. In this cheat sheet, you’ll find the most common string operations and string methods.

__String operations__
- __len(string)__ Returns the length of the string

- __for character in string__ Iterates over each character in the string

- __if substring in string__ Checks whether the substring is part of the string

- __string[i]__ Accesses the character at index i of the string, starting at zero

- __string[i:j]__ Accesses the substring starting at index i, ending at index j-1. If i is omitted, it's 0 by default. If j is omitted, it's len(string) by default.

__String methods__
- __string.lower() / string.upper()__ Returns a copy of the string with all lower / upper case characters

- __string.lstrip() / string.rstrip() / string.strip()__ Returns a copy of the string without left / right / left or right whitespace

- __string.count(substring)__ Returns the number of times substring is present in the string

- __string.isnumeric()__ Returns True if there are only numeric characters in the string. If not, returns False.

- __string.isalpha()__ Returns True if there are only alphabetic characters in the string. If not, returns False.

- __string.split() / string.split(delimiter)__ Returns a list of substrings that were separated by whitespace / delimiter

- __string.replace(old, new)__ Returns a new string where all occurrences of old have been replaced by new.

- __delimiter.join(list of strings)__ Returns a new string with all the strings joined by the delimiter 

Check out the official documentation for [all available String methods](https://docs.python.org/3/library/stdtypes.html#string-methods).  

# Formatting Strings Cheat Sheet

Python offers different ways to format strings. In the video, we explained the format() method. In this reading, we'll highlight three different ways of formatting strings. For this course you only need to know the format() method. But on the internet, you might find any of the three, so it's a good idea to know that the others exist.

__Using the format() method__

The format method returns a copy of the string where the {} placeholders have been replaced with the values of the variables. These variables are converted to strings if they weren't strings already. Empty placeholders are replaced by the variables passed to format in the same order.

```python
# "base string with {} placeholders".format(variables)

example = "format() method"

formatted_string = "this is an example of using the {} on a string".format(example)

print(formatted_string)

"""Outputs:
this is an example of using the format() method on a string
"""
```

If the placeholders indicate a number, they’re replaced by the variable corresponding to that order (starting at zero).

```python
# "{0} {1}".format(first, second)

first = "apple"
second = "banana"
third = "carrot"

formatted_string = "{0} {2} {1}".format(first, second, third)

print(formatted_string)

"""Outputs:
apple carrot banana
"""
```

If the placeholders indicate a field name, they’re replaced by the variable corresponding to that field name. This means that parameters to format need to be passed indicating the field name.

```python
# "{var1} {var2}".format(var1=value1, var2=value2)
```

```python
"{:exp1} {:exp2}".format(value1, value2)
```

If the placeholders include a colon, what comes after the colon is a formatting expression. See below for the expression reference.

Official documentation for [the format string syntax](https://docs.python.org/3/library/string.html#formatstrings)

```python
# {:d} integer value
'{:d}'.format(10.5) → '10'
```

__Formatting expressions__

| Expr | Meaning | Example |
|------|---------|---------|
| {:d} | integer value | '{:d}'.format(10.5) → '10' |
| {:.2f} | floating point with that many decimals | '{:.2f}'.format(0.5) → '0.50' |
| {:.2s} | string with that many characters | '{:.2s}'.format('Python') → 'Py' |
| {:<6s} | string aligned to the left that many spaces | '{:<6s}'.format('Py') → 'Py    ' |
| {:>6s} | string aligned to the right that many spaces | '{:>6s}'.format('Py') → '    Py' |
| {:^6s} | string centered in that many spaces | '{:^6s}'.format('Py') → '  Py  ' |

Check out the official documentation for [all available expressions](https://docs.python.org/3/library/string.html#format-specification-mini-language).

__Old string formatting (Optional)__

The format() method was introduced in Python 2.6. Before that, the % (modulo) operator could be used to get a similar result. While this method is __no longer recommended__ for new code, you might come across it in someone else's code. This is what it looks like:

`"base string with %s placeholder" % variable`

The % (modulo) operator returns a copy of the string where the placeholders indicated by %  followed by a formatting expression are replaced by the variables after the operator.

`"base string with %d and %d placeholders" % (value1, value2)`

To replace more than one value, the values need to be written between parentheses. The formatting expression needs to match the value type.

`"%(var1) %(var2)" % {var1:value1, var2:value2}`

Variables can be replaced by name using a dictionary syntax (we’ll learn about dictionaries in an upcoming video).

`"Item: %s - Amount: %d - Price: %.2f" % (item, amount, price)`

The formatting expressions are mostly the same as those of the format() method. 

Check out the official documentation for [old string formatting](https://docs.python.org/3/library/stdtypes.html#old-string-formatting).

__Formatted string literals (Optional)__

This feature was added in Python 3.6 and isn’t used a lot yet. Again, it's included here in case you run into it in the future, but it's not needed for this or any upcoming courses.

A formatted string literal or f-string is a string that starts with 'f' or 'F' before the quotes. These strings might contain {} placeholders using expressions like the ones used for format method strings.

The important difference with the format method is that it takes the value of the variables from the current context, instead of taking the values from parameters.

Examples:
```
>>> name = "Micah"

>>> print(f'Hello {name}')

Hello Micah
```
 
```
>>> item = "Purple Cup"

>>> amount = 5

>>> price = amount * 3.25

>>> print(f'Item: {item} - Amount: {amount} - Price: {price:.2f}')

Item: Purple Cup - Amount: 5 - Price: 16.25
```

Check out the official documentation for [f-strings](https://docs.python.org/3/reference/lexical_analysis.html#f-strings).


# Lists and Tuples Operations Cheat Sheet

Lists and tuples are both sequences, so they share a number of sequence operations. But, because lists are mutable, there are also a number of methods specific just to lists. This cheat sheet gives you a run down of the common operations first, and the list-specific operations second.

__Common sequence operations__
- __len(sequence)__ Returns the length of the sequence

- __for element in sequence__ Iterates over each element in the sequence

- __if element in sequence__ Checks whether the element is part of the sequence

- __sequence[i]__ Accesses the element at index i of the sequence, starting at zero

- __sequence[i:j]__ Accesses a slice starting at index i, ending at index j-1. If i is omitted, it's 0 by default. If j is omitted, it's len(sequence) by default.

- __for index, element in enumerate(sequence)__ Iterates over both the indexes and the elements in the sequence at the same time

Check out the [official documentation for sequence operations](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range).

__List-specific operations and methods__
- __list[i] = x__ Replaces the element at index i with x

- __list.append(x)__ Inserts x at the end of the list

- __list.insert(i, x)__ Inserts x at index i

- __list.pop(i)__ Returns the element a index i, also removing it from the list. If i is omitted, the last element is returned and removed.

- __list.remove(x)__ Removes the first occurrence of x in the list

- __list.sort()__ Sorts the items in the list

- __list.reverse()__ Reverses the order of items of the list

- __list.clear()__ Removes all the items of the list

- __list.copy()__ Creates a copy of the list

- __list.extend(other_list)__ Appends all the elements of other_list at the end of list

Most of these methods come from the fact that lists are mutable sequences. For more info, see the [official documentation for mutable sequences](https://docs.python.org/3/library/stdtypes.html#mutable-sequence-types) and the [list specific documentation](https://docs.python.org/3/library/stdtypes.html#lists).

__List comprehension__
- __[expression for variable in sequence]__ Creates a new list based on the given sequence. Each element is the result of the given expression.

- __[expression for variable in sequence if condition]__ Creates a new list based on the given sequence. Each element is the result of the given expression; elements only get added if the condition is true.

# Dictionary Methods Cheat Sheet

__Definition__

x = {key1:value1, key2:value2} 

__Operations__

- __len(dictionary)__ - Returns the number of items in the dictionary

- __for key in dictionary__ - Iterates over each key in the dictionary

- __for key, value in dictionary.items()__ - Iterates over each key,value pair in the dictionary

- __if key in dictionary__ - Checks whether the key is in the dictionary

- __dictionary[key]__ - Accesses the item with key key of the dictionary

- __dictionary[key] = value__ - Sets the value associated with key

- __del dictionary[key]__ - Removes the item with key key from the dictionary

__Methods__

- __dict.get(key, default)__ - Returns the element corresponding to key, or default if it's not present

- __dict.keys()__ - Returns a sequence containing the keys in the dictionary

- __dict.values()__ - Returns a sequence containing the values in the dictionary

- __dict.update(other_dictionary)__ - Updates the dictionary with the items coming from the other dictionary. Existing entries will be replaced; new entries will be added.

- __dict.clear()__ - Removes all the items of the dictionary

Check out the [official documentation for dictionary operations and methods](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict).  