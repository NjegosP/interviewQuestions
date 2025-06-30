# React Native Interview Questions

---

## Questions

### 1. **Question**: Explain the difference between React Native and React for web development.

**Difficulty**: Easy  
**Category**: Fundamentals  
**Key Concepts**: Cross-platform development, native components, bridge architecture  
**Sample Answer**:

-   **React** is a JavaScript library for building user interfaces for the web, rendering to the DOM using HTML elements.
-   **React Native** is a framework for building native mobile apps using React. It renders to native components (e.g., `View`, `Text`, `Image`) instead of HTML, and uses a bridge to communicate between JavaScript and native code.

**Comparison:**

-   React Native apps run on iOS and Android, using native UI components.
-   React web apps run in browsers, using HTML/CSS.
-   React Native has platform-specific APIs and navigation patterns.

**Connected Questions**: [#3: Explain the concept of Flexbox in React Native and how it differs from web CSS.], [#9: Explain the concept of platform-specific code in React Native.]

**Further Reading**:

-   [React Native Docs: Introduction](https://reactnative.dev/docs/getting-started)
-   [React Native vs React: Key Differences](https://blog.logrocket.com/react-vs-react-native/)
-   [Fullstack React Native (book)](https://www.fullstackreact.com/react-native/)

---

### 2. **Question**: What is the difference between Expo and React Native CLI?

**Difficulty**: Medium  
**Category**: Development Tools  
**Key Concepts**: Managed vs bare workflow, development experience, native modules  
**Sample Answer**:

-   **Expo** is a set of tools and services built around React Native, providing a managed workflow with pre-built native modules, easy setup, and over-the-air updates. Expo Go app allows quick testing on devices.
-   **React Native CLI** is the official command-line tool for React Native, giving full control over native code and dependencies. It requires more setup but allows custom native modules and advanced configuration.

**Comparison:**

-   Use Expo for rapid prototyping, simple apps, or when you don't need custom native code.
-   Use React Native CLI for complex apps, custom native modules, or advanced integrations.

**Connected Questions**: [#10: What is the difference between development and production builds in React Native?]

**Further Reading**:

-   [Expo Docs: Introduction](https://docs.expo.dev/)
-   [React Native CLI Quickstart](https://reactnative.dev/docs/environment-setup)
-   [Expo vs React Native CLI](https://blog.logrocket.com/expo-vs-react-native-cli/)

---

### 3. **Question**: Explain the concept of Flexbox in React Native and how it differs from web CSS.

**Difficulty**: Medium  
**Category**: Layout  
**Key Concepts**: Flexbox, cross-platform layout, responsive design  
**Sample Answer**:
**Flexbox** is the primary layout system in React Native. It works similarly to CSS Flexbox but with some differences:

-   The default flex direction is `column` (vs `row` on the web).
-   All dimensions are unitless numbers (not pixels).
-   No CSS Grid; all layouts use Flexbox.

**Use Cases:**

-   Responsive layouts
-   Aligning and distributing space among items
-   Building navigation bars, lists, and grids

**Connected Questions**: [#1: Explain the difference between React Native and React for web development.], [#10: What is the difference between development and production builds in React Native?]

**Further Reading**:

-   [React Native Docs: Flexbox](https://reactnative.dev/docs/flexbox)
-   [CSS Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
-   [Fullstack React Native: Layouts](https://www.fullstackreact.com/react-native/layout/)

---

### 4. **Question**: What are React Native bridges and how do they work?

**Difficulty**: Hard  
**Category**: Architecture  
**Key Concepts**: JavaScript bridge, native modules, performance, new architecture  
**Sample Answer**:
A **bridge** in React Native enables communication between JavaScript and native code (Java/Obj-C/Swift). The bridge is asynchronous and serializes data between the JS and native threads. This can introduce performance bottlenecks for frequent or large data transfers.

**New Architecture:**

-   The new Fabric renderer and TurboModules reduce bridge overhead by enabling synchronous and direct communication, improving performance and reliability.

**Connected Questions**: [#2: What is the difference between Expo and React Native CLI?], [#8: What are React Native performance optimization techniques?]

**Further Reading**:

-   [React Native Docs: Native Modules](https://reactnative.dev/docs/native-modules-intro)
-   [React Native New Architecture](https://reactnative.dev/docs/the-new-architecture)
-   [Bridging in React Native](https://blog.logrocket.com/bridging-in-react-native/)

---

### 5. **Question**: Explain the concept of navigation in React Native and popular navigation libraries.

**Difficulty**: Medium  
**Category**: Navigation  
**Key Concepts**: Stack navigation, tab navigation, drawer navigation, React Navigation  
**Sample Answer**:
**Navigation** in React Native is handled by libraries, the most popular being **React Navigation**. It supports:

-   **Stack navigation**: Navigating between screens in a stack (like browser history)
-   **Tab navigation**: Switching between screens using tabs
-   **Drawer navigation**: Side menu navigation

**Features:**

-   Deep linking
-   Navigation state persistence
-   Custom transitions and gestures

**Connected Questions**: [#3: Explain the concept of Flexbox in React Native and how it differs from web CSS.]

**Further Reading**:

-   [React Navigation Docs](https://reactnavigation.org/docs/getting-started)
-   [React Native Navigation (alternative)](https://wix.github.io/react-native-navigation/)
-   [Fullstack React Native: Navigation](https://www.fullstackreact.com/react-native/navigation/)

---

### 6. **Question**: What is the difference between synchronous and asynchronous operations in React Native?

**Difficulty**: Medium  
**Category**: Performance  
**Key Concepts**: JavaScript thread, native thread, blocking operations, performance optimization  
**Sample Answer**:

-   **Synchronous operations** block the JavaScript thread, causing UI freezes and poor user experience. Examples: heavy computations, blocking loops.
-   **Asynchronous operations** (e.g., network requests, timers) run in the background, allowing the UI to remain responsive. Use `async/await`, Promises, or callbacks for async code.

**Best Practices:**

-   Offload heavy work to native modules or background threads
-   Use async APIs for I/O and network

**Connected Questions**: [#8: What are React Native performance optimization techniques?]

**Further Reading**:

-   [React Native Docs: Performance](https://reactnative.dev/docs/performance)
-   [React Native Performance Tips](https://blog.logrocket.com/react-native-performance/)

---

### 7. **Question**: Explain the concept of state management in React Native apps.

**Difficulty**: Medium  
**Category**: State Management  
**Key Concepts**: Redux, Context API, local state, global state  
**Sample Answer**:
State management in React Native can be handled in several ways:

-   **Local state**: Managed with `useState` or class component state, suitable for component-specific data.
-   **Context API**: For simple global state (themes, user info).
-   **Redux**: For complex, app-wide state, providing predictable state updates and middleware support.

**Best Practices:**

-   Use local state for UI and simple data
-   Use Context or Redux for global/shared state
-   Avoid unnecessary re-renders by structuring state carefully

**Connected Questions**: [#6: What is the difference between synchronous and asynchronous operations in React Native?], [#8: What are React Native performance optimization techniques?]

**Further Reading**:

-   [React Native Docs: State](https://reactnative.dev/docs/state)
-   [Redux Docs: Introduction](https://redux.js.org/introduction/getting-started)
-   [React Context API](https://react.dev/learn/passing-data-deeply-with-context)

---

### 8. **Question**: What are React Native performance optimization techniques?

**Difficulty**: Hard  
**Category**: Performance  
**Key Concepts**: FlatList, memoization, image optimization, bundle size  
**Sample Answer**:

-   Use **FlatList** for large lists (virtualization)
-   Memoize expensive components with `React.memo`
-   Optimize images (resize, compress, use `Image` component's caching)
-   Reduce bundle size (code splitting, lazy loading)
-   Enable Hermes engine for faster JS execution
-   Profile with Flipper or React DevTools

**Connected Questions**: [#4: What are React Native bridges and how do they work?], [#6: What is the difference between synchronous and asynchronous operations in React Native?]

**Further Reading**:

-   [React Native Docs: Performance](https://reactnative.dev/docs/performance)
-   [React Native Performance Tips](https://blog.logrocket.com/react-native-performance/)
-   [Flipper: Debugging React Native](https://fbflipper.com/docs/features/react-native/)

---

### 9. **Question**: Explain the concept of platform-specific code in React Native.

**Difficulty**: Medium  
**Category**: Platform Differences  
**Key Concepts**: Platform.OS, platform-specific files, conditional rendering  
**Sample Answer**:
React Native allows writing platform-specific code using:

-   `Platform.OS` to detect the platform (`ios` or `android`)
-   Platform-specific file extensions (`.ios.js`, `.android.js`)
-   Conditional rendering for UI differences

**Best Practices:**

-   Use platform-specific code only when necessary
-   Follow platform conventions for UI/UX

**Connected Questions**: [#1: Explain the difference between React Native and React for web development.]

**Further Reading**:

-   [React Native Docs: Platform-specific code](https://reactnative.dev/docs/platform-specific-code)
-   [React Native Docs: Platform module](https://reactnative.dev/docs/platform)

---

### 10. **Question**: What is the difference between development and production builds in React Native?

**Difficulty**: Medium  
**Category**: Build Process  
**Key Concepts**: Debug vs release builds, bundle optimization, performance differences  
**Sample Answer**:

-   **Development builds** include debugging tools, hot reloading, and are not optimized for performance. They are larger and slower, but easier to debug.
-   **Production builds** are optimized for performance, smaller in size, and do not include debugging tools. Enable Hermes for better performance.

**Best Practices:**

-   Test on both debug and release builds
-   Use different bundle configurations for environments

**Connected Questions**: [#2: What is the difference between Expo and React Native CLI?], [#3: Explain the concept of Flexbox in React Native and how it differs from web CSS.]

**Further Reading**:

-   [React Native Docs: Running on Device](https://reactnative.dev/docs/running-on-device)
-   [React Native Docs: Hermes](https://reactnative.dev/docs/hermes)
-   [React Native CLI Environment Setup](https://reactnative.dev/docs/environment-setup)
