# What is a `Controlled Component`?

These types of question are common in React. Another common question is `Should we wait to store the users responses from the form into state when they submit the form Or should we update the state with their responses as soon as they enter them?`.. How do we decide? Another question is `how do we target what the user is entering if we have an event handler on an input field?`. I will answer these questions in the next section.

## Forms

HTML form elements work a bit differently form other DOM elements in React, because form elements naturally keep some internal state. for example, this form in plain HTML accepts a single name:

```html
<form>
	<label>
		Name:
		<input type="text" name="name" />
	</label>
	<input type="submit" value="Submit" />
</form>
```

This form has the default HTML form behauir of browsing to a new page when the user submits the form. If you want this behavior in React, it just works. But in most cases, it's convenient to have a JavaScript funvtion that handles the submission of the form and has access to the data that the user entered into the form. The standard way to achieve this is with a techique called `controlled components`.

## Controlled Components

In HTML, form elements such as `<input>` `<textarea>` and `<select>` typically maintain their own state and update it basesd on user input. In react, mutable state is typically kept in the state property of components, and only updated with `setState()` calls.

We can combine the two by making the React state be the `single source of truth`. The the React component that renders a form also controls what happens when in that form on subsequent user input. An input form elemtent whose value is controlled by React in this way is called a `controlled component`.

For example, if we watnt to amke the previous example log the name when it is submitted, we can write the form as a `controlled component`:

```js
export default class NameForm extends React.Component {
    constructor(props){
        super(props);
        this.state = {
            value: ''
        };

        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
    }

    handleChange(event) {
        this.setState({
            value: event.target.value
        });
    }

    handleSubmit(event) {
        alert(
            'A name was submitted: ' + this.state.value
        );
        event.preventDefault();
    }

    render() {
        return (
            <form onSubmit={this.handleSubmit}>
            <label>
                Name:
                <input type='text' value={this.state.value} onChange={this.handleChange} />
            </label>
            <input type='submit' value='Submit'>
            </form>
        );
    }
}
```

since the `value` attr is set on or form element, the displayed value will always be `this.state.value`, making the React state the source of truth. Since handleChange runs on every keystroke to update the React state, the displayed value will pdate as the user types. 

With a contrilled component, the inputs's value is always driven by the REact state. While this means you have to type a bit more code, you can now pass the value to other UI elements too, or reset it from other event handlers. 

***

# The `<textarea>` Tag

In Html, a `textarea` element defines it's text by its children: 

```html

<textarea>
    Hello there, this is some text in a text area
</textarea>

```

In React, a `<textarea>` uses a value attr instead. This way, a form using a `<textarea>` can be written very similaryly to a form that uses a single-line input.

```jsx

export default class EssayForm extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            value: 'Please write an essay about your favorite DOM element.'
        }
        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
    };

    handleChange(e) {
        this.setState({
            value: e.target.value
        });
    }
    handleSubmit(e) {
        alert('Ana essay was submitted: ' + this.state.value);
        e.preventDefault();
    }

    render() {
        return (
            <form onSubmit={this.handleSubmit}>
                <label>
                    Essay:
                        <textarea value={this.state.value} onChange={this.handleChange} />
                </label>
                    <input type='submit' value='Submit'>
            </form>
        )
    }
}
```

Notice that `this.state.value` is initialized in the constructor, so that the text area starts off withsome text in it.

***

# The select Tag

In HTML, `<select>` creates a dropdown list. For example, this HTML creates a drop-down list of flavours:

```HTML

<select>
    <option value='grapefruit'>GrapeFruit</option>
    <option value='line'>Lime</option>
    <option selected value='coconut'>Coconut</option>
    <option value='mango'>Mango</option>
</select>
```

Note that the Coconut option is initially selected, because of the `selected` attr. React instead of using this selected atrribute, uses a value atrribute on the root select tag. this is more convenient in a controlled component because you only need to update it in one place. For example: 

```jsx

export default class FlavourForm extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            value: 'coconut'
        }

        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
    }

    handleChange(e) {
        this.setState({
            value: e.target.value
        })
    }

    handleSubmit(e) {
        alert(
            'Your favourite flavor is: ' + this.state.value
        );
    }

    render() {
        return (
            <form onSubmit={this.handleSubmit}>
                <label>
                    Pick your favorite flavour: 
                        <select value={this.state.value} onChange={this.handlechange}>
                            <option value='grapefruit'>GrapeFruit</option>
                            <option value='lime'>Lime</option>
                            <option value='coconut'>Coconut</option>
                            <option value='mango'>Mango</option>
                        </select>
                        <input type='submit' value='Submit'>
                </label>
            </form>
        );
    }
}
```

Overal, this makes it so that `input type='text'`, `<textarea>` and `<select>` all work very similarly. They all accept a value attribute that you can use to implement a contrilled component.

Note
You can pass an array into the value attribute, allowing you to select multiple options in a select tag: 

```HTML
<select multiple={true} value={['B', 'C']}>
```

# The file input tag

In HTML, an `<input type='file'>` lets the user choose one or more files from their device storage to be uploaded to a server or manipulated by JavaScript vie the File API.

Because its value is read-only, it is an uncontrilled component in React. It is discussed together with other uncontrolled components later classes.

## Handling Multiple Inputs

When yuou need to handle multiple controlled input elements, you can add a `name` attribute to each element and let the handler function choose what to do based on the value of `event.target.name`.

As an example:

```jsx

export default class Reservation extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            isGoing: true,
            numberOfGuest: 2
        };

        this.handleInputChange = this.handleInputChange.bind(this);
    }

    handleInputChange(e) {
        const target = e.target;
        const value = target.type === 'checkbox'? target.checked: target.value;
        const name = target.name;

        this.setState({
            [name]: value
        });
    }

    render() {
        return (
            <form>
                <label>
                    Is going:
                        <input 
                            name='Isgoing'
                            type='checkbox'
                            checked={this.state.isGoing}
                            onChange={this.handleInputChange} />
                </label>
                <br />
                <label>
                    Number of guests: 
                        <input
                        name='numberOfGuests'
                        type='number'
                        value={this.state.numberOfGuests}
                        onChange={this.handleInputChange} />
                </label>
            </form>
        );
    }
}

```

Note how we used the ES6 computed property name syntax to update the state key corresponding to the given input name:

```jsx
this.setState({
    [name]: value
})

```

The above is equivalent to this ES5 code:

```jsx

let partialState = {};
partialState[name] = value;
this.setState(partialState);

```

Also, since `setState()` automatically merges a partial state into the current state, ewe only needed to call it with the changed parts.

### Controlled Input Null Value

Specifying the `value` prop on a controlled component prevents the user from changing the input unless you desire so. If you've specified a value but the input is still editable, you may have accidentally set value to undefined ro null.

The following code demonstrates this. (this input is locked at first but becomes editable after a short delay.)

```jsx
ReactDOM.createRoot(mountNode).render(<input value='hi'/>)

setTimeout(function() {
    ReactDOM.createRoot(mountNode).render(<input value={null} />);
}, 1000)

```

***

### Alternative to Contrilled Components

It can sometimes be tedious to use controlled components, because you need to write an event handler for every way your data can change and pipe all of the input state through a REact component. This can become particularly annoying when you are converting a preexisting code base to React, or integrating a React application with a non-React library. In these sistuations, you might want to check out uncontrolled componenents, an alternative technique for implementing input forms. 