# Basics of HTML, CSS & JS

### How a browser sees a web page

In order to understand how HTML content is rendered on a web-browser, one needs to understand how the browser interprets the HTML and JavaScript code and CSS.

Before getting into this subject. There is something called S.E.O which stands for Search Engine Opitimization. Which is how search engine look for browser structure and grade them in accordance S.E.O guidlines. SEO is commonly used by search engines such as Google and Duckduckgo.

* Each page is a separate document. So in other words, each webpage is a one or more documents.
* The importance of page structure for Accessibility purposes is immesurable. At the top of the model is a document object, which represents the whole document. In a tree like structure, beneath the document object is boxes with information in them which are node as **nodes**.
* The use of a rendering engine to show the page on screen. If there is no CSS, the rendering engine will apply default styles to HYML elements.
* When the browser receives CSS rules, the redering engine processes them and applies each rule to its corresponding elements.

All major browsers use a JavaScript interpreter to translate your intructions (in JavaScript) into instructions the computer can follow.

* When JavaScript is run in a web browser, there is a part of the browser that is called an interpreter. 
* It is best practice to keep JavaScript code in their own files. These files are text files like HTML pages and CSS style sheets. 
* The difference between JS, CSS and HTML text files is the extensions they have at the end of their codes. 

## <u> Comparing Techniques: Updating HTML Content</u>

### Understanding (document.write())

The document object's writes() method is a simple way to add content that was not in the original source code to the page, but its use is rarely advised.

<u>Advantages</u>

- It is a quick and easy way to show beginners how content can be added to a page.

<u>Disadvantages</u>

- It only works when the page initially loads. 
- If you use it after the page has loaded it can:
    * Iverwrite the whole page
    * Not add the content to the page
    * Create a new page
- It can cause problems with XHTML pages that are strictly validated.
- This method is very rarely used by programmers these days and generally frowned upon. 

### Understanding (element.innerHTML)

You can shoose different techniques on the task and it is important to keep in mind any developments that may occur in the future.

The innerHTML property lets you get/update the entire content of any element (including markup) as a string.

<u>Advantages</u>

- You can use it to add a lot of new markup using less code than DOM manipulation methods.
- It can be faster than DOM manipulation when adding a lot of new elements to a webpage. 
- It is simple way to remove all of the content from one element (by assigning it a blank string).

<u>Disadvantages</u>

- It should not be used to add content that has come froma user (such as  a username or blog comment), as it can pose a significant security risk.
- It can be difficult to isolate single elements that you want to update within a larger DOM fragement.
- Event handlers may no longer work as intended.

<u>What is DOM Manipulation</u>

DOM manipulation refers to using a set of methods and properties to access, create, and update elements and text nodes.

<u>Advantages</u>

- It is suited to changing one element from a DOM fragment where there are many siblings.
- It does not affect event handlers.
- It easily allows a cript to add elements incrementally.

<u>Disadvantages</u>

- if you have to make a lot of changes to the content of a page, it is slower than innerHTML. 
- You need to write more code to achieve the same thing compared with innerHTML.

