title: Loops: for and while
next_title: Functions
next_url: %url:functions%


[TOC]


## The for loop

A `for` loop executes a code block for each element in an iterable, such as a `list`. Analogous to the `if` statement, the `for` statement ends with a colon, and the to-be-looped code block is defined by indentation:


```python
prime_numbers = [1, 3, 5, 7, 11]
for prime in prime_numbers:
    print(prime)
```

If you iterate (loop) through a `dict`, you iterate through its keys. To iterate through the keys and the values at the same time, you can use `dict.items()` function, which returns an iterable of (key, value) tuples.


```python
ages = {
    'Jay-Z': 47,
    'Emanuel Macron': 40
}
for name, age in ages.items():
    print('{0} is {1} years old'.format(name, age))
```


## The while loop

A `while` loop executes a code block until a particular condition is no longer `True`.


~~~ .python
user_input = ''
while user_input != 'quit':
    user_input = input('>>> ')
    print('The user said: {0}'.format(user_input))
~~~

__Output:__

~~~
>>> Hello!
The user said: Hello!
>>> quit
The user said: quit
~~~


## continue: abort one iteration

The `continue` statement, which you can use in `for` and `while` loops (but nowhere else), aborts a single iteration of a loop, and continues with the next iteration. To give an example, you can use `continue` to skip all cities that are not capitals:


```python
cities = ['Berlin', 'São Paulo', 'Tokyo', 'New York']
capitals = ['Berlin', 'Tokyo']
for city in cities:
  # If the current city is not a capital, continue with the next city
  if city not in capitals:
    continue
  print('{0} is a capital'.format(city))
```


## break: abort a loop

The `break` statement is similar to the `continue` statement, but aborts the loop entirely, rather than just aborting the current iteration. To give an example, you can use `break` to print out all prime numbers below `10`.


```python
for prime in prime_numbers:
  # Abort the loop when we reach a number that is 10 or higher
  if prime >= 10:
    break
  print(prime)
```


## Useful functions

### range(): iterate through a range of values

`range()` corresponds to a range of numbers. The simplest and most common use case is to specify only a stop value, which is exclusive (i.e. `range(3)` does not include `3`!):

```python
for i in range(3):
  print(i)
```

However, you can also specify a start value and a step size:

```python
from_value = 1
to_value = 4
step_size = 2
for i in range(from_value, to_value, step_size):
  print(i)
```


### enumerate(): iterate and count

`enumerate()` takes an iterable, and returns another iterable in which each element is paired with a counter variable.

```python
cities = ['Berlin', 'São Paulo', 'Tokyo', 'New York']
for i, city in enumerate(cities):
  print('{0}: {1}'.format(i, city))
```


### zip(): iterate through multiple iterables

`zip()` takes one or more iterables, and returns a zipped iterable in which elements from the original iterables are paired. This allows you to iterate through multiple iterables at the same time. The zipped iterable is as long as the shortest of the original iterables.


```python
artists = 'The Beatles', 'Elvis Presley', 'Michael Jackson', 'Madonna'
sales = 600e6, 600e6, 350e6, 300e6
for artist, sold in zip(artists, sales):
  print('{0} sold {1} records'.format(artist, sold))
```


## Exercises

<div class='info-box' markdown=1>

### Fibonacci

%-- include: exercises/basic/loops-1.md --%

[View solution](%url:loops%-solution-1)

</div>

<div class='info-box' markdown=1>

### Best-selling artists

%-- include: exercises/basic/loops-2.md --%

[View solution](%url:loops%-solution-2)

</div>
