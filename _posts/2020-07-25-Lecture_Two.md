# Lecture 2: If-Else Statments, For/While Loops, and Lists

Table of Contents:

1. TOC
{:toc}

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

Here's an interesting exercise in Boolean logic. What range of ages and heartbeat would force the above code to print "The patient is fine at the moment". 

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

## Homework 

1. Take a fresh sheet of paper out and write these sections down: INSERT_SECTIONS. Then write down all the syntax from memory that you can remember. 

2. Write a program that 

3. Another "What Would Python Do?" question.

```python
>>> x = 20
>>> x + 2
______

>>> x
______

>>> y = 5
>>> y = y + 3
>>> y * 2
______

>>> y = y // 4
>>> y + x
______
```
