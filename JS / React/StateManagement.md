# React State Management

## Definition

In React, the UI is not manipulated directly by the code, such as using commands like "Disable this button" or similar.
Instead, the developer describes the UI according to various states of the app, and these states are then triggered by user input.

## Additional Information

- The most important rule for states in React is that the state should not contain duplicate or unnecessary information.
- To share a state between multiple components, the state is moved to the nearest common parent component and then passed down through props.
- Using a reducer, state logic can be handled in a separate function and managed in a central location.
- To share information or states across many levels and components, a context is used, which can be queried by the consuming components.
- Reducers and contexts can also be combined to manage complex applications.

## Graphics

### Process of rendering behavior in a React app:

![Image](https://blog.logrocket.com/wp-content/uploads/2021/05/react-usestate-usereducer-hooks.png)

Source: https://blog.logrocket.com/wp-content/uploads/2021/05/react-usestate-usereducer-hooks.png

### Representation of the useReducer-Hook:

![Image](https://blog.logrocket.com/wp-content/uploads/2021/05/react-usereducer-hook.png)

Source: https://blog.logrocket.com/wp-content/uploads/2021/05/react-usereducer-hook.png

## Code

### State

State Initialization:
```js
const [count, setCount] = useState(0);
```

Function to change the State:
```js
setCount(count + 1);
```

Using the State:
```js
<p>You clicked {count} times</p>
```

### Reducer

Initialization of a Reducer:
```js
const [state, dispatch] = useReducer(reducerFunc, 0);
```

Calling a Reducer:
```js
dispatch({ type: 'INCREMENT' })
```

Structure of a Reducer Function:
```js
function reducerFunc(state, action) {
  switch (action.type) {
    case 'INCREMENT':
      return state + 1;
    case 'DECREMENT':
      return state - 1;
    case 'RESET':
      return 0;
    case 'SET':
      return action.val;
  }
}
```

### Context

Creation of a Context:
```js
export const themeContext = createContext('light');
```

Import of a Context in a consumer component:
```js
import { useContext } from 'react';
import { ThemeContext } from './App.js';

export default function Button({ children }) {
    const theme = useContext(ThemeContext);
    // ...
}
```

The render tree above the consumer component has to be placed inside a Provider:
```js
<ThemeContext.Provider value={theme}>
    {children}
</ThemeContext.Provider>
```

## Sources

Kokane, K., 2023. The modern guide to React state patterns. LogRocket Blog. Available at: <https://blog.logrocket.com/modern-guide-react-state-patterns/> [Accessed 31 May 2024].

React, 2024. Managing State – React. [online] Available at: <https://react.dev/learn/managing-state> [Accessed 31 May 2024].