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
## The DOM tree is a model of a web page

As a browser loads a web page, it creates a model of that page. The model is called a DOM tree, and it is stored in the browser's memory. **It consists of four main types of nodes.**

The four types of Nodes.

1. The Body of HTML page.
2. The Document Node.
3. Element Nodes.
4. Dom Tree.

#### The Body of HTML Page

[This is an image of the HTML page](https://www.etutorialspoint.com/images/html_elements.jpg)

As shown above, the image shows the an HTML document, semantically typed.

#### The Document Node

As an example, you can see the HTML code for shopping list, and on the right hand page is its DOM tree. Since such a picture does not exist on this page, I will explain. Every element, attribute, and piece of text in the HTML is represented by its own DOM node. At the top of the tree a **document node** is added; it represents the entire page.

#### Element Nodes

HTML elements describe thestrictire of an HTML page. (The h1-h6 elements describe what parts are headings; the p tags indicate where paragraphs of text start and finish; and so on.)

To access the DOM tree, you start by looking for elements. Once you find the element you want, then you can access its text and attribute nodes if you want to. This is why you start by learning methods that allow you to access element nodes, before learning to acess and alter text or attributes

**NOTE**

Each node is an object with methods and properties.

[Picture of Dom Tree](https://snipcademy.com/img/articles/javascript-document-object-model/dom.svg)

##### Attribute Nodes

the opening tags of HTML elements can carry attributes and these are represented by attribute nodes in the DOM tree. 

Attribute nodes are not children of the element that carries them; they are part of that elemtn. Once you access an element, there are specific JavaScript methods and properties to read or change that element's attributes. for example it is common to change the values of class atrributes to trigger new CSS rules that affect their presentation.

##### Text Nodes

Once you have accessed an element node, you can then reach the text within that element. This is stored in its own text node. 

The text nodes cannot have children. If an element contains text and another child element, the child element is not a child of the text node but rather a child of the containing element. (See the em element on the first li item.) This illustrates how the text node is always a new branch of the DOM tree, and no further branches come off of it.