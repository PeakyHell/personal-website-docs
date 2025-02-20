# Table of Contents
1. [Introduction](#introduction)
2. [Bubble Sort](#bubble-sort)
3. [Selection Sort](#selection-sort)
4. [Insertion Sort](#insertion-sort)
5. [Merge Sort](#merge-sort)
===ENDTOC===

# Sorting algorithms

## Introduction

Sorting algorithms are a very import part of computer science, they are used in many situations and a lot of programs rely on their speed and efficiency. Here are some simple but powerful sorting algorithms.

## Bubble Sort

### Principle

The Bubble Sort algorithm is a sorting algorithm that sort an array by comparing adjacent elements and swapping them if they're in the wrong order. Its name comes from the fact that the biggest elements travel to the end of the list like a bubble going up in a water column.

### Pseudo Code

```txt
for i ← n - 1 down to 0 :
    swapped ← false
    for j ← 1 to i :
        if array[j - 1] > array[j] :
            swap(array[j - 1], array[j])
            swapped ← true
    if not swapped :
        break
return array
```

### Implementation

```python
def bubble_sort(array):
    for i in range(len(array) - 1, 0, -1):
        swapped = False
        for j in range(1, i + 1):
            if array[j - 1] > array[j]:
                array[j - 1], array[j] = array[j], array[j - 1]
                swapped = True

        if not swapped:
            break
    return array
```

### Complexity

Time complexity :<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Best case : O(n) comparisons and O(1) swaps<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Worst case : O(n²) comparisons and O(n²) swaps<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Average case : O(n²) comparisons and O(n²) swaps

## Selection Sort

### Principle

The Selection Sort algorithm is a sorting algorithm that sorts an array by repeatedly selecting the smallest element from the unsorted portion and putting it at the correct position.

### Pseudo Code

```txt
for i ← 0 to n - 1 :
    min ← i
    for j ← i + 1 to n - 1 :
        if array[j] < array[min] :
            min ← j
    if min ≠ i :
        swap(array[i], array[min])
return array
```

### Implementation

```python
def selection_sort(array):
    for i in range(0, len(array)):
        min = i
        for j in range(i + 1, len(array)):
            if array[j] < array[min]:
                min = j
        if min != i:
            array[i], array[min] = array[min], array[i]
    return array
```

### Complexity

Time complexity :<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Best case : O(n²) comparisons and O(1) swaps<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Worst case : O(n²) comparisons and O(n) swaps<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Average case : O(n²) comparisons and O(n) swaps

## Insertion Sort

### Principle

The Insertion Sort algorithm is a sorting algorithm that sort an array by taking each element one by one and putting it in the correct place in a sorted sublist.

### Pseudo Code

```txt
for i ← 1 to n - 1 :
    key ← array[i]
    j ← i - 1
    while j ≥ 0 and array[j] > key :
        array[j + 1] ← array[j]
        j ← j - 1
    array[j + 1] ← key
return array
```

### Implementation

```python
def insertion_sort(array):
    for i in range(1, len(array)):
        key = array[i]
        j = i - 1
        while j >= 0 and array[j] > key:
            array[j + 1] = array[j]
            j -= 1
        array[j + 1] = key
    return array
```

### Complexity

Time complexity :<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Best case : O(n) comparisons and O(1) swaps<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Worst case : O(n²) comparisons and swaps<br>
&nbsp;&nbsp;&nbsp;&nbsp; - Average case : O(n²) comparisons and swaps

## Merge Sort

### Principle

The Merge Sort algorithm is a sorting algorithm that sort an array by dividing the array in smaller arrays recursively until it only needs to sort arrays of 0 or 1 elements. It uses the principle of *Divide and Conquer*

### Pseudo Code

```txt
if n ≤ 1:
    return array

mid ← n/2
l1 ← array[0, half]
l2 ← array[half, n]

merge(l1, l2)

return array
```

### Implementation

```python
def merge_sort(array):
    if len(array) <= 1:
        return array
    
    mid = int(len(array)/2)
    arr1 = array[:mid]
    arr2 = array[mid:]
    
    arr1 = merge_sort(arr1)
    arr2 = merge_sort(arr2)
    
    array = merge(arr1, arr2)
    
    return array
    
    
def merge(arr1, arr2):
    array = []

    while len(arr1) > 0 and len(arr2) > 0:
        if arr1[0] > arr2[0]:
            array.append(arr2[0])
            del arr2[0]
            
        else:
            array.append(arr1[0])
            del arr1[0]
            
    
    while len(arr1) > 0:
        array.append(arr1[0])
        del arr1[0]
    while len(arr2) > 0:
        array.append(arr2[0])
        del arr2[0]
    
    return array
```

### Complexity

Time complexity :<br>
&nbsp;&nbsp;&nbsp;&nbsp; - All cases : Θ(n log n)