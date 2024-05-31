# React State Management

## Definition

In React wird die UI nicht direkt vom Code aus manipuliert, beispielsweise nutzt man keine Commands wie "Diesen Button deaktivieren" oder Ähnliches.
Stattdessen beschreibt der Entwickler die UI passend zu verschiedenen Zuständen der App und diese Zustände werden auf User Input hin getriggert.


## Zusatzinformationen

- Die wichtigste Grundregel für States in React ist, dass der State keine doppelte oder unnötigen Informationen enthalten soll
- Um den State zwischen mehreren Components zu teilen, wird der State in den nächsten gemeinsamen Parent-Component verschoben und dann via Props übergeben
- Mithilfe eines Reducers kann die State-Logik in eine seperate Funktion übergeben und an einer gemeinsame Stelle abgehandelt werden
- Um Informationen oder States über viele Ebenen und Components zu teilen nutzt man einen Context, der von den betroffenen Components abgefragt werden kann
- Reducer und Context können auch kombiniert werden, um komplexe Anwendungen zu steuern

## Grafiken

Ablauf des Render-Verhaltens in einer React-App:
![Image](https://blog.logrocket.com/wp-content/uploads/2021/05/react-usestate-usereducer-hooks.png)
Quelle: https://blog.logrocket.com/wp-content/uploads/2021/05/react-usestate-usereducer-hooks.png

Darstellung der useReducer-Hook:
![Image](https://blog.logrocket.com/wp-content/uploads/2021/05/react-usereducer-hook.png)
Quelle: https://blog.logrocket.com/wp-content/uploads/2021/05/react-usereducer-hook.png

## Code

### State

Erstellung des State:
```js
const [count, setCount] = useState(0);
```

Funktion zum Ändern des States:
```js
setCount(count + 1);
```

Abfragen des State:
```js
<p>You clicked {count} times</p>
```

### Reducer

Erstellung eines Reducers:
```js
const [state, dispatch] = useReducer(reducerFunc, 0);
```

Aufruf des Reducers:
```js
dispatch({ type: 'INCREMENT' })
```

Aufbau der Reducer Funktion:
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

Erstellung eines Context:
```js
export const themeContext = createContext('light');
```

Import des Context in einem Consumer Component:
```js
import { useContext } from 'react';
import { ThemeContext } from './App.js';

export default function Button({ children }) {
    const theme = useContext(ThemeContext);
    // ...
}
```

Der Tree oberhalb des Consumer Component muss in einen Provider eingefügt werden:
```js
<ThemeContext.Provider value={theme}>
    {children}
</ThemeContext.Provider>
```

## Quellen

Kokane, K., 2023. The modern guide to React state patterns. LogRocket Blog. Available at: <https://blog.logrocket.com/modern-guide-react-state-patterns/> [Accessed 31 May 2024].

React, 2024. Managing State – React. [online] Available at: <https://react.dev/learn/managing-state> [Accessed 31 May 2024].