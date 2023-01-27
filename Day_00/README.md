# Getting Started

## Topics covered in today's module
* What is a GPU? 
* Python base library basics
* Numpy basics
* Pandas basics

## Main takeaways from doing today's assignment
- Refreshed my Python knowledge in data structures such as Sets and Dictionaries
- Refreshed my knowledge in NumPy and Pandas

## Challenging, interesting, or exciting aspects of today's assignment
Sorting a dictionary by values can be done like this:
```py
sorted_dict1 = {key: value for key,value in sorted(dict1.items(), key = lambda _: _[1])}
```

Where in: 
```py
sorted(dict1.items(), key = lambda _: _[1])
```
- ``dict1.items()`` is an iterable containing the key and values in the dictionary.The key's index is [0], while the value's index is [1].
- We specify what we will sort according to in the ``key= `` parameter.
- ``key = lambda _: _[1]`` says that in each element of that list, the second item _(the value in the dictionary)_ is the key.<br>Recall that each element looks like this (key, value). Hence, we want to sort all entries of that dictionary by their values. 
- In lambda function, we will basically loop through the dictionary iterable, and get the value (which is at index [1]) which we will use it to sort by.

## Additional resources used 
- [pandas loc documentation](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.loc.html)
- [DataCamp's NumPy Cheatsheet](http://datacamp-community-prod.s3.amazonaws.com/ba1fe95a-8b70-4d2f-95b0-bc954e9071b0)
- [DataCamp's Pandas Cheatsheet](http://datacamp-community-prod.s3.amazonaws.com/f04456d7-8e61-482f-9cc9-da6f7f25fc9b)
