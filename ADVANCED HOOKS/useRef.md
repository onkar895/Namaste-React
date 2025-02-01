# 📌 useRef Hook

### Introduction

`useRef` is a React Hook that lets you reference a **value that doesn’t trigger re-renders** when updated. It is mainly used for:

- Accessing **DOM elements**.
- Keeping a **mutable variable** that persists across renders.
- Storing a **previous state value**.

### Syntax

```js
const ref = useRef(initialValue);
```

### ✅ Parameters:

1. **initialValue** → The initial value for the reference.

### Example 1: Accessing an Input Field

```js
import React, { useRef } from "react";

function FocusInput() {
  const inputRef = useRef(null);

  const handleFocus = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type='text' placeholder='Type something...' />
      <button onClick={handleFocus}>Focus Input</button>
    </div>
  );
}
```

**Explanation:**

- `useRef` holds a reference to the input field.
- Clicking the button **focuses the input field** without triggering a re-render.

### Example 2: Storing a Mutable Value

```js
import React, { useRef, useState } from "react";

function Counter() {
  const countRef = useRef(0);
  const [count, setCount] = useState(0);

  const increment = () => {
    countRef.current += 1;
    setCount(count + 1);
    console.log("Mutable Count (useRef):", countRef.current);
  };

  return (
    <div>
      <p>State Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}
```

**Explanation:**

- `countRef` holds a value **outside of React’s re-render cycle**.
- The console logs show the `useRef` value changing **without causing re-renders**.

### Benefits of `useRef`

✅ **Does not trigger re-renders** when updated.
✅ **Persists values** across renders (useful for tracking values between renders).
✅ **Directly manipulates the DOM** (useful for focusing, animations, etc.).

---

### 🚀 **By using `useRef`, we can optimize performance and avoid unnecessary re-renders in React applications!**
