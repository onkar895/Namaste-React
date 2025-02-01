# 📌 Important Resources

- [Higher Order Components](https://legacy.reactjs.org/docs/higher-order-components.html)
- [Accordion (Bootstrap)](https://getbootstrap.com/docs/5.0/components/accordion/)
- [Controlled Components](https://legacy.reactjs.org/docs/forms.html#controlled-components)
- [New Docs: Controlled & Uncontrolled Components](https://react.dev/learn/sharing-state-between-components#controlled-and-uncontrolled-components)
- [Lifting the State Up](https://react.dev/learn/sharing-state-between-components#lifting-state-up-by-example)
- [Props Drilling Problem](https://react.dev/learn/passing-data-deeply-with-context#the-problem-with-passing-props)
- [Ways to Avoid Props Drilling](https://blog.logrocket.com/solving-prop-drilling-react-apps/)

---

## 📌 Q1. What is a Higher-Order Component?

A **Higher-Order Component (HOC)** in React is a **function that takes a component as an argument and returns a new component that enhances the original component**.

### 🔹 Features:

- HOCs **enhance** a component without modifying its original code.
- They **wrap the original component** and add extra functionality.
- They are **pure functions**, meaning they don’t alter the input component but return a new enhanced one.

### ✅ Benefits:

- **Reusability** → Avoids redundant code across components.
- **Flexibility** → Can accept additional arguments for customization.
- Useful for **authentication, error handling, logging, and performance tracking**.

### 🔹 Example:

```js
function withRouter(ExistingComponent) {
  return function (props) {
    const location = useRouter();
    return <ExistingComponent {...props} location={location} />;
  };
}
```

---

## 📌 Q2. What makes the Data Layer of our app?

The **Data Layer** in a React app consists of:

- **State**
- **Props**
- **Local Variables**
- **Any data the app interacts with**

It serves as the **power source** for the UI layer.

---

## 📌 Q3. What makes the UI Layer of our app?

The **UI Layer** consists of JSX that gets rendered in the browser DOM.

- It is **static** and depends on the **Data Layer** for dynamic updates.

---

## 📌 Q4. What is Lifting the State Up?

Lifting the state up means **moving the state from child components to a common parent component** to maintain synchronization.

### ✅ Why?

- Ensures **consistent state updates** across multiple components.
- Useful when **multiple components need to share a single source of truth**.

### 🔹 Example:

- Instead of each Accordion item having its own state, we move the state to the parent and **pass it down via props**.

---

## 📌 Q5. What are Controlled and Uncontrolled Components?

### ✅ **Controlled Component:**

- **State is controlled by the parent component**.
- Uses **props** to get and set values.
- Example: A menu category component controlled by its parent container.

### ✅ **Uncontrolled Component:**

- **Manages its own state internally**.
- Not dependent on external control.
- Example: A form input where React doesn’t track the state.

---

## 📌 Q6. What is Props Drilling?

**Props Drilling** occurs when **data is passed down multiple levels of components unnecessarily**, even to components that don’t need it.

### 🔴 **Problem:**

- Makes components **tightly coupled**.
- Unnecessary **prop forwarding** increases complexity.

---

## 📌 Q7. What are Context Provider and Context Consumer?

### ✅ **Context Provider:**

- Used to **create a central/global place** to store values.
- Wrapped around parts of the app to provide context data.
- Uses `<SomeContext.Provider value={data}>`.

### ✅ **Context Consumer:**

- Used to **access values from the Context Provider**.
- Uses `<SomeContext.Consumer>` or `useContext(SomeContext)`.

---

## 📌 Q8. If you don't pass a value to the provider, does it take the default value?

**No**, it doesn’t take the default value. Instead:

- The value becomes **undefined**, causing errors.
- If the provider is completely omitted, components will use the **default context value**.

### 🔹 Example:

```js
const ThemeContext = createContext("Default");
```

```js
const User = () => {
  const context = useContext(ThemeContext);
  return <h2>User: {context}</h2>;
};
```

```js
const App = () => {
  return (
    <div>
      {/* Context Provider with a value */}
      <ThemeContext.Provider value={{ context: "User1" }}>
        <User /> {/* Output: User1 */}
      </ThemeContext.Provider>
      {/* Without Context Provider, fallback to default */}
      <User /> {/* Output: Default */}
    </div>
  );
};
```
