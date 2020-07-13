# Introduction to Programming

## What is a computer program

A computer program is a sequence of _instructions_. These instructions are written in code, and vary from language to language. A sequence of instructions that solves a problem is called an _algorithm_. Instructions are typically executed from top to bottom, line by line.

## Types and variables

### Types

Computers are very good at solving problems that deal with data. When working with data, it is important to be aware of its _type_. When we talk about _type_, we mean "what kind of data." This is best explained with some examples:

| type             | examples       |
| ---------------- | -------------- |
| int  (integer)   | 55, -30, 20    |
| string           | "Hello", "cat" |
| char (character) | 'a', 'b', '@'  |
| boolean          | True, False    |

### Variables

A variable in code is just like a variable in an equation. In Python, a variable will be assigned _values_, and these _values_ have _types_. The value of a variable can in most cases change throughout the execution of code. We say a variable is _declared_ when we first introduce it in the code. We say a variable is _assigned_ a value when we give it a value.

#### Examples of variables

```python
# Here we declare a variable called "my_number" and initialize it to 3. We "declare" the variable by giving it a name and value.
my_number = 3

# This line will print the number "3" to the console.
print(my_number)

# Here, we assign the value "5" to the variable my_number. We say that the variable "my_number" has be re-assigned.
my_number = 5

# This line will print the number "5" to the console.
print(my_number)

# Because Python is "dynamically-typed", we can assign a value of a different type to the variable my_number. It is okay if this doesn't make sense yet.
my_number = "now a string";

# This line will print the string "now a string" to the console.
print(my_number)
```

### Types and variables conclusion

* A type describes what kind of data a value has
* A value is the data itself
* In Python, a variable can be used to hold values of different types, and it is the value itself that has a type, not the variable

## Data Structures

### Lists

A list is like a box that can contain different values of the same type. You can think of it as a bookcase that has been turned sideways. Each "shelf" can hold one item. Items are arranged _linearly_, that is, one after the other.

There are many interesting things you can do with lists, but most basically they are used to hold data related data.

There are a few terms we use when we talk about lists:

* Length/Size: this is the number of items the list can hold
* Index: this gives us the item at the specified index (position). Note that lists are 0-indexed, which means that the item at the first position as index 0.

#### List Examples

Given the following list:

```python
list_of_even_numbers = [0, 2, 4 , 6, 8]
```

We can say the following:

* The length/size of the list is 5. That is it has 5 _elements_.
* The _element_ at _index_ 0 is 0, or `list_of_even_numbers[0]` is 0
* The _element_ at _index_ 1 is 2, or `list_of_even_numbers[1]` is 2
* The _element_ at _index_ 2 is 4, or `list_of_even_numbers[2]` is 4
* The _element_ at _index_ 3 is 6, or `list_of_even_numbers[3]` is 6
* The _element_ at _index_ 4 is 8, or `list_of_even_numbers[4]` is 8

Notice that the the last index is always `size - 1`.

#### Looping through Lists

It is very easy to _loop through_ all of the values in a list.

```python
list_of_even_numbers = [0, 2, 4 , 6, 8]
# This for-loop will execute 5 times, and print 0, 2, 4, 6, 8
for even_number in list_of_even_numbers:
    print(even_number)
```

Given the above, we can create a _function_ that will add the first _n_ even numbers to a list

```python
# This is where we define the function
def create_even_numbers_list(number_of_even_numbers):
    # We declare a variable here to hold the result
    result = []
    # We want to run this loop "n" times, where n is equal to number_of_event numbers,
    # so we start at 0 and stop when we get to number_of_event numbers.
    # We use current_index to keep track of how many numbers we have printed (or how many times the loop has executed)
    current_index = 0
    # Keep on executing the loop until we have gone 20 times
    while current_index < number_of_even_numbers:
        # Because current index increases like 0, 1, 2, ..., n-1, n,
        # we can simply multiply this number by 2 to get the sequence of even numbers.
        # Then we add that number to the result
        result.append(current_index * 2)
        # We have to increase current_index here so the loop will exit and we will keep on generating even numbers
        current_index += 1

    # The "return" statement means that the "result" variable
    # will be given to the code that "called" this function
    return result

# This is lower in the code, where we "call" the function.
# even_numbers gets the result of the function, create_even_numbers_list,
# which is "returned" by the return statement
even_numbers = create_even_numbers_list(20)

# this is where we print out the first n even numbers (in this case the first 20)
for i in range(0, len(even_numbers)):
    print(even_numbers[i])
```

### Dictionaries

## Thinking like a programmer

In this section, we will go over how to solve real-world problems by using code.

### How to solve a problem

We can think that computer code runs sequentially, that is line-after-line and from top-to-bottom. Knowing this, we write statements that perform operations to solve our problem. Let's look at how we would do this without writing any code.

This list of steps is called an _algorithm_. An _algorithm_ is a sequence of steps that solves a problem. In Norwegian we sometimes call this _oppskrift_ (or recipe).

#### How to find the tallest person in the room (without code!)

1. Put everyone in the room in a line.
2. Go to the first person.
3. Ask the person how tall he or she is and write his or her height on a piece of paper.
4. Go to the second person
5. Ask the person how tall he or she is, AND IF HE OR SHE IS TALLER THAN THE PERSON ON THE PIECE OF PAPER, write his or her height on the piece of paper.
6. Repeat steps 4 (but going to the third, fourth, etc. person) and 5 until there are no more people left.
7. When you get to the end of the line, the name on the piece of paper will be the name of the tallest person.

#### How to find the tallest person in the room (with code!)

```python
# The "line" of the people in the room. These numbers are stored in an list
heights = [150, 132, 180, 136, 100, 163, 140]

# This variable is our "piece of paper" that we use to keep track of the heights
tallest_person_height = 0

# This is where we go down the line asking each person their height
for height in heights:
    # We compare the current person's height with our "piece of paper"/tallest_person_height value
    if height > tallest_person_height:
        # if the current person (whose height is stored in the "height" variable) is taller than the person on the piece of paper,
        # then we write their information down
        tallest_person_height = height

# This will print out the value 180,
# the height of the tallest person in the room
print(tallest_person_height)
```

#### Part 2, writing this as a function that can look at a line of any number of people

```python
def find_tallest_person(heights):
    tallest_person_height = 0
    for height in heights:
        if height > tallest_person_height:
            tallest_person_height = height
    return tallest_person_height
```
