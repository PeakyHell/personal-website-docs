# Table of Contents
1. [The smallest part of the CPU](#the-smallest-part-of-the-cpu)
2. [The half-adder](#the-half-adder)
3. [The full-adder](#the-full-adder)
===ENDTOC===

# The smallest part of the CPU

The CPU, which stands for Central Processing Unit, is the core of a computer.
When the CPU receives an instruction, it links all the necessary components to execute it.

We can compare the CPU to a chef in a kitchen: when a customer places an order, the chef assigns everyone to a task and creates the final dish.

## Logic gates

We start by looking at the smallest parts in a CPU, the *logic gates*.
In a computer, we use A LOT of logic gates to convert an input of 2 bits (electrical signal) into a 1 bit output.
There are a few logic gates that, combined together, can perform A LOT of complex operations.

## NOT

The simplest logic gate is the NOT gate. It simply outputs the opposite of its input.
It is the only gate that we will see that takes a single bit as input.

Here is its truth table

|   x   |   NOT   |
|-------|---------|
|   0   |    1    |
|   1   |    0    |

## OR

The OR gate returns 1 if at least one of its inputs is 1.

|   x   |   y   |   OR   |
|-------|-------|---------|
|   0   |   0   |    0    |
|   0   |   1   |    1    |
|   1   |   0   |    1    |
|   1   |   1   |    1    |

## AND

The AND gate returns 1 if both its inputs are 1.

|   x   |   y   |   AND   |
|-------|-------|---------|
|   0   |   0   |    0    |
|   0   |   1   |    0    |
|   1   |   0   |    0    |
|   1   |   1   |    1    |

## XOR

The XOR gate is very similar to the OR gate with the exception that it returns 1 only if ONE of its inputs is 1.

|   x   |   y   |   XOR   |
|-------|-------|---------|
|   0   |   0   |    0    |
|   0   |   1   |    1    |
|   1   |   0   |    1    |
|   1   |   1   |    0    |

## NOR

The NOR gate, with the NAND gate, is one of the 2 *universal* logic gates as you can build ANY other logic gate using only NOR (or NAND).

The NOR gate is an OR gate with a reversed output. It's similar to placing a NOT gate immediately after an OR one.

|   x   |   y   |   NOR   |
|-------|-------|---------|
|   0   |   0   |    1    |
|   0   |   1   |    0    |
|   1   |   0   |    0    |
|   1   |   1   |    0    |

## NAND

The NAND gate, with the NOR gate, is one of the 2 *universal* logic gates as you can build ANY other logic gate using only NAND (or NOR).

The NAND gate is an AND gate with a reversed output. It's similar to placing a NOT gate immediately after an AND one.

|   x   |   y   |   NAND   |
|-------|-------|---------|
|   0   |   0   |    1    |
|   0   |   1   |    1    |
|   1   |   0   |    1    |
|   1   |   1   |    0    |

# The half-adder

Now that we know how data is represented in a CPU (binary), how we can apply operations on binary numbers and how we can modify the output of an electric signal (logic gate), we will see HOW the CPU will add 2 numbers using the *half-adder*.

We saw in the addition that when adding 2 bits, there are two possibles outcomes : 
- Either the sum fits in a single bit. 
- Or it produces a carry that affects the next column.

We will then need to create an adder that can handle cases where we have a carry.

Let's start with what's called a *half-adder*, a digital circuit that takes 2 inputs (the 2 bits to add) and outputs 2 values (the sum and the carry).

The sum is calculated by passing the inputs into a XOR gate.
The carry is calculated by passing the inputs into an AND gate.

We can then represent the half-adder like this :

![[images/half-adder.png]]

# The full-adder