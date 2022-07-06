# React Component Liecycle Events

What are component lifecycle events?:
Reacts lets you defin components as classes or functions. The methods that you are able to use one these are called lifecycle events. These methods can be called during the lifecycle of a component, and they allow you to update the UI and application states.

![React Lifecycle Events](https://miro.medium.com/max/1400/0*0saPKFiTUk6W3FYp)

Mounting, Updating, and Unmounting are the three phases of the component lifecycle.

    * Mounting: The component is being mounted into the DOM.
    * Updating: The component is receiving new props.
    * Unmounting: The component is being unmounted from the DOM.

### Mounting

When an instance of a component is being created and inserted into the DOM it occurs during the mounting phase. Constructor, **static**, **getDerivedStateFromProps**, and **componentDidMount** are the three lifecycle methods that are called during this phase.

### Updating

Anytime a component is updated or state changes then it is rerendered. These lifecycle events happen during updating this order. 

**static getDerivedStateFromProps, shouldComponentUpdate, render, getSnapshotBeforeUpdate, componentDidUpdate, UNSAFE_componentWillUpdate, UNSAFE_componentWillMount**

### Unmounting

The final phase of the lifecycle if called when a component is being removed from the DOM.  **componentWillUnmount** is the last lifecycle method that is called.

**constructor()**
The constructor for a React component is called before it is mounted. If the component is a subclass you should call super(props), or the props will be undefined. constructors can be used to assign state using this.state or b=to bind event handle methods to an instance. Let's take a look at some example code.

```js
    class FishTableRow extends React.Component {
        constructor() {
            super(); //gives us access to props
            this.state = { //intitialize local state
            showDescription: false,
            };
        }
    }
```
Avoid using the this.setState() in the constructor because it can lead to side effects, and it is unnecessary. Doing this will ignore all updates to props, so it shouldn't be done unless it is absolutely necessary.

***

**statc getDerivedStateFromProps()**

This method exists for rare cases where the state relies on changes in props over time.

**render()**

Render is the only required method in a class component. It will examine this.props and this.state when called. The render function should not modify the component state because it would cause a lot of bugs by changing the state every time it rerenders. I also should not directly interact wit the vrowser. render will not be invoked if **shouldComponentUpdate** returns false. Here is an example of using render.

```js

ReactDOM.render(

    <FishTable fishes = {fishData}/>, //set fishes to fishData
    document.getElementById('app')
)
```

***

**componentDidMount()**

This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions. If you do that, don’t forget to unsubscribe in componentWillUnmount().

setState() can be called here, but it should be used sparingly, because it will cause a rerender, which can lead to perfomance issues.

Here we use componentDidMount() to connect to the YouTube API and get videos when the components is rendered.

***

**UNSAFE_componentWillReceiveProps()**

These events have lead to a lof of bug and unintended side effects, so in React 17 these will no longer be able to to be used without the UNSAFE_ prefix in tag in front of the them, Instead of componentWillReceiveProps() you should use getDerivedStateFromProps().Instead of componentWillUpdate() you should use componentDidUpdate() or getSnapshotBeforeUpdate().

![Heady image](https://miro.medium.com/max/1244/1*4y9V5936WdJKaIeVPFEa3w.png)

#Full Article On

[React Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)