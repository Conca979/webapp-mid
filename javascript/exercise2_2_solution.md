# Web Application Development — Exercise 2.2 Solution & Deep-Dive Guide
**University of Science and Technology of Hanoi (USTH)**  
**Module:** Web Application Development (JavaScript Advanced Labwork: "Make the Page Say the Right Thing")  
**File Reference:** `Exercise2.2 - JavaScript (Advanced) .pdf`  
**Purpose:** Complete reference solutions, code debugging tables, and exhaustive "Why" explanations for the advanced hands-on lab.

---

## Table of Contents
1. [Lab Objectives & Learning Outcomes](#lab-objectives--learning-outcomes)
2. [Part 1: Make the Page Lie to You (`order-total.html`)](#part-1-make-the-page-lie-to-you-order-totalhtml)
   - [Code Analysis of `order-total.html`](#code-analysis-of-order-totalhtml)
   - [Question 1: Empty Price and Missing `return` Bug](#question-1-empty-price-and-missing-return-bug)
   - [Question 2: Division by Zero and `Infinity`](#question-2-division-by-zero-and-infinity)
   - [Question 3: `innerHTML` vs. `textContent` and XSS Vulnerabilities](#question-3-innerhtml-vs-textcontent-and-xss-vulnerabilities)
   - [Fully Corrected `order-total.html`](#fully-corrected-order-totalhtml)
3. [Part 2: Fix the Sign Up Page (`signup.html`)](#part-2-fix-the-sign-up-page-signuphtml)
   - [The Four Bugs Diagnostic Table](#the-four-bugs-diagnostic-table)
   - [Detailed Answers to the Four Questions](#detailed-answers-to-the-four-questions)
   - [Fully Corrected `signup.html`](#fully-corrected-signuphtml)
4. [Part 3: Write `app.js` Without Touching the HTML (`tasks.html`)](#part-3-write-appjs-without-touching-the-html-taskshtml)
   - [The "One Rule" Constraint](#the-one-rule-constraint)
   - [Complete, Production-Ready `app.js`](#complete-production-ready-appjs)
   - [Task 1: Child Combinator (`div > h1` vs. `div h1`)](#task-1-child-combinator-div--h1-vs-div-h1)
   - [Task 2: Two-Click Stopwatch Closure Logic](#task-2-two-click-stopwatch-closure-logic)
   - [Task 3: Fetching `menu.json`, CORS & Same-Origin Policy](#task-3-fetching-menujson-cors--same-origin-policy)
5. [Oral Check & Midterm Exam Survival Guide](#oral-check--midterm-exam-survival-guide)

---

## Lab Objectives & Learning Outcomes

This advanced lab trains you to:
1. Debug silent logical flaws where JavaScript runs without error but outputs incorrect data.
2. Distinguish between `textContent` (safe plain text) and `innerHTML` (HTML parsing and XSS vectors).
3. Understand non-throwing numeric values: `NaN` and `Infinity`.
4. Debug lifecycle and execution timing issues (DOM parsing vs. script execution).
5. Identify event bubbling limitations (`blur` vs. `focusout`).
6. Prevent form submission reloads with `event.preventDefault()`.
7. Master CSS selectors in JavaScript (`div > h1` vs. `div h1`).
8. Understand browser security models (CORS, origin `null`, Same-Origin Policy).

---

# Part 1: Make the Page Lie to You (`order-total.html`)

---

### Code Analysis of `order-total.html`

The original instructor code provided in the lab:
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Order total</title>
</head>
<body>
  <h2>Order total</h2>
  <div><label>Item name:</label> <input type="text" id="item" placeholder="Pho bo"></div>
  <div><label>Price:</label> <input type="number" id="price" placeholder="60000"></div>
  <div><label>Quantity:</label> <input type="number" id="qty" placeholder="3"></div>
  <div>
    <button onclick="total()">Total</button>
    <button onclick="perPerson()">Split per person</button>
  </div>
  <div id="result">The result is:</div>

  <script>
    function total() {
      const name = document.getElementById("item").value;
      const price = parseFloat(document.getElementById("price").value);
      const qty = parseFloat(document.getElementById("qty").value);

      if (isNaN(price) || isNaN(qty)) {
        document.getElementById("result").innerHTML = "Invalid input";
      }

      const sum = price * qty;
      document.getElementById("result").innerHTML = qty + " x " + name + " = " + sum;
    }

    function perPerson() {
      const name = document.getElementById("item").value;
      const price = parseFloat(document.getElementById("price").value);
      const qty = parseFloat(document.getElementById("qty").value);

      const each = price / qty;
      document.getElementById("result").innerHTML = name + ": " + each + " per person";
    }
  </script>
</body>
</html>
```

---

### Question 1: Empty Price and Missing `return` Bug

#### Test Case
- **Item name**: `Pho bo`
- **Price**: *(left empty)*
- **Quantity**: `3`
- **Action**: Click **Total**

#### What Appears on Screen?
> **Observed Output**: `3 x Pho bo = NaN`

#### Why Did `Invalid input` Disappear?
- When the Price field is left empty, `document.getElementById("price").value` evaluates to the empty string `""`.
- `parseFloat("")` fails to parse a number and returns `NaN` ("Not a Number").
- The condition `isNaN(price) || isNaN(qty)` evaluates to `true`.
- The code inside the `if` block executes: `result.innerHTML = "Invalid input"`.
- **The Fatal Flaw**: The developer **forgot to write `return;`** inside the `if` block!
- Execution continues to the next lines:
  - `const sum = NaN * 3;` $\rightarrow$ evaluates to `NaN`.
  - `result.innerHTML = 3 + " x " + "Pho bo" + " = " + NaN;`
- In less than a millisecond, the browser displays `"Invalid input"` and immediately overwrites it with `"3 x Pho bo = NaN"`. The user never sees the error message.

#### What Single Word Fixes It?
> **Answer**: Adding the word **`return;`** inside the `if` block:
```javascript
if (isNaN(price) || isNaN(qty)) {
  document.getElementById("result").textContent = "Invalid input";
  return; // <-- Halts function execution immediately!
}
```

---

### Question 2: Division by Zero and `Infinity`

#### Test Case
- **Item name**: `Pho bo`
- **Price**: `60000`
- **Quantity**: `0`
- **Action**: Click **Split per person**

#### What Appears on Screen?
> **Observed Output**: `Pho bo: Infinity per person`

#### Why Doesn't the Program Crash?
- In languages like C, Java, or Python, dividing by zero throws an unhandled runtime exception (`ZeroDivisionError` or `ArithmeticException`) and halts the program.
- In JavaScript, following the **IEEE 754 floating-point specification**, dividing a positive non-zero number by zero (`60000 / 0`) evaluates to positive infinity: **`Infinity`**.
- `Infinity` is a valid mathematical value in JavaScript.
- **What is its type?**: `typeof Infinity` is **`"number"`**.

#### What Should the User Have Seen Instead?
> **Answer**: The program should have validated input and displayed an error message:
> `"Quantity must be greater than zero"` or `"Cannot split bill among 0 people"`.

```javascript
if (qty <= 0) {
  document.getElementById("result").textContent = "Quantity must be at least 1 person!";
  return;
}
```

---

### Question 3: `innerHTML` vs. `textContent` and XSS Vulnerabilities

#### Test Case
- **Item name**: `<b>Pho bo</b>`
- **Price**: `60000`
- **Quantity**: `3`
- **Action**: Click **Total**

#### Compare Screen Text with Typed Text
- **What was typed**: `<b>Pho bo</b>` (raw string including HTML tags).
- **What appeared on screen**: The text **Pho bo** rendered in **bold font**. The `<b>` and `</b>` tags disappeared completely from view!

#### Why Did This Happen?
- The code used `.innerHTML = ...`.
- When a string is assigned to `innerHTML`, the browser engine parses it as live HTML markup. The tags `<b>` and `</b>` are converted into an HTML Bold DOM element.

#### Replacing `innerHTML` with `textContent`
When the code is updated to:
```javascript
document.getElementById("result").textContent = qty + " x " + name + " = " + sum;
```
- **New Output**: `3 x <b>Pho bo</b> = 180000`
- The characters `<b>` and `</b>` are printed literally on the screen as plain text.

#### The Security Threat: XSS (Cross-Site Scripting)
```text
When a page takes text from a user and hands it to innerHTML,
the browser does not display that text - it runs it as HTML.
Someone can make it run a script: <img src=x onerror="stealCookies()">.
This is called XSS (Cross-Site Scripting).
```
- If an input field accepts user data (e.g., forum comment, profile name) and writes it into `innerHTML`, an attacker can inject malicious JavaScript payloads to steal session tokens, hijack user accounts, or redirect users to phishing sites.

#### If `textContent` is Safer, Why Does `innerHTML` Exist?
> **Answer**: `innerHTML` exists for scenarios where developers **intentionally need to generate and inject complex HTML structure** from trusted templates.
> - **Legitimate use case**: When dynamically rendering a list of cards from a trusted local data array:
>   `container.innerHTML = '<div class="card"><h3>Title</h3><p>Desc</p></div>';`
> - **Golden Rule**: Use `textContent` for raw strings and user inputs. Only use `innerHTML` when the string consists exclusively of trusted markup written by you.

---

### Fully Corrected `order-total.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Order total (Fixed)</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    div { margin-bottom: 10px; }
    label { display: inline-block; width: 120px; }
    #result { font-weight: bold; margin-top: 15px; color: #1e3a8a; }
  </style>
</head>
<body>
  <h2>Order total</h2>
  <div><label>Item name:</label> <input type="text" id="item" placeholder="Pho bo"></div>
  <div><label>Price:</label> <input type="number" id="price" placeholder="60000"></div>
  <div><label>Quantity:</label> <input type="number" id="qty" placeholder="3"></div>
  <div>
    <button onclick="total()">Total</button>
    <button onclick="perPerson()">Split per person</button>
  </div>
  <div id="result">The result is:</div>

  <script>
    function total() {
      const name = document.getElementById("item").value.trim();
      const price = parseFloat(document.getElementById("price").value);
      const qty = parseFloat(document.getElementById("qty").value);

      // Validate empty or non-numeric inputs
      if (name === "" || isNaN(price) || isNaN(qty) || price < 0 || qty <= 0) {
        document.getElementById("result").textContent = "Invalid input: Please enter valid item, price, and quantity!";
        return; // Fix 1: Added return to stop execution!
      }

      const sum = price * qty;
      // Fix 3: Use textContent to prevent XSS injection
      document.getElementById("result").textContent = `${qty} x ${name} = ${sum.toLocaleString()} VND`;
    }

    function perPerson() {
      const name = document.getElementById("item").value.trim();
      const price = parseFloat(document.getElementById("price").value);
      const qty = parseFloat(document.getElementById("qty").value);

      // Fix 2: Check for zero/negative division
      if (isNaN(price) || isNaN(qty) || qty <= 0) {
        document.getElementById("result").textContent = "Error: Quantity must be at least 1 person to split!";
        return;
      }

      const each = price / qty;
      document.getElementById("result").textContent = `${name}: ${each.toLocaleString()} VND per person`;
    }
  </script>
</body>
</html>
```

---

# Part 2: Fix the Sign Up Page (`signup.html`)

---

### The Four Bugs Diagnostic Table

The original `signup.html` contains 4 distinct bugs:

| # | Line | Symptom on Screen | Root Cause | Exact Fix |
| :-: | :-: | :--- | :--- | :--- |
| **1** | **7** | When clicking Submit, nothing happens; Console throws: `TypeError: Cannot set properties of null (setting 'textContent')`. | **Script runs before DOM exists**: `<script>` in `<head>` executes line 7 immediately. At that moment, `<div id="message">` in `<body>` has not been parsed yet, so `box` is `null`. | Move `const box = ...` inside `checkPassword()`, or add `defer` to the script tag. |
| **2** | **13** | Typing two completely different passwords still outputs: `"Passwords match"`! | **Assignment instead of comparison**: `if (pw1 = pw2)` assigns `pw2` into `pw1`. Because non-empty strings are truthy, the condition always evaluates to true! | Change `pw1 = pw2` to strict equality: `pw1 === pw2`. |
| **3** | **21–25** | Clicking into an input field and clicking away does not display the hint; Console is completely silent. | **The `blur` event does not bubble**: Attaching a `blur` listener to the parent `<form id="signup-form">` never triggers because `blur` does not propagate up the DOM tree. | Replace the `"blur"` event with **`"focusout"`** (which bubbles), or attach `blur` directly to each `<input>`. |
| **4** | **33** | Upon clicking Submit, the page flashes, reloads, and clears all fields and messages immediately. | **Default form submission reload**: Submitting an HTML form causes the browser to reload the page by default. | Add `event.preventDefault();` inside the submit handler (or `return false;`). |

---

### Detailed Answers to the Four Questions

#### Q1. One fault makes the whole script useless before the user touches anything. Line 7 runs the moment the browser reads it. What is in `box` at that moment, and why? Give two different one-line fixes.
> **Answer**:
> - **What is in `box`**: **`null`**.
> - **Why**: The `<script>` is placed in the `<head>` of the document without a `defer` attribute. Browsers execute scripts synchronously as they are encountered. When line 7 executes, the browser has only parsed up to line 7; the `<body>` and `<div id="message">` on line 40 do not exist in the DOM tree yet.
> - **Fix 1 (Change where it sits)**: Move `<script>` to the very bottom of the document right before `</body>`.
> - **Fix 2 (Change when line 7 runs)**: Move `const box = document.getElementById("message");` inside the `checkPassword()` function so it only queries the DOM when the user clicks Submit.

#### Q2. Press Submit with two identical passwords, then with two different ones. The message is the same both times. Which line causes that, and what does that line actually do to `pw1`?
> **Answer**:
> - **The Culprit Line**: Line 13: `if (pw1 = pw2)`.
> - **What it actually does**: It uses the single equals sign `=` (assignment operator) instead of `===` (comparison operator). It **assigns the value of `pw2` into the variable `pw1`**. The evaluation result of an assignment expression is the assigned value itself. Since any non-empty string in JavaScript is **truthy**, the `if` condition always evaluates to `true`, erroneously reporting `"Passwords match"` every single time!

#### Q3. The hint under the form is supposed to appear when you click into a field and then click away. It never appears, and the Console stays clean. The listener is attached correctly and the function is correct — so why is it never called? Name the property of the `blur` event that is responsible, and name the event you would use instead.
> **Answer**:
> - **Why it is never called**: The listener was attached to the `<form>` container, expecting input events to bubble up to the form. However, the `blur` event **does not bubble**!
> - **Property responsible**: `event.bubbles = false`.
> - **Event to use instead**: **`focusout`**. The `focusout` event is identical to `blur` except that it has `bubbles = true`, allowing event delegation on parent containers like forms.

#### Q4. After you fix everything, the page still reloads and blanks itself when you press Submit. What does a `<form>` do by default when it is submitted, and what one line inside `checkPassword` stops it? Why did `Preserve log` matter while you were hunting this one?
> **Answer**:
> - **Default `<form>` behavior**: By default, submitting a form issues an HTTP request to the current URL and **triggers a full browser page reload**.
> - **The one line to stop it**: **`event.preventDefault();`** (or receiving `event` and returning `false`).
> - **Why `Preserve log` mattered**: When a page reloads, the browser clears the Console panel. Any runtime errors (such as `TypeError: Cannot set properties of null`) appear for a fraction of a millisecond and vanish with the reload. Ticking **"Preserve log"** in DevTools prevents the Console from wiping on reload, allowing developers to read the error.

---

### Fully Corrected `signup.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Sign Up (Fixed)</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    div { margin-bottom: 10px; }
    label { display: inline-block; width: 140px; }
    #message { font-weight: bold; margin-top: 15px; }
    #hint { color: #666; font-style: italic; margin-top: 5px; }
  </style>
</head>
<body>

  <h2>Sign Up</h2>

  <form id="signup-form">
    <div><label>Username:</label> <input type="text" id="user"></div>
    <div><label>Password:</label> <input type="password" id="pw1"></div>
    <div><label>Re-type Password:</label> <input type="password" id="pw2"></div>
    <button type="submit">Submit</button>
  </form>

  <div id="message"></div>
  <div id="hint"></div>

  <script>
    // Fix 1 & Fix 4: Attach submit listener properly and prevent reload
    const form = document.getElementById("signup-form");
    const box = document.getElementById("message");
    const hint = document.getElementById("hint");

    form.addEventListener("submit", function (event) {
      event.preventDefault(); // Fix 4: Halts browser page reload

      const pw1 = document.getElementById("pw1").value;
      const pw2 = document.getElementById("pw2").value;

      if (pw1 === "") {
        box.textContent = "Please enter a password.";
        box.style.color = "red";
        return;
      }

      // Fix 2: Strict comparison === instead of assignment =
      if (pw1 === pw2) {
        box.textContent = "Passwords match";
        box.style.color = "green";
      } else {
        box.textContent = "Passwords do not match";
        box.style.color = "red";
      }
    });

    // Fix 3: Use "focusout" instead of "blur" because focusout bubbles!
    form.addEventListener("focusout", function (e) {
      if (e.target.tagName === "INPUT") {
        hint.textContent = "You left the " + (e.target.id || "input") + " field";
      }
    });
  </script>
</body>
</html>
```

---

# Part 3: Write `app.js` Without Touching the HTML (`tasks.html`)

---

### The "One Rule" Constraint
> **`tasks.html` is finished. You may not change a single character of it. Everything you write goes into `app.js`.**

---

### Complete, Production-Ready `app.js`

```javascript
// ============================================================================
// USTH Web Application Development - Exercise 2.2 Complete Solution
// File: app.js
// Target: tasks.html (Unmodified HTML)
// ============================================================================

// ----------------------------------------------------------------------------
// Task 1: Highlight the Right Headings
// When Highlight is pressed, every <h1> that is a DIRECT child of a <div>
// receives class "highlight". Write count into #t1-count.
// ----------------------------------------------------------------------------
const highlightBtn = document.getElementById("highlight-btn");
const t1Count = document.getElementById("t1-count");

if (highlightBtn) {
  highlightBtn.addEventListener("click", () => {
    // Direct child selector: "div > h1"
    const directHeadings = document.querySelectorAll("div > h1");

    directHeadings.forEach(h1 => {
      h1.classList.add("highlight");
    });

    t1Count.textContent = `Found ${directHeadings.length} direct child headings.`;
  });
}

// ----------------------------------------------------------------------------
// Task 2: Click Timer
// First click records moment. Second click writes gap in ms into #t2-log.
// Third click starts fresh pair, fourth reports again, and so on.
// ----------------------------------------------------------------------------
const target = document.getElementById("target");
const t2Log = document.getElementById("t2-log");

// Outer closure variable to persist state across individual clicks
let firstClickMoment = null;

if (target) {
  target.addEventListener("click", () => {
    if (firstClickMoment === null) {
      // First click of the pair
      firstClickMoment = Date.now();
      t2Log.textContent = "First click recorded! Click again...";
      t2Log.style.color = "#d97706"; // Amber
    } else {
      // Second click of the pair
      const secondClickMoment = Date.now();
      const elapsedMs = secondClickMoment - firstClickMoment;

      t2Log.textContent = `Gap: ${elapsedMs} ms (${(elapsedMs / 1000).toFixed(3)}s)`;
      t2Log.style.color = "#16a34a"; // Green

      // Reset to null so click 3 begins a brand-new pair
      firstClickMoment = null;
    }
  });
}

// ----------------------------------------------------------------------------
// Task 3: Load the Menu from a File
// Fetch menu.json, add one <li> per dish into #menu-list showing dish + price.
// Put "Loading..." into #t3-status while it runs, and clear when list appears.
// ----------------------------------------------------------------------------
const loadBtn = document.getElementById("load-btn");
const menuList = document.getElementById("menu-list");
const t3Status = document.getElementById("t3-status");

if (loadBtn) {
  loadBtn.addEventListener("click", async () => {
    t3Status.textContent = "Loading...";
    t3Status.style.color = "#2563eb";
    menuList.innerHTML = ""; // Clear existing list

    try {
      const response = await fetch("menu.json");

      // Verify HTTP status
      if (!response.ok) {
        throw new Error(`Server returned HTTP ${response.status}`);
      }

      const dishes = await response.json();

      // Render items
      dishes.forEach(item => {
        const li = document.createElement("li");
        li.textContent = `${item.dish} - ${item.price.toLocaleString()} VND`;
        menuList.append(li);
      });

      // Clear loading status on success
      t3Status.textContent = "";
    } catch (error) {
      console.error("Fetch failed:", error);
      t3Status.textContent = `Could not load menu: ${error.message}`;
      t3Status.style.color = "#dc2626"; // Red
    }
  });
}
```

---

### Task 1: Child Combinator (`div > h1` vs. `div h1`)

#### Analysis of HTML Structure in `tasks.html`
```html
<div>
  <h1>Introduction</h1>
  <section>
    <h1>Buried inside a section</h1>
  </section>
</div>
<div>
  <h1>About HTML</h1>
  <h1>About CSS</h1>
</div>
<h1>About JavaScript</h1>
```

#### The "Why" Comparison
- If you run: `document.querySelectorAll("div h1")` (Descendant selector):
  - Returns **4 elements**: `Introduction`, `Buried inside a section`, `About HTML`, `About CSS`.
  - It matches any `<h1>` that is a descendant of a `<div>` at any arbitrary nesting depth.
- If you run: `document.querySelectorAll("div > h1")` (Child selector):
  - Returns **3 elements**: `Introduction`, `About HTML`, `About CSS`.
  - It rejects `Buried inside a section` because its immediate parent is `<section>`, NOT `<div>`.
- **Wording in the Exercise**: *"h1 elements that are children of a div"*. In CSS terminology, "child" means direct first-level offspring. Therefore, **`"div > h1"`** is the exact selector matching the specification.

---

### Task 2: Two-Click Stopwatch Closure Logic

#### Why Can't the Variable Live Inside the Click Handler?
```javascript
// BROKEN APPROACH:
target.addEventListener("click", () => {
  let firstClickMoment = null; // Re-initialized to null on EVERY click!
  ...
});
```
- A variable declared inside a function is scoped locally to that function execution. Every time the user clicks, the function is invoked anew, creating a brand new `firstClickMoment = null`. The function has amnesia and can never calculate a difference.
- **The Fix**: The variable must be declared in the **outer scope** (module or global scope) so that its value persists across multiple independent click event executions.

#### Why Must We Reset to `null` on the Second Click?
- Once the gap is calculated on Click 2, resetting `firstClickMoment = null` ensures that Click 3 acts as the beginning of a fresh measurement pair.
- **What happens if you forget to reset?**: If you don't reset, Click 3 will treat Click 1 as the start time, reporting the elapsed time from Click 1 to Click 3. Click 4 will report the time from Click 1 to Click 4, and so on.

---

### Task 3: Fetching `menu.json`, CORS & Same-Origin Policy

#### (a) Double-Clicking `tasks.html` in File Manager
1. Address bar displays: `file:///C:/Users/.../tasks.html`.
2. Click **Load menu**.
3. **Exact Error in Console**:
   ```text
   Access to fetch at 'file:///C:/.../menu.json' from origin 'null' has been blocked by CORS policy: 
   Cross origin requests are only supported for protocol schemes: http, data, https...
   Failed to load resource: net::ERR_FAILED
   Uncaught (in promise) TypeError: Failed to fetch
   ```

#### (b) Opening via VS Code Live Server
1. Address bar displays: `http://127.0.0.1:5500/tasks.html`.
2. Click **Load menu**.
3. **Result**: Status shows `Loading...`, then menu items render smoothly.

#### Who Refused to Serve the File: The Browser or the Server?
> **Answer**: **THE BROWSER REFUSED!**
> - In case (a), there was **no web server running at all**. The browser itself blocked the request.
> - Web browsers enforce the **Same-Origin Policy (SOP)**. Under the `file:///` protocol, the origin is evaluated as `null`. Because an origin of `null` cannot establish mutual trust with local files, the browser engine blocks JavaScript from reading arbitrary files from your hard drive to prevent malicious downloaded HTML files from stealing private documents.

---

# Oral Check & Midterm Exam Survival Guide

1. *"Why did `sum` equal `NaN` when price was empty?"*  
   $\rightarrow$ `parseFloat("")` returns `NaN`. Any arithmetic with `NaN` yields `NaN` (`NaN * 3 = NaN`).
2. *"Why did `Invalid input` not stay on screen?"*  
   $\rightarrow$ The `if` statement was missing `return;`, causing execution to fall through and immediately overwrite `innerHTML`.
3. *"Why does `60000 / 0` return `Infinity` instead of crashing?"*  
   $\rightarrow$ JavaScript numbers conform to IEEE 754 floating-point standards where non-zero division by zero evaluates to `Infinity` of type `"number"`.
4. *"Why did `if (pw1 = pw2)` always evaluate to true?"*  
   $\rightarrow$ Single `=` is assignment, not comparison. It assigns `pw2` into `pw1`, returning a non-empty string which is truthy.
5. *"Why did the `blur` event fail on the `<form>` element?"*  
   $\rightarrow$ The `blur` event has `bubbles: false`. It does not propagate up the DOM tree to parent elements. You must use `focusout` instead.
6. *"What is the difference between `div h1` and `div > h1`?"*  
   $\rightarrow$ `div h1` matches any descendant `h1` at any depth. `div > h1` strictly matches direct first-level children.
