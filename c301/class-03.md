# List and Keys

`First, let's review how you can transform list in JavaScript.`

Given the code below, we use the `map()` function to take an array of numvers and double their values. We assign the new array returnedby the `map()` function to the `doubled` variable.

```js
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(number => number * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
```

In React, transformin arrays into lists of elements is nearly identical.

### Rendering Multiple Components

You can build collections of elemts and `include them in JSX` using curly braces. 

Below, we loop through the numbers array using the JavaScript `map()` function. We return a `<li>` element for each number in the array.

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map(number => <li>{number}</li>);
```

Then, we can include the entire listItems array inside a `<ul>` element.

```js
<ul>{listItems}</ul>
```

This code displays the numbers 1 through 5 in a list.

### Basic List Component

Ususally, you would render lists indide a `component` class.

We can refactor the previous example into a component that accepts an array of numbers and output a list of elements. 

``` js
function NumberList(props) {
    const numbers = props.numbers;
    const listItems = numbers.map(number => <li>{number}</li>);

    return (
        <ul>{listItems}</ul>
    );
}

const numbers = [1, 2, 3, 4, 5];
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<NumberList numbers={numbers} />);
```

When you run this code, you'll be given a warning that a key should be provided for list items. A 'key' is should be provided for list items. A 'key' is  `special` string attribute you need to include when creating list of elements. We'll discess why it's important in the next section. 

Let's assign a 'key' to our list items inside `numbers.map()` and fix the missing key issue.

```js

function NumberList(props) {
    const numbers = props.numbers;
    const listItems = numbers.map(number => <li key={number.toString()}>{number}</li>);

    return (
        <ul>{listItems}</ul>
    );
}

```

full article on 
[React Full Article](https://reactjs.org/docs/react-api.html#reactchildren)