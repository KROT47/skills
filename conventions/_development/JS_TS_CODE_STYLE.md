# JS TS CODE STYLE

### 1. References and variables

- **Declarations:** Default to `const`; use `let` for reassignment and avoid `var`.
- **Grouping:** Keep `const` declarations together, followed by `let` declarations.
- **Naming:** Use camelCase for objects, functions and instances, PascalCase for classes and constructors, and `SCREAMING_SNAKE_CASE` for exported constants. Always use PascalCase for React components.

### 2. Objects and arrays

- **Shorthand:** Prefer shorthand properties and methods.
- **Keys:** Quote property names only when required by syntax.
- **Copies:** Use spread to create shallow copies of objects and arrays.
- **Iterables:** Convert iterables with `Array.from()`.
- **Trailing commas:** Include trailing commas in multiline object and array literals.

### 3. Destructuring

- **Objects:** Prefer destructuring when reading multiple properties.
- **Arrays:** Use array destructuring.
- **Returns:** Return named properties in an object rather than positional array entries for multiple values.

### 4. Strings

- **Quotes:** Use single-quoted strings.
- **Interpolation:** Use template literals for programmatic strings instead of concatenation.

### 5. Functions and arrow functions

- **Declarations:** Prefer `function` declarations for module-level functions.
- **Local helpers:** Prefer arrow functions for local helper functions.
- **Parameters:** Prefer destructuring parameters in function signatures. Use default parameters rather than mutating arguments.
- **Arguments:** Use rest parameters rather than `arguments`.
- **Callbacks:** Use arrow functions for anonymous callbacks; use concise bodies for single-expression returns.
- **Binding:** Arrow functions capture `this` lexically.

### 6. Modules

- **Syntax:** Use ES module imports and exports rather than CommonJS.
- **Imports:** Avoid wildcard imports.
- **Exports:** Prefer a default export for a single-export file and named exports for utilities.

### 7. Classes

- **Syntax:** Use `class` rather than directly manipulating prototypes.
- **Inheritance:** Use `extends`.
- **Methods:** Return `this` when enabling chaining; keep custom `toString()` methods safe and side-effect free.

### 8. Iteration and control flow

- **Iteration:** Prefer array methods such as `map`, `filter`, `reduce`, `some`, and `every` over `for...in` and `for...of`.
- **Equality:** Use strict equality and inequality.
- **Coercion:** Check for unintended implicit type coercion.
- **Blocks:** Use braces for control-flow blocks.
- **Booleans:** Prefer concise truthiness checks.
- **Nesting:** Prefer early returns to deep nesting.
