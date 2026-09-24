**157-Question Assessment Portal & Exam Revision Guide**

---

## Repository Structure

```text
webapp/
├── quiz.html                         
├── question_bank.json               
├── question_bank.js               
├── README.md                      
│
├── introduction/                     # Lecture 01: Internet & WWW
│   ├── 1. Introduction to Internet & WWW.pdf
│   └── slide_explain.md              # Line-by-line lecture slide analysis & core concepts
│
├── html_and_css/                     # Lecture 02: HTML5 & CSS3 Architecture
│   ├── 2. Introduction to HTML + CSS.pdf
│   ├── Exercise1.1 - HTML+CSS (Basic).pdf
│   ├── Exercise1.2 - HTML+CSS (Advanced).pdf
│   ├── slide_explain.md              # Line-by-line lecture slide breakdown
│   ├── exercise1_1_solution.md       # Complete line-by-line solution for Lab 1.1
│   └── exercise1_2_solution.md       # Complete line-by-line solution for Lab 1.2
│
├── javascript/                       # Lecture 03: JavaScript & Asynchronous Programming
│   ├── 3. JavaScript (1).pdf
│   ├── Exercise2.1 - JavaScript (basic).pdf
│   ├── Exercise2.2 - JavaScript (Advanced) .pdf
│   ├── slide_explain.md              # Line-by-line lecture slide breakdown
│   ├── exercise2_1_solution.md       # Complete line-by-line solution for Lab 2.1
│   └── exercise2_2_solution.md       # Complete line-by-line solution for Lab 2.2
│
└── scripts/
    ├── build_question_bank.ps1       # Automated validator & merger for all module JSONs
    └── generate_full_banks.ps1       # Generator pipeline compiling all drafts into master banks
```

---

## How to Use This Repository

### Instant Offline Practice (Zero Setup / Recommended)

You do **not** need to install Node.js, Python, or a database to practice:
1. Open your file explorer, navigate to this folder, and **double-click [`quiz.html`]**.
2. It will instantly launch in Google Chrome, Microsoft Edge, Firefox, Brave, or Safari.

---

## High-Yield Midterm Exam Traps Summary

Review these recurring traps tested across past exams and code prediction scenarios:

| Concept | Trap / Misconception | Ground Truth |
| :--- | :--- | :--- |
| **`<!DOCTYPE html>`** | Believing it is an HTML root tag requiring `</!DOCTYPE>`. | It is a preamble that prevents the browser rendering engine from dropping into legacy Quirks Mode. |
| **`box-sizing`** | Calculating total width as `width` when using `box-sizing: content-box`. | In `content-box`, total width = `width + padding + border`. In `border-box`, padding and border are absorbed inside `width`. |
| **CSS Specificity** | Thinking multiple class selectors can override an ID selector. | Specificity is a tuple `(IDs, Classes, Elements)`. 1 ID `(1, 0, 0)` beats 100 classes `(0, 100, 0)`. |
| **`!important` vs JS** | Assuming `el.style.color = "green"` overrides stylesheet rules. | Regular JS inline style assignments cannot override a stylesheet declaration flagged with `!important`. |
| **`el.style` vs `getComputedStyle`** | Trying to read CSS stylesheet properties via `el.style.color`. | `el.style` ONLY inspects inline `style=""` attributes. Styles from external stylesheets return `""`. Use `window.getComputedStyle(el)`. |
| **`display: none` vs `visibility: hidden`** | Believing both elements have non-zero `offsetWidth`. | `display: none` removes the element from the render tree (`offsetWidth = 0`). `visibility: hidden` maintains geometry (`offsetWidth > 0`). |
| **`e.target` vs `e.currentTarget`** | Assuming `e.target` is always the element where `addEventListener` was registered. | `e.target` is the lowest innermost element initiating the event; `e.currentTarget` (and `this`) is the element where the handler is bound. |
| **`children` vs `childNodes`** | Treating `childNodes.length` as equivalent to element tag count. | `children` contains only Element nodes (`nodeType === 1`). `childNodes` includes whitespace/newline Text nodes and comments. |
| **Event Loop Microtasks** | Believing `setTimeout(fn, 0)` runs before `.then()` promise callbacks. | Promise callbacks are placed in the Microtask queue, which is completely emptied before any Macrotask (`setTimeout`). |
| **`const` in JS** | Believing `const obj = {}` makes object properties immutable. | `const` protects the variable binding reference from reassignment. Properties (`obj.price = 50`) can be freely modified. |
| **`typeof null`** | Expecting `typeof null` to return `"null"`. | Returns `"object"` due to a legacy 1995 type-tagging bug where null was represented as a NULL pointer (`0x00`). |
| **`NaN` Identity** | Expecting `NaN === NaN` to evaluate to `true`. | Under IEEE 754, `NaN` is never equal to itself. Must test using `Number.isNaN(x)`. |
| **Fetch 404/500** | Assuming `fetch()` rejects (jumps to `catch`) on HTTP 404 or 500. | `fetch()` resolves successfully on 404/500 because the HTTP transaction completed. You must manually check `if (!res.ok)`. |
| **Event Delegation** | Trying to delegate `blur` or `focus` on a parent `<form>`. | `blur` and `focus` do not bubble (`bubbles: false`). You must listen for `focusout` or `focusin` instead. |
| **CORS Origins** | Assuming `http://127.0.0.1:5500` can fetch `http://127.0.0.1:3000`. | Origin is defined as `(protocol, host, port)`. Different ports make it cross-origin and blocked by the browser SOP. |
| **Checkbox `preventDefault()`** | Expecting `this.checked` to be `true` after clicking an unchecked box with `preventDefault()`. | `preventDefault()` cancels the browser default toggling behavior, keeping `this.checked = false`. |
| **HTML Form Validation** | Expecting empty `required type="email"` to trigger `typeMismatch: true`. | Empty inputs fail `valueMissing: true`; format validation (`typeMismatch`) only triggers on non-empty values. |

---

*Good luck with your midterm exam revision!*
