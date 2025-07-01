# React Native Interview Questions

---

### 1. What is the difference between React Native and React for web development? [Easy]

**Sample Answer**:

-   **React** is a JavaScript library for building user interfaces for the web, rendering to the DOM using HTML elements.
-   **React Native** is a framework for building native mobile apps using React. It renders to native components (e.g., `View`, `Text`, `Image`) instead of HTML, and uses a bridge to communicate between JavaScript and native code.

**Comparison:**

-   React Native apps run on iOS and Android, using native UI components.
-   React web apps run in browsers, using HTML/CSS.
-   React Native has platform-specific APIs and navigation patterns.

**Connected Questions**: [#3](#3)

**Further Reading**:

-   [React Native Docs: Introduction](https://reactnative.dev/docs/getting-started)
-   [React Native vs React: Key Differences](https://blog.logrocket.com/react-vs-react-native/)
-   [Fullstack React Native (book)](https://www.fullstackreact.com/react-native/)

---

### 2. What is the difference between Expo and React Native CLI?

-   **Expo** is a set of tools and services built around React Native, providing a managed workflow with pre-built native modules, easy setup, and over-the-air updates. Expo Go app allows quick testing on devices.
-   **React Native CLI** is the official command-line tool for React Native, giving full control over native code and dependencies. It requires more setup but allows custom native modules and advanced configuration.

**Comparison:**

-   Use Expo for rapid prototyping, simple apps, or when you don't need custom native code.
-   Use React Native CLI for complex apps, custom native modules, or advanced integrations.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Expo Docs: Introduction](https://docs.expo.dev/)
-   [React Native CLI Quickstart](https://reactnative.dev/docs/environment-setup)
-   [Expo vs React Native CLI](https://blog.logrocket.com/expo-vs-react-native-cli/)

---

### 3. Explain the concept of Flexbox in React Native and how it differs from web CSS. [Easy]

**Sample Answer**:
**Flexbox** is the primary layout system in React Native. It works similarly to CSS Flexbox but with some differences:

-   The default flex direction is `column` (vs `row` on the web).
-   All dimensions are unitless numbers (not pixels).
-   No CSS Grid; all layouts use Flexbox.

**Use Cases:**

-   Responsive layouts
-   Aligning and distributing space among items
-   Building navigation bars, lists, and grids

**Connected Questions**: [#1](#1)

**Further Reading**:

-   [React Native Docs: Flexbox](https://reactnative.dev/docs/flexbox)
-   [CSS Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
-   [Fullstack React Native: Layouts](https://www.fullstackreact.com/react-native/layout/)

---

### 4. What are React Native bridges and how do they work? [Easy]

**Sample Answer**:
A **bridge** in React Native enables communication between JavaScript and native code (Java/Obj-C/Swift). The bridge is asynchronous and serializes data between the JS and native threads. This can introduce performance bottlenecks for frequent or large data transfers.

**New Architecture:**

-   The new Fabric renderer and TurboModules reduce bridge overhead by enabling synchronous and direct communication, improving performance and reliability.

**Connected Questions**: [#2](#2)

**Further Reading**:

-   [React Native Docs: Native Modules](https://reactnative.dev/docs/native-modules-intro)
-   [React Native New Architecture](https://reactnative.dev/docs/the-new-architecture)
-   [Bridging in React Native](https://blog.logrocket.com/bridging-in-react-native/)

---

### 5. Explain the concept of navigation in React Native and popular navigation libraries. [Easy]

**Sample Answer**:
**Navigation** in React Native is handled by libraries, the most popular being **React Navigation**. It supports:

-   **Stack navigation**: Navigating between screens in a stack (like browser history)
-   **Tab navigation**: Switching between screens using tabs
-   **Drawer navigation**: Side menu navigation

**Features:**

-   Deep linking
-   Navigation state persistence
-   Custom transitions and gestures

**Connected Questions**: [#3](#3)

**Further Reading**:

-   [React Navigation Docs](https://reactnavigation.org/docs/getting-started)
-   [React Native Navigation (alternative)](https://wix.github.io/react-native-navigation/)
-   [Fullstack React Native: Navigation](https://www.fullstackreact.com/react-native/navigation/)

---

### 6. What is the difference between synchronous and asynchronous operations in React Native? [Easy]

**Sample Answer**:

-   **Synchronous operations** block the JavaScript thread, causing UI freezes and poor user experience. Examples: heavy computations, blocking loops.
-   **Asynchronous operations** (e.g., network requests, timers) run in the background, allowing the UI to remain responsive. Use `async/await`, Promises, or callbacks for async code.

**Best Practices:**

-   Offload heavy work to native modules or background threads
-   Use async APIs for I/O and network

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [React Native Docs: Performance](https://reactnative.dev/docs/performance)
-   [React Native Performance Tips](https://blog.logrocket.com/react-native-performance/)

---

### 7. Explain the concept of state management in React Native apps. [Easy]

**Sample Answer**:
State management in React Native can be handled in several ways:

-   **Local state**: Managed with `useState` or class component state, suitable for component-specific data.
-   **Context API**: For simple global state (themes, user info).
-   **Redux**: For complex, app-wide state, providing predictable state updates and middleware support.

**Best Practices:**

-   Use local state for UI and simple data
-   Use Context or Redux for global/shared state
-   Avoid unnecessary re-renders by structuring state carefully

**Connected Questions**: [#6](#6)

**Further Reading**:

-   [React Native Docs: State](https://reactnative.dev/docs/state)
-   [Redux Docs: Introduction](https://redux.js.org/introduction/getting-started)
-   [React Context API](https://react.dev/learn/passing-data-deeply-with-context)

---

### 8. What are React Native performance optimization techniques? [Easy]

**Sample Answer**:

-   Use **FlatList** for large lists (virtualization)
-   Memoize expensive components with `React.memo`
-   Optimize images (resize, compress, use `Image` component's caching)
-   Reduce bundle size (code splitting, lazy loading)
-   Enable Hermes engine for faster JS execution
-   Profile with Flipper or React DevTools

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [React Native Docs: Performance](https://reactnative.dev/docs/performance)
-   [React Native Performance Tips](https://blog.logrocket.com/react-native-performance/)
-   [Flipper: Debugging React Native](https://fbflipper.com/docs/features/react-native/)

---

### 9. Explain the concept of platform-specific code in React Native. [Easy]

**Sample Answer**:
React Native allows writing platform-specific code using:

-   `Platform.OS` to detect the platform (`ios` or `android`)
-   Platform-specific file extensions (`.ios.js`, `.android.js`)
-   Conditional rendering for UI differences

**Best Practices:**

-   Use platform-specific code only when necessary
-   Follow platform conventions for UI/UX

**Connected Questions**: [#1](#1)

**Further Reading**:

-   [React Native Docs: Platform-specific code](https://reactnative.dev/docs/platform-specific-code)
-   [React Native Docs: Platform module](https://reactnative.dev/docs/platform)

---

### 10. What is the difference between development and production builds in React Native? [Easy]

**Sample Answer**:

-   **Development builds** include debugging tools, hot reloading, and are not optimized for performance. They are larger and slower, but easier to debug.
-   **Production builds** are optimized for performance, smaller in size, and do not include debugging tools. Enable Hermes for better performance.

**Best Practices:**

-   Test on both debug and release builds
-   Use different bundle configurations for environments

**Connected Questions**: [#2](#2)

**Further Reading**:

-   [React Native Docs: Running on Device](https://reactnative.dev/docs/running-on-device)
-   [React Native Docs: Hermes](https://reactnative.dev/docs/hermes)
-   [React Native CLI Environment Setup](https://reactnative.dev/docs/environment-setup)

### 11. What is the difference between React Native and native app development? [Easy]

**Sample Answer**:
React Native allows you to build mobile apps using JavaScript and React, sharing code across iOS and Android. Native development uses platform-specific languages (Swift, Kotlin). React Native offers faster development and code reuse, but may have performance trade-offs for complex features.

**Connected Questions**: [#1](#1)

**Further Reading**:

-   [React Native Docs: Introduction](https://reactnative.dev/docs/getting-started)
-   [Medium: React Native vs Native](https://medium.com/react-native-training/react-native-vs-native-app-development-4e3b3b3b3b3b)

---

### 12. How does navigation work in React Native? [Easy]

**Sample Answer**:
Navigation in React Native is typically handled by libraries like React Navigation, which provides stack, tab, and drawer navigators. These allow users to move between screens and manage navigation history in a mobile-friendly way.

**Connected Questions**: [#3](#3)

**Further Reading**:

-   [React Navigation Docs](https://reactnavigation.org/docs/getting-started)
-   [React Native Docs: Navigation](https://reactnative.dev/docs/navigation)

---

### 13. What is the role of the Metro bundler in React Native? [Easy]

**Sample Answer**:
Metro is the JavaScript bundler for React Native. It transforms and bundles JavaScript code for the app, supports hot reloading, and optimizes assets for mobile devices.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [React Native Docs: Metro](https://reactnative.dev/docs/metro)
-   [Metro Bundler Docs](https://facebook.github.io/metro/)

---

### 14. How do you handle images and assets in React Native? [Easy]

**Sample Answer**:
Images and assets are handled using the `require` function for local files or by providing a URI for remote images. React Native optimizes images for different device resolutions and platforms.

**Connected Questions**: [#7](#7)

**Further Reading**:

-   [React Native Docs: Images](https://reactnative.dev/docs/images)
-   [React Native Docs: Assets](https://reactnative.dev/docs/assets)

---

### 15. What is the difference between controlled and uncontrolled components in React Native? [Easy]

**Sample Answer**:
Controlled components have their state managed by React, while uncontrolled components use refs to access values directly. Controlled components are preferred for complex forms and validation.

**Connected Questions**: [#6](#6)

**Further Reading**:

-   [React Native Docs: TextInput](https://reactnative.dev/docs/textinput)
-   [React Docs: Controlled vs Uncontrolled](https://react.dev/learn/sharing-state-between-components#controlled-and-uncontrolled-components)

---

### 16. How do you handle device permissions in React Native? [Easy]

**Sample Answer**:
Device permissions (camera, location, etc.) are managed using native modules or libraries like `react-native-permissions`. You must request and check permissions at runtime, handling user responses appropriately for both iOS and Android.

**Connected Questions**: [#8](#8)

**Further Reading**:

-   [React Native Permissions](https://github.com/zoontek/react-native-permissions)
-   [React Native Docs: PermissionsAndroid](https://reactnative.dev/docs/permissionsandroid)

---

### 17. What is the difference between ScrollView and FlatList? [Easy]

**Sample Answer**:
`ScrollView` renders all its children at once, suitable for small lists. `FlatList` only renders visible items, improving performance for large lists through virtualization.

**Connected Questions**: [#9](#9)

**Further Reading**:

-   [React Native Docs: FlatList](https://reactnative.dev/docs/flatlist)
-   [React Native Docs: ScrollView](https://reactnative.dev/docs/scrollview)

---

### 18. How do you handle push notifications in React Native? [Easy]

**Sample Answer**:
Push notifications are handled using services like Firebase Cloud Messaging (FCM) for Android and Apple Push Notification Service (APNs) for iOS. Libraries like `react-native-push-notification` help integrate these services and manage notification handling in the app.

**Connected Questions**: [#16](#16)

**Further Reading**:

-   [React Native Push Notification](https://github.com/zoontek/react-native-push-notification)
-   [Firebase Docs: FCM](https://firebase.google.com/docs/cloud-messaging)

---

### 19. How do you optimize performance in a React Native app? [Easy]

**Sample Answer**:
Optimize performance by using FlatList for large lists, minimizing re-renders, using the `useMemo` and `useCallback` hooks, and profiling with tools like Flipper. Avoid memory leaks by cleaning up listeners and timers.

**Connected Questions**: [#17](#17)

**Further Reading**:

-   [React Native Docs: Performance](https://reactnative.dev/docs/performance)
-   [Flipper Docs](https://fbflipper.com/docs/features/react-native/)

---

### 20. How do you debug a React Native app? [Easy]

**Sample Answer**:
Debugging can be done using Flipper, Chrome DevTools, and built-in logging. Flipper provides advanced tools for inspecting app state, network requests, and performance.

**Connected Questions**: [#13](#13)

**Further Reading**:

-   [React Native Docs: Debugging](https://reactnative.dev/docs/debugging)
-   [Flipper Docs](https://fbflipper.com/docs/features/react-native/)
