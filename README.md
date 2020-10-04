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
