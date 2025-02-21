# Table of Contents
1. [Introduction](#introduction)
2. [Stack](#stack)
3. [Queue](#queue)
4. [Binary Tree](#binary-tree)
===ENDTOC===

# Abstract Data Types

## Introduction

## Stack

### Principle

A Stack is a collection of elements that can be added or removed according to the LIFO (last-in first-out) principle.
- The first element that can be removed (pop) is the last one that was inserted (push)
- No element can be removed if the stack is empty

### Specification

```python
class Stack:
    def push(self, item):
        """
        pre: -
        post: add a new item on top of the stack
        """
    def pop(self):
        """
        pre: the stack is not empty
        post: remove and return the item on top of the stack
        """
```

### Implementation

The best ways to implement a Stack are :
- with a dynamic array
- with a linked list 

## Queue

### Principle

A Queue is a collection of elements that can be added or removed according to the FIFO (first-in first-out) principle.
- The first element that can be removed (dequeue) is the oldest one that was inserted (enqueue) and has not yet been removed
- No element can be removed if the queue is empty

### Specification

```python
class Queue:
    def enqueue(self, item):
        """
        pre: -
        post: add a new item at the end of the queue
        """
    def dequeue(self):
        """
        pre: the queue is not empty
        post: remove and return the first item of the queue
        """
```

### Implementation

The best ways to implement a Queue are :
- with a linked list
- with a circular dynamic array

## Binary Tree

### Principle

A Binary Tree is a recursive collection of elements defined by two principles :
- a tree contains a root node
- the root node has 0 or 2 children each of which is itself a binary tree

### Specification

```python
class BinaryTree:
    def __init__(self, elem=None):
        """
        pre: -
        post: initialize a new Binary Tree with "elem" stored at the root node, when "elem" is None, this is interpreted as an empty BinaryTree
        """
        self.root = elem
        if elem is not None:
            self.left = BinaryTree()
            self.right = BinaryTree()
        else:
            self.left = None
            self.right = None
```

### Implementation

The best ways to implement a Binary Tree are :
- with a linked structure
- with a dynamic array