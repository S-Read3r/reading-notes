# Object Literals and Document Object Model 

Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, variables and funvtions take on new names. 
In simpler terms, variables become known as properties, meaning if a variable is part of an ovject, it is called a property. Properties tell us about the object, such as the name of a hotel or the number of rooms it has.

Objects can hold things or properties called methods, which in literial term meaning functions.

## Ways to Create an Object.

* Literal notation: This is the most popular way to create objects.
* Object with a constructor: Objects can be created using a object constructors.
* Object.create(): There is a method that can be used to create objects. This method uses an existing object as the prototype of the newly created object.
* Using es6 classes: ES6 supports class concept like any other Statically typed or object oriented language.

### Accessing object

One can access the properties or methods of an object using dot notation. Another way is to use the square brackets.

## DocumentObject 

This specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.

The DOM is neither part of HTML, nor part of JavaScript: it is a separate set of rules. It is implemented by all major browser makers, and covers two primary areas:

1. Making a model of the HTML Page
    * When the browser loads a web page, it creates a model of the page in memory. The DOM specifies the way in which the browser should structure this model s=using a DOM tree.
    * The DOM is called an object model because the model (the DOM tree) is made of objects.
    * Each object represents a different part of the page loaded in the browser window. 
2. Accessing and changing the HTML page.
    * The DOM also defines methods and properties to access and update each object in this model, which in turn updates what the user sees in the browser.
    * You will hear people call the DOM an Application Programming Interface(API). User interfaces let humans interact with programs; APIs let programs (and scripts) talk to each other. the DOM states what your script can ask the browser
3.  