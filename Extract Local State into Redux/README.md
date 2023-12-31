You're almost done! Recall that you wrote all the Redux code so that Redux could control the state management of your React messages app. Now that Redux is connected, you need to extract the state management out of the Presentational component and into Redux. Currently, you have Redux connected, but you are handling the state locally within the Presentational component.

In the Presentational component, first, remove the messages property in the local state. These messages will be managed by Redux. Next, modify the submitMessage() method so that it dispatches submitNewMessage() from this.props, and pass in the current message input from local state as an argument. Because you removed messages from local state, remove the messages property from the call to this.setState() here as well. Finally, modify the render() method so that it maps over the messages received from props rather than state.

Once these changes are made, the app will continue to function the same, except Redux manages the state. This example also illustrates how a component may have local state: your component still tracks user input locally in its own state. You can see how Redux provides a useful state management framework on top of React. You achieved the same result using only React's local state at first, and this is usually possible with simple apps. However, as your apps become larger and more complex, so does your state management, and this is the problem Redux solves.

Tests
The AppWrapper should render to the page.
The Presentational component should render to page.
The Presentational component should render an h2, input, button, and ul elements.
The Presentational component should receive messages from the Redux store as a prop.
The Presentational component should receive the submitMessage action creator as a prop.
The state of the Presentational component should contain one property, input, which is initialized to an empty string.
Typing in the input element should update the state of the Presentational component.
Dispatching the submitMessage on the Presentational component should update Redux store and clear the input in local state.
The Presentational component should render the messages from the Redux store.