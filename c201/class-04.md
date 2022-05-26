# Links

### What are links and they are uses

Links are the defining feature of the web because they allow you to move from one web page to another - enabling the very idea of browing or surfing.

There are types of link, which range from one website to another, one page to another on the same website, one part of a web page to another part of the same page, some that open in a new browser window and links that start up your email program and address a new email to someone.
Links are created using the <a> element and users can click anything that in between the openeing and the closing tag.

#### Relative URLS

Relative URLs can be used when linking to pages within your own website. They provide a shorthand way of telling browser where to find your files. 

**Relative Link Type**

* **Same folder:** To link to a file in the same folder, just use the file name. (<a href='reviews.html'>Reviews</a>)
* **Child folder:** For a child folder, use the name of the cild folder, followed by a forward slash, then the file name. (<a href='music/listings.html'>Listings</a>)
* **Grandchild Folder:** Use the name of the child, followed by a forward slash, then the name of the grandchold folder, followed by a nother forward slash, then the file name.(<a href="movies/dvd/reviews.html">Review</a>)
* **Parent Folder:** Use ../ to indicate the folder above the current one, then follow it with the file name.(<a href="../index.html">Home</a>)
* **Grandparent Folder:** Repeat the ../ to indicate that you want to go up two folders (rather than one), then follow it with the file name.

**Email Links**

To create a link that strats yp the user's email program and addresses an email to a specified email address, you use the <a> element. Hoever, this time the vaue of the href attribute starts with mailto: and is followed by the email address you want the email to be sent to. (<a href="mailto:jon@example.org">Email Jon</a>)

**Summary**

There is so much more ways that links can be utilized. Such as adding an attribute call target with the value of _blank. Doing so will open the link in the a new tab. Also adding a (#) sign before the beginning of the link will make it so that the link is local to the page it is on.

# Layout

Layout is about controlling the position of the elements, creating site layots and designing for different sized screens. This to know about CSS is that it treats each HTML element as if it is own box. Hence the term box model is thrown around in the front end circle. The box will either be a **block-level box** or an **inline box**.

#### Box-level boxes

Box level boxes start on a new line and act as the main building blocks of any layout.

#### Inline boxes

Inline boxes flow between surrounding text. 

## Understanding boxes

To separate boxes, things like padding, margin, borders and background colors are used.If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.

## Position Schemes

CSS has the following posotioning schemes that allow you to control the layout of a page.


#### Normal Flow

Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one. Even if you specify the width of the boxes and there is space for two elements to sit side-by-side, they will not appear next to each other. This is the default behavior (unless you tell the browser to do something else).

#### Relative Positioning

This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. This does not affect the position of surrounding elements; they stay in the position they would be in in normal flow.

#### Absolute Positioning

This positions the element 
in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position 
of any surrounding elements 
(as they simply ignore the space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.

#### Fixed Positioning

This is a form of absolute positioning that positions 
the element in relation to the browser window, as opposed to the containing element. Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user scrolls up or down the page.

#### Floating Elements

Floating an element allows you to take that element out of normal flow and position 
it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.