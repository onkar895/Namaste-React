# useMemo Hook:

- useMemo is a React Hook that lets you cache the result of a calculation between re-renders.
- In the context of useMemo, cache means storing the result of a computation so that it doesn't need to be recalculated on every render unless its dependencies change.

## Syntax:

```js
const cachedValue = useMemo(calculateValue, dependencies);
```

## Usage:

- Skipping expensive recalculations
- Skipping re-rendering of components
- Preventing an Effect from firing too often
- Memoizing a dependency of another Hook
- Memoizing a function

## How useMemo Works:

- When a component re-renders, all functions and expressions inside it are re-executed.
- If there's an expensive calculation inside the component, it will run again on every render, even if the inputs haven't changed.
- useMemo caches the result of the computation and only recalculates when the dependencies change.

```js
import { useState, useMemo } from "react";

function ExpensiveComponent({ num }) {
  const expensiveCalculation = (n) => {
    console.log("Calculating...");
    return n * 2; // Simulating an expensive operation
  };

  const result = useMemo(() => expensiveCalculation(num), [num]);

  return <div>Result: {result}</div>;
}

export default function App() {
  const [count, setCount] = useState(0);
  const [num, setNum] = useState(5);

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Increment Count: {count}</button>
      <button onClick={() => setNum(num + 1)}>Change Num: {num}</button>
      <ExpensiveComponent num={num} />
    </div>
  );
}
```

### What Happens Here?

- useMemo(() => expensiveCalculation(num), [num]) caches the result.
- If num doesn't change, useMemo returns the cached result instead of running expensiveCalculation again.
- If you click "Increment Count", the component re-renders, but expensiveCalculation does not run again because num didn't change.
- If you click "Change Num", then expensiveCalculation runs again and updates the cached value.

## FOR MORE INFORMATION PLEASE VISIT : https://react.dev/reference/react/useMemo
