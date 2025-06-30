# JavaScript Interview Questions

---

## Questions

### 1. **Question**: Explain the difference between `var`, `let`, and `const` in JavaScript.

**Difficulty**: Easy  
**Category**: Variable Declaration  
**Key Concepts**: Hoisting, scope, temporal dead zone, reassignment  
**Sample Answer**:

-   `var` is function-scoped and is hoisted to the top of its function. It can be re-declared and updated. Hoisting means the declaration is moved to the top, but not the assignment.
-   `let` is block-scoped (limited to the nearest `{}`) and is not accessible before its declaration due to the temporal dead zone. It can be updated but not re-declared in the same scope.
-   `const` is also block-scoped and must be assigned a value at declaration. It cannot be re-assigned, but if the value is an object or array, its contents can be mutated.

**Best Practices:**

-   Use `const` by default for variables that won't be reassigned.
-   Use `let` for variables that will be reassigned.
-   Avoid `var` in modern code.

**Connected Questions**: [#7: Explain the difference between `null` and `undefined` in JavaScript.], [#2: What is closure in JavaScript and how does it work?]

**Further Reading**:

-   [MDN: var, let, const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)
-   [JavaScript: The Definitive Guide by David Flanagan](https://www.oreilly.com/library/view/javascript-the-definitive/9781491952023/)
-   [You Don't Know JS Yet (book series)](https://github.com/getify/You-Dont-Know-JS)

---

### 2. **Question**: What is closure in JavaScript and how does it work?

**Difficulty**: Medium  
**Category**: Functions  
**Key Concepts**: Lexical scope, function scope, memory management  
**Sample Answer**:
A **closure** is a function that "remembers" the environment in which it was created. This means it has access to variables from its containing (outer) function, even after that function has finished executing. Closures are created every time a function is created, at function creation time.

**Use Cases:**

-   Creating private variables
-   Implementing factory functions
-   Event handlers and callbacks

**Example:**

```js
function makeCounter() {
    let count = 0;
    return function () {
        return ++count;
    };
}
const counter = makeCounter();
counter(); // 1
counter(); // 2
```

**Connected Questions**: [#1: Explain the difference between `var`, `let`, and `const` in JavaScript.], [#5: Explain the concept of `this` in JavaScript and how it's determined.]

**Further Reading**:

-   [MDN: Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
-   [JavaScript: The Good Parts by Douglas Crockford](https://www.oreilly.com/library/view/javascript-the-good/9780596517748/)
-   [You Don't Know JS: Scope & Closures](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/scope-closures)

---

### 3. **Question**: Explain the difference between `==` and `===` operators.

**Difficulty**: Easy  
**Category**: Operators  
**Key Concepts**: Type coercion, strict equality, loose equality  
**Sample Answer**:

-   `==` is the loose equality operator. It compares two values for equality after converting both values to a common type (type coercion). This can lead to unexpected results (e.g., `0 == '0'` is `true`).
-   `===` is the strict equality operator. It compares both value and type, so no type conversion occurs (e.g., `0 === '0'` is `false`).

**Best Practices:**

-   Always use `===` for predictable, bug-free code.
-   Use `==` only when you explicitly want type coercion and understand the rules.

**Connected Questions**: [#7: Explain the difference between `null` and `undefined` in JavaScript.]

**Further Reading**:

-   [MDN: Equality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
-   [You Don't Know JS: Types & Grammar](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/types-grammar)

---

### 4. **Question**: What are Promises and how do they work?

**Difficulty**: Medium  
**Category**: Asynchronous Programming  
**Key Concepts**: Promise states, then/catch, async/await, error handling  
**Sample Answer**:
A **Promise** is an object representing the eventual completion or failure of an asynchronous operation. Promises have three states: pending, fulfilled, and rejected. They allow chaining of asynchronous operations using `.then()` and `.catch()`, and can be used with `async/await` for more readable code.

**Example:**

```js
fetch('https://api.example.com/data')
    .then((response) => response.json())
    .then((data) => console.log(data))
    .catch((error) => console.error(error));
```

**Best Practices:**

-   Use `Promise.all` for parallel async operations.
-   Use `async/await` for cleaner syntax.
-   Always handle errors with `.catch()` or try/catch.

**Connected Questions**: [#10: What is the event loop in JavaScript and how does it work?], [#6: What is event delegation and why is it useful?]

**Further Reading**:

-   [MDN: Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
-   [JavaScript.info: Promises, async/await](https://javascript.info/async)
-   [You Don't Know JS: Async & Performance](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/async-performance)

---

### 5. **Question**: Explain the concept of `this` in JavaScript and how it's determined.

**Difficulty**: Hard  
**Category**: Context  
**Key Concepts**: Execution context, binding, arrow functions, call/apply/bind  
**Sample Answer**:
`this` refers to the execution context of a function. Its value depends on how the function is called:

-   **Global context**: In browsers, `this` is the global object (`window`).
-   **Object method**: `this` refers to the object before the dot.
-   **Constructor function**: `this` refers to the new instance.
-   **Event handler**: `this` refers to the element receiving the event.
-   **Arrow functions**: `this` is lexically inherited from the enclosing scope.

**Changing `this`:** Use `call`, `apply`, or `bind` to set `this` explicitly.

**Connected Questions**: [#2: What is closure in JavaScript and how does it work?], [#9: Explain the concept of prototypal inheritance in JavaScript.]

**Further Reading**:

-   [MDN: this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
-   [You Don't Know JS: this & Object Prototypes](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/this-object-prototypes)

---

### 6. **Question**: What is event delegation and why is it useful?

**Difficulty**: Medium  
**Category**: DOM Manipulation  
**Key Concepts**: Event bubbling, event capturing, performance optimization  
**Sample Answer**:
**Event delegation** is a technique where a single event listener is added to a parent element to manage events for multiple child elements. It leverages event bubbling, where events propagate up the DOM tree. This reduces the number of event listeners, improves performance, and allows handling of dynamically added elements.

**Example:**

```js
document.getElementById('list').addEventListener('click', function (e) {
    if (e.target.tagName === 'LI') {
        alert('Item clicked: ' + e.target.textContent);
    }
});
```

**Connected Questions**: [#4: What are Promises and how do they work?], [#10: What is the event loop in JavaScript and how does it work?]

**Further Reading**:

-   [MDN: Event delegation](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_delegation)
-   [JavaScript.info: Event delegation](https://javascript.info/event-delegation)

---

### 7. **Question**: Explain the difference between `null` and `undefined` in JavaScript.

**Difficulty**: Easy  
**Category**: Data Types  
**Key Concepts**: Primitive types, type checking, intentional vs unintentional absence  
**Sample Answer**:

-   `undefined` means a variable has been declared but not assigned a value, or a function does not return a value.
-   `null` is an assignment value that represents "no value" or "empty value". It is intentionally set by the programmer.
-   `typeof null` returns "object" (a historical bug), while `typeof undefined` returns "undefined".

**Best Practices:**

-   Use `null` for intentional absence of value.
-   Use `undefined` for uninitialized variables.

**Connected Questions**: [#1: Explain the difference between `var`, `let`, and `const` in JavaScript.], [#3: Explain the difference between `==` and `===` operators.]

**Further Reading**:

-   [MDN: null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null)
-   [MDN: undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)
-   [You Don't Know JS: Types & Grammar](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/types-grammar)

---

### 8. **Question**: What are ES6 modules and how do they differ from CommonJS?

**Difficulty**: Medium  
**Category**: Modules  
**Key Concepts**: Import/export, static analysis, tree shaking, circular dependencies  
**Sample Answer**:
**ES6 modules** use `import` and `export` syntax and are statically analyzable, enabling features like tree shaking (removing unused code). They are loaded asynchronously and support both named and default exports. **CommonJS** (used in Node.js) uses `require` and `module.exports`, is loaded synchronously, and does not support tree shaking.

**Comparison:**

-   Use ES6 modules for modern JavaScript projects and when targeting browsers.
-   Use CommonJS for Node.js projects or legacy code.

**Connected Questions**: [#9: Explain the concept of prototypal inheritance in JavaScript.]

**Further Reading**:

-   [MDN: ES6 modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
-   [Node.js: Modules](https://nodejs.org/api/modules.html)
-   [JavaScript.info: Modules](https://javascript.info/modules)

---

### 9. **Question**: Explain the concept of prototypal inheritance in JavaScript.

**Difficulty**: Hard  
**Category**: Object-Oriented Programming  
**Key Concepts**: Prototype chain, Object.create, constructor functions, classes  
**Sample Answer**:
**Prototypal inheritance** means objects inherit properties and methods from other objects via the prototype chain. Every object has an internal `[[Prototype]]` property, accessible via `__proto__` or `Object.getPrototypeOf`. Functions have a `prototype` property used when creating new objects with `new`.

**Modern JavaScript** uses `class` syntax as syntactic sugar over prototypal inheritance.

**Example:**

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.speak = function () {
    return this.name + ' makes a noise.';
};
const dog = new Animal('Rex');
dog.speak(); // 'Rex makes a noise.'
```

**Connected Questions**: [#5: Explain the concept of `this` in JavaScript and how it's determined.], [#8: What are ES6 modules and how do they differ from CommonJS?]

**Further Reading**:

-   [MDN: Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
-   [You Don't Know JS: this & Object Prototypes](https://github.com/getify/You-Dont-Know-JS/tree/2nd-ed/this-object-prototypes)

---

### 10. **Question**: What is the event loop in JavaScript and how does it work?

**Difficulty**: Hard  
**Category**: Runtime  
**Key Concepts**: Call stack, callback queue, microtasks, macrotasks, non-blocking I/O  
**Sample Answer**:
The **event loop** is the mechanism that allows JavaScript to perform non-blocking operations despite being single-threaded. It works by:

-   Executing code on the call stack
-   Moving asynchronous callbacks (from Promises, timers, etc.) to the callback queue
-   Processing microtasks (Promises) before macrotasks (setTimeout, I/O)
-   Continuously checking the call stack and callback queue, executing tasks as the stack becomes empty

**Best Practices:**

-   Use Promises and async/await for readable async code
-   Avoid blocking the event loop with heavy computations

**Connected Questions**: [#4: What are Promises and how do they work?], [#6: What is event delegation and why is it useful?]

**Further Reading**:

-   [MDN: Event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)
-   [Philip Roberts: What the heck is the event loop anyway? (video)](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
-   [JavaScript.info: Event loop](https://javascript.info/event-loop)
