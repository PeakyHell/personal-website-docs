# Table of Contents
1. [Introduction](#introduction)
===ENDTOC===

# Searching algorithms

## Introductiion

Searching algorithms are a very import part of computer science, they are used in many situations and a lot of programs rely on their speed and efficiency. Here are some simple but powerful searching algorithms.

## Linear search

### Principle

The Linear Search algorithm is a searching algorithm that search a value in an array by simply going through the whole array and returning the index of the value when it finds it.

### Pseudo Code

```txt
for i ← 0 to n - 1 :
    if key == array[i] :
        return i
return -1
```

### Implementation

```python
def linear_search(array, key):
    for i in range(0, len(array)):
        if key == array[i]:
            return i
    return -1
```

### Complexity

Time complexity :<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Best case : O(1)
&nbsp;&nbsp;&nbsp;&nbsp; - Worst case : O(n)
&nbsp;&nbsp;&nbsp;&nbsp; - Average case : O(n)

## Binary Search

### Principle

The Binary Search algorithm is a searching algorithm that search a value in a **sorted** array by recursively dividing the array in 2 and keeping the part where the value should be.

### Pseudo Code

```txt
if low > high :
    return -1
middle ← (low + high)/2
if key == array[middle] :
    return middle
if key < array[middle] :
    return binary_search(array, key, low, middle -1)
else :
    return binary_search(array, key, middle + 1, high)
```

### Implementation

```python
def binary_search(array, key, low, high):
    if low > high:
        return -1
    middle = int((low + high)/2)
    if key == array[middle]:
        return middle
    if key < array[middle]:
        return binary_search(array, key, low, middle - 1)
    else:
        return binary_search(array, key, middle + 1, high)
```

### Complexity

Time complexity :<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Best case : O(1)
&nbsp;&nbsp;&nbsp;&nbsp; - Worst case : O(log n)
&nbsp;&nbsp;&nbsp;&nbsp; - Average case : O(log n)