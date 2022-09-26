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