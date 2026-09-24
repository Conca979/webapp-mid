# Web Application Development — Lecture 03: JavaScript
**University of Science and Technology of Hanoi (USTH)**  
**Information and Communication Technology Laboratory (ICTLab)**  
**Lecturers:** KIEU Quoc Viet, HUYNH Vinh Nam  
**Audience:** Web Application Development Students (Midterm Exam Preparation)

---

## Master Table of Contents
1. [Course Orientation & Syllabus Context](#course-orientation--syllabus-context)
2. [Section 1: Setup (Slides 4–8)](#section-1-setup-slides-48)
   - [Slide 4: Section 1 — Setup](#slide-4-section-1--setup)
   - [Slide 5: Before You Write Any Code (Files, `defer`, and Live Server)](#slide-5-before-you-write-any-code-files-defer-and-live-server)
   - [Slide 6: The Standard Page (HTML Skeleton & Three Rules)](#slide-6-the-standard-page-html-skeleton--three-rules)
   - [Slide 7: Two Places to Run JavaScript (Console vs. `app.js`)](#slide-7-two-places-to-run-javascript-console-vs-appjs)
   - [Slide 8: When It Breaks (Error Types & Troubleshooting)](#slide-8-when-it-breaks-error-types--troubleshooting)
3. [Section 2: Modern JavaScript (ES6+) (Slides 9–21)](#section-2-modern-javascript-es6-slides-921)
   - [Slide 9: Section 2 — Modern JavaScript](#slide-9-section-2--modern-javascript)
   - [Slide 10: What JavaScript Is (History, Engine & ECMAScript)](#slide-10-what-javascript-is-history-engine--ecmascript)
   - [Slide 11: The Three Languages of the Front-End (Structure, Style, Behavior)](#slide-11-the-three-languages-of-the-front-end-structure-style-behavior)
   - [Slide 12: What Carries Over From Your First Course (C/Python to JS)](#slide-12-what-carries-over-from-your-first-course-cpython-to-js)
   - [Slide 13: Variables and Types (`const`, `let`, Scopes, Primitives)](#slide-13-variables-and-types-const-let-scopes-primitives)
   - [Slide 14: Example: Variables and Types (Code & Console Analysis)](#slide-14-example-variables-and-types-code--console-analysis)
   - [Slide 15: Strings and Operators (Quotes, Backticks, `===` vs. `==`)](#slide-15-strings-and-operators-quotes-backticks--vs-)
   - [Slide 16: Example: Template Literals](#slide-16-example-template-literals)
   - [Slide 17: Example: Operators and Strict Equality](#slide-17-example-operators-and-strict-equality)
   - [Slide 18: Making Decisions and Repeating (The 9 Falsy Values & Loops)](#slide-18-making-decisions-and-repeating-the-9-falsy-values--loops)
   - [Slide 19: Example: `if / else` and the Ternary Operator](#slide-19-example-if--else-and-the-ternary-operator)
   - [Slide 20: Example: `switch` and Fallthrough](#slide-20-example-switch-and-fallthrough)
   - [Slide 21: Example: 3 Kinds of Loops (`for`, `for...of`, `while`)](#slide-21-example-3-kinds-of-loops-for-forof-while)
4. [Section 3: Functions and Objects (Slides 22–29)](#section-3-functions-and-objects-slides-2229)
   - [Slide 22: Section 3 — Functions and Objects](#slide-22-section-3--functions-and-objects)
   - [Slide 23: Functions (Parameters, Return, Arrow Functions)](#slide-23-functions-parameters-return-arrow-functions)
   - [Slide 24: Example: Functions](#slide-24-example-functions)
   - [Slide 25: Example: Arrow Functions](#slide-25-example-arrow-functions)
   - [Slide 26: Objects and Arrays (Destructuring, Spread, Higher-Order Methods)](#slide-26-objects-and-arrays-destructuring-spread-higher-order-methods)
   - [Slide 27: Example: Objects & Mutability](#slide-27-example-objects--mutability)
   - [Slide 28: Example: Destructuring and Spread](#slide-28-example-destructuring-and-spread)
   - [Slide 29: Example: Array Methods (`map`, `filter`, `reduce`)](#slide-29-example-array-methods-map-filter-reduce)
5. [Section 4: The DOM and Events (Slides 30–37)](#section-4-the-dom-and-events-slides-3037)
   - [Slide 30: Section 4 — The DOM and Events](#slide-30-section-4--the-dom-and-events)
   - [Slide 31: The DOM: The Page as a Tree](#slide-31-the-dom-the-page-as-a-tree)
   - [Slide 32: Finding and Changing Elements (API Overview & Security)](#slide-32-finding-and-changing-elements-api-overview--security)
   - [Slide 33: Example: Selecting Elements](#slide-33-example-selecting-elements)
   - [Slide 34: Example: Changing the Page (DOM Mutation)](#slide-34-example-changing-the-page-dom-mutation)
   - [Slide 35: Events and Forms (`addEventListener`, `preventDefault`)](#slide-35-events-and-forms-addeventlistener-preventdefault)
   - [Slide 36: Example: Events (Click & Live Input)](#slide-36-example-events-click--live-input)
   - [Slide 37: Example: Forms and Validation](#slide-37-example-forms-and-validation)
6. [Section 5: Asynchronous JavaScript (Slides 38–50)](#section-5-asynchronous-javascript-slides-3850)
   - [Slide 38: Section 5 — Asynchronous JS](#slide-38-section-5--asynchronous-js)
   - [Slide 39: Why Asynchronous? (Single-Threaded Model & Pho Shop Analogy)](#slide-39-why-asynchronous-single-threaded-model--pho-shop-analogy)
   - [Slide 40: The `menu.json` File (JSON Syntax Rules)](#slide-40-the-menujson-file-json-syntax-rules)
   - [Slide 41: CORS: Why the Browser Blocks a Fetch](#slide-41-cors-why-the-browser-blocks-a-fetch)
   - [Slide 42: Promises and `async / await`](#slide-42-promises-and-async--await)
   - [Slide 43: Example: Promises with `.then()`](#slide-43-example-promises-with-then)
   - [Slide 44: Example: `async / await`](#slide-44-example-async--await)
   - [Slide 45: Fetch and Error Handling (The `res.ok` Trap)](#slide-45-fetch-and-error-handling-the-resok-trap)
   - [Slide 46: Example: Checking `res.ok`](#slide-46-example-checking-resok)
   - [Slide 47: Example: Putting It Together (End-to-End Application)](#slide-47-example-putting-it-together-end-to-end-application)
   - [Slide 48: Summary of Lecture 03](#slide-48-summary-of-lecture-03)
   - [Slide 49 & 50: Practical Work 3: Make Pho Thin Come Alive (Full Solution)](#slide-49--50-practical-work-3-make-pho-thin-come-alive-full-solution)
   - [Slide 51: Conclusion](#slide-51-conclusion)
7. [Appendices (Slides 52–55)](#appendices-slides-5255)
   - [Slide 52: Appendix A: Reserved Keywords](#slide-52-appendix-a-reserved-keywords)
   - [Slide 53: Appendix B: Number Literals](#slide-53-appendix-b-number-literals)
   - [Slide 54: Appendix C: Strings and Escape Sequences](#slide-54-appendix-c-strings-and-escape-sequences)
   - [Slide 55: Appendix D: The Other Value Types (`typeof null` & `NaN`)](#slide-55-appendix-d-the-other-value-types-typeof-null--nan)
8. [Midterm Exam Master Review: Key Differences, Traps & Exam Questions](#midterm-exam-master-review-key-differences-traps--exam-questions)

---

# Course Orientation & Syllabus Context

### Slide 1: Title Slide
```text
JavaScript
Web Application Development
KIEU Quoc Viet      HUYNH Vinh Nam
Information and Communication Technology Laboratory (ICTLab),
University of Science and Technology of Hanoi
Hanoi, August 2026 | Lecture 03 | 1 / 55
```
- **Context**: Third lecture in the USTH Web Application Development sequence. It bridges static front-end documents with dynamic programmatic interactivity, setting the stage for Node.js back-ends and React front-ends.

---

### Slide 2: Course Syllabus
```text
Course Syllabus
Class 1: Introduction to Web Application Development (Why web apps, Client-server model, HTTP)
Class 2: HTML5 & CSS3 (Semantic structure, Box model, Flexbox & Grid, Responsive design)
Class 3: JavaScript (ES6+ syntax, functions, objects, DOM manipulation & events, Promise, async/await, Fetch API & error handling)
Class 4: Node.js Fundamentals (Runtime, modules, the event loop, npm, build tooling)
Class 5: Front-end Frameworks (Components, composition, props, state, hooks, routing, REST APIs)

"Class 2 gave you a static Pho Thin page. Today it reacts."
```
- **The Core Theme**: In Class 2, the "Pho Thin" restaurant page was purely static text and CSS styling. In Class 3, JavaScript transforms it into a living web application that calculates prices, validates inputs, responds to clicks, and fetches real data over the network.

---

### Slide 3: Table of Contents
```text
Table of Contents
1. Setup
2. Modern JavaScript (ES6+)
3. Functions and Objects
4. The DOM and Events
5. Asynchronous JavaScript
```

---

# Section 1: Setup (Slides 4–8)

---

### Slide 4: Section 1 — Setup
```text
1. Setup
```

---

### Slide 5: Before You Write Any Code

```text
Before You Write Any Code
• Nothing new to install - you already have a browser, VS Code and the Live Server extension from class 2
• Today's project is three files in one folder: index.html, app.js, menu.json
• The JavaScript lives in a separate .js file, never mixed into the HTML
• index.html loads it with <script src="app.js" defer> - defer makes the script run after the HTML is parsed, so the elements it looks for already exist
• Open the folder with Live Server, not by double-clicking the file. A page opened as file:// cannot fetch menu.json - the browser blocks it.
• Watch out: All three files go in the same folder. A wrong path is the number one reason "my code does nothing" on day one.
```

#### Line-by-Line Meaning & Midterm Traps
1. **Three-File Architecture**:
   - `index.html`: The structural markup skeleton.
   - `app.js`: The application logic and DOM manipulation script.
   - `menu.json`: The data source representing menu items sent from a server.
2. **Separation of Concerns**: Never write JavaScript inside HTML tags (e.g., inline `onclick="..."` or embedded `<script>code here</script>`). Keep scripts in dedicated `.js` files.
3. **The `defer` Attribute (Critical Exam Concept)**:
   - By default, `<script src="app.js">` blocks HTML parsing: the browser halts rendering, downloads the JS, and executes it immediately. If the script queries `<ul id="menu">` before the parser reaches line 10, `document.getElementById("menu")` returns `null`!
   - `defer` tells the browser: *"Download `app.js` in parallel in the background, but do NOT execute it until the entire HTML document has finished parsing into the DOM tree."*
4. **Why `file:///` Fails**:
   - Double-clicking `index.html` loads it under the `file:///` protocol. Under the browser security model, local files have an origin of `null`. The Fetch API blocks requests to local JSON files due to CORS (Cross-Origin Resource Sharing) security restrictions.
   - Running via **Live Server** serves files via HTTP (`http://127.0.0.1:5500`), providing a legitimate web origin.

---

### Slide 6: The Standard Page

```text
The Standard Page
```

#### HTML Skeleton (`index.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Pho Thin</title>
</head>
<body>
  <h1 id="heading">Pho Thin</h1>
  <ul id="menu">
    <li class="dish">Pho bo</li>
    <li class="dish">Pho ga</li>
    <li class="dish">Pho tai</li>
  </ul>
  <form id="signup">
    <input id="customer" placeholder="Your name">
    <button>Order</button>
  </form>
  <div id="out"></div>
  <script src="app.js" defer></script>
</body>
</html>
```

#### Three Working Rules for Today
```text
1. index.html is typed once and never changes
2. One snippet at a time - delete the old one first
3. Save, then reload the browser
```
- JavaScript modifies the live DOM in browser memory; you do not need to manually touch `index.html` to add items or alter text.

---

### Slide 7: Two Places to Run JavaScript

```text
Two Places to Run JavaScript
```

#### Detailed Comparison Table
| Feature / Dimension | The Browser Console | The File `app.js` |
| :--- | :--- | :--- |
| **How to Open** | Press `F12` (or Right-Click $\rightarrow$ Inspect), then open the **Console** tab | Open in **VS Code** |
| **Best Used For** | Scratchpad testing: trying one line of code, inspecting live variables, running ad-hoc queries | Writing the permanent, real codebase of your web application |
| **Survives a Page Reload (`F5`)?** | **No**. The console environment is wiped clean upon refresh | **Yes**. Saved to disk and reloaded by the browser |
| **Displays Output** | **REPL Mode**: Types the evaluation result back to you automatically | **Strict Mode**: Only displays output explicitly passed to `console.log(...)` |

#### Key Observation
```text
Typing 2 + 2 in the console prints 4 straight away.
The same line in app.js prints nothing - a file only shows what you ask it to show.
```
- In `app.js`, typing `2 + 2;` computes the sum in CPU registers and immediately discards it. To see output, you must write `console.log(2 + 2);`.

---

### Slide 8: When It Breaks

```text
When It Breaks
• A red line in the Console is JavaScript telling you exactly what went wrong - read it, do not guess
• Chrome prints the message, then the file and line number, like app.js:14. Click it and the editor jumps there
• After the first red error the rest of the file does not run. Fix the top one first
```

#### Error Diagnostics Table (High-Yield Exam Material!)
| Error Message in Console | What It Actually Means | How to Fix It |
| :--- | :--- | :--- |
| `Uncaught SyntaxError: Unexpected token` | JavaScript parser encountered an illegal character: a missing closing `)`, `}`, or `;`. | Check the indicated line, and **always inspect the line directly above it**! |
| `Uncaught ReferenceError: x is not defined` | The variable or function name `x` was never declared with `let`/`const`, or is a typo/misspelling. | Check spelling, casing (JS is case-sensitive), or variable declaration order. |
| `Cannot read properties of null` (or `undefined`) | You called `.textContent`, `.addEventListener`, or `.value` on an element that does not exist. | `querySelector` failed to find a match (bad selector), or the `<script>` ran before the HTML parsed (missing `defer`). |
| `Nothing at all appears` | Script did not run or produced no terminal output. | Verify script tag path `<script src="app.js">`, or confirm whether your code contains `console.log()`. |

> **Critical Rule**: When a runtime error occurs, the JavaScript thread **halts execution** at that exact line. Code below that error will never execute. Always debug the **first (topmost)** error in the console.

---

# Section 2: Modern JavaScript (ES6+) (Slides 9–21)

---

### Slide 9: Section 2 — Modern JavaScript
```text
2. Modern JavaScript
```

---

### Slide 10: What JavaScript Is

```text
What JavaScript Is
• The programming language of the web - it runs in every browser
• High-level and multi-paradigm: imperative, functional and object-oriented
• Dynamically typed and just-in-time compiled - fast, and nothing to compile before you run it
• No longer only in the browser: with Node.js the same language runs on servers, tools and desktop apps (class 4)
• JavaScript is the language; ECMAScript (ES) is the specification it follows
• ES6 (2015) was the turning point - let, const, arrow functions, classes, promises, modules
• Since then one small release every year - ES2016, ES2017, ... up to ES2026
• The name has nothing to do with Java - it was a 1995 marketing decision
```

#### Architectural Deconstruction
1. **Multi-Paradigm**: Supports imperative state changes, object-oriented programming with prototypes/classes, and functional programming with first-class functions (`map`, `filter`, `reduce`).
2. **Just-In-Time (JIT) Compilation**: Modern JavaScript engines (such as Google Chrome's **V8** or Mozilla's **SpiderMonkey**) compile JavaScript bytecode into native machine instructions at runtime on-the-fly.
3. **ECMAScript vs. JavaScript**: ECMAScript (standard ECMA-262) is the official specification. JavaScript is the concrete language implementing that specification.
4. **The ES6 (ECMAScript 2015) Milestone**: Modern JavaScript is universally split into "Pre-ES6" (legacy ES5) and "Post-ES6" (modern standards: `let`, `const`, template literals, arrow functions, destructuring, promises, ES modules).
5. **Java vs. JavaScript**: Brendan Eich originally created the language under the name *Mocha*, then *LiveScript*. Netscape rebranded it *JavaScript* in late 1995 to capitalize on the popularity of Sun Microsystems' Java. The two languages share zero lineage.

---

### Slide 11: The Three Languages of the Front-End

```text
The Three Languages of the Front-End
One page, three jobs:
  HTML          CSS              JavaScript
  structure     presentation     behaviour
  what is on    how it looks     what it does
  the page
```
- **HTML and CSS describe; only JavaScript can react and decide.**
- HTML and CSS are declarative markup languages; they cannot perform arithmetic, store variables, validate conditional logic, or communicate with external servers.
- JavaScript transforms a static, read-only document into an interactive software application.

---

### Slide 12: What Carries Over From Your First Course

```text
What Carries Over From Your First Course
```
| Programming Concept | Prior Knowledge (C / Python) | Modern JavaScript Implementation |
| :--- | :--- | :--- |
| **Variables** | Named storage location in memory | Declared with `let` (mutable) or `const` (immutable reference) |
| **Types** | Fixed, static at compile-time (C: `int x = 5;`) | **Dynamically typed**; evaluated at runtime |
| **Control Flow** | `if`, `else`, `while`, `for` | Identical syntax, plus modern `for...of` loops |
| **Functions** | Takes arguments, returns output | First-class functions, function expressions, **arrow functions** |
| **Arrays / Lists** | Zero-indexed linear sequences | Dynamic arrays with functional methods (`.map()`, `.filter()`) |
| **Objects / Structs** | C structs, Python dictionaries, OOP classes | Object literals: `{ key: value }` |

```text
The logic is the same. What is new is the browser, the DOM, and talking to a server.
```

---

### Slide 13: Variables and Types

```text
Variables and Types
• const by default; use let only when the value must change
• Both are block-scoped - they exist only inside the { } they are declared in
• var is function-scoped and error-prone; modern code does not use it
• Five types you meet every day: number, string, boolean, null, undefined (also bigint and symbol, rarely needed)
• Integers and decimals are one type: number
• typeof tells you the type of any value at run time
• null = "empty on purpose"; undefined = "no value assigned yet"
```

#### Core Variable Rules
1. **Rule of Thumb**: Always declare variables with `const`. Only use `let` when you know the variable will be reassigned (e.g., loop counters, accumulators). Never use `var`.
2. **Block Scope**: `let` and `const` variables are scoped strictly to the nearest enclosing curly braces `{ ... }`. They do not leak outside loops or `if` statements.
3. **The 5 Common Primitive Types**:
   - `number`: 64-bit floating point numbers (covers both integers like `42` and decimals like `3.14`).
   - `string`: Sequence of textual characters.
   - `boolean`: `true` or `false`.
   - `null`: Intentional absence of any object value (*"empty on purpose"*).
   - `undefined`: Variable declared, but no value has been assigned yet.

---

### Slide 14: Example: Variables and Types

#### Code (`app.js`)
```javascript
let count = 10;
count = count + 1;
console.log("count:", count);

const PI = 3.14159;
console.log("types:", typeof PI, typeof "Nam", typeof true);

let city = "Hanoi";
let isOpen = true;
let nothing = null;
let notSet;

// null and undefined are NOT the same
console.log("null vs notSet:", typeof nothing, typeof notSet);

PI = 3; // keep this line LAST
```

#### Console Output
```text
count: 11
types: number string boolean
null vs notSet: object undefined
Uncaught TypeError: Assignment to constant variable.
```

#### Line-by-Line Breakdown & Quirks
- `let count = 10; count = count + 1;`: Legal reassignment because `count` was declared with `let`. Prints `11`.
- `typeof PI, typeof "Nam", typeof true`: Evaluates to `"number"`, `"string"`, `"boolean"`.
- `typeof nothing` (where `nothing = null`): **Returns `"object"`!**
  - *Midterm Historical Fact*: This is a famous bug from the original 1995 JavaScript implementation. Type tags were stored in 32 bits, and the object type tag was `000`. Because `null` was represented as a NULL pointer (`0x00`), `typeof null` returned `"object"`. It can never be fixed because doing so would break millions of existing websites.
- `typeof notSet`: Returns `"undefined"` because the variable was declared without an initializer.
- `PI = 3;`: Attempting to reassign a `const` throws an `Uncaught TypeError`. Because JavaScript halts on uncaught exceptions, this line must remain last.

---

### Slide 15: Strings and Operators

```text
Strings and Operators
• Three ways to quote a string: '...', "..." and backticks `...`
• Only backticks allow ${ ... } to drop a value straight into the text, and only backticks can span several lines
• Arithmetic: + - * / % **. With two strings, + joins them instead of adding
• Comparison: always use === and !== (strict - value and type)
• Logical: && (and), || (or), ! (not)
• Watch out: == converts types behind your back: 5 == "5" and 0 == "" are both true. This is a classic beginner bug - never use it.
```

#### Strict (`===`) vs. Loose (`==`) Equality
- **Strict Equality (`===`)**: Does NOT perform type coercion. If the operand types differ, it immediately returns `false`.
  - `5 === "5"` $\rightarrow$ `false` (Number vs. String).
- **Loose Equality (`==`)**: Attempts automatic type conversion before comparing values.
  - `5 == "5"` $\rightarrow$ `true` (The string `"5"` is coerced to number `5`).
  - `0 == ""` $\rightarrow$ `true` (The empty string `""` is coerced to number `0`).
  - `0 == false` $\rightarrow$ `true`.

---

### Slide 16: Example: Template Literals

#### Code (`app.js`)
```javascript
let city = "Hanoi";
let year = 2026;

// old way: glue with +
let a = "Welcome to " + city + " in " + year;

// modern way: backticks
let b = `Welcome to ${city} in ${year}`;

console.log("with +:", a);
console.log("with backticks:", b);
console.log("same result?", a === b);
```

#### Console Output
```text
with +: Welcome to Hanoi in 2026
with backticks: Welcome to Hanoi in 2026
same result? true
```
- Template literals use backticks (`` ` ``) and interpolation syntax `${expression}`. They avoid manual string concatenation, space errors, and cleanly support multi-line strings.

---

### Slide 17: Example: Operators and Strict Equality

#### Code (`app.js`)
```javascript
// arithmetic
console.log("5 + 2 =", 5 + 2);
console.log('"a" + "b" =', "a" + "b");
console.log("7 % 2 =", 7 % 2);

// === compares value AND type
console.log('5 === 5 ->', 5 === 5);
console.log('5 === "5" ->', 5 === "5");

// == converts first, then compares
console.log('5 == "5" ->', 5 == "5");
console.log('0 == "" ->', 0 == "");

// logical
console.log("true && false ->", true && false);
console.log("true || false ->", true || false);
console.log("!true ->", !true);
```

#### Console Output
```text
5 + 2 = 7
"a" + "b" = ab
7 % 2 = 1
5 === 5 -> true
5 === "5" -> false
5 == "5" -> true
0 == "" -> true
true && false -> false
true || false -> true
!true -> false
```

> **Watch Out Callout**:
> `Number("")` converts to `0`, not `NaN`. An empty string (or whitespace string) converts numerically to zero. That is why `0 == ""` evaluates to `true`. Always use `===`.

---

### Slide 18: Making Decisions and Repeating

```text
Making Decisions and Repeating
• if / else works exactly as in C or Python
• The ternary condition ? ifTrue : ifFalse is a compact if/else that returns a value
• Exactly nine values are falsy: false, 0, -0, 0n, "", null, undefined, NaN, and the legacy document.all. Everything else is truthy
• switch is good when one value is compared against many fixed options - every case needs break or execution "falls through" to the next
• Loops: classic for when you need the index, for...of to walk a list, while to repeat while a condition holds
• Prefer for...of for arrays - it is shorter and avoids off-by-one index mistakes.
```

#### The 9 Falsy Values in JavaScript (Must Memorize for Midterm!)
When coerced to a boolean (`Boolean(x)`), exactly these 9 values evaluate to `false`:
1. `false`
2. `0` (positive zero)
3. `-0` (negative zero)
4. `0n` (BigInt zero)
5. `""` (empty string)
6. `null`
7. `undefined`
8. `NaN` (Not-a-Number)
9. `document.all` (legacy DOM object)

**Everything else in JavaScript is Truthy!** Including: `"0"` (non-empty string), `"false"`, `[]` (empty array), and `{}` (empty object)!

---

### Slide 19: Example: `if / else` and the Ternary Operator

#### Code (`app.js`)
```javascript
let grade = 72;

if (grade >= 60) {
  console.log("if/else ->", "Passed");
} else {
  console.log("if/else ->", "Failed");
}

let result = grade >= 60 ? "Passed" : "Failed";
console.log("ternary ->", result);

// the falsy values, one by one
console.log('0, empty, "0" ->', Boolean(0), Boolean(""), Boolean("0"));
console.log("false, -0, 0n ->", Boolean(false), Boolean(-0), Boolean(0n));
```

#### Console Output
```text
if/else -> Passed
ternary -> Passed
0, empty, "0" -> false false true
false, -0, 0n -> false false false
```
- Notice that `Boolean("0")` is `true`. Even though the number `0` is falsy, the string `"0"` has a length of 1, making it a non-empty string and therefore **truthy**.

---

### Slide 20: Example: `switch` and Fallthrough

#### Code (`app.js`)
```javascript
let code = 84;
let country;

switch (code) {
  case 84:
    country = "Vietnam";
    break;
  case 1:
    country = "US";
    break;
  default:
    country = "Unknown";
}
console.log("code 84 ->", country);
```

#### Console Output
```text
// as written above:
code 84 -> Vietnam

// now delete the first break and reload:
code 84 -> US
```
- **The Fallthrough Bug**: In a `switch` statement, if you omit the `break;` statement inside a matching case, execution continues falling down through all subsequent case blocks regardless of whether their condition matches! Deleting `break` in `case 84:` causes execution to spill into `case 1:`, overwriting `country` with `"US"`.

---

### Slide 21: Example: 3 Kinds of Loops

#### Code (`app.js`)
```javascript
// classic for - when you need the index
for (let i = 0; i < 3; i++) {
  console.log("for i =", i);
}

// for...of - walk through a list
const cities = ["Hanoi", "Hue", "Da Nang"];
for (const city of cities) {
  console.log("for...of city =", city);
}

// while - repeat while a condition holds
let n = 1;
while (n <= 3) {
  n++;
}
console.log("while ended, n =", n);
```

#### Console Output
```text
for i = 0
for i = 1
for i = 2
for...of city = Hanoi
for...of city = Hue
for...of city = Da Nang
while ended, n = 4
```
- Prefer `for...of` when iterating arrays: It directly accesses the values without managing an explicit counter variable `i`, preventing off-by-one errors (`i <= array.length` bug).

---

# Section 3: Functions and Objects (Slides 22–29)

---

### Slide 22: Section 3 — Functions and Objects
```text
3. Functions and Objects
```

---

### Slide 23: Functions

```text
Functions
• A function packages code you can call again with different inputs
• return sends a value back and ends the function
• A default parameter fills in a value when the caller gives none: function greet(who = "friend")
• Arrow functions are a shorter syntax introduced in ES6
• One parameter: the parentheses are optional. One expression: the return and the braces are optional
• They are everywhere in modern code - especially as arguments to array methods and event handlers
• Defining a function runs nothing. Nothing happens until you call it - a snippet that only defines functions prints an empty console.
```

---

### Slide 24: Example: Functions

#### Code (`app.js`)
```javascript
function areaOfCircle(r) {
  return 3.14159 * r * r;
}

const greet = function (name = "guest") {
  return "Hello, " + name;
};

function noReturn() { }

// nothing runs until you CALL them
console.log("area r=2:", areaOfCircle(2));
console.log("with a name:", greet("Nam"));
console.log("with default:", greet());
console.log("no return:", noReturn());
```

#### Console Output
```text
area r=2: 12.56636
with a name: Hello, Nam
with default: Hello, guest
no return: undefined
```
- If a function does not have a `return` statement (or calls `return;` empty), its evaluation result is implicitly `undefined`.
- Default parameters (`name = "guest"`) activate when an argument is missing or explicitly passed as `undefined`.

---

### Slide 25: Example: Arrow Functions

#### Code (`app.js`)
```javascript
// these three do exactly the same thing
const square1 = function (x) {
  return x * x;
};

const square2 = (x) => { return x * x; };

const square3 = x => x * x;

console.log("all three squares:", square1(4), square2(4), square3(4));

const add = (a, b) => a + b;
console.log("add(2, 3):", add(2, 3));
```

#### Console Output
```text
all three squares: 16 16 16
add(2, 3): 5
```

#### Arrow Function Syntax Evolution
1. Traditional function expression: `function (x) { return x * x; }`
2. Full arrow syntax: `(x) => { return x * x; }`
3. Concise arrow syntax: `x => x * x` (Single parameter omits `()`; single expression omits `{}` and implicit `return`).

---

### Slide 26: Objects and Arrays

```text
Objects and Arrays
• An object groups related data (properties) and behaviour (methods) under named keys
• Read a property with a dot (student.year) or with brackets (student["year"])
• This is exactly the shape of the JSON you will receive from a server in the last section
• Destructuring unpacks an object or an array in one line
• Spread (...) copies or merges without touching the original
• map, filter and reduce transform an array without a loop - each one takes a function
• map returns a new array of the same length, filter a shorter one, reduce a single value.
```

---

### Slide 27: Example: Objects & Mutability

#### Code (`app.js`)
```javascript
const dish = {
  name: "Pho bo",
  price: 60000,
  spicy: false,
  label() {
    return `${this.name} costs ${this.price}`;
  }
};

console.log("dot access:", dish.name);
console.log("bracket access:", dish["price"]);
console.log("method:", dish.label());

// a key that does not exist is not an error
console.log("missing key:", dish.sauce);
```

#### Console Output
```text
dot access: Pho bo
bracket access: 60000
method: Pho bo costs 60000
missing key: undefined
```

> **Key Rule**:
> Declaring an object with `const dish = { ... }` prevents you from reassigning the variable `dish = somethingElse;`. However, the object itself is **mutable**: you can freely add, modify, or delete properties (`dish.price = 65000;`).

---

### Slide 28: Example: Destructuring and Spread

#### Code (`app.js`)
```javascript
const dish = { title: "Pho bo", price: 60000 };
const scores = [8, 9, 10];

// destructuring: pull values out
const { title, price } = dish;
const [first, second] = scores;

// title and price are now normal variables
console.log("from object:", title, price);
console.log("from array:", first, second);

// spread: copy or merge
const copy = { ...dish, sold: true };
const all = [...scores, 7];

console.log("merged copy:", copy);
console.log("extended array:", all);
```

#### Console Output
```text
from object: Pho bo 60000
from array: 8 9
merged copy: {title: 'Pho bo', price: 60000, sold: true}
extended array: (4) [8, 9, 10, 7]
```
- **Destructuring**: Extracts properties from objects or values from arrays directly into standalone variables in a single statement.
- **Spread Operator (`...`)**: Creates a shallow copy of an existing object or array while allowing you to merge in new properties or items without mutating the original.

---

### Slide 29: Example: Array Methods (`map`, `filter`, `reduce`)

#### Code (`app.js`)
```javascript
const nums = [1, 2, 3, 4];

// forEach just visits, it returns nothing
nums.forEach(n => console.log("forEach saw:", n));

const doubled = nums.map(n => n * 2);
const evens = nums.filter(n => n % 2 === 0);
const total = nums.reduce((s, n) => s + n, 0);

console.log("map doubled:", doubled);
console.log("filter evens:", evens);
console.log("reduce total:", total);
console.log("original nums:", nums);
```

#### Console Output
```text
forEach saw: 1
forEach saw: 2
forEach saw: 3
forEach saw: 4
map doubled: (4) [2, 4, 6, 8]
filter evens: (2) [2, 4]
reduce total: 10
original nums: (4) [1, 2, 3, 4]
```

#### The Functional Holy Trinity (Exam Favorite!)
| Method | Purpose | Return Value | Modifies Original Array? |
| :--- | :--- | :--- | :--- |
| **`forEach()`** | Side effects (logging, updating DOM) | `undefined` | No |
| **`map()`** | Transform every item by applying a formula | A new array of the **exact same length** | **No** (Immutable) |
| **`filter()`** | Select items matching a true/false condition | A new array of the **same or shorter length** | **No** (Immutable) |
| **`reduce()`** | Aggregate all items into a single final result | A **single accumulated value** (number, object, string) | **No** (Immutable) |

- In `nums.reduce((s, n) => s + n, 0)`: `0` is the initial accumulator value (`s`). In each step, `s` accumulates `n`.

---

# Section 4: The DOM and Events (Slides 30–37)

---

### Slide 30: Section 4 — The DOM and Events
```text
4. The DOM and Events
```

---

### Slide 31: The DOM: The Page as a Tree

```text
The DOM: The Page as a Tree
The browser turns your HTML into the DOM - a tree of objects, one node per tag, arranged as a tree.
DOM = Document Object Model
Every tag becomes a node you can read and change from JavaScript, the page updates live, the user sees it immediately, with no reload.
Think of the folder tree in your file explorer: parents, children, nesting.
This is the tree of your index.html - every selector in this section points at one of these nodes.
```

#### Hierarchical Tree Structure
```text
                      [ document ]
                           │
                       [ <html> ]
                      ┌────┴────┐
                  [ <head> ] [ <body> ]
                     │          │
                 [ <title> ]    ├──────────┬──────────┬──────────┐
                             [ <h1> ]   [ <ul> ]   [ <form> ] [ <div> ]
                                           │
                                     ┌─────┼─────┐
                                  [ <li> ][ <li> ][ <li> ]
```
- The DOM is an object-oriented in-memory data representation of the web page. Every element, attribute, and text piece becomes a node that JavaScript can query and mutate.

---

### Slide 32: Finding and Changing Elements

```text
Finding and Changing Elements
• getElementById("menu") when the element has an id - the clearest and fastest way
• querySelector takes any CSS selector (#id, .class, tag) and returns the first match - use it when there is no id
• querySelectorAll returns all matches as a list you can walk with forEach
• textContent changes the text inside an element
• classList .add .remove .toggle switches CSS classes on and off
• style.color sets a single CSS property directly
• createElement plus append puts a brand-new node into the tree
• Watch out: Use textContent to set text. innerHTML with untrusted input lets an attacker inject markup - we come back to this in class 9.
```

#### DOM Mutation Cheat Sheet
- **Selection**:
  - `document.getElementById('id')`: Returns single element matching ID.
  - `document.querySelector('cssSelector')`: Returns **first** element matching CSS selector.
  - `document.querySelectorAll('cssSelector')`: Returns a static `NodeList` containing **all** matching elements.
- **Content & Styling**:
  - `el.textContent = "New text"`: Safely sets text without parsing HTML.
  - `el.classList.add("active")`: Adds class.
  - `el.classList.remove("active")`: Removes class.
  - `el.classList.toggle("active")`: Adds class if absent; removes if present.
  - `el.style.backgroundColor = "red"`: Sets inline CSS.
- **Node Creation**:
  - `const newEl = document.createElement("li")`: Creates element in memory.
  - `parent.append(newEl)`: Attaches element to DOM tree.

---

### Slide 33: Example: Selecting Elements

#### Code (`app.js`)
```javascript
const titleEl = document.getElementById("heading");
const firstDish = document.querySelector(".dish");
const allDishes = document.querySelectorAll(".dish");
const menuList = document.querySelector("#menu");

console.log("by id:", titleEl.textContent);
console.log("first .dish:", firstDish.textContent);
console.log("how many .dish:", allDishes.length);
console.log("tag name:", menuList.tagName);

allDishes.forEach(d => console.log("dish:", d.textContent));
```

#### Console Output
```text
by id: Pho Thin
first .dish: Pho bo
how many .dish: 3
tag name: UL
dish: Pho bo
dish: Pho ga
dish: Pho tai
```
- `querySelector(".dish")` matches only the **first** element with class `.dish` (`Pho bo`).
- `querySelectorAll(".dish")` returns all 3 dishes as a `NodeList` with a `.length` property and `.forEach()` method.

---

### Slide 34: Example: Changing the Page

#### Code (`app.js`)
```javascript
const titleEl = document.getElementById("heading");
titleEl.textContent = "Welcome to Pho Thin";
titleEl.style.color = "crimson";

const li = document.createElement("li");
li.textContent = "Pho sot vang";
li.classList.add("dish");
document.getElementById("menu").append(li);

document.getElementById("out").textContent =
  `Now ${document.querySelectorAll('.dish').length} dishes`;
```

#### Page Visual Changes
- **Before**: Heading says `Pho Thin` (black); menu has 3 items (`Pho bo`, `Pho ga`, `Pho tai`).
- **After**: Heading changes to `Welcome to Pho Thin` (crimson red); a 4th item `Pho sot vang` is dynamically appended; `#out` displays: `Now 4 dishes`.

---

### Slide 35: Events and Forms

```text
Events and Forms
• addEventListener(type, handler) is the modern way to respond to what the user does
• It keeps behaviour in the .js file, not in onclick="..." attributes inside the HTML
• Common types: click, input, change, submit, keydown
• The handler receives an event object; event.target is the element that fired it and event.target.value is what the user typed
• event.preventDefault() stops the browser's default action - for a form that default is submit and reload the page
• Read a field with .value, and .trim() away the spaces before you check it
• Watch out: Never trust the client. Checking in the browser is for convenience; the server must check again.
```

---

### Slide 36: Example: Events

#### Code (`app.js`)
```javascript
const button = document.querySelector("#signup");
const nameBox = document.getElementById("customer");

button.addEventListener("click", (event) => {
  event.preventDefault();
  console.log("click ->", "Order button");
});

nameBox.addEventListener("input", (event) => {
  // event.target = the element that fired it
  console.log("typing ->", event.target.value);
});
```

#### Console Output
```text
// you click Order:
click -> Order button

// you type P, h, o into the input box:
typing -> P
typing -> Ph
typing -> Pho
```

> **Why `event.preventDefault()` is mandatory**:
> Inside an HTML `<form>`, clicking a `<button>` triggers an automatic form submission: the browser attempts to serialize fields and reload the page. That page reload clears the console immediately! `event.preventDefault()` halts the default reload, keeping the page and console intact.

---

### Slide 37: Example: Forms and Validation

#### Code (`app.js`)
```javascript
const form = document.getElementById("signup");
const nameBox = document.getElementById("customer");

form.addEventListener("submit", (event) => {
  event.preventDefault();
  const customer = nameBox.value.trim();
  if (customer === "") {
    alert("Name must be filled out");
    return;
  }
  console.log("submitted for:", customer);
});
```
- `.trim()` strips leading and trailing whitespace. If a user enters only spaces `"   "`, `.trim()` evaluates to `""`, triggering the validation error dialog.

---

# Section 5: Asynchronous JavaScript (Slides 38–50)

---

### Slide 38: Section 5 — Asynchronous JS
```text
5. Asynchronous JS
```

---

### Slide 39: Why Asynchronous? (Single-Threaded Model & Pho Shop Analogy)

```text
Why Asynchronous
Start the slow job, keep working, collect the result later:
[ start the request ] ──► [ keep working (page stays responsive) ] ──► [ result arrives ]

• Some tasks take time: fetching data from a server, reading a file, a timer
• JavaScript runs on a single thread - it must not freeze while waiting
• So slow tasks run in the background and notify you when they finish
• Remember the pho shop from class 1? You order, get a ticket, and keep chatting - the food arrives later. A Promise is that ticket: a value that is not ready yet.
```

#### The Pho Shop Metaphor Explained
- **Synchronous Model (Blocking)**: You walk up to the counter, order pho, and stand frozen at the register for 15 minutes. The line behind you cannot move, and the entire restaurant grinds to a halt.
- **Asynchronous Model (Non-Blocking / Promises)**: You order pho, the cashier hands you a numbered ticket (**The Promise**), and you sit at your table talking with friends. When the pho is prepared, the waiter calls your ticket number (**Fulfillment**) and hands you the bowl.

---

### Slide 40: The `menu.json` File

```text
The menu.json File
[
  { "name": "Pho bo", "price": 60000 },
  { "name": "Pho ga", "price": 55000 },
  { "name": "Pho tai", "price": 65000 }
]
```

#### Strict JSON Syntax Rules
1. Every string and property key **must be enclosed in double quotes** (`"name"`, not `'name'`).
2. Values can be strings, numbers, booleans, arrays, objects, or `null`.
3. **No trailing commas**: `{ "name": "Pho bo", }` is illegal in JSON and causes a parsing exception.
4. No comments allowed inside standard JSON.

---

### Slide 41: CORS: Why the Browser Blocks a Fetch

```text
CORS: Why the Browser Blocks a Fetch
An origin is scheme + host + port together - in http://127.0.0.1:5500/index.html it is http://127.0.0.1:5500.
A page may only fetch from its own origin. That rule is CORS.
```

#### The 3 Components of an Origin
$$\text{Origin} = \text{Scheme (Protocol)} + \text{Host (Domain/IP)} + \text{Port}$$

#### When Does the Browser Allow a Fetch?
| Request Origin | Destination URL | Allowed? | Reason |
| :--- | :--- | :--- | :--- |
| `http://127.0.0.1:5500` | `menu.json` (Relative) | **Yes** | Same scheme (`http`), host (`127.0.0.1`), and port (`5500`). |
| `http://127.0.0.1:5500` | `http://127.0.0.1:3000/menu.json` | **No** | **Different port** (`3000` vs `5500`). |
| `http://127.0.0.1:5500` | `https://api.pho.vn/menu` | **No** | **Different host** (`api.pho.vn` vs `127.0.0.1`) and scheme. |
| `file:///C:/index.html` | `menu.json` | **No** | `file://` has origin `null`, matching nothing. Triggers CORS error! |

- **The Solution**: Always serve files through Live Server (`http://127.0.0.1:5500`). For remote servers, the remote server must send the HTTP header: `Access-Control-Allow-Origin: *`.

---

### Slide 42: Promises and `async / await`

```text
Promises and async / await
• A Promise is a value that is not ready yet. It ends in one of two states: fulfilled or rejected
• .then() schedules what happens when the value is ready; .catch() handles the failure in one place
• Chaining .then() avoids the deeply nested callbacks of old code
• await pauses inside an async function until the promise settles, then hands you the value
• The result reads top-to-bottom like ordinary code - much easier to follow than a chain of .then()
• Wrap it in try / catch to handle the rejected case
• await only works inside an async function. Writing it anywhere else is a SyntaxError.
```

#### Promise State Transitions
```text
                 ┌───► [ Fulfilled ] (Success -> .then() or resolved await)
  [ Pending ] ───┤
                 └───► [ Rejected ]  (Error   -> .catch() or catch block)
```

---

### Slide 43: Example: Promises with `.then()`

#### Code (`app.js`)
```javascript
fetch("menu.json")
  .then(response => response.json())
  .then(dishes => {
    console.log("how many dishes:", dishes.length);
    console.log("first dish:", dishes[0].name);
    console.log("whole array:", dishes);
  })
  .catch(error => console.log("Failed:", error));
```

#### Console Output
```text
how many dishes: 3
first dish: Pho bo
whole array: (3) [{...}, {...}, {...}]
```
- Step 1: `fetch("menu.json")` returns a Promise for the HTTP Response object.
- Step 2: `response.json()` parses the JSON body stream into native JavaScript objects (also returns a Promise).
- Step 3: Second `.then()` receives the parsed `dishes` array.
- Step 4: `.catch()` catches any network error across the entire chain.

---

### Slide 44: Example: `async / await`

#### Code (`app.js`)
```javascript
async function loadMenu() {
  try {
    const res = await fetch("menu.json");
    const dishes = await res.json();
    console.log("how many dishes:", dishes.length);
    console.log("first dish:", dishes[0].name);
  } catch (error) {
    console.log("Failed:", error);
  }
}

loadMenu();
```
- Syntactic sugar over Promises. `await` temporarily yields execution back to the browser event loop until the promise settles, then resumes execution right on the next line. Handled cleanly using standard `try / catch` blocks.

---

### Slide 45: Fetch and Error Handling (The `res.ok` Trap)

```text
Fetch and Error Handling
• fetch is the built-in way to talk to a server - it replaced XMLHttpRequest and jQuery's $.ajax
• It returns a promise for a Response; the body is read separately with await res.json()
• res.ok is true for status 200-299 and false otherwise; res.status is the number
• The promise only rejects when the request itself fails - a badly-formed URL, a blocked request, or a network error
• A 404 or 500 is still a successful request, so it does not reject - you have to check res.ok yourself
• Watch out: This one costs students hours every year: the fetch "worked", the data is missing, and there is no error message - because nobody checked res.ok.
```

> **THE NUMBER ONE MIDTERM EXAM TRAP**:
> - Does `fetch()` reject when the server returns a `404 Not Found` or `500 Server Error`?  
> - **NO!** In HTTP, a 404 or 500 response was successfully delivered across the network by the server. As far as the network transport is concerned, the HTTP transaction succeeded.
> - Therefore, `fetch()` **only rejects on network disconnects, DNS failures, or CORS blocks**.
> - You **must manually verify `res.ok`**!

---

### Slide 46: Example: Checking `res.ok`

#### Code (`app.js`)
```javascript
async function check(file) {
  const res = await fetch(file);
  console.log("file:", file, "| ok:", res.ok, "| status:", res.status);
  if (!res.ok) {
    throw new Error(`HTTP ${res.status}`);
  }
  return await res.json();
}

check("menu.json")
  .catch(e => console.log("Caught:", e.message));
```

#### Console Output (When File Exists)
```text
file: menu.json | ok: true | status: 200
```

#### Console Output (When Given `typo.json` Which Does Not Exist)
```text
GET .../typo.json 404 (Not Found)
file: typo.json | ok: false | status: 404
Caught: HTTP 404
```
- Checking `if (!res.ok) throw new Error(...)` forces execution into the `catch` block when receiving 404/500 errors.

---

### Slide 47: Example: Putting It Together

#### Full Integration Code (`app.js`)
```javascript
const menuList = document.getElementById("menu");

async function loadMenu() {
  try { // happy path below
    const res = await fetch("menu.json");
    if (!res.ok) throw new Error(`HTTP ${res.status}`);
    const dishes = await res.json();
    menuList.textContent = ""; // clear initial loading state
    for (const dish of dishes) {
      const li = document.createElement("li");
      li.textContent = `${dish.name} - ${dish.price} VND`;
      menuList.append(li);
    }
  } catch (err) { // any failure lands here
    menuList.textContent = "Could not load the menu.";
  }
}

loadMenu();
```
- **Happy Path**: Fetches `menu.json`, clears the list, iterates over the dish objects with `for...of`, constructs `<li>` tags, and appends them to the DOM.
- **Error Path**: If the file is missing or corrupted, execution jumps to `catch (err)`, displaying a user-friendly error message `"Could not load the menu."`.

---

### Slide 48: Summary of Lecture 03

```text
Summary
• One folder, three files, one place to paste - that is the whole workspace for today
• JavaScript adds behaviour: it turns a page into an application
• Modern JavaScript is ES6+: let/const, template literals, arrow functions, destructuring
• Objects and arrays carry your data; map/filter/reduce transform it without a loop
• The DOM is the page as a tree; getElementById, querySelector and addEventListener read and change it
• Slow work is asynchronous: promises, async/await, and fetch
• Always check res.ok and handle the failure case - not only the happy path
• Class 2 gave you a page that looks right. Today it responds. Class 4 moves the same language to the server.
```

---

### Slide 49 & 50: Practical Work 3: Make Pho Thin Come Alive

```text
Practical Work 3: Make Pho Thin Come Alive
Task 1: Click a bowl to order (click listener, append to order list, running total via reduce)
Task 2: The order form (customer name + table number, validate, confirmation message)
Task 3: Load today's menu (fetch menu.json, async/await, check res.ok, error handling)
```

#### Complete Practical Work Solution (`app.js`)
```javascript
// ============================================================================
// USTH Web Application Development - Practical Work 3 Complete Solution
// ============================================================================

// State: Array of ordered prices
const order = [];

// ----------------------------------------------------------------------------
// Task 3: Load today's menu from menu.json
// ----------------------------------------------------------------------------
async function loadMenu() {
  const menuList = document.getElementById("menu");
  try {
    const res = await fetch("menu.json");
    if (!res.ok) throw new Error(`HTTP Error ${res.status}`);
    const dishes = await res.json();

    menuList.textContent = ""; // Clear existing static list

    dishes.forEach(dish => {
      const li = document.createElement("li");
      li.className = "dish";
      li.textContent = `${dish.name} - ${dish.price} VND`;
      li.dataset.name = dish.name;
      li.dataset.price = dish.price;

      // Attach Task 1 click listener to dynamically created bowl
      attachBowlClickListener(li);

      menuList.append(li);
    });
  } catch (error) {
    console.error("Failed to load menu:", error);
    menuList.textContent = "Could not load the menu. Please try again later.";
  }
}

// ----------------------------------------------------------------------------
// Task 1: Click a bowl to order
// ----------------------------------------------------------------------------
function attachBowlClickListener(li) {
  li.addEventListener("click", () => {
    const price = Number(li.dataset.price);
    const name = li.dataset.name;

    // 1. Add price to state array
    order.push(price);

    // 2. Add bowl name to #order list in the DOM
    const orderList = document.getElementById("order");
    const orderItem = document.createElement("li");
    orderItem.textContent = `${name} (${price} VND)`;
    orderList.append(orderItem);

    // 3. Compute running total using reduce
    const total = order.reduce((sum, itemPrice) => sum + itemPrice, 0);
    document.getElementById("total").textContent = total;
  });
}

// Attach listener to any static items on startup
document.querySelectorAll("#menu li").forEach(attachBowlClickListener);

// ----------------------------------------------------------------------------
// Task 2: The order form (customer name + table number validation)
// ----------------------------------------------------------------------------
const signupForm = document.getElementById("signup");
if (signupForm) {
  signupForm.addEventListener("submit", (event) => {
    event.preventDefault(); // Stop page reload

    const nameInput = document.getElementById("customer");
    const name = nameInput.value.trim();

    // Validation
    if (name === "") {
      alert("Please enter customer name!");
      return;
    }

    if (order.length === 0) {
      alert("Please click at least one bowl of pho before ordering!");
      return;
    }

    const total = order.reduce((s, p) => s + p, 0);
    const outDiv = document.getElementById("out");
    outDiv.textContent = `Order confirmed for ${name}! Total: ${total} VND for ${order.length} bowls.`;
    outDiv.style.color = "green";
    outDiv.style.fontWeight = "bold";
  });
}

// Execute initial data load
loadMenu();
```

#### Question for the Class (Slide 49)
**"Where should each price really be checked — in the browser, on the server, or both?"**
> **Answer**: **BOTH!**
> - **In the browser**: For immediate user experience (instant calculation, responsive UI without waiting for network latency).
> - **On the server (MANDATORY for security)**: Because clients can easily open Chrome DevTools and alter `li.dataset.price` or manipulate the JavaScript variables before sending, the server must never trust prices sent by the client. The server must independently look up the authentic prices in its database before charging the customer or saving the order.

---

### Slide 51: Conclusion
```text
Thank you for listening!
KIEU Quoc Viet, HUYNH Vinh Nam | JavaScript | Hanoi, August 2026 | 51 / 55
```

---

# Appendices (Slides 52–55)

---

### Slide 52: Appendix A: Reserved Keywords

```text
Appendix A: Reserved Keywords
```
- **Always Reserved (Cannot be variable or function names)**:
  `break`, `case`, `catch`, `class`, `const`, `continue`, `debugger`, `default`, `delete`, `do`, `else`, `enum`, `export`, `extends`, `false`, `finally`, `for`, `function`, `if`, `import`, `in`, `instanceof`, `new`, `null`, `return`, `super`, `switch`, `this`, `throw`, `true`, `try`, `typeof`, `var`, `void`, `while`, `with`.
- **Reserved in Strict Mode**:
  `implements`, `interface`, `let`, `package`, `private`, `protected`, `public`, `static`.
- **Reserved only in Context**:
  - `await`: reserved inside `async` functions and ES modules.
  - `yield`: reserved inside generator functions.
- **Contextual Keywords (NOT reserved elsewhere)**:
  `async`, `of`, `get`, `set` are ordinary identifiers that only carry special meaning in specific syntactic positions.

---

### Slide 53: Appendix B: Number Literals

```javascript
let dec = 2534;        // decimal
let neg = -1000;       // negative
let frac = 0.3555;     // decimals
let exp = 19.5e-2;     // exponent (0.195)
let hex = 0xCCFF;      // hexadecimal (52479)
let binary = 0b1010;   // binary (10)
let octal = 0o17;      // octal (15)

console.log("largest safe int:", Number.MAX_SAFE_INTEGER); // 9007199254740991 (2^53 - 1)
console.log("0/0 and 1/0:", 0 / 0, 1 / 0);                 // NaN and Infinity
```
- Every numeric literal in JavaScript belongs to the exact same primitive type: `number`.
- `NaN` ("Not a Number") and `Infinity` are ordinary numeric values.

---

### Slide 54: Appendix C: Strings and Escape Sequences

```text
Three ways to quote:
let single = 'single quotes';
let double = "double quotes";
let templ = `backticks, with ${single}`;
let empty = "";
```

#### Escape Sequences Table
| Escape Code | Character Represented |
| :--- | :--- |
| `\n` | Newline (Line break) |
| `\t` | Horizontal Tab |
| `\'` | Literal Single Quote |
| `\"` | Literal Double Quote |
| `\\` | Literal Backslash |
| `\u{1F60A}` | Unicode Code Point (Emoji / international symbols) |

- Single and double quotes behave identically in JavaScript. Pick one style and stay consistent. Only template literals (backticks) permit embedded `${...}` and direct multiline breaks.

---

### Slide 55: Appendix D: The Other Value Types (`typeof null` & `NaN`)

#### Code (`app.js`)
```javascript
let flag = true;
let nothing = null;
let notSet;

console.log("three types:", typeof flag, typeof nothing, typeof notSet);
console.log('null vs undefined:', null === undefined, null == undefined);
console.log("NaN === NaN:", NaN === NaN);
```

#### Console Output
```text
three types: boolean object undefined
null vs undefined: false true
NaN === NaN: false
```

#### Three Classic Exam Traps
1. **`typeof null === "object"`**: Historical 1995 engine bug that will remain forever to preserve backward compatibility.
2. **`null === undefined` is `false`, but `null == undefined` is `true`**: Under loose equality, `null` and `undefined` are coerced to match each other, but strictly they are different primitive types.
3. **`NaN === NaN` evaluates to `FALSE`!**: `NaN` is the **only value in JavaScript that is not equal to itself**. To test whether a value is `NaN`, you cannot write `if (x === NaN)`. You must use `Number.isNaN(x)`.

---

# Midterm Exam Master Review: Key Differences, Traps & Exam Questions

---

### 1. High-Yield Comparison Tables

#### A. `const` vs. `let` vs. `var`
| Feature | `const` | `let` | `var` |
| :--- | :--- | :--- | :--- |
| **Scope** | Block `{}` | Block `{}` | Function |
| **Reassignable?** | **No** (Error) | **Yes** | **Yes** |
| **Redeclarable?** | No | No | Yes (Bug-prone) |
| **Hoisting Behavior** | Temporal Dead Zone | Temporal Dead Zone | Initialized as `undefined` |
| **Recommendation** | **Default choice** | Only for changing values | **Never use** |

#### B. `map()` vs. `filter()` vs. `reduce()`
| Method | Purpose | Input $\rightarrow$ Output | Returns |
| :--- | :--- | :--- | :--- |
| **`map`** | Transforms every item | $[A, B, C] \rightarrow [A', B', C']$ | New array of **same length** |
| **`filter`** | Selects items by condition | $[A, B, C] \rightarrow [A, C]$ | New array of **equal/smaller length** |
| **`reduce`** | Aggregates into single value | $[A, B, C] \rightarrow \text{Total}$ | **Single accumulated value** |

---

### 2. Common Midterm Pitfalls & Traps

1. **Trap: "Fetch rejects when a 404 Not Found error is returned."**
   - **Correction**: `fetch()` resolves successfully on 404 and 500! It only rejects on network failures. You **must** check `if (!res.ok)`.
2. **Trap: "An empty array `[]` or string `"0"` is falsy."**
   - **Correction**: `[]` and `"0"` are **TRUTHY**. Only the 9 specific falsy values evaluate to false.
3. **Trap: "Changing properties of a `const` object throws a TypeError."**
   - **Correction**: `const` protects the variable binding from reassignment; it does **not** make the internal object immutable. `dish.price = 70000;` is 100% legal.
4. **Trap: "You can compare `if (x === NaN)`."**
   - **Correction**: `NaN === NaN` is `false`. You must use `Number.isNaN(x)`.
5. **Trap: "A script in `<head>` without `defer` can query elements in `<body>`."**
   - **Correction**: Without `defer`, the script runs before `<body>` is parsed; `querySelector` will return `null` and throw `Cannot read properties of null`.

---

### 3. Practice Midterm Exam Questions & Solutions

#### Question 1 (Asynchronous Fetch)
**Explain why double-clicking `index.html` to open it in a browser causes `fetch("menu.json")` to fail. What error appears in the console, and what is the proper fix?**
> **Answer**:
> - **Cause**: Opening `index.html` via double-click uses the `file:///` protocol, which assigns an origin of `null`. The browser's Same-Origin Policy (SOP) blocks fetch requests from `null` origins for local security reasons.
> - **Error**: `Access to fetch at 'file:///...' from origin 'null' has been blocked by CORS policy`.
> - **Fix**: Serve the folder using a local HTTP development server like **VS Code Live Server**, which serves files over `http://127.0.0.1:5500`.

#### Question 2 (Equality & Falsy Values)
**What does each of the following expressions evaluate to?**
1. `5 == "5"`
2. `5 === "5"`
3. `Boolean("0")`
4. `Boolean("")`
5. `null == undefined`
6. `null === undefined`
> **Answer**:
> 1. `true` (Loose equality coerces `"5"` to `5`)
> 2. `false` (Strict equality: number vs string)
> 3. `true` (Non-empty string is truthy)
> 4. `false` (Empty string is falsy)
> 5. `true` (Loose equality coerces them together)
> 6. `false` (Strict equality: null object vs undefined type)

#### Question 3 (Functional Programming)
**Given `const prices = [10, 20, 30];`, write a single line using an array method to calculate the total sum.**
> **Answer**:
> ```javascript
> const total = prices.reduce((acc, curr) => acc + curr, 0);
> ```

#### Question 4 (DOM & Event Handling)
**Why is `event.preventDefault()` typically called inside a form's `"submit"` event listener in single-page applications?**
> **Answer**: By default, submitting an HTML form sends an HTTP request and triggers a full browser page reload. Calling `event.preventDefault()` cancels this default behavior, allowing client-side JavaScript to validate the form, update the DOM, or send background asynchronous `fetch()` requests without reloading the page.
