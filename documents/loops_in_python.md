# Loops in Python

## What is a loop

A loop is a _flow control statement_ that lets a _block_ of code execute several times. This can be useful for repeating tasks, and reduces the amount of code you need to write.

Loops _iterate_ over a given _sequence_. A sequence is a collection of objects where the order of the objects matter. This could be for example the numbers [0, 1, 2, 3, 4, 5], or the animals ["Cat", "Dog", "Elephant"].

## For Loops

For loops are useful when you have the sequence you want to iterate over. For example, if we want to create the first 10 even numbers, _10_ is the sequence we want to iterate over. In Python, you can iterate over the first ten _natural_ numbers (the natural numbers are the numbers used for counting, i.e. [0, 1, 2, 3, 4, 5, ...]) with the following code:

```python
# range(0, 10) == [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
for i in range(0, 10):
    print(i)
```

The code under the _for_ loop is called the _body_. The body of the loop will execute _x_ number of times, which is determined by the code after the _in_ keyword.

Let's look at what this code means:

```python
for i in range(0, 10):
    print(i)
```

1. The _for_ keyword tells us that we want to start a for loop
2. The variable _i_ will contain the value of the current iterative element as we loop through the sequence. It is _declared_ here, so you do not need to declar it above the for loop.
3. The _in_ keyword is used to specify the sequence
4. _range(0, 10)_ gives us the sequence (this is [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] in this case

When the loop above is executed, here is what happens:

1. _i_ receives the value 0
2. print(i) prints 0
3. The body of the loop is finished so we go back to the top of the body and give _i_ the next value in the sequence, which is _i + 1_
4. print(i) prints 1
5. Steps 3 and 4 repeat until we get to the last value in the sequence, and then loop exits and we get further along down in the code

With that knowledge above, we now know that a loop can be _unfolded_, and the loop above is equivalent to:

```python
print(0)
print(1)
print(2)
print(3)
print(4)
print(5)
print(6)
print(7)
print(8)
print(9)
```

## While Loops

A _while_ loop is similiar to a _for_ loop in that repeats a _body_ of code several times. The difference is that a while loop does not iterate over a sequence. A while loop checks whether a condition is true or false, and stops when the condition is true. Let's take a look at an example:

```python
x = 0 # we have to declare the variable outside (above) the while loop, since a while loop does not declare variables like the foor loop does
while x < 5:
    print(x)
    x = x + 1
```

The loop above looks like this when we unfold it:

```python
x = 0

# first iteration
if (0 < 5): # if (x < 5) and x = 0
    print(0)
    x = 0 + 1
# second iteration
if (1 < 5): # if (x < 5) and x = 1
    print(1)
    x = 1 + 1
# third iteration
if (2 < 5): # if (2 < 5) and x = 1
    print(2)
    x = 2 + 1
# fourth iteration
if (3 < 5): # if (x < 5) and x = 3
    print(3)
    x = 3 + 1
# fifth iteration
if (4 < 5): # if (x < 5) and x = 4
    print(4)
    x = 4 + 1
# sixth iteration (we exit and the body does not get executed)
if (5 < 5): # if (x < 5) and x = 5
    # We do not go here because 5 is not less than 5, so the loop "exits"
```

## Try some examples yourself

Try these with both the _for_ and _while_ loops.

### Print the first 10 natural numbers

Expected result: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9

### Print the first 10 even numbers

Expected result: 0, 2, 4, 6, 8, 10, 12, 14, 16, 18

### Print the first 10 odd numbers

Expected result: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21

### Print the sum of the first 10 natural numbers

```python
sum = 0 # we will declare this variable here to keep track of the sum
for i in range(0, 10):
    sum = sum + i # we add the current value of i to sum

# Line by line this looks like
for i in [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    sum = sum + 1

# Remember, the single equals sign is an assignment, which means the variable "sum" is set to the value of "sum" + i
# You can think of this as "the new value of sum is set to the old value of sum, + i"
# sum = sum + i
# sum = 0 + 0 (the new value of sum is now the old value of sum (0) + 0)
# sum = 0 + 1 (the new value of sum is now the old value of sum (0) + 1)
# sum = 1 + 2 (the new value of sum is now the old value of sum (1) + 2)
# sum = 3 + 3 (the new value of sum is now the old value of sum (3) + 3)
# sum = 6 + 4
# sum = 10 + 5
# sum = 15 + 6
# sum = 21 + 7
# sum = 28 + 8
# sum = 36 + 9
# sum = 45
```