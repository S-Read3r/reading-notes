# Understanding Forms 

Forms are how we collect information from visitors. There are different kinds of form controls. Traditionally, the term 'form' has referred to a printed document that contains spaces for you to full in information. HTML borrows the concept of a form to refer to different elements that allow you to collect information from visitors to yours site. Whether you are adding a simple search box to your website or you need to create more complicated insureance applications, HTML forms give you a set of elemtns to collect data from your users. In this chapter you will: 

- How to create a form on your website
- The different tools for collecting data
- New HTML5 form controls

## Form Controls

There are several types of form controls that you can use to collect information from visitors to your site.

### Adding Text:

1. Text inpu(single-line): This type used to collect information such as emails, names, address.
2. Password input: Like a single line text box but it masks the characters entered.
3. Text area(multi-line): This is for longer areas of text, such as messages and comments.

### Making Choices:

1. Radio Buttons: These are for use when a user must select one of a number of options.
2. Checkboxes: These are used when a user has multiple options to choose from. 
3. Drop-down boxes: When a user must pick one of a number of options from a list.

### Submitting Forms:

1. Submit buttons: This is to submit data from your form to another web page.
2. Image buttons: This is similar to submit buttons but they allow you to use an image. 

### Uploading Files:

1. File upload: This allows a user to upload fules i.e. images to website.


## Form Structure

The main tag is **form**, and this element should always carry an action attribut. What is an action attribute you may wonder? Also the form will usually have a **method** and **id** attributes.

* Action: As mention above, a form element requires am action attribute. Its value is the **URL** for the page on the server that will receive the information in the form when it is submitted. 
* Method: forms can be sen using one of the methods: **get** and  **post**. 
    - With the get method, the values from the form are added to the end of the URL specified in the action attribute. The get method is ideal for: 
        1. short forms such as search boxes.
        2. When you are just retrueving sata from the web server. (FYI, not sending informataion that should be added to or deleted form a database)
    - With the post method, the values are sent in what are known as HTTP header. As a rule fo thumb you should use the post method if your form:
        1. Allows users to upload a file. 
        2. Is very.
        3. Contains sensitive data eg **passwords**.
        4. Adds information to, or deletes information form, a database. 

**NOTE**: If the **method** attribute is not used, the form data will be sent using the get method.

## id

The id attributes used to identify the form distictly **from** other elements on the page. It's also used by scripts such as those that check you have entered information into fuelds that require values.

## input type Attribute

The input attribute has many uses and it's very important that one knows how the input attribute can be used. There are many uses as already mentioned and some of them are self-explanatory.
- type='data'
- type='radio'
- type='hidden'
- type='text'
- type='image'
- type='submit'
- type='file'

## for Attribute

The for attribute state which form control the label belongs to. Note how the radio buttons use the id attributes use the id attribute. The value of the id attribute uniquely identifies an element from all other elements on a page. The value of the for attribute matches that of the id attribute on the form control it is labelling. This technique ising the for and id attributes can be used on any form control.

# Boxes

It is important to control the size of the box and box model does precisely this. Box model for borders, margin and padding, displaying and hiding boxes.

# Events

When you browse the web, your browser registers different types of events. It's the browser's way of saying, 'Hey, this just happened.' Your script can then respond to these events. Script often respond to these events by updating the content of the web page (via the DOM) which makes the page feel more interactive. In this chapter, you will learn.

### Interactions create events

Events occur when users click or tap on a link, hover or wipe over an element, type on the keyboard, resize the window, or when the page they requested has loaded.

### Events trigger code

When an event occurs, or fires, it can be used to trigger a paarticular function. Different code can be triggered when useres interact with different parts of the page. 

### Code responds to uesrs

The events can trigger the kinds of changes the DOM is capable of. This is how a web page reacts to users.