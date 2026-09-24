# Web Application Development — Exercise 1.2 Solution & Deep-Dive Guide
**University of Science and Technology of Hanoi (USTH)**  
**Module:** Web Application Development (HTML + CSS: Read It, Break It, Fix It, Style It)  
**File Reference:** `Exercise1.2 - HTML+CSS (Advanced).pdf`  
**Purpose:** Complete reference solutions, code predictions, debugging tables, and exhaustive "Why" answers for the advanced hands-on lab.

---

## Table of Contents
1. [Lab Learning Outcomes & Workflow](#lab-learning-outcomes--workflow)
2. [Part 1: Read the Code, Predict the Screen](#part-1-read-the-code-predict-the-screen)
   - [Q1: How Many Lines Appear on Screen? (Block vs. Inline)](#q1-how-many-lines-appear-on-screen-block-vs-inline)
   - [Q2: Which Colour Wins? (Specificity & Cascade Rules)](#q2-which-colour-wins-specificity--cascade-rules)
   - [Q3: How Much Space Does the Box Take? (Box Model Calculations)](#q3-how-much-space-does-the-box-take-box-model-calculations)
   - [Q4: Same CSS, One Extra Line (`box-sizing: border-box`)](#q4-same-css-one-extra-line-box-sizing-border-box)
   - [Q5: The `style` Attribute (`!important` Trap)](#q5-the-style-attribute-important-trap)
3. [Part 2: Find the Mistakes (`broken.html`)](#part-2-find-the-mistakes-brokenhtml)
   - [The 9 Mistakes Answer Table](#the-9-mistakes-answer-table)
   - [Answers to the Three Questions Under the Table](#answers-to-the-three-questions-under-the-table)
   - [Fully Corrected `fixed.html` Code](#fully-corrected-fixedhtml-code)
4. [Part 3: Look Inside a Real Page with F12 (DevTools)](#part-3-look-inside-a-real-page-with-f12-devtools)
   - [The 5 DevTools Essentials](#the-5-devtools-essentials)
   - [Task 1: Identify Element](#task-1-identify-element)
   - [Task 2: Declared vs. Computed Values](#task-2-declared-vs-computed-values)
   - [Task 3: The Box Model Arithmetic](#task-3-the-box-model-arithmetic)
   - [Task 4: Who Won the Fight?](#task-4-who-won-the-fight)
   - [Task 5: Switching Declarations Off](#task-5-switching-declarations-off)
   - [Task 6: The Client-Server Question That Matters](#task-6-the-client-server-question-that-matters)
   - [Task 7: Two Ways of Looking (`Ctrl+U` vs. Elements Tab)](#task-7-two-ways-of-looking-ctrlu-vs-elements-tab)
5. [Part 4: Style a Page Without Touching the HTML (`ict-department.html`)](#part-4-style-a-page-without-touching-the-html-ict-departmenthtml)
   - [The "One Rule" Constraint](#the-one-rule-constraint)
   - [Complete, Working `style.css` File](#complete-working-stylecss-file)
   - [Tasks T1–T13: CSS Code & Exhaustive "Why" Explanations](#tasks-t1t13-css-code--exhaustive-why-explanations)
6. [Oral Check & Midterm Exam Survival Guide](#oral-check--midterm-exam-survival-guide)

---

## Lab Learning Outcomes & Workflow

By completing this lab, you master:
1. **Predictive Reading**: Looking at raw HTML and CSS and visualizing the exact pixel layout before opening a browser.
2. **Cascade & Specificity Calculation**: Mathematically determining which CSS rule overrides another when selectors clash.
3. **The Box Model**: Calculating exact pixel consumption using `content-box` vs. `border-box`.
4. **Debugging**: Spotting syntax, semantic, and inheritance errors in existing code.
5. **DOM vs. Source**: Understanding how Chrome DevTools operates and how the client-side DOM differs from static HTTP responses.
6. **Constraint-Based Styling**: Writing complete stylesheets without modifying existing HTML markup.

---

# Part 1: Read the Code, Predict the Screen

---

### Q1: How Many Lines Appear on Screen? (Block vs. Inline)

#### Code Snippet
```html
<div>Pho bo</div>
<div>Pho ga</div>
<span>Bun cha</span>
<span>Banh mi</span>
<p>Com tam</p>
```

#### Toolbox & Concepts
- **Tags**: `<div>`, `<span>`, `<p>`
- **Core Concept**: Block-level vs. Inline display behaviors.

#### Questions & Official Answers

**Q1. How many separate lines does the browser draw?**
> **Answer**: Exactly **4 separate lines**.

**Q2. Write down which text sits on which line.**
> **Answer**:
> - **Line 1**: `Pho bo`
> - **Line 2**: `Pho ga`
> - **Line 3**: `Bun cha Banh mi` (Both sit on the same line!)
> - **Line 4**: `Com tam`

**Q3. `<span>` and `<div>` have no colour and no border of their own. So why does the screen look different?**
> **Answer**: Because `<div>` is a **block-level element** by default, whereas `<span>` is an **inline element**:
> - A `<div>` generates a block formatting context: It always breaks onto a **new line** and expands horizontally to take **100% of the available width**, pushing subsequent content down.
> - A `<span>` stays **inline within the current text flow**: It only occupies the horizontal width of its enclosed text, allowing adjacent inline elements (`Bun cha` and `Banh mi`) to sit side-by-side on the exact same line.
> - `<p>` is also block-level, so it forces itself onto a new line below the `<span>` elements.

---

### Q2: Which Colour Wins? (Specificity & Cascade Rules)

#### Code Snippet
```html
<p id="first" class="note highlight">Beef noodle soup</p>
```
```css
p          { color: gray; }
.note      { color: blue; }
.highlight { color: green; }
#first     { color: red; }
```

#### Toolbox & Concepts
- **Tags**: `<p>`, **Attributes**: `id`, `class`
- **CSS Selectors**: Type (`p`), Class (`.note`, `.highlight`), ID (`#first`)
- **Core Concept**: Specificity hierarchy and rule ordering in the cascade.

#### Questions & Official Answers

**Q1. What colour is the text?**
> **Answer**: **Red**.
> - **Why**: The selector `#first` is an **ID selector**, which has a specificity score of `(0, 1, 0, 0)`. This outweighs class selectors `(0, 0, 1, 0)` and element selectors `(0, 0, 0, 1)`.

**Q2. Delete the `#first` rule. What colour now?**
> **Answer**: **Green**.
> - **Why**: With `#first` removed, both `.note` and `.highlight` target the element. Both are class selectors with equal specificity `(0, 0, 1, 0)`. When specificity is tied, the rule declared **later in the stylesheet** wins. Because `.highlight` is declared below `.note`, green overrides blue.

**Q3. Also swap the `.note` and `.highlight` lines in CSS. What colour now?**
> **Answer**: **Blue**.
> - **Why**: When `.note` is placed below `.highlight` in the CSS file, it becomes the last declared rule. Since specificity is tied, the later rule wins.
> - *Crucial Exam Note*: The order of class names in the HTML attribute (`class="note highlight"` vs `class="highlight note"`) has **zero effect** on CSS cascade priority! Only the order in the CSS stylesheet matters.

**Q4. The element carries two classes. Do two classes beat one id? Answer yes or no, and say why.**
> **Answer**: **NO**.
> - **Why**: Specificity scores are structured in categorical tiers: `(Inline, ID, Class, Element)`. An ID selector represents tier 2 `(0, 1, 0, 0)`, while two classes represent tier 3 `(0, 0, 2, 0)`. A higher category always beats a lower category, no matter how many lower selectors you accumulate. Even 1,000 classes cannot beat one single ID selector.

---

### Q3: How Much Space Does the Box Take? (Box Model Calculations)

#### Code Snippet
```html
<div class="card">Pho Thin</div>
```
```css
.card {
  width: 300px;
  padding: 15px;
  border: 5px solid black;
  margin: 10px;
}
```

#### Toolbox & Concepts
- **CSS Properties**: `width`, `padding`, `border`, `margin`
- **Core Concept**: Standard CSS Box Model (`box-sizing: content-box`).

#### Completed Measurement Table
| Measurement Field | Formula / Calculation | Value in Pixels (px) |
| :--- | :--- | :--- |
| **content width** | Declared `width` property | **300px** |
| **padding left + right** | `15px + 15px` | **30px** |
| **border left + right** | `5px + 5px` | **10px** |
| **width of the box the browser draws** | `content + padding + border` | **340px** |
| **margin left + right** | `10px + 10px` | **20px** |
| **total horizontal space used** | `box drawn + margin` | **360px** |

#### Question & Official Answer
**Q1. Which of the four boxes takes the background colour, and which one never does?**
> **Answer**:
> - **Takes background color**: **Padding** (and Content). The `background-color` fills the entire interior area up to the inner edge of the border.
> - **Never takes background color**: **Margin**. Margins are strictly transparent whitespace used to push neighboring elements away.

---

### Q4: Same CSS, One Extra Line (`box-sizing: border-box`)

#### Code Snippet
```css
.card {
  width: 300px;
  padding: 15px;
  border: 5px solid black;
  margin: 10px;
  box-sizing: border-box; /* The extra line! */
}
```

#### Questions & Official Answers

**Q1. The box the browser draws is now how many px wide?**
> **Answer**: Exactly **300px** wide.

**Q2. The content inside it is now how many px wide?**
> **Answer**: **260px** wide.
> - **Arithmetic**: $\text{Content Width} = \text{Declared Width} - (\text{Padding Left} + \text{Padding Right} + \text{Border Left} + \text{Border Right})$  
>   $\text{Content Width} = 300 - (15 + 15 + 5 + 5) = 300 - 40 = 260\text{px}$.

**Q3. In one sentence: with `border-box`, what does the number in `width` mean?**
> **Answer**: With `box-sizing: border-box`, the `width` property sets the **total visible width of the element from outer border to outer border**, forcing padding and border to be subtracted from the inside so that the box never expands beyond that number.

---

### Q5: The `style` Attribute (`!important` Trap)

#### Code Snippet
```html
<p class="price" style="color: black;">60,000 VND</p>
```
```css
.price { color: red; }
p      { color: blue; }
```

#### Questions & Official Answers

**Q1. What colour is the price?**
> **Answer**: **Black**.
> - **Why**: Inline styles applied directly via the `style="..."` attribute carry a specificity score of `(1, 0, 0, 0)`, which overrides all class `(0, 0, 1, 0)` and tag `(0, 0, 0, 1)` selectors in external/embedded stylesheets.

**Q2. You are not allowed to edit the HTML. Write a CSS rule that turns the price red anyway.**
> **Answer**:
> ```css
> .price {
>   color: red !important;
> }
> ```
> *(Or `p { color: red !important; }` or `#price-id { color: red !important; }`)*

**Q3. Your teacher tells you never to write that rule in real work. Why not?**
> **Answer**: Because `!important` **destroys the natural cascading behavior of CSS**. It creates an unmaintainable "specificity arms race" where subsequent developers cannot override the style without writing even more `!important` declarations. It breaks modularity, makes site-wide theming impossible, and makes debugging CSS extremely difficult.

---

# Part 2: Find the Mistakes (`broken.html`)

---

### The 9 Mistakes Answer Table

Here is the complete debugging analysis of the 9 errors in `broken.html`:

| # | Line | Symptom on Screen | Root Cause | Exact Fix |
| :-: | :-: | :--- | :--- | :--- |
| **1** | **7** | `<h1>` title is black instead of dark red. | **Invalid Hex color**: `#b0000` has only 5 characters (Hex requires 6 digits or 3 shorthand). Browser drops the declaration. | Change `#b0000` to `#b00000`. |
| **2** | **8** | `<p class="title">` ("Since 1979") is not italic and not gray. | **Wrong selector type**: `title` is written as a tag selector, but in HTML it is an attribute: `class="title"`. | Add a dot prefix: `.title { ... }`. |
| **3** | **9–10** | Price text is neither bold nor dark red. | **Missing semicolon**: No `;` after `bold`. Browser reads `bold color: #b00000` as one invalid value and discards both lines. | Add semicolon after `bold;`. |
| **4** | **16** | Invalid DOM tree structure; styling inconsistencies. | **Mismatched tags**: Opening tag is `<h1>`, but closing tag is `</h2>`. | Change `</h2>` to `</h1>`. |
| **5** | **24** | "Pho tai" renders outside the bulleted list as raw unformatted text. | **Orphan `<li>` element**: Placed on line 24 after the `</ul>` list was already closed on line 23. | Move `<li>Pho tai</li>` inside `<ul>` before line 23. |
| **6** | **28** | Table header cell stretches beyond columns or distorts grid. | **Wrong column span**: `<th colspan="3">` is used, but table only has 2 columns (`<td>Dish</td>` and `<td>Price</td>`). | Change `colspan="3"` to `colspan="2"`. |
| **7** | **34** | Text "Open 6am - 10am, closed on Monday." turns blue, underlined, and clickable! | **Missing closing tag**: `<a href="...">` is never closed with `</a>`. The link bleeds into all text below it. | Add `</a>` after "Visit our website". |
| **8** | **38** | Image fails accessibility standards; no placeholder text if image fails to load. | **Missing `alt` attribute**: The `<img>` tag has no `alt` description, harming screen-reader users and SEO. | Add `alt="A bowl of Pho Thin"`. |
| **9** | **11** | Table borders appear doubled with ugly gaps between cells. | **Missing CSS property**: Table does not specify `border-collapse: collapse;`. | Add `border-collapse: collapse;` to `table` rule on line 11. |

---

### Answers to the Three Questions Under the Table

#### Q1. In two places the CSS contains a value the browser cannot understand, so it throws that declaration away and says nothing at all. Which two? Explain how the browser decides to discard a declaration instead of complaining. Careful with one of them - more is lost than you first think.
> **Answer**:
> 1. **Line 7 (`color: #b0000;`)**: Hexadecimal color codes must be 3 or 6 hex digits. A 5-digit hex code is syntactically invalid. The browser ignores `color` and leaves text default black.
> 2. **Line 9–10 (`font-weight: bold color: #b00000;`)**: Missing semicolon after `bold`. The CSS parser treats `bold color: #b00000;` as a single property-value expression. Because `bold color: #b00000` is invalid for `font-weight`, the browser **discards both `font-weight` AND `color`**!
> 
> **How the browser decides**: The CSS specification mandates **graceful degradation / error recovery**. If a CSS parser encounters an unrecognized property or invalid value, it discards that single declaration (up to the next semicolon) and continues parsing the rest of the stylesheet without crashing or displaying error dialogs to the end user.

#### Q2. One mistake makes text that is not inside a link behave like a link. Which one, and why does the damage spread past the line where the mistake is?
> **Answer**:
> - **The Mistake**: Line 34: `<a href="https://phothin.vn">Visit our website` is missing the closing `</a>` tag.
> - **Why damage spreads**: The browser parses HTML sequentially. An open `<a>` tag instructs the browser: *"everything that follows is clickable until you hit `</a>`"*. Because `</a>` never appears, the browser keeps the anchor active, transforming the opening hours text below it into a clickable link.

#### Q3. One mistake costs nothing today because the image file is missing anyway, but it would still be wrong if the image loaded. Which one, and who is harmed by it?
> **Answer**:
> - **The Mistake**: Line 38: `<img src="bowl.jpg">` is missing the `alt` attribute.
> - **Who is harmed**: **Visually impaired users** who rely on screen-reading assistive software. Screen readers cannot interpret pixels; they read the `alt` text out loud. Without `alt`, the user has no idea what the image represents. Additionally, search engine web crawlers are harmed because they cannot index the image content.

---

### Fully Corrected `fixed.html` Code
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Pho Thin - Menu</title>
    <style>
      body {
        font-family: Arial, sans-serif;
      }
      /* Fix 1: Corrected 6-digit hex code #b00000 */
      h1 {
        color: #b00000;
        text-align: center;
      }
      /* Fix 2: Changed tag selector 'title' to class selector '.title' */
      .title {
        font-style: italic;
        color: gray;
      }
      /* Fix 3: Added semicolon after bold */
      .price {
        font-weight: bold;
        color: #b00000;
      }
      /* Fix 9: Added border-collapse: collapse to eliminate double borders */
      table {
        border-collapse: collapse;
      }
      table, th, td {
        border: 1px solid #999;
        padding: 8px;
      }
      th {
        background-color: #b00000;
        color: white;
      }
    </style>
  </head>
  <body>
    <!-- Fix 4: Matching closing tag </h1> -->
    <h1>Pho Thin</h1>
    <p class="title">Since 1979</p>

    <h2>Our bowls</h2>
    <ul>
      <li>Pho bo</li>
      <li>Pho ga</li>
      <!-- Fix 5: Moved <li>Pho tai</li> inside <ul> -->
      <li>Pho tai</li>
    </ul>

    <h2>Prices</h2>
    <table>
      <!-- Fix 6: Changed colspan="3" to colspan="2" -->
      <tr>
        <th colspan="2">Menu of the day</th>
      </tr>
      <tr>
        <td>Pho bo</td>
        <td class="price">60,000</td>
      </tr>
      <tr>
        <td>Pho ga</td>
        <td class="price">55,000</td>
      </tr>
    </table>

    <h2>Find us</h2>
    <p>
      <!-- Fix 7: Added closing </a> tag -->
      <a href="https://phothin.vn">Visit our website</a><br>
      Open 6am - 10am, closed on Monday.
    </p>

    <!-- Fix 8: Added alt attribute -->
    <img src="bowl.jpg" alt="A delicious hot bowl of Pho Thin beef noodle soup">
  </body>
</html>
```

---

# Part 3: Look Inside a Real Page with F12 (DevTools)

---

### The 5 DevTools Essentials
1. **Open DevTools**: `F12` or `Ctrl + Shift + I` (macOS: `Cmd + Option + I`).
2. **Elements Tab**: Left panel displays live DOM hierarchy; hovering highlights page elements.
3. **Element Picker**: Click the top-left cursor icon (`Ctrl + Shift + C`), then click any UI element on screen to jump directly to its DOM node.
4. **Styles Pane**: Right panel displays all active CSS rules targeting the element, sorted by **strongest specificity first**.
5. **Computed Tab**: Shows the **final computed values** (the verdict) applied by the rendering engine after cascading and inheritance have resolved.

---

### Task 1: Identify Element
Using the element picker on the main heading of `https://usth.edu.vn`:
- **Which tag is it?**: `<h1>`
- **Does it carry a `class`?**: Yes, typically `.title` or `.main-title` (depending on current CMS template).
- **Does it carry an `id`?**: Usually none (or an explicit anchor ID).

---

### Task 2: Declared vs. Computed Values
- **In Styles, which `font-family` list is declared?**:  
  Typically: `font-family: "Roboto", Arial, sans-serif;`
- **In Computed, which single font is actually used?**:  
  `Roboto` (or `Arial` if Roboto is not locally cached/served).
- **Why are those two answers different?**:  
  Styles shows the declared fallback stack (the wishlist). Computed shows the single font file that the operating system actually loaded and used to draw glyphs on screen.
- **The text colour in Computed as `rgb(...)`**:  
  `rgb(0, 43, 91)` (Dark blue) or `rgb(176, 0, 0)`.
- **The same colour written as hex**:  
  `#002b5b` or `#b00000`.

---

### Task 3: The Box Model Arithmetic
Inspecting the heading's box-model diagram in Computed tab:
- **Formula**:  
  $\text{Total Horizontal Space} = \text{Content Width} + \text{Padding Left/Right} + \text{Border Left/Right} + \text{Margin Left/Right}$
- Example calculation:  
  $\text{Total} = 850\text{px} + (0 + 0) + (0 + 0) + (15 + 15) = 880\text{px}$.

---

### Task 4: Who Won the Fight?
- **Q1. How many separate rules target this element?**: Typically 3 to 5 (e.g., user-agent stylesheet `h1`, global typography `body`, layout reset `*`, utility class `.title`).
- **Q2. Find one declaration with a line through it**: E.g., `font-size: 2em;` in user-agent stylesheet.
- **Q3. Write the selector of the rule that beat it**: `.site-title h1` or `h1.title`.
- **Q4. Explain in one sentence why the winner won**: The winner won due to **higher specificity** (`.site-title h1` is class + tag `(0,0,1,1)`, beating user-agent tag selector `(0,0,0,1)`).

---

### Task 5: Switching Declarations Off
- Unticking `background-color` in Styles panel instantly renders the parent container transparent.
- Changing `display: flex` to `display: block` causes child elements aligned horizontally in a row to immediately drop and stack vertically on top of each other.
- Setting `body { font-family: monospace; }` turns all text across the page into fixed-width code-like font.

---

### Task 6: The Client-Server Question That Matters

**Q1. Press F5. What happened to your changes?**
> **Answer**: All changes vanished instantly. The webpage reverted back to its original design.

**Q2. Ask a classmate to load the same page. Do they see your changes?**
> **Answer**: No, they see the normal, unmodified website.

**Q3. Explain, using what you learned in Lecture 1 about client and server: where did your edits live, and why did the server never know about them?**
> **Answer**:
> - Your edits lived strictly in the **client browser's local RAM (in-memory DOM tree)**.
> - Web browsing is fundamentally **stateless and unidirectional** during document rendering: The server sent the HTML/CSS over HTTP in Step 4, and the connection was closed.
> - DevTools is purely a client-side debugging tool. It does **not** send HTTP `POST` or `PUT` requests back to the remote server when you change values in the Styles pane.
> - When you pressed `F5`, your browser issued a brand new HTTP `GET` request to the server, downloading the fresh, unmodified code from disk.

---

### Task 7: Two Ways of Looking (`Ctrl+U` vs. Elements Tab)

**Q1. First five lines of `Ctrl+U`**:
```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
```

**Q2. Find one thing that appears in Elements but not in View Source**:
- Elements injected dynamically via client-side JavaScript (e.g., mobile navigation drawer `<div class="menu-open">`, carousel slider clones, or browser extension markup).

**Q3. Explain the difference in one sentence. Which one is the file the server sent, and which one is what the browser built in memory?**
> **Answer**: **`Ctrl+U` (View Source)** is the exact, static byte-stream sent by the server over the network, whereas the **`Elements` tab** is the live, dynamic DOM (Document Object Model) tree constructed and continuously updated in the browser's memory after HTML parsing and JavaScript execution.

---

# Part 4: Style a Page Without Touching the HTML (`ict-department.html`)

---

### The "One Rule" Constraint
> **You may not change a single character of the HTML file. You write `style.css` only.**

---

### Complete, Working `style.css` File

```css
/* ==========================================================================
   USTH Web Application Development - Lab 1.2 Solution Stylesheet
   File: style.css
   Target: ict-department.html (Unmodified HTML)
   ========================================================================== */

/* Universal Reset & Border-Box */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, sans-serif;
  color: #333;
  line-height: 1.5;
  background-color: #fafafa;
}

/* --------------------------------------------------------------------------
   Task T1: Banner
   Dark red background #b00000, white text, 24px padding, text centered.
   -------------------------------------------------------------------------- */
.banner {
  background-color: #b00000;
  color: white;
  padding: 24px;
  text-align: center;
}

.banner .site-name {
  font-size: 28px;
  margin-bottom: 6px;
}

.banner .tagline {
  font-size: 16px;
  font-style: italic;
  opacity: 0.9;
}

/* --------------------------------------------------------------------------
   Task T2 & T3: Navigation Bar & Current Page Marker
   Horizontal row, 20px apart, no underlines, dark red hover.
   Current page link is bold and dark red permanently.
   -------------------------------------------------------------------------- */
.main-nav {
  display: flex;
  gap: 20px;
  background-color: #f1f1f1;
  padding: 12px 24px;
  border-bottom: 1px solid #ddd;
}

.main-nav .nav-link {
  text-decoration: none;
  color: #444;
  font-size: 15px;
  transition: color 0.2s ease;
}

.main-nav .nav-link:hover {
  color: #b00000;
}

/* T3: Current marker placed BELOW .nav-link in stylesheet */
.main-nav .nav-link.current {
  color: #b00000;
  font-weight: bold;
}

/* --------------------------------------------------------------------------
   Task T4: Two Columns Layout
   Sidebar: exactly 220px, must not shrink.
   Main content: takes remaining width.
   30px gap between columns.
   -------------------------------------------------------------------------- */
.layout {
  display: flex;
  gap: 30px;
  max-width: 1100px;
  margin: 24px auto;
  padding: 0 16px;
}

.sidebar {
  width: 220px;
  flex-shrink: 0; /* Prevents sidebar from shrinking */
}

.content {
  flex: 1; /* Takes all remaining available width */
}

/* --------------------------------------------------------------------------
   Task T5: Sidebar Links
   No bullet points, dark gray, no underline, dark red on hover.
   -------------------------------------------------------------------------- */
.sidebar .side-title {
  font-size: 18px;
  margin-bottom: 12px;
  color: #222;
}

.sidebar .side-list {
  list-style: none; /* Removes bullets from the list */
  margin-bottom: 16px;
}

.sidebar .side-list li {
  margin-bottom: 8px;
}

.sidebar .side-link {
  color: #555;
  text-decoration: none;
  font-size: 14px;
  transition: color 0.2s;
}

.sidebar .side-link:hover {
  color: #b00000;
}

/* --------------------------------------------------------------------------
   Task T6: The Stubborn Note
   HTML has inline style="color: #888;". Must be dark red.
   Requires !important because HTML cannot be modified.
   -------------------------------------------------------------------------- */
.side-note {
  color: #b00000 !important;
  font-size: 13px;
  font-style: italic;
}

/* --------------------------------------------------------------------------
   Task T7: Lead Paragraphs
   Inside #about, .lead paragraphs are 18px and dark red. Plain <p> stays as is.
   -------------------------------------------------------------------------- */
.block {
  margin-bottom: 32px;
}

.block-title {
  font-size: 22px;
  margin-bottom: 14px;
  color: #111;
  border-bottom: 2px solid #eee;
  padding-bottom: 6px;
}

#about .lead {
  font-size: 18px;
  color: #b00000;
  margin-bottom: 10px;
}

#about p:not(.lead) {
  margin-bottom: 10px;
}

/* --------------------------------------------------------------------------
   Task T8: The Cards
   Three cards in a row, share width equally, 16px padding, 1px gray border, 20px gap.
   -------------------------------------------------------------------------- */
.card-row {
  display: flex;
  gap: 20px;
}

.card {
  flex: 1; /* Distributes width equally (33.33% each) */
  padding: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
  background-color: white;
}

.card-title {
  font-size: 18px;
  margin-bottom: 8px;
}

.card-text {
  font-size: 14px;
  color: #666;
  margin-bottom: 12px;
}

/* --------------------------------------------------------------------------
   Task T9: Badges
   Small dark red label, white text, 4px padding.
   .badge.closed is gray.
   -------------------------------------------------------------------------- */
.badge {
  display: inline-block; /* Enables proper padding and height control */
  background-color: #b00000;
  color: white;
  padding: 4px 8px;
  font-size: 12px;
  border-radius: 3px;
  font-weight: bold;
}

.badge.closed {
  background-color: #777; /* Overrides red for closed badge */
}

/* --------------------------------------------------------------------------
   Task T10: The Timetable
   Single borders, 8px padding, dark red header with white text.
   Empty cells must show their border.
   -------------------------------------------------------------------------- */
.schedule {
  width: 100%;
  border-collapse: collapse; /* Merges doubled lines into single line */
  empty-cells: show;        /* Ensures empty cells render borders */
  margin-top: 10px;
}

.schedule th,
.schedule td {
  border: 1px solid #999;
  padding: 8px;
  text-align: center;
}

.schedule th {
  background-color: #b00000;
  color: white;
}

.schedule .slot {
  font-weight: bold;
  background-color: #f7f7f7;
}

/* --------------------------------------------------------------------------
   Task T11: Credits Table (#ects-table)
   Dark blue header, light gray background, row hover pale yellow.
   Timetable above must NOT change.
   -------------------------------------------------------------------------- */
#ects-table {
  width: 100%;
  border-collapse: collapse;
  background-color: #f9f9f9; /* Light gray whole table */
  margin-top: 10px;
}

#ects-table th,
#ects-table td {
  border: 1px solid #ccc;
  padding: 8px 12px;
  text-align: left;
}

#ects-table th {
  background-color: #0d3b66; /* Dark blue header */
  color: white;
}

#ects-table tbody tr:hover {
  background-color: #fff3cd; /* Row hover turns pale yellow */
}

/* --------------------------------------------------------------------------
   Task T12: News List
   No bullets. .news-date is gray, monospace, 70px wide in a column.
   .news-link has no underline, dark red on hover.
   -------------------------------------------------------------------------- */
.news-list {
  list-style: none;
}

.news-item {
  margin-bottom: 10px;
}

.news-date {
  display: inline-block; /* Required for width: 70px to take effect! */
  width: 70px;
  color: #777;
  font-family: monospace;
}

.news-link {
  text-decoration: none;
  color: #333;
}

.news-link:hover {
  color: #b00000;
}

/* --------------------------------------------------------------------------
   Task T13: Footer
   Dark red background, white text, centered, 16px padding.
   -------------------------------------------------------------------------- */
.page-footer {
  background-color: #b00000;
  color: white;
  text-align: center;
  padding: 16px;
  margin-top: 40px;
}
```

---

### Tasks T1–T13: CSS Code & Exhaustive "Why" Explanations

#### Task T1: Banner
- **CSS Code**:
  ```css
  .banner {
    background-color: #b00000;
    color: white;
    padding: 24px;
    text-align: center;
  }
  ```
- **"Why" Explanation**:
  - `color` paints the text glyphs (foreground). `background-color` fills the rectangular box behind the text.
  - `padding: 24px` creates space **inside** the border and background area, making the dark red banner taller and framing the text.
  - If we had used `margin: 24px`, the white space would appear **outside** the dark red box, leaving the red background hugging the text tightly with an ugly 24px transparent gap around the whole banner.

---

#### Task T2: Navigation Bar
- **CSS Code**:
  ```css
  .main-nav {
    display: flex;
    gap: 20px;
  }
  .main-nav .nav-link {
    text-decoration: none;
  }
  .main-nav .nav-link:hover {
    color: #b00000;
  }
  ```
- **"Why" Explanation**:
  - **(a) Which element got `display: flex` and why not `.nav-link`?**: We set `display: flex` on the **parent `<nav class="main-nav">` container**. In CSS Flexbox, flex properties must be applied to the parent element (flex container) to dictate how its immediate children (flex items) arrange themselves. Applying it to `.nav-link` would only turn the link's inner text into flex items.
  - **(b) What would you write if `gap` did not exist?**: We would have to use margin on children: `.main-nav .nav-link { margin-right: 20px; }` and remove it from the last child using `:last-child { margin-right: 0; }`.
  - **(c) Meaning of `:hover`**: A pseudo-class is a CSS keyword added to a selector that targets an element only when it enters a specific interactive state (in this case, when the user's cursor hovers over the element).

---

#### Task T3: The Current Page Marker
- **CSS Code**:
  ```css
  .main-nav .nav-link.current {
    color: #b00000;
    font-weight: bold;
  }
  ```
- **"Why" Explanation**:
  - The HTML has `class="nav-link current"`. Both `.nav-link` and `.current` rules target this element.
  - The compound selector `.nav-link.current` carries a specificity score of `(0, 0, 2, 0)` (two classes), which naturally defeats `.nav-link` `(0, 0, 1, 0)`.
  - If we had used single `.current` and placed it *above* `.nav-link`, both would have equal specificity `(0, 0, 1, 0)`. Since `.nav-link` appeared later in the file, it would have overwritten `.current`, turning the current link back to gray! Placing `.current` below (or using `.nav-link.current`) guarantees it wins.

---

#### Task T4: Two Columns Layout
- **CSS Code**:
  ```css
  .layout {
    display: flex;
    gap: 30px;
  }
  .sidebar {
    width: 220px;
    flex-shrink: 0;
  }
  .content {
    flex: 1;
  }
  ```
- **"Why" Explanation**:
  - The `.layout` container became the **flex container**. Its two direct children, `<aside class="sidebar">` and `<main class="content">`, became the **flex items**.
  - If we set `width: 220px` without `flex-shrink: 0`, the default flex behavior is `flex-shrink: 1`. When the browser window is resized or content expands, Flexbox compresses flex items to fit within the viewport, causing the sidebar to shrink narrower than 220px. `flex-shrink: 0` explicitly forbids shrinking.

---

#### Task T5: Sidebar Links
- **CSS Code**:
  ```css
  .side-list {
    list-style: none;
  }
  .side-link {
    color: #555;
    text-decoration: none;
  }
  .side-link:hover {
    color: #b00000;
  }
  ```
- **"Why" Explanation**:
  - The bullet point is a marker rendered by the list container formatting context. In CSS, the property `list-style: none` is inherited by list item elements (`<li>`). Setting it on the parent `<ul>` (`.side-list`) strips bullet markers from all nested list items in one single declaration.

---

#### Task T6: The Stubborn Note (The Trap!)
- **CSS Code**:
  ```css
  .side-note {
    color: #b00000 !important;
  }
  ```
- **"Why" Explanation**:
  - **What happened first**: Writing `.side-note { color: #b00000; }` completely failed. The text stayed gray (`#888`).
  - **The Cause**: The HTML file contained an **inline style**: `<p class="side-note" style="color: #888;">`. An inline style carries a specificity of `(1, 0, 0, 0)`. A class selector has only `(0, 0, 1, 0)` and cannot defeat inline styles under normal cascade rules.
  - **The Solution**: Because the lab rules strictly forbid modifying the HTML file, the only mechanism in CSS capable of overriding an inline style is the `!important` declaration.
  - **Would you do this in a real project?**: **No.** In a production project, you would delete the bad inline `style="color: #888;"` from the HTML template and style it cleanly in CSS. Using `!important` is an emergency workaround, not good architecture.

---

#### Task T7: Lead Paragraphs
- **CSS Code**:
  ```css
  #about .lead {
    font-size: 18px;
    color: #b00000;
  }
  ```
- **"Why" Explanation**:
  - The `#about` section contains three `<p>` tags, but only two carry `class="lead"`. The browser uses class matching to filter elements: `#about .lead` selects only elements that are descendants of `#about` AND possess the class `lead`.
  - If we had written `#about p`, the selector would match **all three `<p>` elements**, incorrectly enlarging and coloring the plain middle paragraph as well.

---

#### Task T8: The Cards
- **CSS Code**:
  ```css
  .card-row {
    display: flex;
    gap: 20px;
  }
  .card {
    flex: 1; /* Solution 1 */
    padding: 16px;
    border: 1px solid #ccc;
  }
  ```
- **"Why" Explanation**:
  - **Why card 3 dropped with `width: 33%`**: Under standard `content-box`, `width: 33%` applies only to content. Adding `16px + 16px` of padding and `1px + 1px` of border increases each card's total width to `33% + 34px`. Three cards require `99% + 102px`, which exceeds 100% of the parent width, causing the third card to wrap onto a new line.
  - **Two ways to prevent it**:
    1. Set `box-sizing: border-box;` and account for gap.
    2. Use `flex: 1;` on each card inside a `display: flex` container.
  - **Which we chose and why**: We chose `flex: 1` combined with `box-sizing: border-box`. Flexbox automatically calculates exact fractional widths minus the 20px gap, guaranteeing all three cards fit perfectly on one row.

---

#### Task T9: The Badge
- **CSS Code**:
  ```css
  .badge {
    display: inline-block;
    background-color: #b00000;
    color: white;
    padding: 4px 8px;
  }
  .badge.closed {
    background-color: #777;
  }
  ```
- **"Why" Explanation**:
  - In HTML, `<span>` is an **inline element**. On inline elements, `padding-top` and `padding-bottom` render visually but **do not expand the containing line box** and can overlap neighboring lines of text. Inline elements also ignore `height`, `min-height`, and vertical margins.
  - To give the badge complete control over its own height and dimensions without breaking text flow, we set `display: inline-block`.

---

#### Task T10: The Timetable
- **CSS Code**:
  ```css
  .schedule {
    width: 100%;
    border-collapse: collapse;
    empty-cells: show;
  }
  .schedule th,
  .schedule td {
    border: 1px solid #999;
    padding: 8px;
  }
  .schedule th {
    background-color: #b00000;
    color: white;
  }
  ```
- **"Why" Explanation**:
  - **(a) Which declaration merged the doubled lines and where did it go?**: `border-collapse: collapse;` went on the parent `<table>` element (`.schedule`).
  - **(b) Why empty `<td>` loses border**: In older browsers or certain table rendering models, cells with no text content are treated as empty and hide their borders. Specifying `empty-cells: show;` (and setting explicit border definitions on `td`) ensures every cell displays its borders.

---

#### Task T11: The Credits Table
- **CSS Code**:
  ```css
  #ects-table {
    width: 100%;
    border-collapse: collapse;
    background-color: #f9f9f9;
  }
  #ects-table th {
    background-color: #0d3b66;
    color: white;
  }
  #ects-table tbody tr:hover {
    background-color: #fff3cd;
  }
  ```
- **"Why" Explanation**:
  - The table has both `class="credits"` and `id="ects-table"`.
  - If a second credits table were added to the page, `.credits` would target **both tables**, while `#ects-table` targets **only that specific table** because an ID must be unique per page.
  - **Real project choice**: We choose `.credits` (classes) for generic reusable table styling, and `#ects-table` only when styling unique, one-off instances. Here the requirement explicitly specified *"and only the credits table"*, making `#ects-table` the correct choice.

---

#### Task T12: News List
- **CSS Code**:
  ```css
  .news-date {
    display: inline-block;
    width: 70px;
    font-family: monospace;
    color: #777;
  }
  .news-link {
    text-decoration: none;
    color: #333;
  }
  .news-link:hover {
    color: #b00000;
  }
  ```
- **"Why" Explanation**:
  - `<span class="news-date">` is inline. The CSS specification states that the `width` and `height` properties have **no effect on non-replaced inline elements**.
  - Changing its display mode to `display: inline-block` allows it to accept `width: 70px` while still sitting on the same line as the news link. This aligns all date spans into an even 70px column.

---

#### Task T13: Footer
- **CSS Code**:
  ```css
  .page-footer {
    background-color: #b00000;
    color: white;
    text-align: center;
    padding: 16px;
  }
  ```
- **"Why" Explanation**:
  - `<footer>` is a **block-level semantic element**. Block elements automatically expand to take **100% of the available width** of their parent container (`<body>`) by default. Therefore, no `width: 100%` declaration is required.

---

# Oral Check & Midterm Exam Survival Guide

During lab evaluations or midterm exams, professors will point to code snippets and ask:
1. *"Why did the heading remain black in broken.html?"*  
   $\rightarrow$ Point out line 7: Hex color `#b0000` has 5 digits; CSS silently discarded it.
2. *"Why did the price stay unstyled in broken.html?"*  
   $\rightarrow$ Point out line 9: Missing semicolon `;` caused the parser to merge two declarations into one invalid value.
3. *"Why did you use `!important` on `.side-note`?"*  
   $\rightarrow$ Point out that the HTML had an inline `style="color: #888;"` attribute `(1,0,0,0)`. Because the exam rules forbid editing the HTML, `!important` was the only legal mechanism to override it.
4. *"What is the difference between `display: flex` on the parent vs child?"*  
   $\rightarrow$ Flex must be placed on the container parent to establish the flex formatting context for its direct children.
5. *"Why did card 3 wrap to a new line when width was 33%?"*  
   $\rightarrow$ Default `box-sizing: content-box` adds padding and border on top of width, pushing total row consumption beyond 100%.
