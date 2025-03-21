# Table of Contents
1. [The binary representation](#the-binary-representation)
2. [Other representations](#other-representations)
3. [Binary operations](#binary-operations)
===ENDTOC===

# The binary representation

In a computer, the smallest form of data is *binary*. Binary is a data representation using only 1s or 0s, so a base 2 representation.

In the everyday life, we use base 10 numbers where each digit can take any of 10 values between 0 and 9, so a power of 10.
For example, the number 121 can be represented as $1*10^2 + 2*10^1 + 1*10^0 = 100 + 20 + 1 = 121$.

Binary follows the same principle but using base 2, so each digit can take any of 2 values, 0 or 1.
If we take the same example, 121 in binary will be 0111 1001 which can be represented as $0111 1001 = 0*2^7 + 1*2^6 + 1*2^5 + 1*2^4 + 1*2^3 + 0*2^2 + 0*2^1 + 1*2^0 = 0 + 64 + 32 + 16 + 8 + 0 + 0 + 1 = 121$.

Now, you might be wondering why use binary which takes more digits than the base 10 that we use in the everyday life. The answer is that CPUs use power to represent values, so power ON = 1 and power OFF = 0. Binary is also commonly used to represent logical values, such as True (1) and False (0).

This fundamental concept allows computers to represent numbers using electrical signals: presence of current (1) or absence of current (0).

Sequences of bit can represent larger values.

8 bits = 1 byte
16 bits = 1 word
32 bits = 1 double-word
64 bits = 1 quadruple-word

# Other representations

## Octal representation

Using 3 bits, we can represent all the digits of the base 8 *octal* system which uses digits from 0 to 7.
This representation is shown in the table below.

| $2^2$ | $2^1$ | $2^0$ |  Octal  |
|-------|-------|-------|---------|
|   0   |   0   |   0   |    0    |
|   0   |   0   |   1   |    1    |
|   0   |   1   |   0   |    2    |
|   0   |   1   |   1   |    3    |
|   1   |   0   |   0   |    4    |
|   1   |   0   |   1   |    5    |
|   1   |   1   |   0   |    6    |
|   1   |   1   |   1   |    7    |

## Hexadecimal representation

Using 4 bits, we can represent all the digits of the base 16 *hexadecimal* system which uses digits from 0 to 9 and letters from A to F.
this representation is shown in the table below.

| $2^3$ | $2^2$ | $2^1$ | $2^0$ | Hexadecimal |
| ----- | ----- | ----- | ----- | ----------- |
| 0     | 0     | 0     | 0     | 0           |
| 0     | 0     | 0     | 1     | 1           |
| 0     | 0     | 1     | 0     | 2           |
| 0     | 0     | 1     | 1     | 3           |
| 0     | 1     | 0     | 0     | 4           |
| 0     | 1     | 0     | 1     | 5           |
| 0     | 1     | 1     | 0     | 6           |
| 0     | 1     | 1     | 1     | 7           |
| 1     | 0     | 0     | 0     | 8           |
| 1     | 0     | 0     | 1     | 9           |
| 1     | 0     | 1     | 0     | A           |
| 1     | 0     | 1     | 1     | B           |
| 1     | 1     | 0     | 0     | C           |
| 1     | 1     | 0     | 1     | D           |
| 1     | 1     | 1     | 0     | E           |
| 1     | 1     | 1     | 1     | F           |

The hexadecimal system is also very useful and is often used because if you take 2 hexadecimal values, it represents a byte.
So for example, instead of writing 1010 0110 we can write A6, which is much easier to read or write.

# Binary operations

Now that we know how to represent number in binary, we might want to make operations on them.

## Addition

First, we'll start with the simplest operation, the addition.

To add 2 binary numbers, we use the same principle as when we add 2 decimal numbers.

- Each time we have to do 1 + 0 or 0 + 1, we get 1.
- Each time we have to do 1 + 1, we get 0 and report 1 to the next digit.

For example let's add 0100 1110 (78) and 0110 1001 (105) :

```
  1  1
  0100 1110
+ 0110 1001
-----------
  1011 0111
```

## Substraction

The substraction is also very simple and uses the same principle as when we substract 2 decimal numbers.

- Each time we have to do 1 - 0, we get 1.
- Each time we have to do 1 - 1, we get 0.
- Each time we have to do 0 - 1, we borrow 1 from the next higher order bit and do 2 - 1 = 1. Don't forget to set the borrowed bit to 0.
If you couldn't take the immediate left bit but a further one, also set it to 0 and set all the intermediate 0s to 1.

For example let's substract 1001 1010 (154) and 0100 1110 (78)

```
  1001 1010
- 0100 1110
-----------
  0100 1100
```

## Multiplication

The multiplication can be a bit harder but also uses the same principle as when we multiply 2 decimal numbers.

You take each of the first bits sequence and multiply it with the whole second bit sequence.
Each time you go to the nth bit, you add n -1 0s at the beggining.

For example, let's multiply 0111 (7) and 0011 (3)

```
     0111
x    0011
---------
     0011
    00110
   001100
+ 0000000
---------
    10101
```

## Division

The division