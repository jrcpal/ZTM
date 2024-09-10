# Redux Overview

Redux simplifies state management by storing state as props in a collective object. It can be thought of as similar to `this.state` in React.

## Key Concepts

- **State Management**: 
  - Pass down state to components that need it as props.
  - Avoid cascading props through all parent components to reach a final child component.
  - Ideal for managing large state and sharing data between containers.
  - Provides predictable state management using three principles:
    1. **Single Source of Truth**: The state of your whole application is stored in an object tree within a single store.
    2. **State is Read-Only**: The only way to change the state is to emit an action, an object describing what happened.
    3. **Changes Using Pure Functions**: To specify how the state tree is transformed by actions, you write pure reducers.

## Core Components

- **Action**:
  - An action is something that a user does, such as a button click.

- **Reducer**:
  - A pure function that receives an input (the action) and creates an output (the state).

- **Store**:
  - The entire state object of the app.

## Making Changes

- As the store gets updated, changes are made.
- All actions go through one reducer, which, because it's a pure function, always returns the state through the store to make changes. This acts as a funnel to control the flow of action.
- Uses the traditional Flux Pattern as a one-way data flow, in contrast to MVC (Model View Controller).

## Integration

- Redux can still be used together with `this.state`.
- Redux Toolkit helps reduce the manual work of creating boilerplates for Redux.

## Redux Hooks

- **`useDispatch`**:
  - Used to send actions to the Redux store.
  - Returns the `dispatch` function.

- **`useSelector`**:
  - Used to read data from the Redux store state.
  - Takes a selector function to specify which part of the state to extract.


## Middleware

- **Purpose**:
  - Middleware provides a way to extend Redux with custom functionality.
  - It sits between the dispatching of an action and the moment it reaches the reducer.
  - Common use cases include logging, crash reporting, performing asynchronous tasks, and handling side effects.

- **How It Works**:
  - Middleware intercepts every action dispatched to the store before it reaches the reducer.
  - It can perform tasks, modify actions, or even dispatch other actions.

- **Common Middleware Libraries**:
  - **Redux Thunk**: Allows you to write action creators that return a function instead of an action. This is useful for handling asynchronous operations.
  - **Redux Saga**: Uses generator functions to handle side effects in a more manageable way.
  - **Redux Logger**: Logs actions and state changes to the console, useful for debugging.

  
## Slices (Redux Toolkit)

- **Purpose**:
  - A slice is a collection of Redux reducer logic and actions for a single feature of your application.
  - It simplifies the process of writing Redux logic by combining actions and reducers in a single file.

- **Creating a Slice**:
  - Use the `createSlice` function from Redux Toolkit to create a slice.
  - Define the initial state, reducers, and actions within the slice.