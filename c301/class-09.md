# What is Functional Programming.

After a long time learning and working with object-oriented programming, I took a step back to think about system complexity.
Complexity is anything that makes software hard to understand or to modify.

Doing some research, I found functional programming concepts like immutability and pure function. Those concepts are big advantages to build side-effect-free functions, so it is easier to maintain systems — with some other benefits.

***

Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

## Pure functions

The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?

Pure functions return the same result if given the same arguments(it is also referred as deterministic).
Pure functions do not cause side-effects.

### It returns the same result if given the same arguements.

Imagine we want to implement a function that calculates the area of a circle. An impure function would receive radius as the parameter, and then calculate radius * radius * PI:

#### Why is that example above an impure function?

Simply because it uses a global object that was not passed as a parameter to the function.
Now imagine some mathematicians argue that the PI value is actually 42and change the value of the global object.

Our impure function will now result in 10 * 10 * 42 = 4200. For the same parameter (radius = 10), we have a different result. Let's fix it!

* TA-DA 🎉! Now we’ll always pass thePI value as a parameter to the function. So now we are just accessing parameters passed to the function. No external object.

* For the parameters radius = 10 & PI = 3.14, we will always have the same the result: 314.0
For the parameters radius = 10 & PI = 42, we will always have the same the result: 4200

#### Reading Files
If our function reads external files, it’s not a pure function — the file’s contents can change.

#### Random number generation
Any function that relies on a random number generator cannot be pure.

## Pure functions benefits
The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:

Given a parameter A → expect the function to return value B
Given a parameter C → expect the function to return value D
A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.

## What is a module?

A module is a collection of functions and variables. It is a way to organize code.

## What is a package?

A package is a collection of modules. It is a way to organize code.

## How do we bring another module into the file we are working on?

By using key word `import` and the name of the module or by using the `require` function.

## What do we have to do to make the module available to the file we are working on?

    #### Importing a module
    import module_name
    #### Requiring a module
    const module_name = require('module_name')

    #### Importing a module from a subdirectory
    import subdirectory/module_name
    #### Requiring a module from a subdirectory
    const module_name = require('subdirectory/module_name')

    

