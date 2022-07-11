## Putting it all together

The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names. If you’re working with a designer, they may have already done this, so go talk to them! Their Photoshop layer names may end up being the names of your React components!

But how do you know what should be its own component? Use the same techniques for deciding if you should create a new function or object. One such technique is the single responsibility principle, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

![Image](https://reactjs.org/static/9381f09e609723a8bb6e4ba1a7713b46/90cbd/thinking-in-react-components.png)

You’ll see here that we have five components in our app. We’ve italicized the data each component represents. The numbers in the image correspond to the numbers below.

1. FilterableProductTable (orange): contains the entirety of the example
2. SearchBar (blue): receives all user input
3. ProductTable (green): displays and filters the data collection based on user input
4. ProductCategoryRow (turquoise): displays a heading for each category
5. ProductRow (red): displays a row for each product

If you look at ProductTable, you'll see that the table header (containing the 'Name' and 'Price' labels) isn't its own component. This is a matter of preference, and there's an argument to be made either way. For this example, we left it as part of ProductTable because it is part of rendering the data collection which is ProductTable's responsibility. However, if this header grows to be complex (e.g . if we were to add affordances for sorting), it would certainly make sense to make this its own ProductTableHeader component.

Now that we’ve identified the components in our mock, let’s arrange them into a hierarchy. Components that appear within another component in the mock should appear as a child in the hierarchy:

* FilterableProductTable

    * SearchBar
    * ProductTable
        * ProductCategoryRow
        * ProductRow

The complete article is on:
[Article](https://reactjs.org/docs/thinking-in-react.html)