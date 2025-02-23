# Table of Contents
1. [Introduction](#introduction)
2. [Data Types](#data-types)
3. [Operators](#operators)
4. [Control Structures](#control-structures)
5. [Functions](#functions)
6. [Object Oriented Programming](#object-oriented-programming)
7. [Error handling](#error-handling)
8. [Testing](#testing)
===ENDTOC===

# Introduction

# Data Types

Python has different data types that can each store different values and have different behaviors, they also have some very useful methods.
Variables in python are very easy to declare as they can contain any data type and can be changed as you want.

## Numeric types

### Common Operators

These operators are common to all the numeric types

```python
x + y -> # sum of x and y
x - y -> # difference of x and y
x * y -> # product of x and y
x / y -> # quotient of x and y
x // y -> # floored quotient of x and y
x % y -> # reminder of x / y
-x -> # negate x
x ** y # x to the power of y
```

### Common methods

#### is_integer

Returns *True* if the variable is an integer, else otherwise.
Only works for integers and floats.
For integers, the method only works on a variable and not on an integer directly.

```python
x = 1
y = 2.0
z = 2.5

x.is_integer() -> True
y.is_integer() -> True
z.is_integer() -> False
```

#### abs

Returns the absolute value of x

```python
x = -7

abs(x) -> 7
```

#### divmod

Returns a pair of the floored quotient and the remainder of the quotient x / y

```python
x = 7
y = 2

divmod(x, y) -> (3, 1)
```

#### pow

Returns x to the power of y

```python
pow(x, y)
```

### Integer

#### Declaration

You can create a integer variable either by directly declaring an integer or by using the [int()](#constructor) method.

```python
x = 5
```

#### Methods

##### Constructor

The *int()* constructor allow to create an integer from an integer, a float or a string.

```python
int(10) -> 10
int(3.14) -> 3
int("64") -> 64
```

### Float

#### Declaration

You can create a float variable either by directly declaring a float or by using the [float()](#constructor-1) method.

```python
x = 3.14
```

#### Methods

##### Constructor

The *float()* constructor allow to create a float from an integer, a float or a string.

```python
float(10) -> 10.0
float(3.14) -> 3.14
float("64") -> 64.0
```

##### as_integer_ratio

Returns a pair of integers whose ratio equals the given float.

```python
x = 1.5

x.as_integer_ratio() -> (3, 2)
```

### Complex

#### Declaration

You can create a complex variable either by directly declaring a complex or by using the [complex()](#constructor-2) method.

```python
x = 3+5j
```

#### Methods

##### Constructor

The *complex()* constructor allow to create a complex from two integers, two floats or a string.

```python
complex(3, 5) -> 3+5j
complex(1.2, 4.6) -> 1.2+4.6j
complex("1+3j") -> 1+3j
```

## Boolean

The boolean type is very simple, a boolean can either be *True* or *False*.

### Operators

```python
x or y -> # True if x or y is True, False if none
x and y -> # True if x and y are True, False otherwise
not x -> # True if x is False, False if x is True
```

### Declaration

You can create a boolean variable either by directly declaring a complex or by using the [bool()](#constructor-3) method.

```python
t = True
f = False
```

### Methods

#### Constructor

```python
bool(None) -> False
bool(0) -> False
bool(1) -> True
bool("") -> False
bool("x") -> True
bool([]) -> False
bool([1]) -> True
bool(range(0)) -> False
bool(range(1)) -> True
```

## Sequence types

### Common Operators

```python
obj in seq -> #True if obj is an item of s, else False
obj not in seq -> # False if obj is an item of s, else True
seq + seq2 -> # concatenation of s and t
seq * n -> # make a sequence of n times seq
seq[i] -> # i th item of seq
seq[i:j] -> # slice of seq from i to j-1
seq[i:j:k] -> # slice of seq from i to j-1 with stepping of k
```

### Mutable sequence operators

```python
seq[i] = x -> # replace the i th item of seq with x
seq[i:j] = seq2 -> # replace slice of seq from i to j-1 by the elements of seq2
seq[i:j:k] = seq2 -> # replace slice of seq from i to j-1 with stepping of k by the elements of seq2
del seq[i] -> # remove the i th item of seq
seq *= n -> # update seq by the sequence of n times seq
```

### Common methods

#### len

Returns the length of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

len(seq) -> 6
```

#### min

Returns the smallest element of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

min(seq) -> 1
```

#### max

Returns the largest element of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

max(seq) -> 8
```

#### index

Returns the index of the first occurence of x in the sequence. 

```python
seq = [1, 3, 5, 6, 8, 3]
x = 5

seq.index(x) -> 2
```

#### count

Returns the number of occurences of x in the sequence

```python
seq = [1, 3, 5, 6, 8, 3]
x = 3

seq.count(x) -> 2
```

### Mutable sequence methods

#### append

Add x at the end of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]
x = 4

seq.append(x) -> [1, 3, 5, 6, 8, 3, 4]
```

#### clear

Removes all the items of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

seq.clear() -> []
```

#### copy

Creates a copy of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

seq2 = seq.copy() -> [1, 3, 5, 6, 8, 3]
```

#### extend

Add the content of another sequence at the end of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]
seq2 = [4, 5, 6]

seq.extend(seq2) -> [1, 3, 5, 6, 8, 3, 4, 5, 6]
```

#### insert

Insert x at a given index in the sequence while keeping all the content of the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]
x = 2

seq.insert(1, 2) -> [1, 2, 3, 5, 6, 8, 3]
```

#### pop

Returns the i th element of the sequence and removes it. If i is not specified, remove the last element

```python
seq = [1, 3, 5, 6, 8, 3]

seq.pop(2) -> 5 -> [1, 3, 6, 8, 3]
```

#### remove

Remove the first occurence of x in the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

seq.remove(3) -> [1, 5, 6, 8, 3]
```

#### reverse

Reverse the sequence.

```python
seq = [1, 3, 5, 6, 8, 3]

seq.reverse() -> [3, 8, 6, 5, 3, 1]
```

### List

#### Declaration

You can create list either by directly declaring a list or by using the [list()](#constructor-4) method.

```python
x = []
y = [1, 2, 3]
z = [i for i in iterable]
```

#### Methods

##### Constructor

The *list()* constructor allow to create a list from any type of sequence.

```python
list([1, 2, 3]) -> [1, 2, 3]
list(('a', 'b', 'c')) -> ['a', 'b', 'c']
list(range(3)) -> [0, 1, 2]
list({"car", "boat", "plane"}) -> ["car", "boat", "plane"]
```

##### sort

Sorts the list in-place in ascending order.

```python
seq = [1, 3, 5, 6, 8, 3]

seq.sort() -> [1, 3, 3, 5, 6, 8]
```

### Tuple

#### Declaration

You can create tuple either by directly declaring a tuple or by using the [tuple()](#constructor-5) method.

```python
x = ()
y = (1, 2, 3)
```

#### Methods

##### Constructor

The *tuple()* constructor allow to create a tuple from any type of sequence.

```python
tuple([1, 2, 3]) -> (1, 2, 3)
tuple(('a', 'b', 'c')) -> ('a', 'b', 'c')
tuple(range(3)) -> (0, 1, 2)
tuple({"car", "boat", "plane"}) -> ("car", "boat", "plane")
```

### Range

#### Declaration

You can only create a range by using the [range()](#constructor-5) method.

#### Methods

##### Constructor

The *range()* constructor allow to create a range while specifying start, end and step.

```python
range(5) -> [0, 1, 2, 3, 4]
range(1, 7) -> [1, 2, 3, 4, 5, 6]
range(1, 15, 3) -> [1, 4, 7, 10, 13]
```

## String

## Set

## Dictionary

# Operators

# Control Structures

# Functions

# Object Oriented Programming

# Error handling

# Testing