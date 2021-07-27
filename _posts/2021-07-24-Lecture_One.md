# Lecture 1: Course Philosophy, Variables, Types, Input/Output

Table of Contents:

1. TOC
{:toc}

## Why should you learn to program?

One of the most irritating aspects of high school is that it often reduces to being force-fed a mixture of random facts or formulas without anyone ever telling you why you should care about all of that stuff in the first place. This course will *not* be like that. First, everything you will learn has been carefully selected and is being taught for a reason (which I'll always explain to you). We have a very limited amount of time together and I've put a lot of thought into what will be most useful to you for your future careers. Second, learning to program is **very** different from other disciplines. You'll need to memorize a few things, but the focus of the course is really about learning to think computationally. Like all things worth doing, learning to think computationally is hard. But if you actually do it, it pays off in a big way. 

I promised you at the beginning of this lecture that I would always explain **why** you should actually care about what we're going to learn. Since this is a programming course, let's start with one question: why should you learn to program?

There are probably a million reasons - here are the best three. 

**1. Learning to program is like having a superpower - it opens up an infinite number of possibilities.** 
Programming is one of the 21st century's greatest inventions. Never in the history of this planet has one person sitting at a laptop been able to have such a large impact on the world. The world's biggest companies - Facebook, Google, Apple, and Microsoft - were all started by one or two people sitting down at a computer with a vision. The world is becomingly increasingly more technological and people who have the ability to program are going to run it. The most innovative technologies of the past few years are all software companies and the programmers who run them are becoming the most wealthy and powerful people in the world. You can and should be one of them.

**2. Learning to program is the best investment you can make in your career and all it costs is time.** 
Whether you want to be a software engineer (which is a fancy name for professional programmers), doctor, or lawyer, learning to program makes you someone who has a rare and valuable skillset. It means you can make websites, automate boring parts of your work, and back up your ideas with data and prototypes. Employers and colleges love it (and for good reason). 

Also, if you like this course, I encourage you to look into a career in software engineering. No one ever told me about it, and it's one of the most lucrative and fun jobs out there. For some hard evidence, check out [levels.fyi](levels.fyi). College graduates can make almost $200,000 a year right out of school and it only gets better and better from there. 

![](/images/levels.png "Google New Grad Salary")

**3. Learning to program is one of the best ways to exercise your brain - it makes you smarter.**
One idea that is perpetuated over and over in the modern education system is that some kids are just "smarter" than others. This is bullshit. Overwhelmingly, research shows that what most people consider being smart is a combination of two things: **hard work and deliberate practice**. Working hard is a pre-requisite, but if all I do is basic addition for two hours a day, I'm not going to learn anything. If I instead programmed more and more complicated things, not only am I learning new skills, I'm training my brain to think about complicated, difficult scenarios and how to problem-solve them.

## Variables, Input, and Output
Programming is all about data - storing it, manipulating it, and performing computations on it. But how do we store data inside a program? By using **variables**.

```python
# Creates a variable called number
number = 2021
```

In the above line of code, we've *assigned* the integer 2021 to a variable called "number". The way you create a variable in Python is by using the assignment (=) operator. To the left of the = operator, we put the **name** of our variable. To the right of the = operator, we put the **data** that we want to store in that variable. The first line in the program is what we call a "comment" - putting a # in front of a line of code means you can type anything there and Python will ignore it.

So what can we do with our variable?

```python
# Re-assign number to 4042
number = number * 2
print(number)
```
All the **print** operator does is show us what data is stored inside a variable by outputting it to the console.

One thing we can do is **reassign** it. Reassignment is simple: you just use the assignment operator again. But be careful here: the "number" on the left of the assignment operator is different from the "number" on the right. The way Python interprets this *expression* is by first "evaluating" everything to the right of the assignment operator, then assigning number to whatever *value* the *expression* evaluates to. 

We can also use parantheses and other operations. Remember PEMDAS? Python knows PEMDAS. 

```python
# What's number now? 
number = (9 + 3 * 5)/ 12
```

What about if we tried adding two variables together?

```python
# Add two variables
num1 = 2
num2 = 3
print(num1 + num2)
```

Congratulations! You just wrote your very first program. One **very** important note: programs are written to by read by humans. I could have also written the above code the following way.

```python
# DO NOT DO THIS
sadalskndlkasnd = 2
aknlkfndslnf = 3
print(sadalskndlkasnd + aknlkfndslnf)
```

The issue with the above code is that no one has any idea what's going on. Use **descriptive** variable names - it should be crystal clear what the variable is supposed to be storing.

## Types of Data
So far, we've only worked with numbers. But a lot of the data in the world comes in text too. Python has different **types** of data. 

```python
# Different types of data
integer_data = 2
float_data = 3.0
string_data = "Hello World!"
```
There are three types of data in the above code. Numbers like 1,2, and 3 are what we call **integers**. Numbers with decimal points are called **floats**. Text data made up of words and spaces are called **strings**. The way you tell Python you are working with strings is by surrounding text with double quotes (e.g., string = "Hogwarts").

Let's write a program that takes in a user's name as input and prints "Hello USER_NAME!" as output.

```python
# Say hi to our user
user_name = input("Hi! What's your name?")
print("Hello " + user_name)
```

This is also a neat example of how Python does something different (in this case addition of strings) depending on what the *type* of the data is.

So, let's review everything we learned so far about variables, types, and input/output. Write a program that takes in two numbers that a user inputs and then outputs the sum of the two numbers. 

```python
# Program that outputs sum of two numbers
num1 = input("Please input your first number.")
num2 = input("Please input your second number.")
print(num1 + num2)
```

But wait! We have an issue. Python thinks our input is **strings** not numbers. How do we fix this?

```python
# Casting our input to integers
num1 = int(input("Please input your first number."))
num2 = int(input("Please input your second number."))
print(num1 + num2)
```

This is called **casting**. Surrounding our input with the **int** operator *casts* a string into an integer. But it only works when there's a valid conversion. 

## Errors

So, what happens if we try to add a string to an integer?

```python
print("3" + 3)
```

This is what is called a runtime error. **Errors**, also known as bugs are horrible things - they stop your program in the middle of them running. If you want your program to work, you have to **debug** your code. 

The first step in debugging is always to check the content of the error message. It tells you what line is causing the problem and what Python is having difficulty with. 

```python
print(3 + 3)
```

All good now.

Writing bug-free code is hard. Here are four of the most common bugs that can sneak into your code if you're a new programmer.

**1. Using a variable you never created or misspelling one that you did.**
Python interprets everything you type literally. If you misspell a variable, it's going to throw an error since it has never seen that name before. Likewise, if you try to use a variable you forgot to create, it's going to throw an error.

```python
#Misspelling a variable
number = 2021
print(nubmer * 2)

#Using a variable we've never created
number = uncreated_variable * 2
```

How would debug the above code?

**2. Forgetting to complete parentheses or other necessary syntax.**
If you have one opening parentheses "(", Python demands you complete it with a closing parentheses ")" somewhere. Similarly, if you start a string (e.g. string = "didn't complete) without the second double quote ", Python will throw an error.  

```python
#Forgetting to complete syntax
print("Hello World!"
string = incomplete"

#Putting together too many expressions on one line of code
print() 5 6 7
```

Debug it!

**3. Mixing up the order of lines of code.**
Python executes your code top to bottom. Even if you create a variable in the lines of code below where you use the variable, Python will throw an error.

```python
#Mixing up the order of code
print(variable)
variable = 5
```

Debug it!

**4. Writing code with flawed logic.**
Even if Python runs your code without throwing an error, you can still have **logical** errors inside your code. Imagine I'm trying to write a program that finds the average of two numbers the user inputs.

```python
x = float(input('Enter a number: '))
y = float(input('Enter a number: '))

average = x+y/2
print('The average of the two numbers you have entered is: ', average)
```

This program has a logical error in it. If you can't figure it out, go run the code and see what it is. Then, debug it!

## Functions

Remember when I told you that a big part of programming is just thinking about input and output? Functions are just boxes of computation in Python that take inputs and spit out output. Addition, multiplication, and the print statement are all functions. But how do we create our own functions?

```python
#Our first function
def function_name(input1, input2):
  total = input1 + input2
  return total
```

Remember, indentation matters in Python! You have to indent the lines inside a function.

The way you define a function in Python is using the keyword **def**. After def, you put the function name. Then, within the parentheses of the function, you put the inputs to the function. Finally, once you've done all your computation and manipulation of the data, you use the **return** keyword to tell Python what the output of the function is. Once you **return** from a function, nothing else is done inside the function.

## Homework 

1. Take a fresh sheet of paper out and write these sections down: Variables, Types, Input, Output, Errors, and Functions. Then write down all the syntax from memory that you can remember. This is called the Feynman technique: quizzing yourself is the best way to learn. Once you've taken your best attempt, come back to the blog post and re-read it. 

2. Write a program that that asks the user for two numbers as input. Then, print the first number multiplied by the fourth power of the second number. Hint: I haven't taught you how to raise a number to another number as its power (known as exponentiation), so you should Google this. After doing that, let's make the problem more general. Write a function that takes three things as input: two numbers and an exponent. The output of the function should be the first number multiplied by the second number raised to an arbitrary exponent (which is passed to the function).

3. The following is an exercise called "What Would Python Do?" from my introductory computer science class at Berkeley ([CS61A](https://cs61a.org)). Your goal is to fill in the blanks (without running the code) to think through what Python would do.

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

## What happens if I get stuck?

First, you should try Googling things. Almost everything you get stuck on, someone else has and it will probably come up. Second, you can make an Ed post and I'll try to respond. Finally, you should just experiment in Python and see if you can fix it. Learning to debug your own programs is **really** valuable and something you'll have to do. 
