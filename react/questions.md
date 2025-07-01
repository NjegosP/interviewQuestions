# React Interview Questions

---

### 1. Explain the difference between state and props in React?

**Difficulty**: Easy  
**Sample Answer**:

-   **Props** are read-only data passed from parent to child components. They are immutable within the child and are used to configure or customize components. Props enable data flow from parent to child (unidirectional data flow).
-   **State** is internal data managed by a component. State can change over time, usually in response to user actions or network responses. State changes trigger re-renders.

**Comparison:**

-   Use props for data that comes from outside the component and should not be changed by the component.
-   Use state for data that is managed and changed within the component.

**Connected Questions**: [#2](#2), [#7](#7)

**Further Reading**:

-   [React Docs: State and Lifecycle](https://react.dev/learn/state-a-components-memory)
-   [React Docs: Props](https://react.dev/learn/passing-props-to-a-component)
-   [Pure React by Dave Ceddia](https://daveceddia.com/pure-react/)

---

### 2. What are React hooks and why were they introduced?

**Difficulty**: Medium  
**Sample Answer**:
**React hooks** are functions that let you use state and other React features in functional components. Introduced in React 16.8, hooks allow you to manage state (`useState`), side effects (`useEffect`), context (`useContext`), and more without writing class components.

**Why introduced?**

-   To avoid the complexity of class components
-   To enable code reuse via custom hooks
-   To make logic easier to share and test

**Connected Questions**: [#3](#3), [#6](#6)

**Further Reading**:

-   [React Docs: Introducing Hooks](https://react.dev/learn/introducing-hooks)
-   [Overreacted: Why Do React Hooks Exist?](https://overreacted.io/why-do-react-hooks-exist/)
-   [React Docs: Hooks API Reference](https://react.dev/reference/react)

---

### 3. Explain the useEffect hook and its dependencies array.

**Difficulty**: Medium  
**Sample Answer**:
**useEffect** is a hook for performing side effects in functional components (e.g., data fetching, subscriptions, manual DOM updates). It runs after every render by default, but you can control when it runs using the dependencies array.

-   **Dependencies array**: If empty (`[]`), effect runs once after initial render. If it contains variables, effect runs when any of them change. If omitted, effect runs after every render.
-   **Cleanup**: Return a function from useEffect to clean up (e.g., unsubscribe, clear timers).

**Connected Questions**: [#2](#2), [#6](#6)

**Further Reading**:

-   [React Docs: useEffect](https://react.dev/reference/react/useEffect)
-   [Overreacted: A Complete Guide to useEffect](https://overreacted.io/a-complete-guide-to-useeffect/)

---

### 4. What is the virtual DOM and how does it work?

**Difficulty**: Medium  
**Sample Answer**:
The **virtual DOM** is a lightweight, in-memory representation of the real DOM. When state or props change, React creates a new virtual DOM tree, compares it to the previous one (diffing), and calculates the minimal set of changes needed. It then updates the real DOM efficiently (reconciliation).

**Benefits:**

-   Reduces expensive direct DOM manipulations
-   Improves performance and responsiveness
-   Enables declarative UI programming

**Connected Questions**: [#8](#8), [#10](#10)

**Further Reading**:

-   [React Docs: Reconciliation](https://react.dev/learn/reconciliation)
-   [React Docs: Rendering Elements](https://react.dev/learn/rendering-elements)
-   [React Internals: How React Reconciles](https://react.dev/learn/how-react-reconciles)

---

### 5. Explain the concept of controlled vs uncontrolled components.

**Difficulty**: Medium  
**Sample Answer**:

-   **Controlled components**: Form data is handled by React state. Input values are set via state, and changes are handled by event handlers. This makes form state predictable and easy to validate.
-   **Uncontrolled components**: Form data is handled by the DOM itself. You use refs to access values. This can be simpler for simple forms or when integrating with non-React code.

**Comparison:**

-   Use controlled components for complex forms, validation, and dynamic UI.
-   Use uncontrolled components for simple forms or when you need to avoid re-renders.

**Connected Questions**: [#1](#1), [#7](#7)

**Further Reading**:

-   [React Docs: Forms](https://react.dev/learn/forms)
-   [React Docs: Controlled vs Uncontrolled Components](https://react.dev/learn/uncontrolled-components)

---

### 6. What is the difference between useCallback and useMemo?

**Difficulty**: Hard  
**Sample Answer**:

-   **useCallback** memoizes a function, returning the same function instance unless dependencies change. Useful for passing stable callbacks to child components to prevent unnecessary re-renders.
-   **useMemo** memoizes a computed value, recalculating only when dependencies change. Useful for expensive calculations.

**Best Practices:**

-   Use only when necessary; overuse can hurt performance.
-   Combine with React.memo for optimal results.

**Connected Questions**: [#2](#2), [#10](#10)

**Further Reading**:

-   [React Docs: useCallback](https://react.dev/reference/react/useCallback)
-   [React Docs: useMemo](https://react.dev/reference/react/useMemo)
-   [Kent C. Dodds: When to useMemo and useCallback](https://kentcdodds.com/blog/usememo-and-usecallback)

---

### 7. Explain React Context and when to use it?

**Difficulty**: Medium  
**Sample Answer**:
**React Context** provides a way to pass data through the component tree without having to pass props down manually at every level. It is useful for global state like themes, authentication, or language preferences.

-   Create a context with `React.createContext()`
-   Use a Provider to supply the value
-   Use `useContext` or a Consumer to access the value

**Best Practices:**

-   Use for truly global data
-   Avoid overusing for frequently changing state (can cause re-renders)

**Connected Questions**: [#1](#1), [#5](#5)

**Further Reading**:

-   [React Docs: Context](https://react.dev/learn/passing-data-deeply-with-context)
-   [Kent C. Dodds: How to use React Context effectively](https://kentcdodds.com/blog/how-to-use-react-context-effectively)

---

### 8. What are React keys and why are they important?

**Difficulty**: Easy  
**Sample Answer**:
**Keys** are unique identifiers for elements in a list. They help React identify which items have changed, been added, or removed, enabling efficient updates during reconciliation. Keys should be stable, predictable, and unique (preferably IDs, not array indices).

**Best Practices:**

-   Use unique IDs for keys
-   Avoid using array indices as keys unless the list is static

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [React Docs: Lists and Keys](https://react.dev/learn/rendering-lists#keeping-list-items-in-order-with-key)
-   [Kent C. Dodds: React Keys](https://kentcdodds.com/blog/understanding-react-keys)

---

### 9. Explain the concept of React portals?

**Difficulty**: Medium  
**Sample Answer**:
**React portals** allow you to render children into a DOM node outside the parent component hierarchy. This is useful for modals, tooltips, and overlays that need to visually break out of their parent container but still participate in React's event system.

**Example:**

```js
ReactDOM.createPortal(child, container);
```

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [React Docs: Portals](https://react.dev/learn/portals)
-   [React Docs: Advanced Guides](https://react.dev/learn/advanced-guides)

---

### 10. What is the difference between React.memo, useMemo, and useCallback?

**Difficulty**: Hard  
**Sample Answer**:

-   **React.memo** is a higher-order component that memoizes a component, preventing re-renders if props haven't changed.
-   **useMemo** memoizes a computed value, recalculating only when dependencies change.
-   **useCallback** memoizes a function, returning the same function instance unless dependencies change.

**Best Practices:**

-   Use React.memo for pure components
-   Use useMemo/useCallback for expensive calculations or stable callbacks
-   Profile before optimizing

**Connected Questions**: [#4](#4), [#6](#6)

**Further Reading**:

-   [React Docs: React.memo](https://react.dev/reference/react/memo)
-   [React Docs: useMemo](https://react.dev/reference/react/useMemo)
-   [React Docs: useCallback](https://react.dev/reference/react/useCallback)
-   [Kent C. Dodds: When to useMemo and useCallback](https://kentcdodds.com/blog/usememo-and-usecallback)

### 11. What is the Context API in React and when should you use it?

**Difficulty**: Medium  
**Sample Answer**:
The Context API allows you to share state across the component tree without passing props down manually at every level. Use it for global data like themes, authentication, or user settings, but avoid overusing it for all state management.

**Connected Questions**: [#5](#5), [#10](#10)

**Further Reading**:

-   [React Docs: Context](https://react.dev/reference/react/Context)
-   [Kent C. Dodds: When to use Context](https://kentcdodds.com/blog/how-to-use-react-context-effectively)

---

### 12. What are React Portals and when would you use them?

**Difficulty**: Medium  
**Sample Answer**:
React Portals allow you to render children into a DOM node outside the parent component hierarchy. They are useful for modals, tooltips, and overlays, ensuring correct stacking and event handling.

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [React Docs: Portals](https://react.dev/reference/react-dom/createPortal)
-   [CSS Tricks: React Portals](https://css-tricks.com/using-react-portals/)

---

### 13. What is the difference between controlled and uncontrolled components?

**Difficulty**: Medium  
**Sample Answer**:
Controlled components have their form data managed by React state, while uncontrolled components use refs to access DOM values directly. Controlled components offer more control and validation, while uncontrolled components are simpler for basic use cases.

**Connected Questions**: [#6](#6)

**Further Reading**:

-   [React Docs: Forms](https://react.dev/reference/react-dom/components/input)
-   [Kent C. Dodds: Controlled vs Uncontrolled](https://kentcdodds.com/blog/controlled-vs-uncontrolled-inputs)

---

### 14. What are React Hooks and why were they introduced?

**Difficulty**: Medium  
**Sample Answer**:
Hooks are functions that let you use state and lifecycle features in functional components. Introduced in React 16.8, they simplify code, avoid class components, and enable code reuse through custom hooks.

**Connected Questions**: [#7](#7)

**Further Reading**:

-   [React Docs: Hooks](https://react.dev/reference/react/Hooks)
-   [Overreacted: Why Hooks](https://overreacted.io/why-do-we-write-super-props/)

---

### 15. What is useMemo and when should you use it?

**Difficulty**: Medium  
**Sample Answer**:
`useMemo` is a React Hook that memoizes the result of a computation, recomputing only when dependencies change. Use it to optimize expensive calculations or prevent unnecessary re-renders of child components.

**Connected Questions**: [#9](#9)

**Further Reading**:

-   [React Docs: useMemo](https://react.dev/reference/react/useMemo)
-   [Kent C. Dodds: useMemo and useCallback](https://kentcdodds.com/blog/usememo-and-usecallback)

---

### 16. What is React Suspense and how does it work?

**Difficulty**: Medium  
**Sample Answer**:
React Suspense lets you wait for some code or data to load before rendering a component. It works with `React.lazy` for code splitting and can be used with data fetching libraries for smoother loading states.

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [React Docs: Suspense](https://react.dev/reference/react/Suspense)
-   [React Docs: Lazy Loading](https://react.dev/reference/react/lazy)

---

### 17. What is reconciliation in React?

**Difficulty**: Hard  
**Sample Answer**:
Reconciliation is the process React uses to update the DOM efficiently. It compares the new virtual DOM with the previous one, calculates the minimal set of changes, and updates the real DOM accordingly. This makes updates fast and efficient.

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [React Docs: Reconciliation](https://react.dev/reference/react/Reconciliation)
-   [React Docs: Rendering Elements](https://react.dev/reference/react/Rendering_elements)

---

### 18. What is the difference between useEffect and useLayoutEffect?

**Difficulty**: Medium  
**Sample Answer**:
`useEffect` runs after the DOM has been painted, while `useLayoutEffect` runs synchronously after all DOM mutations but before the browser paints. Use `useLayoutEffect` for measurements or DOM manipulations that must happen before paint.

**Connected Questions**: [#14](#14)

**Further Reading**:

-   [React Docs: useEffect](https://react.dev/reference/react/useEffect)
-   [React Docs: useLayoutEffect](https://react.dev/reference/react/useLayoutEffect)

---

### 19. What is server-side rendering (SSR) in React and what are its benefits?

**Difficulty**: Medium  
**Sample Answer**:
Server-side rendering (SSR) renders React components on the server and sends HTML to the client. This improves initial load performance and SEO, as content is available before JavaScript loads. Hydration attaches event listeners on the client.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [React Docs: Server Components](https://react.dev/reference/react-server/overview)
-   [Next.js Docs: SSR](https://nextjs.org/docs/pages/building-your-application/rendering/server-side-rendering)

---

### 20. What is React Fiber?

**Difficulty**: Hard  
**Sample Answer**:
React Fiber is the new reconciliation engine in React 16+. It enables incremental rendering, better scheduling, and improved responsiveness for complex applications. Fiber breaks rendering work into units, allowing React to pause and resume rendering as needed.

**Connected Questions**: [#17](#17)

**Further Reading**:

-   [React Docs: Fiber Architecture](https://react.dev/reference/react/Fiber)
-   [Overreacted: React Fiber Architecture](https://overreacted.io/react-as-a-ui-runtime/)
