# CSS & HTML Interview Questions

---

## Questions

### 1. **Question**: Explain the difference between inline, block, and inline-block display properties.

**Difficulty**: Easy  
**Category**: CSS Layout  
**Key Concepts**: Box model, display properties, element behavior  
**Sample Answer**:

-   **Inline** elements do not start on a new line and only take up as much width as necessary. They ignore width and height properties, and padding/margin only applies horizontally. Examples: `<span>`, `<a>`, `<strong>`.
-   **Block** elements start on a new line and take up the full width available. They respect width, height, margin, and padding in all directions. Examples: `<div>`, `<p>`, `<h1>`.
-   **Inline-block** elements are like inline elements in that they do not start on a new line, but they respect width, height, margin, and padding in all directions. Useful for creating layouts where elements need to sit next to each other but still have box-like properties.

**Comparison:**

-   Use inline for text-level elements.
-   Use block for structural layout.
-   Use inline-block for horizontal layouts with box properties (e.g., navigation menus).

**Connected Questions**: [#2: What is the CSS box model and how does it work?], [#3: Explain the difference between relative, absolute, fixed, and sticky positioning.]

**Further Reading**:

-   [MDN: display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
-   [CSS Tricks: Inline vs Block](https://css-tricks.com/quick-css-trick-how-to-center-an-object-exactly-in-the-center/)
-   [HTML & CSS: Design and Build Websites by Jon Duckett](https://www.htmlandcssbook.com/)

---

### 2. **Question**: What is the CSS box model and how does it work?

**Difficulty**: Easy  
**Category**: CSS Fundamentals  
**Key Concepts**: Content, padding, border, margin, box-sizing  
**Sample Answer**:
The **CSS box model** describes how the size of elements is calculated and how they are rendered on the page. Every element is a rectangular box consisting of:

-   **Content**: The actual content (text, image, etc.)
-   **Padding**: Space between the content and the border
-   **Border**: Surrounds the padding (if any) and content
-   **Margin**: Space outside the border, separating the element from others

The `box-sizing` property determines how width and height are calculated:

-   `content-box` (default): width/height apply to content only; padding and border are added outside.
-   `border-box`: width/height include content, padding, and border.

**Connected Questions**: [#1: Explain the difference between inline, block, and inline-block display properties.], [#5: Explain the concept of CSS specificity and how it works.]

**Further Reading**:

-   [MDN: Box Model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
-   [CSS Tricks: Box Sizing](https://css-tricks.com/box-sizing/)
-   [HTML & CSS: Design and Build Websites by Jon Duckett](https://www.htmlandcssbook.com/)

---

### 3. **Question**: Explain the difference between relative, absolute, fixed, and sticky positioning.

**Difficulty**: Medium  
**Category**: CSS Positioning  
**Key Concepts**: Position property, containing blocks, stacking context  
**Sample Answer**:

-   **Relative**: The element is positioned relative to its normal position. Offsets (`top`, `left`, etc.) move it from where it would normally be.
-   **Absolute**: The element is removed from the normal flow and positioned relative to the nearest positioned ancestor (not static). If none, it's relative to the `<html>` element.
-   **Fixed**: The element is removed from the flow and positioned relative to the viewport. It stays in place when scrolling.
-   **Sticky**: The element toggles between relative and fixed, depending on the scroll position. It acts as relative until a threshold is met, then becomes fixed.

**Use Cases:**

-   Relative: Fine-tuning position without breaking flow.
-   Absolute: Tooltips, dropdowns, modals.
-   Fixed: Navigation bars, floating buttons.
-   Sticky: Headers that stay at the top while scrolling.

**Connected Questions**: [#1: Explain the difference between inline, block, and inline-block display properties.], [#4: What are CSS Grid and Flexbox, and when would you use each?]

**Further Reading**:

-   [MDN: position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
-   [CSS Tricks: Positioning](https://css-tricks.com/absolute-relative-fixed-positioining-how-do-they-differ/)
-   [HTML & CSS: Design and Build Websites by Jon Duckett](https://www.htmlandcssbook.com/)

---

### 4. **Question**: What are CSS Grid and Flexbox, and when would you use each?

**Difficulty**: Medium  
**Category**: CSS Layout  
**Key Concepts**: Grid layout, flexbox, responsive design  
**Sample Answer**:

-   **Flexbox** is a one-dimensional layout system for arranging items in a row or column. It excels at distributing space and aligning items within a container, making it ideal for navigation bars, toolbars, and form layouts.
-   **CSS Grid** is a two-dimensional layout system for arranging items in rows and columns. It is best for complex layouts like page grids, card layouts, and dashboards.

**Comparison:**

-   Use Flexbox for linear layouts (one row or column).
-   Use Grid for complex, two-dimensional layouts.
-   Both support responsive design and can be combined.

**Connected Questions**: [#3: Explain the difference between relative, absolute, fixed, and sticky positioning.], [#10: What is responsive design and how do you implement it?]

**Further Reading**:

-   [MDN: Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
-   [MDN: CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
-   [CSS Grid Garden Game](https://cssgridgarden.com/)
-   [CSS Flexbox Froggy Game](https://flexboxfroggy.com/)

---

### 5. **Question**: Explain the concept of CSS specificity and how it works.

**Difficulty**: Medium  
**Category**: CSS Fundamentals  
**Key Concepts**: Selector specificity, cascade, inheritance  
**Sample Answer**:
**CSS specificity** determines which CSS rule is applied when multiple rules could apply to the same element. Specificity is calculated based on the types of selectors used:

-   Inline styles: highest specificity
-   IDs: more specific than classes
-   Classes, attributes, pseudo-classes: more specific than elements
-   Elements and pseudo-elements: lowest specificity

The browser uses the most specific rule. If specificity is equal, the last rule in the CSS is applied. The `!important` flag overrides normal specificity but should be avoided as it breaks the cascade.

**Connected Questions**: [#2: What is the CSS box model and how does it work?], [#7: Explain CSS preprocessors and their benefits.]

**Further Reading**:

-   [MDN: Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
-   [CSS Tricks: Specificity](https://css-tricks.com/specifics-on-css-specificity/)
-   [HTML & CSS: Design and Build Websites by Jon Duckett](https://www.htmlandcssbook.com/)

---

### 6. **Question**: What are semantic HTML elements and why are they important?

**Difficulty**: Easy  
**Category**: HTML Fundamentals  
**Key Concepts**: Semantic markup, accessibility, SEO  
**Sample Answer**:
**Semantic HTML** uses elements that convey meaning about the structure and content of a web page (e.g., `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`). These elements help browsers, search engines, and assistive technologies understand the content, improving accessibility and SEO.

-   Semantic elements make code more readable and maintainable.
-   They improve accessibility for screen readers.
-   They help search engines better index and rank content.

**Connected Questions**: [#10: What is responsive design and how do you implement it?]

**Further Reading**:

-   [MDN: Semantics](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
-   [WebAIM: Semantic Structure](https://webaim.org/techniques/semanticstructure/)
-   [HTML & CSS: Design and Build Websites by Jon Duckett](https://www.htmlandcssbook.com/)

---

### 7. **Question**: Explain CSS preprocessors and their benefits.

**Difficulty**: Medium  
**Category**: CSS Tools  
**Key Concepts**: Sass, Less, variables, mixins, nesting  
**Sample Answer**:
**CSS preprocessors** like Sass and Less extend CSS with features such as variables, nesting, mixins, and functions. They allow for more maintainable, reusable, and organized code. Preprocessors are compiled into standard CSS for browsers.

**Benefits:**

-   Variables for consistent values (colors, spacing)
-   Mixins for reusable code blocks
-   Nesting for clearer structure
-   Functions and operations for dynamic styles

**Connected Questions**: [#5: Explain the concept of CSS specificity and how it works.]

**Further Reading**:

-   [Sass Official Guide](https://sass-lang.com/guide)
-   [Less Documentation](https://lesscss.org/)
-   [MDN: CSS preprocessors](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor)

---

### 8. **Question**: What is the difference between localStorage and sessionStorage?

**Difficulty**: Medium  
**Category**: Web Storage  
**Key Concepts**: Browser storage, persistence, scope  
**Sample Answer**:

-   **localStorage** stores data with no expiration date. Data persists even after the browser is closed and reopened. Shared across tabs/windows from the same origin.
-   **sessionStorage** stores data for the duration of the page session. Data is cleared when the tab or window is closed. Not shared across tabs/windows.

Both store key-value pairs as strings and are limited in size (usually 5-10MB). They are useful for storing user preferences, temporary data, or caching.

**Connected Questions**: [#10: What is responsive design and how do you implement it?]

**Further Reading**:

-   [MDN: Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
-   [HTML5 Rocks: localStorage and sessionStorage](http://www.html5rocks.com/en/tutorials/storage/intro/)

---

### 9. **Question**: Explain CSS animations and transitions. What's the difference?

**Difficulty**: Medium  
**Category**: CSS Animations  
**Key Concepts**: Transitions, keyframes, performance, GPU acceleration  
**Sample Answer**:

-   **Transitions** allow property changes in CSS values to occur smoothly over a specified duration. They are triggered by events like hover or focus.
-   **Animations** use keyframes to define a sequence of style changes. They can run automatically, loop, or be triggered by events.

**Differences:**

-   Transitions are for simple, state-based changes.
-   Animations are for complex, multi-step sequences.
-   Both can be hardware-accelerated for better performance.

**Connected Questions**: [#4: What are CSS Grid and Flexbox, and when would you use each?]

**Further Reading**:

-   [MDN: CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
-   [MDN: CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
-   [CSS Tricks: Animations vs Transitions](https://css-tricks.com/transitions-vs-animations/)

---

### 10. **Question**: What is responsive design and how do you implement it?

**Difficulty**: Medium  
**Category**: Responsive Design  
**Key Concepts**: Media queries, mobile-first, viewport, flexible layouts  
**Sample Answer**:
**Responsive design** ensures that web pages look and function well on all devices and screen sizes. Key techniques include:

-   **Media queries**: Apply styles based on device characteristics (width, orientation, etc.)
-   **Flexible layouts**: Use relative units (%, em, rem) instead of fixed pixels
-   **Mobile-first**: Design for small screens first, then scale up
-   **Flexible images**: Use `max-width: 100%` to make images scale

Test responsiveness using browser dev tools and real devices.

**Connected Questions**: [#4: What are CSS Grid and Flexbox, and when would you use each?], [#6: What are semantic HTML elements and why are they important?]

**Further Reading**:

-   [MDN: Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
-   [Responsive Web Design by Ethan Marcotte](https://abookapart.com/products/responsive-web-design)
-   [Google Web Fundamentals: Responsive Web Design Basics](https://web.dev/responsive-web-design-basics/)
