# Web Application Development — Exercise 2.1 Solution & Code Guide
**University of Science and Technology of Hanoi (USTH)**  
**Module:** Web Application Development (JavaScript Basic Labwork)  
**File Reference:** `Exercise2.1 - JavaScript (basic).pdf`  
**Purpose:** Complete reference solutions, interactive HTML/JS implementations, and line-by-line explanations for midterm exam preparation.

---

## Table of Contents
1. [Labwork Overview & Core Concepts](#labwork-overview--core-concepts)
2. [Question 1: Temperature Converter (Celsius $\leftrightarrow$ Fahrenheit)](#question-1-temperature-converter-celsius--fahrenheit)
3. [Question 2: Find the Largest of Five Numbers](#question-2-find-the-largest-of-five-numbers)
4. [Question 3: Odd or Even Number Iterator (1 to 15)](#question-3-odd-or-even-number-iterator-1-to-15)
5. [Question 4: Sign Up Form & Password Matching Validation](#question-4-sign-up-form--password-matching-validation)
6. [Question 5: Multiplication and Division Calculator](#question-5-multiplication-and-division-calculator)
7. [Question 6: Child Selector (`div > h1`) & Background Styling](#question-6-child-selector-div--h1--background-styling)
8. [Question 7: The `blur` Event Handler](#question-7-the-blur-event-handler)
9. [Question 8: Styled Hyperlinks (`:visited` & `:hover`)](#question-8-styled-hyperlinks-visited--hover)
10. [Question 9: Click Timing Stopwatch (Milliseconds Between Two Clicks)](#question-9-click-timing-stopwatch-milliseconds-between-two-clicks)
11. [Midterm Exam Cheat Sheet for Lab 2.1](#midterm-exam-cheat-sheet-for-lab-21)

---

## Labwork Overview & Core Concepts

This labwork reinforces fundamental JavaScript programming concepts:
- Mathematical calculations, formula conversions, and numeric data types.
- Conditional statements (`if / else`), comparison operators, and loops (`for`).
- Form handling, input extraction (`.value`), and client-side validation.
- DOM manipulation (`document.getElementById`, `document.querySelectorAll`).
- Event listeners (`click`, `blur`, `submit`) and event timing (`Date.now()`).
- CSS pseudo-classes and child combinators (`div > h1`).

---

## Question 1: Temperature Converter (Celsius $\leftrightarrow$ Fahrenheit)

### Requirement
Write a JavaScript program to convert temperatures to and from Celsius and Fahrenheit using the formula:
```text
c / 5 = (f - 32) / 9
```
Where `c` is the temperature in Celsius and `f` is the temperature in Fahrenheit.
- Derivation for Celsius to Fahrenheit: `f = (c * 9 / 5) + 32`
- Derivation for Fahrenheit to Celsius: `c = (f - 32) * 5 / 9`

### Complete Code (`q1_temperature.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Temperature Converter</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    .box { margin-bottom: 15px; }
    label { display: inline-block; width: 120px; }
  </style>
</head>
<body>
  <h2>Temperature Converter</h2>
  
  <div class="box">
    <label for="celsius">Celsius (°C):</label>
    <input type="number" id="celsius" placeholder="Enter Celsius">
    <button onclick="convertToFahrenheit()">Convert to °F</button>
  </div>

  <div class="box">
    <label for="fahrenheit">Fahrenheit (°F):</label>
    <input type="number" id="fahrenheit" placeholder="Enter Fahrenheit">
    <button onclick="convertToCelsius()">Convert to °C</button>
  </div>

  <p id="temp-result" style="font-weight: bold; color: #0d3b66;"></p>

  <script>
    function convertToFahrenheit() {
      const cInput = document.getElementById("celsius").value;
      if (cInput === "") {
        alert("Please enter a Celsius temperature!");
        return;
      }
      const c = parseFloat(cInput);
      const f = (c * 9 / 5) + 32;
      document.getElementById("temp-result").textContent = 
        `${c}°C is equal to ${f.toFixed(2)}°F`;
      document.getElementById("fahrenheit").value = f.toFixed(2);
    }

    function convertToCelsius() {
      const fInput = document.getElementById("fahrenheit").value;
      if (fInput === "") {
        alert("Please enter a Fahrenheit temperature!");
        return;
      }
      const f = parseFloat(fInput);
      const c = (f - 32) * 5 / 9;
      document.getElementById("temp-result").textContent = 
        `${f}°F is equal to ${c.toFixed(2)}°C`;
      document.getElementById("celsius").value = c.toFixed(2);
    }
  </script>
</body>
</html>
```

### Line-by-Line Explanation
- `const cInput = document.getElementById("celsius").value;`: Extracts the text string entered into the input box.
- `if (cInput === "")`: Validates that the input is not empty before performing mathematical operations.
- `const c = parseFloat(cInput);`: Converts the string into a floating-point number.
- `const f = (c * 9 / 5) + 32;`: Implements the mathematical conversion formula.
- `f.toFixed(2)`: Formats the resulting number to 2 decimal places.
- `document.getElementById("temp-result").textContent = ...`: Safely injects the human-readable result into the DOM.

---

## Question 2: Find the Largest of Five Numbers

### Requirement
Write a JavaScript program to find the largest of five numbers. Display an `alert()` box showing the result.

### Complete Code (`q2_largest.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Largest of Five Numbers</title>
</head>
<body>
  <h2>Find the Largest of 5 Numbers</h2>
  <button onclick="findLargest()">Find Largest</button>

  <script>
    function findLargest() {
      // Five sample numbers
      const num1 = -5;
      const num2 = -2;
      const num3 = -6;
      const num4 = 0;
      const num5 = -1;

      // Method 1: Using Math.max()
      const largest = Math.max(num1, num2, num3, num4, num5);

      // Display via alert box as requested
      alert(`The numbers are: ${num1}, ${num2}, ${num3}, ${num4}, ${num5}\nThe largest number is: ${largest}`);
    }

    // Method 2: Algorithmic approach using conditionals (Exam Alternative)
    function findLargestManual(a, b, c, d, e) {
      let max = a;
      if (b > max) max = b;
      if (c > max) max = c;
      if (d > max) max = d;
      if (e > max) max = e;
      return max;
    }
  </script>
</body>
</html>
```

### Line-by-Line Explanation
- `Math.max(num1, num2, num3, num4, num5)`: Built-in JavaScript function that returns the largest numerical argument passed. Works correctly with negative values, zero, and decimals.
- `alert(...)`: Browser method that halts execution and opens a modal alert dialog showing the result to the user.
- `findLargestManual`: Algorithmic conditional comparison initializing `max = a` and comparing each subsequent number sequentially.

---

## Question 3: Odd or Even Number Iterator (1 to 15)

### Requirement
Write a JavaScript program that iterates from 1 to 15. For each iteration, check whether the current number is odd or even, and display a message to the screen.  
Output format:
```text
1 is odd
2 is even
...
15 is odd
```

### Complete Code (`q3_odd_even.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Odd or Even Iterator</title>
  <style>
    body { font-family: monospace; padding: 20px; }
    .even { color: blue; }
    .odd { color: crimson; }
  </style>
</head>
<body>
  <h2>Iteration 1 to 15 (Odd or Even)</h2>
  <ul id="output-list"></ul>

  <script>
    const outputList = document.getElementById("output-list");

    for (let i = 1; i <= 15; i++) {
      const li = document.createElement("li");
      
      // Modulo operator % checks remainder when divided by 2
      if (i % 2 === 0) {
        li.textContent = `${i} is even`;
        li.className = "even";
      } else {
        li.textContent = `${i} is odd`;
        li.className = "odd";
      }

      outputList.append(li);
    }
  </script>
</body>
</html>
```

### Line-by-Line Explanation
- `for (let i = 1; i <= 15; i++)`: Standard loop starting at 1 and terminating after 15.
- `if (i % 2 === 0)`: The modulo operator `%` calculates the integer division remainder. If `i % 2 === 0`, the number divides evenly by 2 and is **even**. Otherwise, it is **odd**.
- `document.createElement("li")` and `.append(li)`: Constructs a new `<li>` element for each iteration and appends it to the parent `<ul>`.

---

## Question 4: Sign Up Form & Password Matching Validation

### Requirement
Create a Sign Up form with:
- `Username` (text input)
- `Password` (password input)
- `Re-type Password` (password input)
- `Reset` and `Submit` buttons
- Write a JavaScript function called when the user clicks "Submit" to verify that both passwords are identical.

### Complete Code (`q4_signup.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sign Up Form</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 30px; }
    .form-container { width: 320px; margin: 0 auto; }
    h2 { text-align: center; }
    .form-row { margin-bottom: 12px; display: flex; justify-content: space-between; }
    label { font-weight: bold; font-size: 14px; }
    input { width: 160px; padding: 4px; }
    .button-row { text-align: center; margin-top: 15px; }
    button { padding: 6px 14px; margin: 0 5px; cursor: pointer; }
    #msg { text-align: center; margin-top: 15px; font-weight: bold; }
  </style>
</head>
<body>
  <div class="form-container">
    <h2>Sign Up</h2>
    <form id="signup-form">
      <div class="form-row">
        <label for="username">Username:</label>
        <input type="text" id="username" required>
      </div>
      <div class="form-row">
        <label for="password">Password:</label>
        <input type="password" id="password" required>
      </div>
      <div class="form-row">
        <label for="repassword">Re-type Password:</label>
        <input type="password" id="repassword" required>
      </div>
      <div class="button-row">
        <button type="reset">Reset</button>
        <button type="submit">Submit</button>
      </div>
    </form>
    <div id="msg"></div>
  </div>

  <script>
    const form = document.getElementById("signup-form");
    const msg = document.getElementById("msg");

    form.addEventListener("submit", function (event) {
      // 1. Prevent default form submission and page reload
      event.preventDefault();

      // 2. Extract values
      const user = document.getElementById("username").value.trim();
      const pw1 = document.getElementById("password").value;
      const pw2 = document.getElementById("repassword").value;

      // 3. Validation
      if (user === "") {
        msg.textContent = "Username cannot be empty!";
        msg.style.color = "red";
        return;
      }

      if (pw1 === "") {
        msg.textContent = "Password cannot be empty!";
        msg.style.color = "red";
        return;
      }

      // Check whether passwords are strictly identical
      if (pw1 === pw2) {
        msg.textContent = "Success: Passwords match!";
        msg.style.color = "green";
      } else {
        msg.textContent = "Error: Passwords do not match!";
        msg.style.color = "red";
      }
    });
  </script>
</body>
</html>
```

### Line-by-Line Explanation & Traps
- `event.preventDefault()`: **Critical!** Without this, the browser submits the form immediately and reloads the page, wiping out the validation message.
- `if (pw1 === pw2)`: Uses strict equality `===`.
- `<button type="reset">`: Built-in HTML form button that automatically resets all input fields to their initial empty states.

---

## Question 5: Multiplication and Division Calculator

### Requirement
Write a JavaScript program to calculate the multiplication and division of two numbers using an HTML form.  
Interface layout:
- `1st Number : [input]`
- `2nd Number : [input]`
- Buttons: `Multiply`, `Divide`
- Output: `The Result is : [result]`

### Complete Code (`q5_calculator.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Multiply and Divide Calculator</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    .form-group { margin-bottom: 10px; }
    label { display: inline-block; width: 110px; }
    .actions { margin-top: 15px; margin-bottom: 15px; }
    button { padding: 5px 12px; margin-right: 10px; cursor: pointer; }
    #result-box { font-size: 16px; font-weight: bold; }
  </style>
</head>
<body>
  <h3>Multiply and Divide two numbers:</h3>

  <div class="form-group">
    <label for="num1">1st Number :</label>
    <input type="number" id="num1" placeholder="Enter first number">
  </div>

  <div class="form-group">
    <label for="num2">2nd Number :</label>
    <input type="number" id="num2" placeholder="Enter second number">
  </div>

  <div class="actions">
    <button onclick="multiply()">Multiply</button>
    <button onclick="divide()">Divide</button>
  </div>

  <div id="result-box">The Result is : <span id="result"></span></div>

  <script>
    function getNumbers() {
      const val1 = document.getElementById("num1").value;
      const val2 = document.getElementById("num2").value;

      if (val1 === "" || val2 === "") {
        alert("Please enter both numbers!");
        return null;
      }

      const n1 = parseFloat(val1);
      const n2 = parseFloat(val2);

      if (isNaN(n1) || isNaN(n2)) {
        alert("Invalid numbers provided!");
        return null;
      }

      return { n1, n2 };
    }

    function multiply() {
      const nums = getNumbers();
      if (!nums) return;

      const res = nums.n1 * nums.n2;
      document.getElementById("result").textContent = res;
    }

    function divide() {
      const nums = getNumbers();
      if (!nums) return;

      // Division by zero check
      if (nums.n2 === 0) {
        alert("Error: Division by zero is undefined!");
        document.getElementById("result").textContent = "Cannot divide by zero";
        return;
      }

      const res = nums.n1 / nums.n2;
      document.getElementById("result").textContent = res;
    }
  </script>
</body>
</html>
```

### Line-by-Line Explanation
- `getNumbers()`: Helper function to extract, validate, and parse inputs, avoiding code duplication across buttons.
- `if (nums.n2 === 0)`: **Crucial check!** In JavaScript, `x / 0` evaluates to `Infinity` without throwing an error. A robust calculator checks for zero explicitly.
- `document.getElementById("result").textContent = res;`: Updates the inner text of `#result`.

---

## Question 6: Child Selector (`div > h1`) & Background Styling

### Requirement
Given the HTML:
```html
<body>
  <h1>Introduction</h1>
  <div>
    <h1>About HTML</h1>
    <h1>About CSS</h1>
  </div>
  <h1>About JavaScript</h1>
</body>
```
Find all `h1` elements that are children of a `div` element and apply a background to them.

### Complete Code (`q6_selectors.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Child Selector Styling</title>
  <style>
    /* CSS Child Selector: targets h1 that is an immediate direct child of div */
    div > h1 {
      background-color: #ffe082;
      color: #333;
      padding: 6px;
      border-left: 4px solid #ffb300;
      margin: 6px 0;
    }
  </style>
</head>
<body>
  <h1>Introduction</h1>
  <div>
    <h1>About HTML</h1>
    <h1>About CSS</h1>
  </div>
  <h1>About JavaScript</h1>

  <script>
    // Pure JavaScript Alternative via DOM API:
    // querySelectorAll("div > h1") selects only the two headings inside the div
    const divHeadings = document.querySelectorAll("div > h1");
    divHeadings.forEach(h1 => {
      h1.style.backgroundColor = "gold";
    });
  </script>
</body>
</html>
```

### Line-by-Line Explanation & CSS Combinator Distinction
- `div > h1`: **Direct Child Combinator**. Targets `<h1>` elements whose immediate parent is a `<div>`.
  - It matches: `<h1>About HTML</h1>` and `<h1>About CSS</h1>`.
  - It does **NOT** match: `<h1>Introduction</h1>` or `<h1>About JavaScript</h1>` (their parent is `<body>`).
- *Difference between `div h1` and `div > h1`*: `div h1` matches any `h1` descendant at any depth (e.g. `<div><section><h1>Nested</h1></section></div>`). `div > h1` matches only immediate 1st-level children.

---

## Question 7: The `blur` Event Handler

### Requirement
Attach a function to the `blur` event that occurs when `<input id="field1">` loses focus:
```html
<form>
  <input id="field1" type="text" value="Field 1">
  <input id="field2" type="text" value="Field 2">
</form>
```

### Complete Code (`q7_blur.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Blur Event Demo</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    input { padding: 6px; margin: 6px; }
    #status { margin-top: 10px; font-style: italic; color: #555; }
  </style>
</head>
<body>
  <h2>Blur Event Demonstration</h2>
  <form>
    <input id="field1" type="text" value="Field 1">
    <input id="field2" type="text" value="Field 2">
  </form>
  <p id="status">Click into Field 1, then click into Field 2 to trigger blur.</p>

  <script>
    const field1 = document.getElementById("field1");
    const statusText = document.getElementById("status");

    // Attach listener to the 'blur' event
    field1.addEventListener("blur", function () {
      statusText.textContent = `Field 1 lost focus at ${new Date().toLocaleTimeString()}! Value: "${field1.value}"`;
      field1.style.borderColor = "red";
    });

    // Optional: Restore style on focus
    field1.addEventListener("focus", function () {
      field1.style.borderColor = "blue";
    });
  </script>
</body>
</html>
```

### Line-by-Line Explanation
- **What is `blur`?**: The `blur` event fires when an interactive element (e.g., an input field) **loses focus** (i.e. the user clicks outside it or presses Tab to jump to the next field).
- `field1.addEventListener("blur", ...)`: Registers the callback function to execute on blur.
- Common practical use case: Triggering immediate field-level input validation (e.g., checking if an email format is valid as soon as the user finishes typing and leaves the field).

---

## Question 8: Styled Hyperlinks (`:visited` & `:hover`)

### Requirement
Create a web page named `task8.html` containing three links to other pages:
- Use `text-decoration: none` to remove underlines.
- If a link is visited, its color becomes red.
- Change link color to green when hovered.

### Complete Code (`task8.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>task8.html - Styled Links</title>
  <style>
    /* Unvisited links */
    a:link {
      text-decoration: none; /* Removes underline */
      color: blue;
      font-size: 18px;
      margin-right: 15px;
    }

    /* Visited links */
    a:visited {
      text-decoration: none;
      color: red; /* Red when visited */
    }

    /* Hovered links */
    a:hover {
      text-decoration: underline; /* Optional: adds underline on hover */
      color: green; /* Green when hovered */
    }

    /* Active links */
    a:active {
      color: orange;
    }
  </style>
</head>
<body>
  <h2>Styled Hyperlinks (LVHA Order)</h2>
  <p>
    <a href="https://usth.edu.vn">USTH</a>
    <a href="https://google.com">Google</a>
    <a href="https://github.com">GitHub</a>
  </p>
</body>
</html>
```

### Midterm Exam Tip: The LVHA Ordering Rule
The selectors must be written in this exact sequence:
1. `:link`
2. `:visited`
3. `:hover`
4. `:active`
If `:visited` is placed below `:hover`, a visited link will never turn green because `:visited` overrides the hover state.

---

## Question 9: Click Timing Stopwatch (Milliseconds Between Two Clicks)

### Requirement
Count the number of milliseconds between two click events on a paragraph.
Sample HTML:
```html
<body>
  <h1>Heading1</h1>
  <h2>Heading2</h2>
  <p>Paragraph</p>
  <button>Button</button>
  <div id="log"></div>
</body>
```

### Complete Code (`q9_click_timer.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Click Time Counter</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    p {
      padding: 15px;
      background-color: #f0f4f8;
      border: 1px solid #cbd5e1;
      cursor: pointer;
      display: inline-block;
      user-select: none;
    }
    #log {
      margin-top: 15px;
      font-weight: bold;
      color: #1e3a8a;
    }
  </style>
</head>
<body>
  <h1>Heading1</h1>
  <h2>Heading2</h2>
  <p id="clickable-p">Paragraph (Click me twice!)</p>
  <br>
  <button id="reset-btn">Reset</button>
  <div id="log"></div>

  <script>
    const targetPara = document.getElementById("clickable-p");
    const logDiv = document.getElementById("log");
    const resetBtn = document.getElementById("reset-btn");

    let firstClickTime = null;

    targetPara.addEventListener("click", function () {
      if (firstClickTime === null) {
        // First click: record the starting timestamp
        firstClickTime = Date.now();
        logDiv.textContent = "First click recorded! Click again to measure time gap...";
        logDiv.style.color = "orange";
      } else {
        // Second click: compute elapsed milliseconds
        const secondClickTime = Date.now();
        const diffMs = secondClickTime - firstClickTime;

        logDiv.textContent = `Time elapsed between the two clicks: ${diffMs} ms (${(diffMs / 1000).toFixed(3)} seconds)`;
        logDiv.style.color = "green";

        // Reset state so subsequent clicks measure a new pair
        firstClickTime = null;
      }
    });

    resetBtn.addEventListener("click", function () {
      firstClickTime = null;
      logDiv.textContent = "Timer reset. Click the paragraph to start.";
      logDiv.style.color = "#1e3a8a";
    });
  </script>
</body>
</html>
```

### Line-by-Line Explanation
- `let firstClickTime = null;`: State variable declared outside the event listener closure to remember the timestamp between clicks.
- `Date.now()`: Returns current Unix epoch time in milliseconds.
- `const diffMs = secondClickTime - firstClickTime;`: Calculates the exact difference in milliseconds.
- `firstClickTime = null;`: Resets the variable after reporting so that click 3 and click 4 measure a fresh interval.

---

## Midterm Exam Cheat Sheet for Lab 2.1

1. **`event.preventDefault()`**: Must be called on form submit to avoid full-page reloads.
2. **`Date.now()` vs `performance.now()`**: `Date.now()` gives millisecond timestamps; `performance.now()` provides microsecond precision.
3. **The `blur` Event**: Does **not bubble**. Fires when an input field loses focus.
4. **Child Combinator (`>`)**: `div > h1` matches only immediate children, whereas `div h1` matches any descendant at any nesting depth.
5. **Division by Zero**: In JavaScript, `10 / 0` evaluates to `Infinity`, not an error. Always check `if (divisor === 0)`.
