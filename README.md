using props to initialize the state in counter component

props include data that we will give to a component

state includes data that is local or private to the component. So that other components cannot access the state. Its completely internal to the component.

Similarly in our counters component, it has its own local state which is completely
invisible too other components.

Sometimes component may not have a state, it gets all the data that it needs from props.

props is readonly, cannot change input(via props) to the component inside component.

Raising and handling events:

Adding delete button beside the counter component and adding click event for the button.
The component that owns the piece of the state should be the one modifying it.
Here, counter component raising the event, counters component handling the event

## Single Source of Truth:

Though the counter value is 0, but we dont see it on the view due to issue single source of truth.

Each of the counter component have their own local state, our counters component has array of counters and each counter component has a value. This value is currently disconnected from the value property of each counter object that we have in this array.

As you can see, we are initializing the value property of our state object, based on what we get from our props. This piece of code gets executed only once when instance of counter component gets created. So that's why when the page loads, we get the initial values here, and we can increment it beacuse this is a local state in our component from webpage,but when we click reset button, local counter component not updated. So to fix this, we need to remove local state in our counter component and have single source of truth.

## Removing local State:

Herein Counter component, we want to remove local state and only rely on props and receive the data that this component needs. This kind of components are controlled components(doesnt have ist own local state and receive all the data from props, raises events whenever data needs to be changed). So this component is entirely controlled by its parent.

## Lift the state up

Herein, when two components does not have parent-child relationship,(counters and navbar) so how do we display total number of counters on navigation bar? In these situations, if you want to keep the data in sync, and if you want to share data between them, we need to lift the state up. So here, we lift the state of the counters component to it's parent(App) component,then we pass it to child using props.

## Stateless Functional Components

Herein, In navbar component, we only have single method i.e, render method, we dont have nay event handlers, helper methods to calculate values,we only have single render method. Also we don't have any state, we are getting all the data via props. In situations we convert this component into statless Functional component. So instead of using a class, we can use a fucntion.

## Lifecycle Hooks

Components go through a few phases during their lifecycle.
Mounting phase: The first phase is the mounting phase and this is when an instance of a component is created and inserted into DOM.There are some special methods that we can add to our components and React will automatically call these methods. We refer to these methods as Lifecycle Hooks. So they allow us to hook into certain moments during the lifecycle of a component and do something.Mounting phase will have 3 lifecycle hooks constructor, render, componentDidMount. React will call these methods in order.

Update phase: when the state or props of the component get changed.
In this phase, we have 2 lifecycle hooks render and componentDidUpdate. So whenever we change the state of the component or give it new props, these two methods are called in order.

Unmount phase:
This is when the component is removed from the DOM as such when we are deleting the counter.In this phase we have componentWillUnmount hook.
These lifecycle hooks we see are frequently used ones. We have few more hooks but are not used much.
