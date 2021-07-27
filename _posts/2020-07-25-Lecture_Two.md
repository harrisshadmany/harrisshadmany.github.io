# Lecture 2: Global/Local Environments, If-Else Statments, For/While Loops, and Lists

Table of Contents:

1. TOC
{:toc}

## Quiz

Let's review what we learned from last time about functions. What would the following Python code output?

```python
# Quiz
def mystery(x, y, z):
   x += y
   z -= x
   print(x, y, z)

x = 2
y = 5
z = 3
mystery(z, x, y)
print(x, y, z)
```
**Warning**: This is an intentionally hard question to demonstrate a very important property of Python. It might take 15 - 20 minutes to understand this section. Take the time, write it out, and think really hard. It will pay **enormous** dividends if you take the time to understand it now as opposed to later on. Otherwise, you'll always see imaginary bugs and be confused by what your programs are doing.

The first is that I swapped the order of *x, y, z* when I called the mystery function. The second is that when I call a function, it opens its own **local environment**. That's just a fancy way of saying that all of the variables **outside the indented block of the function** live in a different environment called the **global environment**. Everything that goes on **inside a function** has its own set of variables. 

Thus, when I called mystery(z, x, y), the "x" in the mystery function is now the "z" from below it because Python doesn't care about the names when you call functions. All it cares about are the order of the inputs. 

Thus, since (z, x, y) is equivalent to (3, 5, 2) in the *global environment* outside my function, the (x, y, z) in my *local environment* inside the function is actually equivalent to (3, 5, 2) since all it cares about is order. Then, after the operations on x and z, we have (x, y, z) equal to (5, 2, 0). 

Thus, the first line of output is (5, 2, 0). The second line, however, is, just (2, 5, 3). Why? Because the (x, y, z) in the global environment outside the function is **unchanged** by the computations inside the function local environment on a **different** (x, y, z). It doesn't matter what you call your function inputs, Python doesn't know there might be similar names outside of the function.

Generally, this is a lot less confusing because people don't use the **same** names for their function inputs and global variables. They also don't mix up the order of things. 

In short, I'm mean, I apologize, I hope you learned something :).

## If-Else Statements

Another big part of programming is **conditional logic**. Depending on what the *state* of our variables is, we want to take different actions. Imagine you were writing an app to help people find veterinarian stores near their location. If the user has a cat, you'd probably want to do something different than if they had a dog, and so on. If-Else statements are the glue that holds all of these various pieces of logic together in a simple, concise way.

Let's start with a simple example. Depending on the type of animal the user inputs, we'll print different sounds like "Bark!" or "Meow!". This is how an if-else statement is structured.

```python
# If-Else Statement example
animal = input("What type of animal do you have?")

if animal == "Dog":
   print("Bark!")
elif animal == "Cat":
   print("Meow!")
else:
   print("Na na na na.... BATMAN!)
```

Note that the indentation matters - the code that gets excecuted after a statement is triggered is the indented block below that statement.

This is the usual anatomy of an if-else block of logic. We have one or more variables that encode the state of the world. Then, depending on what the state of the world is, we take different actions. 

The way you start a block of conditional logic is always with the keyword **if**. After the *if*, you have what is known as a **Boolean expression**. That's just a fancy way of saying something that evaluates to True or False. Then, you can add as many **elif** statements as you want. If you want to capture all the remaining cases, you can also have an **else** statement. 

In summary, you have always have 1 if statement. Then, you have 0 to infinite elif statements. Finally, you have 0 or 1 else statements. 

Sometimes, the logic behind our programs can get more complicated. To capture more complex cases, we may have to make our Boolean expressions stronger. The way we do this is by using the keywords **and** + **or**. 

The following example is a toy program that one might imagine a medical professional uses. 

```python
# If-Else Statement example
heartbeat = int(input("What is the patient's heartbeat?"))
age = int(input("How old is the patient?"))

if heartbeat > 150:
   print("The patient is in severe danger")
elif heartbeat > 130 and age > 80:
   print("The patient is in severe danger")
elif heartbeat > 110 or age > 65:
   print("The patient needs monitoring")
else:
   print("The patient is fine at the moment")
```

Here's an interesting exercise in Boolean logic. What range of ages and heartbeat would force the above code to print "The patient is fine at the moment"?

## For Loops

A lot of programming is repeating computation. Imagine we wanted to take the sum of all of the numbers from 1 to 150. We could always type out all of the numbers or expressions, but it would take forever.

Or say we wanted to print "Hello" 100 times? Would we just copy and paste print("Hello") over and over again?

The solution to both of these issues is to use a for loop. 

```python
# Sum numbers from 1 to 150 using a for loop.
total = 0
for index in range(1, 151):
   total += index

# Print "Hello" 100 times.
for index in range(1, 101):
   print("Hello")
```

You start a for loop by using the keyword **for**. The **range** keyword specifies how many times you want to run whatever is inside the for loop and the variable after the *for* is what we call an "index". Remember, the *second* number in the range operator is the number *after* you want to stop. If you want to iterate for 100 times, you make it 101. You can call your index variable whatever you want. Each time the block of code inside the loop is run, the index increases by one. You can access index any time within the block of code being executed.

Combining loops and conditional logic can be powerful. For example, a common introductory CS class problem is called *fizzbuzz*. For all the numbers from 1 to 100, we want to print "fizz" if the number is divisible by 3, "buzz" if the number is divisible by 5, and "fizzbuzz" if it's divisible by both. 

```python
# Fizzbuzz implementation. 
for number in range(1, 101):
   if number % 3 == 0 and number % 5 == 0:
      print("fizzbuzz")
   elif number % 3 == 0:
      print("fizz)
   elif number % 5 == 0:
      print("buzz")
```

## While Loops
While loops are similar to for loops in that they execute blocks of code repetitively to achieve some goal. They are more useful however when you don't know how many times you'll have to execute that block of code, and you want to stop when some condition is met.

Remember those pesky Boolean expressions? Those come up in while loops too. The anatomy of a while loop is very simple. It goes something like this.

```python
# Anatomy of a while loop
while <some Boolean expression>:
    print("This block of code")
    print("is being")
    print("executed.")
```

As long as "some Boolean expression" evaluates to True, the block of code indented underneath the while loop will continue to be executed.

For a concrete example, let's say we want to find out how many numbers I have to sum starting from 1 and going to infinity before the total sum goes over 2021. Because I don't know how many numbers it is, I want to use a while loop. That would look like this.

```python
# Find how many numbers you need to sum until the total is greater than 2021
total, index = 0, 1

while total < 2021:
    total += index
    index += 1
    
print(index)
```

## Lists
So far, we've learned how to store data in variables. However, say we were collecting usernames from users as they signed up for an app. We need to store each and every one of their usernames, but how would we know how many variables to create? And what if we had thousands of users? Would we need thousands of variables?

The solution to the above problem is to use a **list**. Lists are an ordered collection of **elements**. Here's how we create a list in Python.

```python
# Create a list
list = ["Harris", 2, True, 3.5]
```

This is a list of **length** *four*. As you can see, we can put all types of things in a list, including strings, integers, floats, and Booleans (True/False). To store elements in a list you simply put the elements inside the brackets separated by commas.  

How do we access elements of the list? Each *element* of the list has a **value** and an **index**. Since Python lists start at index 0, the list in our above example has the *value* "Harris" at *index* 0. At index 1, the value is 2 and so on. Thus, we access the elements of the list by using a for loop like so.

```python
# Loop through a list and print each element
for index in range(len(list)):
   element = list[index]
   print(element)
```

As you can see, we use the brackets with an index inside to access the *value* at a specific *index*. If we choose not to specify a starting point for the range operator, it starts at 0. Then, as we know from the for loop section, the second number in the range operator has to be 1 bigger than the value we want to stop at. Since we have a list of length 4 (which starts at index 0), we want to stop at index 3. Thus, the length of the list is exactly the right number to feed into the range operator.

Don't worry, this becomes instinctive after the first couple times, and you'll learn to type range(len(list)) effortlessly from memory.

But back to the original question: if we want to store usernames as users sign up, how would we do it? It turns out you can start with an empty list and add to the end of it like so.

```python
# Append items to the end of a list
list = []
list.add("Harris")
list.add("John")
list.add("Natalie")
```

You can also an item at a specific index by using the **pop** operator. If I wanted to remove "John" from the list, I would feed the index 1 into the pop operator like this.

```python
# Append items to the end of a list
list.pop(1)
```

Now, with one variable, we can store as many elements as we could ever want to **in order**. Furthermore, we can access the *value* of specific elements  of the list instantaneously via their *index*. 

## Homework 

1. Take a fresh sheet of paper out and write these sections down: Global/Local Environments, If-Else Statements, For/While Loops, and Lists. Then write down all the syntax from memory that you can remember and brainstorm a couple examples of short programs you would write. 

Here's a couple questions from my intro computer science class [CS61A](https://cs61a.org/disc/disc01/). Check out the link for lots of cool questions! You haven't learned how to do questions 6-9 and question 12. 

2. Write a function that returns True if a positive integer n is a prime number and False otherwise.

3. Here's a "What Would Python Do?" question - fill in the blanks.

```python
def special_case():
    x = 10
    if x > 0:
        x += 2
    elif x < 13:
        x += 3
    elif x % 2 == 1:
        x += 4
    return x

special_case()
______


def just_in_case():
    x = 10
    if x > 0:
        x += 2
    if x < 13:
        x += 3
    if x % 2 == 1:
        x += 4
    return x

just_in_case()
______

def case_in_point():
    x = 10
    if x > 0:
        return x + 2
    if x < 13:
        return x + 3
    if x % 2 == 1:
        return x + 4
    return x

case_in_point()
______
```
