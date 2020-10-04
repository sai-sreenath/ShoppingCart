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
