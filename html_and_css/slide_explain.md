# Web Application Development — Lecture 02: Introduction to HTML + CSS
**University of Science and Technology of Hanoi (USTH)**  
**Information and Communication Technology Laboratory (ICTLab)**  
**Lecturers:** KIEU Quoc Viet, HUYNH Vinh Nam  
**Audience:** Web Application Development Students (Midterm Exam Preparation)

---

## Master Table of Contents
1. [Course Orientation & Slide Focus](#course-orientation--slide-focus)
2. [Section 1: Tools and Workflow (Slides 1–6)](#section-1-tools-and-workflow-slides-16)
   - [Slide 1: Title Slide & Context](#slide-1-title-slide--context)
   - [Slide 2: Table of Contents](#slide-2-table-of-contents)
   - [Slide 3: Section 1 — Tools and Workflow](#slide-3-section-1--tools-and-workflow)
   - [Slide 4: Your Toolbox: Editor, Live Server, Browser](#slide-4-your-toolbox-editor-live-server-browser)
   - [Slide 5: Set Up in Five Minutes](#slide-5-set-up-in-five-minutes)
   - [Slide 6: DevTools: Look Inside Any Page](#slide-6-devtools-look-inside-any-page)
3. [Section 2: What HTML Is (Slides 7–19)](#section-2-what-html-is-slides-719)
   - [Slide 7: Section 2 — What HTML Is](#slide-7-section-2--what-html-is)
   - [Slide 8: A Web Page Is Text With Tags](#slide-8-a-web-page-is-text-with-tags)
   - [Slide 9: Parts of a Tag](#slide-9-parts-of-a-tag)
   - [Slide 10: Tags That Close, Tags That Don't](#slide-10-tags-that-close-tags-that-dont)
   - [Slide 11: The Page Skeleton](#slide-11-the-page-skeleton)
   - [Slide 12: Text Tags (Headings, Formatting, Line Breaks)](#slide-12-text-tags-headings-formatting-line-breaks)
   - [Slide 13: List Tags (`<ul>`, `<ol>`, `<dl>`)](#slide-13-list-tags-ul-ol-dl)
   - [Slide 14: Link and Image Tags (Paths & Formats)](#slide-14-link-and-image-tags-paths--formats)
   - [Slide 15 & 16: Table Tags (Structure & Missing Borders)](#slide-15--16-table-tags-structure--missing-borders)
   - [Slide 17: Cells That Span (`colspan` & `rowspan`)](#slide-17-cells-that-span-colspan--rowspan)
   - [Slide 18: Block and Inline Elements](#slide-18-block-and-inline-elements)
   - [Slide 19: Exercise — Build This Page (With Solutions)](#slide-19-exercise--build-this-page-with-solutions)
4. [Section 3: Styling with CSS (Slides 20–41)](#section-3-styling-with-css-slides-2041)
   - [Slide 20: Section 3 — Styling with CSS](#slide-20-section-3--styling-with-css)
   - [Slide 21: From Tags to Looks (Separation of Concerns)](#slide-21-from-tags-to-looks-separation-of-concerns)
   - [Slide 22: Parts of a CSS Rule](#slide-22-parts-of-a-css-rule)
   - [Slide 23: Three Ways to Attach CSS (Inline, Internal, External)](#slide-23-three-ways-to-attach-css-inline-internal-external)
   - [Slide 24: Selectors: Class, ID, Type](#slide-24-selectors-class-id-type)
   - [Slide 25: Which Rule Wins (Specificity, Cascade, `!important`)](#slide-25-which-rule-wins-specificity-cascade-important)
   - [Slide 26: Colours and Backgrounds](#slide-26-colours-and-backgrounds)
   - [Slide 27: Colour Values (Hex, RGB, RGBA, HSL)](#slide-27-colour-values-hex-rgb-rgba-hsl)
   - [Slide 28: Fonts (Font Stack & Fallbacks)](#slide-28-fonts-font-stack--fallbacks)
   - [Slide 29: Choosing a Font (Generic Families & Bold Semantics)](#slide-29-choosing-a-font-generic-families--bold-semantics)
   - [Slide 30: Font Values (`weight`, `style`, `size`, `stretch`)](#slide-30-font-values-weight-style-size-stretch)
   - [Slide 31: Formatting Text (`align`, `line-height`, `decoration`)](#slide-31-formatting-text-align-line-height-decoration)
   - [Slide 32: Text Values (`align`, `decoration`, `vertical-align`)](#slide-32-text-values-align-decoration-vertical-align)
   - [Slide 33: Pseudo-classes (`:link`, `:visited`, `:hover`, `:active`)](#slide-33-pseudo-classes-link-visited-hover-active)
   - [Slide 34: The Box Model (Content, Padding, Border, Margin)](#slide-34-the-box-model-content-padding-border-margin)
   - [Slide 35: Box Values (Shorthands & Dimensions)](#slide-35-box-values-shorthands--dimensions)
   - [Slide 36: Sizing the Box (`content-box` vs. `border-box`)](#slide-36-sizing-the-box-content-box-vs-border-box)
   - [Slide 37: Boxes in a Row (Flexbox Basics)](#slide-37-boxes-in-a-row-flexbox-basics)
   - [Slide 38: Styling a Table (`border-collapse`, hover effects)](#slide-38-styling-a-table-border-collapse-hover-effects)
   - [Slide 39: Table Values (Spacing, Alignment, Captions)](#slide-39-table-values-spacing-alignment-captions)
   - [Slide 40: Final Exercise — Read This Page (4 Questions & Solutions)](#slide-40-final-exercise--read-this-page-4-questions--solutions)
   - [Slide 41: Conclusion](#slide-41-conclusion)
5. [Midterm Exam Master Review: Key Traps, Calculations & Formulas](#midterm-exam-master-review-key-traps-calculations--formulas)

---

## Course Orientation & Slide Focus

This document provides a line-by-line, element-by-element study guide for **Lecture 02: HTML + CSS**. 
The content focuses strictly on the syllabus, rules, conventions, and examples presented in the lecture slides by USTH professors KIEU Quoc Viet and HUYNH Vinh Nam.

For each slide, you will find:
1. **Verbatim Slide Text & Visual Diagram Breakdown**: Every piece of code, visual layout, and caption.
2. **Line-by-Line Meaning**: Why each tag, attribute, property, or punctuation mark exists.
3. **Midterm Exam Traps & Pitfalls**: Common bugs, syntax errors, and trick questions tested in exams.
4. **Complete Exercise Solutions**: Full solutions and explanations for all classroom exercises in the slide deck.

---

# Section 1: Tools and Workflow (Slides 1–6)

---

### Slide 1: Title Slide & Context
```text
HTML + CSS
Web Application Development
KIEU Quoc Viet      HUYNH Vinh Nam
Information and Communication Technology Laboratory (ICTLab),
University of Science and Technology of Hanoi
Hanoi, August 2024 | Lecture 02 | 1 / 40
```

#### Line-by-Line Meaning
- **HTML + CSS**: The two foundational client-side technologies of web development. HTML provides structure and semantics; CSS provides styling, layout, and visual presentation.
- **Academic Context**: Taught under the Web Application Development module at USTH ICTLab. Builds directly on Lecture 01 (Internet and WWW fundamentals).

---

### Slide 2: Table of Contents
```text
Table of Contents
1 Tools and Workflow
2 What HTML Is
3 Styling with CSS
```

#### Overview of Lecture Structure
- **Part 1 (Tools & Workflow)**: Setting up a local developer environment using VS Code, Live Server, and Chrome DevTools.
- **Part 2 (What HTML Is)**: Document markup, elements, tags, attributes, void/self-closing elements, document skeleton, text tags, lists, links, images, tables, table spanning (`colspan`/`rowspan`), and block vs. inline layout modes.
- **Part 3 (Styling with CSS)**: Separation of concerns, CSS rule syntax, stylesheet attachment methods, selectors, specificity cascade rules, color models, typography, text formatting, link pseudo-classes, the CSS Box Model, `box-sizing`, Flexbox layout, and table styling.

---

### Slide 3: Section 1 — Tools and Workflow
```text
1. Tools and Workflow
```
Introductory section marker for local development setup.

---

### Slide 4: Your Toolbox: Editor, Live Server, Browser

```text
Your Toolbox: Editor, Live Server, Browser
```

#### 1. The Development Loop Diagram
```text
  ┌──────────────┐     Ctrl + S     ┌──────────────┐   auto reload   ┌──────────────┐
  │   VS Code    │ ───────────────► │ Live Server  │ ──────────────► │   Browser    │
  │ you type here│                  │hands file out│                 │draws the page│
  └──────────────┘                  └──────────────┘                 └──────────────┘
         ▲                                                                   │
         └──────────────── something wrong? go back and fix it ──────────────┘
```
- **Step 1 (VS Code)**: You write HTML structure and CSS styles inside a text editor.
- **Step 2 (Ctrl + S)**: Saving the file triggers the local development server file-watcher.
- **Step 3 (Live Server)**: The extension serves the updated file over HTTP and injects a tiny WebSocket script that sends a reload command to the client.
- **Step 4 (Browser)**: The browser immediately reloads and renders the updated DOM and styles without manual user intervention.
- **Feedback Loop**: Inspecting the output allows immediate debugging and iterative refinement.

#### 2. "Why not just double-click the file?"
```text
• Double-click opens file:///... - works, but not a server
• Live Server gives http://localhost:5500 - a real web address
```
- **`file:///` Protocol**: When you double-click an `.html` file in File Explorer, the browser opens it directly from the local filesystem.
  - *Drawbacks*: Does not use HTTP. Features requiring true HTTP requests (AJAX, `fetch()`, ES modules, proper root-relative paths like `/order`, CORS, and WebSockets) will fail or trigger security errors.
- **`http://localhost:5500`**: Live Server runs a lightweight local HTTP server process listening on port `5500`.
  - Simulates a real production web server environment over HTTP.
  - `localhost` resolves to `127.0.0.1` (the loopback address from Lecture 01).

#### 3. "What you do NOT need"
```text
• No compiler, no build step
• No paid software
• Any text editor works - VS Code is just easier
```
- HTML and CSS are interpreted runtime languages parsed natively by the browser engine. No compilation step (like `gcc` in C or `javac` in Java) is required.
- Everything runs on free, open-source software.

---

### Slide 5: Set Up in Five Minutes

```text
Set Up in Five Minutes
1. Install VS Code (code.visualstudio.com)
2. Add Live Server (Ctrl+Shift+X → Install)
3. Create index.html inside a new folder
4. Click Go Live (bottom right)
Go Live - bottom right of the status bar
```

#### Detailed Setup Breakdown
1. **VS Code**: Microsoft's free, cross-platform source code editor.
2. **Live Server Extension**: Installed via Extension Marketplace (`Ctrl+Shift+X` or `Cmd+Shift+X` on macOS).
3. **`index.html`**: The standard default entry point file for any web project.
4. **"Go Live" Button**: Located in the blue bottom status bar of VS Code. Clicking it launches the browser to `http://127.0.0.1:5500/index.html`.

---

### Slide 6: DevTools: Look Inside Any Page

```text
DevTools: Look Inside Any Page
F12 opens DevTools
Elements live page structure
Ctrl+U raw text from server
Hover a line that part lights up
```

#### Key Browser Tools & Shortcuts
- **`F12` (or Right-Click -> Inspect)**: Opens browser Developer Tools.
- **Elements Panel**: Displays the live, currently active **DOM (Document Object Model)** tree after browser parsing and JavaScript modifications.
- **`Ctrl + U` (View Page Source)**: Displays the **raw, static text** received from the web server before any client-side DOM parsing or JavaScript execution.
- **DOM Inspector Hover**: Hovering over any HTML element in the Elements panel highlights its bounding box, padding (green), margin (orange), and border on the rendered webpage.

> **Midterm Exam Distinction**:
> `Ctrl + U` shows what the server sent over HTTP. The `Elements` tab shows what the browser constructed in memory (the DOM). If JavaScript dynamically inserts a paragraph, it appears in `Elements`, but never in `Ctrl + U`.

---

# Section 2: What HTML Is (Slides 7–19)

---

### Slide 7: Section 2 — What HTML Is
```text
2. What HTML Is
```
Introductory section marker for HTML markup and elements.

---

### Slide 8: A Web Page Is Text With Tags

```text
A Web Page Is Text With Tags
```

#### What You Write (Plain Text) vs. What the Browser Shows
```html
<h1>Pho Thin</h1>
<p>Beef noodle soup
60,000 VND</p>
<a href="/order">Order now</a>
```

#### Slide Breakdown & Bullet Points
```text
What you write - plain text:
• Characters only - no pixels, no colours
• Words in angle brackets = tags
• A tag opens <p> and closes </p>

What the browser shows:
• Browser reads the tags, then draws
• <h1> = heading, <p> = paragraph
• <a> = link the user can click
```

#### Core Takeaways
- An HTML file is purely unformatted Unicode text. It contains no embedded pixels, colors, or fonts.
- Angle brackets `<...>` identify instructions (tags) to the browser engine.
- The browser reads the tags, strips them from view, and applies default typography and spacing to the enclosed content.
- Note on whitespace: In the code above, `Beef noodle soup` and `60,000 VND` are on two separate lines, but the browser collapses line breaks and multiple spaces into a single space on screen.

---

### Slide 9: Parts of a Tag

```text
Parts of a Tag
```

#### Detailed Visual Diagram Breakdown
```text
           opening tag                        attribute
       (name of element)                   (name = "value")
               │                                  │
               ▼                                  ▼
             < p            lang = "en"               > Beef noodle soup </ p >
                                                              ▲             ▲
                                                              │             │
                                                           content     closing tag
                                                        (the only part  (same name,
                                                          users see)    with a slash)
```

#### Rules to Remember (Must Memorize!)
```text
• Element = opening tag + content + closing tag
• Attribute value goes in double quotes
• Attributes live in the opening tag only
• One tag can carry several attributes
```
- **Element Definition**: The entire entity from opening tag `<p>` to closing tag `</p>`, including inner content.
- **Attributes**: Provide metadata, configuration, or styling hooks (`lang="en"`, `class="price"`, `id="main"`).
- **Attribute Placement**: Attributes **never** appear in the closing tag (`</p lang="en">` is invalid HTML syntax).
- **Multiple Attributes**: Separated by spaces within the opening tag (e.g., `<a href="/order" target="_blank" class="btn">`).

#### What Ends Up on Screen
```text
• Only Beef noodle soup
• Tag names never show
• lang="en" never shows - it tells the browser the language
```
- The browser uses `lang="en"` for hyphenation, screen-reader voice synthesis, and translation services. The text itself is completely invisible to visitors.

---

### Slide 10: Tags That Close, Tags That Don't

```text
Tags That Close, Tags That Don't
```

#### 1. Paired Tags (Wrap Content)
```text
Most tags come in pairs
• They wrap content: <p>Beef noodle soup</p>
• <html>, <head>, <title>, <body>, <h1>, <p>, <a>, <ul>, <ol>, <li>, <div>, <table>
• Closing tag = same name with a slash in front (</...>)
```

#### 2. Void Elements (Tags That Never Close)
```text
A few never close
• Nothing goes inside them, so there is nothing to wrap
• <br>, <hr>, <img>, <input>, <meta>
• Older pages write <br /> - same meaning
```
- In HTML5, void elements cannot contain children or closing tags.
- `<br />` is valid XHTML syntax; in HTML5, `<br>` and `<br />` are treated identically by the browser.

#### 3. The Unclosed Tag Trap
```text
Forget one closing tag, and the rest of the page pays for it
<a href="/order">Order now    no </a> here
<p>Beef noodle soup 60,000 VND</p>

Result: the price line turns blue and clickable too - the link never ended.
```
- Because browsers attempt error recovery, an unclosed `<a>` tag remains open in the DOM tree, causing all subsequent text and blocks to become part of the clickable hyperlink!

---

### Slide 11: The Page Skeleton

```text
The Page Skeleton
```

#### The Standard HTML5 Boilerplate
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Pho Thin</title>
  </head>
  <body>
    <h1>Pho Thin</h1>
  </body>
</html>
```

#### Structural Boxes (Hierarchy)
```text
┌────────────────────────────────────────────────────────┐
│ <html> (Root element wrapping all document content)    │
│ ┌────────────────────────────────────────────────────┐ │
│ │ <head>                                             │ │
│ │   Title of the tab, metadata, links to CSS/scripts │ │
│ └────────────────────────────────────────────────────┘ │
│ ┌────────────────────────────────────────────────────┐ │
│ │ <body>                                             │ │
│ │   Everything the user sees:                        │ │
│ │   headings, paragraphs, images, tables, links      │ │
│ └────────────────────────────────────────────────────┘ │
└────────────────────────────────────────────────────────┘
```

#### Core Points to Make (Exam Favorites!)
```text
• <!DOCTYPE html> is not a tag - it tells the browser to read the file as modern HTML
• <head> holds information about the page - <title> <meta> <style> <script> - none of it is drawn
• <title> is the tab name, the name your bookmark gets, and the line Google shows in its results
• <body> holds the page itself; from here on, every tag we meet goes inside it
• The indenting is only for you - the browser ignores spaces and line breaks
```
- **`<!DOCTYPE html>`**: A Document Type Declaration. Without it, browsers fall back into legacy **Quirks Mode**, breaking modern CSS box layout and standards rendering.
- **`<title>` Significance**: Used in 3 key places:
  1. The browser tab title.
  2. The default label when bookmarking a webpage.
  3. The primary blue clickable headline in Google / search engine results pages (SERPs).
- **Whitespace Collapsing**: Multiple consecutive spaces, tabs, or newlines in HTML source code are collapsed into a single space during rendering.

---

### Slide 12: Text Tags (Headings, Formatting, Line Breaks)

```text
Text Tags
```

#### Example Code & Visual Output
```html
<h1>Pho Thin</h1>
<h2>Menu</h2>
<p>Beef noodle soup
<strong>60,000 VND</strong>
<em>herbs included</em></p>
<hr>
<p>Open 6am - 10am<br>
Closed on Monday</p>
```

#### Rendered Result
- `Pho Thin` (Rendered in huge bold text)
- `Menu` (Rendered in large bold text)
- `Beef noodle soup ` **60,000 VND** *herbs included*
- `─────────────────────────────────────────────────` (Horizontal rule across page)
- `Open 6am - 10am`  
  `Closed on Monday` (Forced onto a new line via `<br>`)

#### Key Points
```text
• Six heading levels, <h1> down to <h6> - <h1> is the biggest
• <strong> makes text bold, <em> makes it italic
• <br> breaks a line, <hr> draws a rule - neither one closes
```
- **Heading Hierarchy**: `<h1>` (main document title, use only once per page for SEO), followed by `<h2>` (sections), `<h3>` (sub-sections) down to `<h6>`.
- **`<strong>` vs `<b>`**: `<strong>` carries semantic importance (screen readers stress it). `<b>` is purely visual bold with no added meaning.
- **`<em>` vs `<i>`**: `<em>` carries semantic emphasis (altered voice inflection). `<i>` is purely visual italics.
- **`<br>` vs `<hr>`**: Both are void tags. `<br>` forces an inline line-break without paragraph margins. `<hr>` creates a horizontal dividing rule (thematic break).

---

### Slide 13: List Tags (`<ul>`, `<ol>`, `<dl>`)

```text
List Tags
```

#### The Three Types of Lists in HTML
```html
<!-- 1. Unordered List (Bullet Points) -->
<ul>
  <li>Beef</li>
  <li>Chicken</li>
</ul>

<!-- 2. Ordered List (Numbered Sequence) -->
<ol>
  <li>Pick a bowl</li>
  <li>Pay at the counter</li>
</ol>

<!-- 3. Description List (Term-Definition Pairs) -->
<dl>
  <dt>Pho</dt>
  <dd>Rice noodle soup</dd>
</dl>
```

#### Rendered Result
```text
  • Beef
  • Chicken

  1. Pick a bowl
  2. Pay at the counter

  Pho
      Rice noodle soup
```

#### Key Rules to Remember
```text
• <li> is one item - it works inside both <ul> and <ol>
• <ul> gives bullets, <ol> counts 1, 2, 3 - the browser writes the numbers, not you
• <dl> comes in pairs: <dt> is the word, <dd> is what it means
```
- Do **not** manually type `1.` or `2.` inside `<ol>` tags. The browser engine calculates sequence numbers automatically.
- `<dl>` = Description List, `<dt>` = Description Term (the word/concept), `<dd>` = Description Definition/Data (indented explanation).

---

### Slide 14: Link and Image Tags (Paths & Formats)

```text
Link and Image Tags
```

#### Code Examples
```html
<a href="https://phothin.vn">Visit us</a>
<img src="bowl.jpg" alt="A bowl of pho">
<a href="/order">
  <img src="bowl.jpg" alt="Order now">
</a>
```

#### 1. Writing the Address (File Paths)
```text
• Same folder: src="bowl.jpg"
• Sub-folder: src="figures/bowl.jpg"
• Parent folder: href="../index.html"
• Full address: protocol + domain + path (https://phothin.vn/order)
• No file name? The server sends index.html
```
- **Relative Paths**:
  - `bowl.jpg`: Look in the exact same directory as the current `.html` file.
  - `figures/bowl.jpg`: Look inside the `figures` subfolder.
  - `../index.html`: Go up one directory level (`..`), then find `index.html`.
- **Absolute Paths**:
  - `/order`: Root-relative path starting from the domain root.
  - `https://phothin.vn`: Full URL specifying protocol, host, and domain.

#### 2. Choosing the Image Format
```text
• JPEG - photos, small file
• PNG - see-through background
• SVG - logos and icons, sharp at any size
• GIF - short animations only
• alt - text if the picture fails to load
```
| Format | Best For | Transparency? | Lossy vs. Lossless |
| :--- | :--- | :--- | :--- |
| **JPEG** | Real-world photographs, gradients | No | Lossy (High compression) |
| **PNG** | Screenshots, graphics requiring alpha transparency | Yes | Lossless |
| **SVG** | Logos, vector icons, UI glyphs | Yes | Vector math (Infinitely scalable) |
| **GIF** | Simple short animated clips | Yes (1-bit) | 8-bit palette (Max 256 colors) |

- **The `alt` Attribute**: Mandatory accessibility requirement. Displayed when the image URL is broken, and read aloud by screen-readers for visually impaired users.

---

### Slide 15 & 16: Table Tags (Structure & Missing Borders)

```text
Table Tags
```

#### Table Markup
```html
<table>
  <tr>
    <th>Dish</th>
    <th>Price</th>
  </tr>
  <tr>
    <td>Pho bo</td>
    <td>60,000</td>
  </tr>
  <tr>
    <td>Pho ga</td>
    <td>55,000</td>
  </tr>
</table>
```

#### Points to Make
```text
• <tr> is one row, <td> is one cell, <th> is a heading cell - bold and centred
• Cells go left to right, rows top to bottom; the browser lines the columns up for you
```
- `<table>`: Wraps the entire tabular grid.
- `<tr>`: Table Row (horizontal container).
- `<th>`: Table Header cell (automatically styled in bold and center-aligned by default).
- `<td>`: Table Data cell (standard left-aligned table cell).

#### "A table has no lines of its own"
```text
• Do not expect a grid - HTML draws no borders at all
• Lines come from CSS: table, th, td { border: 1px solid; }
• Add border-collapse: collapse; or every line comes out double
```
- By default, modern HTML tables render with **zero borders**.
- Adding `border: 1px solid` without `border-collapse: collapse` renders double borders because each cell maintains its own independent border box separated by a default 2px gap.

---

### Slide 17: Cells That Span (`colspan` & `rowspan`)

```text
Cells That Span
```

#### Code with Colspan & Rowspan
```html
<style>
  table { border-collapse: collapse; }
  table, th, td { border: 1px solid; }
</style>
<table>
  <tr>
    <th colspan="2">Menu</th>
  </tr>
  <tr>
    <td rowspan="2">Noodles</td>
    <td>Pho bo</td>
  </tr>
  <tr>
    <td>Pho ga</td>
  </tr>
</table>
```

#### Visual Layout Grid
```text
  ┌────────────────────────────────────────────────────────┐
  │                         Menu                           │ <── Row 1 (th colspan="2")
  ├────────────────────────────┬───────────────────────────┤
  │                            │          Pho bo           │ <── Row 2 (td rowspan="2" + td)
  │          Noodles           ├───────────────────────────┤
  │                            │          Pho ga           │ <── Row 3 (td only!)
  └────────────────────────────┴───────────────────────────┘
```

#### Key Rules & Cell Counting Trap
```text
• colspan="2" - one cell takes the place of two sitting side by side
• rowspan="2" - one cell takes the place of two stacked on top of each other
• Count your cells: a spanned cell is written once, so the row below it has one <td> fewer
```
- **The Midterm Trap**: In Row 3, students often mistakenly write two `<td>` tags. Because `Noodles` in Row 2 has `rowspan="2"`, it extends downward into Row 3. Row 3 only requires one `<td>` (`Pho ga`). Writing a second `<td>` pushes it out to form an unwanted 3rd column!

---

### Slide 18: Block and Inline Elements

```text
Block and Inline
```

#### Code Example
```html
<div>Beef noodle soup</div>
<div>Chicken noodle soup</div>
<p>Today only: <span>60,000 VND</span> per bowl</p>
```

#### Visual Representation of Space Taken
```text
  ┌────────────────────────────────────────────────────────────────────────┐
  │ Beef noodle soup                                                       │ <── Takes full 100% width
  └────────────────────────────────────────────────────────────────────────┘
  ┌────────────────────────────────────────────────────────────────────────┐
  │ Chicken noodle soup                                                    │ <── Forces new line below
  └────────────────────────────────────────────────────────────────────────┘
  Today only: [ 60,000 VND ] per bowl <── span stays inline inside sentence
```

#### Comparison: Block vs. Inline
| Feature | Block-level Elements | Inline Elements |
| :--- | :--- | :--- |
| **Line Behavior** | Always begins on a **new line**; forces elements after it onto a new line. | Stays on the **same line**; flows naturally within text. |
| **Width** | Expands horizontally to take the **full width** of its parent container. | Takes up **only as much width as its content** requires. |
| **Tags List** | `<h1>`-`<h6>`, `<p>`, `<ul>`, `<ol>`, `<li>`, `<div>`, `<table>`, `<header>`, `<nav>`, `<main>`, `<footer>` | `<a>`, `<img>`, `<span>`, `<strong>`, `<em>`, `<br>` |
| **Dimensions**| Accepts `width`, `height`, `margin-top/bottom`, `padding-top/bottom`. | `width` and `height` properties have **no effect**; top/bottom margins are ignored. |

#### Points to Make
```text
• This is why <h1> always jumps to a new line while <a> stays inside the sentence
• <div> and <span> are empty boxes with no look of their own - they group things so that CSS can style them later
```
- `<div>`: Generic **block-level** container.
- `<span>`: Generic **inline** container.
- Both carry zero semantic meaning; they exist purely as hooks for CSS styling and JavaScript DOM manipulation.

---

### Slide 19: Exercise — Build This Page (With Solutions)

```text
Exercise: Build This Page
```

#### The Page Specification Requirements
1. Start from the skeleton — the browser tab must say **Pho Thin**.
2. One `<h1>`, one `<h2>`.
3. `Since 1979` in italic (`<em>`), the prices in bold (`<strong>`).
4. The three bowls as a bulleted list (`<ul>`, `<li>`).
5. In the table, the Prices row covers both columns (`colspan="2"`).
6. "Order now" links to `https://phothin.vn`.
7. One picture, with an `alt` attribute that describes it — a local file or web address.
8. Bonus: Add a `<dl>` for `tai` and `nam`, and make one cell cover two rows (`rowspan="2"`).

#### Complete HTML Solution Code
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Pho Thin</title>
  </head>
  <body>
    <h1>Pho Thin</h1>
    <p><em>Since 1979</em></p>

    <h2>Our bowls</h2>
    <ul>
      <li>Pho bo</li>
      <li>Pho ga</li>
      <li>Pho tai</li>
    </ul>

    <table border="1">
      <tr>
        <th colspan="2">Prices</th>
      </tr>
      <tr>
        <td>Pho bo</td>
        <td><strong>60,000</strong></td>
      </tr>
      <tr>
        <td>Pho ga</td>
        <td><strong>55,000</strong></td>
      </tr>
    </table>

    <p><a href="https://phothin.vn">Order now</a></p>
    <img src="bowl.jpg" alt="A hot steaming bowl of Pho Thin beef noodle soup">

    <!-- Bonus Tasks -->
    <h2>Descriptions</h2>
    <dl>
      <dt>Tai</dt>
      <dd>Rare sliced beef cooked in steaming broth</dd>
      <dt>Nam</dt>
      <dd>Well-done beef flank</dd>
    </dl>
  </body>
</html>
```

#### Answers to the Two Slide Questions
1. **"Which tags on your page need no closing tag, and why?"**
   - **Answer**: `<img>` (and `<meta>`, `<br>`, `<hr>` if used). These are **void elements**. They have no inner content or children; their data is passed entirely through attributes (`src`, `alt`), so there is nothing to wrap with a closing tag.
2. **"Pho Thin shows up in the tab and in the page — which tag gives each one?"**
   - **Answer**: 
     - Browser tab: `<title>Pho Thin</title>` (inside `<head>`).
     - Webpage canvas: `<h1>Pho Thin</h1>` (inside `<body>`).

---

# Section 3: Styling with CSS (Slides 20–41)

---

### Slide 20: Section 3 — Styling with CSS
```text
3. Styling with CSS
```
Introductory section marker for Cascading Style Sheets.

---

### Slide 21: From Tags to Looks (Separation of Concerns)

```text
From Tags to Looks
The HTML never changes:
<h1>Pho Thin</h1>
<p class="price">60,000 VND</p>

No CSS:
Pho Thin
60,000 VND

With three lines of CSS:
h1 { color: #b00000; text-align: center; }
.price { background: yellow; }
```

#### Points to Make
```text
• HTML says what a thing is; CSS says how it looks
• Same page, different style sheet - the words on screen never moved
• This is why we spent time on class and <div>: CSS needs something to aim at
```
- **Separation of Concerns**: HTML handles content structure and semantic meaning; CSS handles typography, colors, layout, and visual presentation.
- Redesigning a website does not require altering HTML markup; updating the `.css` stylesheet restyles the entire website.

---

### Slide 22: Parts of a CSS Rule

```text
Parts of a CSS Rule
```

#### Anatomy of a Rule
```text
          selector              property
    (which elements this hits) (what to change)
               │                     │
               ▼                     ▼
              h1       {           color : red ;           }
                                            ▲  ▲
                                            │  │
                                         value semicolon
                                   (what it    (ends every
                                     should be) declaration)
```

#### Rules to Remember
```text
• One declaration = property: value;
• One rule can hold as many declarations as you like
• The curly braces mark where the rule starts and stops
• Forget a semicolon and the next line is ignored
```

#### Syntax Example
```css
h1 {
  color: red;
  text-align: center;
  font-size: 32px;
}
```
- **Critical Semicolon Rule**: In CSS, declarations are delimited by semicolons `;`. If you omit a semicolon after `color: red`, the parser reads `color: red text-align: center;` as an invalid property value and discards **both** declarations!

---

### Slide 23: Three Ways to Attach CSS (Inline, Internal, External)

```text
Three Ways to Attach CSS
```

#### 1. Inline Styles (On the Tag)
```html
<h1 style="color: red;">Pho Thin</h1>
<!-- Scope: One tag only -->
```

#### 2. Internal / Embedded Styles (In the Head)
```html
<head>
  <style>
    h1 { color: red; }
  </style>
</head>
<!-- Scope: One page only -->
```

#### 3. External Stylesheet (In its Own File)
```html
<link rel="stylesheet" href="style.css">
<!-- Scope: Every page that links to style.css -->
```

#### Points to Make & Cascade Precedence
```text
• When two rules clash, style="..." on the tag always wins
• Between <style> and the linked file, whichever comes later in the <head> wins
• Use the separate file: change one line, every page that links it changes
```
- **Precedence**: `Inline style attribute` > `Internal/External (whichever is declared later in source code)`.
- **Engineering Standard**: Always use **External CSS** files (`style.css`). It enables browser caching, reduces bandwidth, and permits site-wide visual updates from a single file.

---

### Slide 24: Selectors: Class, ID, Type

```text
Selectors: Class, ID, type
```

#### HTML Markup & CSS Selectors
```html
<h1 id="name">Pho Thin</h1>
<p>Beef noodle soup</p>
<p class="price">60,000 VND</p>
<p class="price">55,000 VND</p>
```
```css
h1, h2 { font-family: sans-serif; }
p { color: gray; }
.price { font-weight: bold; }
#name { color: red; }
```

#### Explanation of Selector Types
```text
• p - just the tag name, hits every paragraph on the page
• .price - a dot in front; the same class can sit on as many elements as you want
• #name - a hash in front; an id belongs to one element only
• h1, h2 - a comma applies the same rule to both tags
• Two rules can hit the same element: the prices are grey and bold
```
- **Type (Tag) Selector** (`p`): Matches all elements of that tag type globally.
- **Class Selector** (`.price`): Prefix with a dot `.`. Multi-use; multiple elements can share the same class name, and an element can have multiple classes (`class="price highlight"`).
- **ID Selector** (`#name`): Prefix with a hash `#`. Strictly unique; an ID must appear on only **one** element per page.
- **Grouping Selector** (`h1, h2`): Comma-separated list applying declarations to multiple selectors simultaneously.

---

### Slide 25: Which Rule Wins (Specificity, Cascade, `!important`)

```text
Which Rule Wins
```

#### Evaluation Order (Specificity Hierarchy)
```text
1. More specific selector wins: id > class > tag
2. Still tied? The one written later wins
3. style="..." on the tag beats every selector
```

#### Two Common Traps
```text
• One id beats any number of classes - the counts do not add up
• !important overrules all of it. You will meet it in other people's code; do not write it yourself
```
- Specificity operates in strict categorical tiers:
  - Inline styles = `1,0,0,0`
  - ID selectors = `0,1,0,0`
  - Class, attribute, and pseudo-class selectors = `0,0,1,0`
  - Element (tag) selectors = `0,0,0,1`
- **One ID beats 1,000 classes**: A selector `#name` always overrides `.header.nav.item.active.btn...`. Specificity counts do not overflow into higher categories!

#### Side-by-Side Slide Examples
- **Example 1: Class beats Tag**:
  ```css
  .price { color: red; }
  p { color: gray; }
  ```
  On `<p class="price">`: Text is **red**. The class selector `.price` has higher specificity than the tag selector `p`, even though `p` was written later in the stylesheet!
- **Example 2: Last Line Wins (Tied Specificity)**:
  ```css
  p { color: red; }
  p { color: gray; }
  ```
  On `<p>`: Text is **gray**. Specificity is tied (both are single tag selectors), so the rule declared later in the stylesheet wins.

#### Debugging in DevTools
```text
When your CSS does nothing:
Press F12, click the element, read the Styles panel - the rule that lost is shown crossed out.
```

---

### Slide 26: Colours and Backgrounds

```text
Colours and Backgrounds
```

#### Code Example
```html
<h1>Pho Thin</h1>
<p class="price">60,000 VND</p>
<p class="note">Open 6am - 10am</p>
<p class="badge">Best seller</p>
```
```css
h1 { color: darkred; }
.price { color: #b00000; }
.note { color: rgb(90, 90, 90); }
.badge { background-color: gold; }
```

#### Core Principles
```text
• color paints the text, background-color paints the box behind it
• red = #ff0000 = rgb(255, 0, 0) - the same colour written three ways
• Hex is three pairs - red, green, blue - each from 00 to ff
```
- `color`: Applies to font glyphs and text characters.
- `background-color`: Fills the rectangular bounding box behind the text.
- Hexadecimal color values represent 8-bit channels for Red, Green, and Blue: `00` (decimal 0, zero intensity) to `ff` (decimal 255, maximum intensity).

---

### Slide 27: Colour Values (Hex, RGB, RGBA, HSL)

```text
Colour Values
```

#### The Four Color Notations
1. **Named Colors**: Standardized keywords (e.g., `red`, `gold`, `teal`, `indigo`, `white`, `tomato`, `olive`, `steelblue`, `gray`, `black`).
2. **Hexadecimal Notation (`#rrggbb`)**:
   - `#b00000`, `#00a86b`, `#1e90ff`, `#ffa500`, `#333333`.
   - **Shorthand Rule**: `#f00` expands to `#ff0000`. You can shorten `#rrggbb` to `#rgb` only when each channel pair contains identical characters.
3. **RGB and RGBA**:
   - `rgb(red, green, blue)`: Integers from `0` to `255`. E.g., `rgb(255, 99, 71)`.
   - `rgba(red, green, blue, alpha)`: Fourth parameter is opacity ranging from `0.0` (fully transparent) to `1.0` (fully solid/opaque).
   - E.g., `rgba(0, 0, 0, 0.5)` renders 50% semi-transparent black.
4. **HSL (Hue, Saturation, Lightness)**:
   - `Hue`: Angle on the color circle from `0` to `360` degrees (`0` = red, `120` = green, `240` = blue).
   - `Saturation`: `0%` (monochrome gray) to `100%` (fully vibrant color).
   - `Lightness`: `0%` (pure black), `50%` (normal color), `100%` (pure white).
   - E.g., `hsl(0, 100%, 50%)` is pure red.

---

### Slide 28: Fonts (Font Stack & Fallbacks)

```text
Fonts
The HTML:
<h1>Pho Thin</h1>
<p>Beef noodle soup</p>
<p class="note">herbs included</p>

The CSS:
body { font-family: Arial, Helvetica, sans-serif; }
h1 { font-size: 32px; font-weight: bold; }
.note { font-style: italic; font-size: 12px; }
```

#### The Three Primary Font Families
- **`serif`**: Characters with small decorative finishing strokes/feet (e.g., Times New Roman).
- **`sans-serif`**: Clean, modern letterforms without decorative feet (e.g., Arial, Helvetica).
- **`monospace`**: Fixed-width typefaces where every character occupies the exact same horizontal space (e.g., Courier New).

#### Rules for `font-family` Stacks
```text
• The list is read left to right - the browser takes the first font the computer actually has
• The last name must be serif, sans-serif or monospace - every computer has one of those
• font-weight: bold looks like <strong> but carries no meaning - keep meaning in HTML, looks in CSS
```

---

### Slide 29: Choosing a Font (Generic Families & Bold Semantics)

```text
Choosing a Font
```

#### 1. Fallback Logic Walkthrough
`font-family: Arial, Helvetica, sans-serif;`
- Step 1: Does the client computer have `Arial` installed? If yes, use it.
- Step 2: If no, does it have `Helvetica` installed? If yes, use it.
- Step 3: If neither exists, fall back to the operating system's default `sans-serif` font.

#### 2. "Bold Two Ways — Pick the Right One" (Exam Favorite!)
```text
• <strong>..</strong> - HTML. Says the words matter
• font-weight: bold - CSS. Says nothing; a screen reader will not stress it
• Important to the reader → <strong>. Bold only because it looks better → CSS
```
- If a word carries critical semantic importance (e.g., a deadline or warning), wrap it in `<strong>`. Screen-readers will emphasize it vocally.
- If text is made bold purely for aesthetic design reasons, use CSS `font-weight: bold`.

#### 3. Generic Font Families Table
| Generic Font Name | Description / Characteristics | Real-World Example |
| :--- | :--- | :--- |
| **`Serif`** | Fonts with small decorative feet at stroke ends | Times New Roman, Georgia |
| **`Sans-serif`** | Modern, clean fonts without serifs | Arial, Helvetica, Inter |
| **`Monospace`** | Fixed-width characters (code editors) | Courier, Consolas, Monaco |
| **`Cursive`** | Emulates handwriting and script calligraphy | Comic Sans, Brush Script |
| **`Fantasy`** | Decorative, stylized fonts for display banners | Impact, Papyrus |

---

### Slide 30: Font Values (`weight`, `style`, `size`, `stretch`)

```text
Font Values
```

#### Detailed Property Options
- **`font-weight`**:
  - Keywords: `normal`, `bold`, `lighter`, `bolder`.
  - Numerical Scale: `100, 200, 300, 400 (normal), 500, 600, 700 (bold), 800, 900`.
- **`font-style`**:
  - `normal`, `italic` (uses cursive glyphs designed for the font), `oblique` (mechanically slanted text).
- **`font-size`**:
  - Absolute Units: `px` (pixels), `pt` (points, 1pt = 1/72 inch).
  - Relative Units: `%` (percentage of parent), `em` (relative to current element font-size), `rem` (relative to root `<html>` font-size).
  - Keywords: `small`, `medium`, `large`.
- **`font-stretch`**:
  - `ultra-condensed`, `extra-condensed`, `condensed`, `semi-condensed`, `normal`, `semi-expanded`, `expanded`, `extra-expanded`, `ultra-expanded`.

---

### Slide 31: Formatting Text (`align`, `line-height`, `decoration`)

```text
Formatting Text
The HTML:
<h1>Pho Thin</h1>
<p>Beef noodle soup with fresh herbs</p>
<p><span class="old">70,000 VND</span> 60,000 VND</p>
<a href="/order">Order now</a>

What you write:
h1 { text-align: center; }
p { line-height: 1.6; }
a { text-decoration: none; }
.old { text-decoration: line-through; }
```

#### Key Properties Explained
```text
• text-align: center centres the text inside its box - it does not move the box itself
• text-decoration: none is how you take the underline off a link; line-through is how you show an old price
• line-height: 1.6 means 1.6 times the font size
```
- `text-align: center`: Centers inline text content horizontally within its block-level parent. It does not center the block element itself on the screen.
- `text-decoration: none`: Removes default browser link underlines.
- `text-decoration: line-through`: Draws a strikethrough horizontal line across text.
- `line-height: 1.6`: Unitless line height multiplier. If font-size is `16px`, line-height is `16px * 1.6 = 25.6px`.

---

### Slide 32: Text Values (`align`, `decoration`, `vertical-align`)

```text
Text Values
```

#### Available Values Summary
- **`text-align`**:
  - `left`: Left-aligned text (default for LTR languages).
  - `center`: Centered text.
  - `right`: Right-aligned text.
  - `justify`: Spaces words so text lines align flush with both left and right margins.
- **`text-decoration`**:
  - `none`, `underline`, `overline`, `line-through`.
- **`vertical-align` (For Inline Elements)**:
  - `baseline` (aligns with text baseline), `sub` (subscript), `super` (superscript).
- **`vertical-align` (For Table Cells `<td>`, `<th>`)**:
  - `top`, `middle`, `bottom`.

---

### Slide 33: Pseudo-classes (`:link`, `:visited`, `:hover`, `:active`)

```text
Pseudo-classes
a:link - never opened yet
a:link { color: red; }

a:visited - opened before
a:visited { color: green; }

a:hover - mouse is on it
a:hover { color: deeppink; }

a:active - button held down
a:active { background: yellow; }
```

#### The Four Anchor States
1. **`:link`**: Default unvisited state. The user has never clicked this destination URL in browser history.
2. **`:visited`**: Visited state. The user has navigated to this URL previously.
3. **`:hover`**: Triggered when the user's cursor hovers over the element.
4. **`:active`**: Triggered at the exact moment the mouse button is pressed down over the element, before it is released.

> **Midterm Order Rule (The LVHA Rule)**:
> In CSS stylesheets, link pseudo-classes must be declared in this exact sequence:  
> **L**ink $\rightarrow$ **V**isited $\rightarrow$ **H**over $\rightarrow$ **A**ctive ("**L**o**V**e **HA**te").  
> If `:hover` is declared before `:visited`, a visited link will never display its hover color because `:visited` overrides it!

---

### Slide 34: The Box Model (Content, Padding, Border, Margin)

```text
The Box Model
Every element is four boxes:
margin -> border -> padding -> content
```

#### Concentric Box Model Diagram
```text
  ┌────────────────────────────────────────────────────────┐
  │ MARGIN (Outside border, transparent, creates spacing)  │
  │   ┌────────────────────────────────────────────────┐   │
  │   │ BORDER (Surrounds padding and content)         │   │
  │   │   ┌────────────────────────────────────────┐   │   │
  │   │   │ PADDING (Inside border, shows bg color)│   │   │
  │   │   │   ┌────────────────────────────────┐   │   │   │
  │   │   │   │ CONTENT (Text, images, video)  │   │   │   │
  │   │   │   └────────────────────────────────┘   │   │   │
  │   │   └────────────────────────────────────────┘   │   │
  │   └────────────────────────────────────────────────┘   │
  └────────────────────────────────────────────────────────┘
```

#### Mathematical Calculation (Slide Example)
```css
.card {
  width: 200px;
  padding: 20px;
  border: 5px solid;
  margin: 10px;
}
```

```text
Calculation under standard Box Model:
  content width                     = 200px
+ padding (left 20px + right 20px)  =  40px
+ border (left 5px + right 5px)     =  10px
-------------------------------------------
= Box drawn on screen (visible width)= 250px

+ margin (left 10px + right 10px)   =  20px
-------------------------------------------
= Total space used on screen        = 270px
```

#### Key Rules to Memorize
```text
• padding is inside the border, margin is outside it - padding takes the background colour, margin never does
• width sets the content only; padding and border are added on top of it
• Press F12 and hover an element - DevTools draws these four boxes in the same four colours
```

---

### Slide 35: Box Values (Shorthands & Dimensions)

```text
Box Values
```

#### 1. Border Properties
- `border-style`: `solid`, `dashed`, `dotted`, `double`, `none`.
- `border-width`: `thin (1px)`, `medium (3px)`, `thick (5px)` or exact pixel values (`border-width: 2px;`).

#### 2. Margin & Padding Shorthand (Clockwise: Top, Right, Bottom, Left)
```text
• margin: 10px;
  all four sides = 10px

• margin: 10px 20px;
  top+bottom = 10px, left+right = 20px

• margin: 10px 20px 30px;
  top = 10px, left+right = 20px, bottom = 30px

• margin: 10px 20px 30px 40px;
  top = 10px, right = 20px, bottom = 30px, left = 40px (TRBL: Clockwise!)

• margin: 0 auto;
  top+bottom = 0, left+right = auto (Centres a block box horizontally inside its parent)
```

#### 3. Width and Height Properties
```text
• a fixed size:           width: 200px;
• share of the parent:    width: 50%;
• browser decides:        width: auto;
• never wider than:       max-width: 800px;
• never shorter than:     min-height: 400px;
```

---

### Slide 36: Sizing the Box (`content-box` vs. `border-box`)

```text
Sizing the Box
Same width - two results:
.a { width: 200px; padding: 20px; border: 5px solid; }
.b { width: 200px; padding: 20px; border: 5px solid; box-sizing: border-box; }
```

#### Side-by-Side Comparison
```text
Box .a (content-box - Default):
  Total drawn width = 200 (content) + 40 (padding) + 10 (border) = 250px
  Content remains 200px wide.

Box .b (border-box):
  Total drawn width = 200px FIXED.
  Padding and border eat into the inside:
  Content width shrinks to 200 - 40 - 10 = 150px.
```

#### Points to Make
```text
• Default is content-box: width counts the content only, so padding and border push the box wider
• border-box: width is the final width, and padding and border eat into it - the content shrinks instead
• Real projects start the stylesheet with * { box-sizing: border-box; } so every box behaves the second way
```

---

### Slide 37: Boxes in a Row (Flexbox Basics)

```text
Boxes in a Row
The HTML:
<div class="menu">
  <div class="card">Pho bo</div>
  <div class="card">Pho ga</div>
  <div class="card">Pho tai</div>
</div>

No CSS - div is block:
  Pho bo
  Pho ga
  Pho tai

With three lines of CSS:
.menu { display: flex; gap: 10px; justify-content: center; }
  Pho bo   Pho ga   Pho tai
```

#### Points to Make
```text
• display: flex goes on the parent; the children line up in a row by themselves
• gap sets the space between children - no margin tricks needed
• justify-content: flex-start center space-between space-around - where the row sits
• align-items: center centres them top to bottom - the thing that used to be hard
```
- **Parent Container Role**: Setting `display: flex` on `.menu` transforms its direct children (`.card`) into flexible flex items aligned horizontally along the main row axis.
- **`gap: 10px`**: Creates a 10px gap strictly between adjacent flex items, without adding unwanted margin to the outer edges.
- **`justify-content`**: Aligns items along the horizontal main axis (`center`, `flex-start`, `flex-end`, `space-between`, `space-around`).
- **`align-items`**: Aligns items along the cross axis (vertical centering).

---

### Slide 38: Styling a Table (`border-collapse`, Hover Effects)

```text
Styling a Table
The CSS:
table { border-collapse: collapse; }
th, td { border: 1px solid #999; padding: 8px; text-align: left; }
th { background-color: #b00000; color: white; }
tr:hover { background-color: #fff3cd; }
```

#### Points to Make
```text
• This is the promise from the HTML section: the lines were never in the table, they come from CSS
• border-collapse: collapse merges the doubled lines into one
• Style th, td together first, then override th on its own
• tr:hover is a pseudo-class - it only applies while the mouse is over that row
```
- Tables require CSS borders; without them, tables appear as borderless text grids.
- `tr:hover` highlights an entire row in pale yellow (`#fff3cd`) when hovered, improving readability on large data tables.

---

### Slide 39: Table Values (Spacing, Alignment, Captions)

```text
Table Values
```

#### Available Properties Breakdown
- **`border-collapse`**:
  - `collapse`: Adjacent cell borders merge into a single shared rule.
  - `separate`: Cells have individual borders separated by spacing.
- **`text-align in a cell`**: `left`, `center`, `right`.
- **`vertical-align in a cell`**: `top`, `middle`, `bottom`.
- **Size and Caption Properties**:
  - `width: 100%`: Table expands to fill the entire width of its parent container.
  - `width: auto`: Table contracts to fit the intrinsic width of its contents.
  - `border-spacing`: Specifies distance between cell borders when `border-collapse: separate`.
  - `caption-side: top` or `bottom`: Controls whether the `<caption>` element renders above or below the table.

---

### Slide 40: Final Exercise — Read This Page (4 Questions & Solutions)

```text
Exercise
Read this page:
<h1 class="title">Pho Thin</h1>
<p class="price">60,000 VND</p>

title { color: red; }
.price { color: green
font-size: 20px; }
.card { width: 300px; padding: 10px;
border: 2px solid; }

Four questions:
1. What colour is the heading, and why is it not red?
2. One character is missing in the second rule. Which one?
3. Because of that, will the price be green? Will it be 20px?
4. How wide is .card on screen?
```

#### Complete Solutions and Rationale

#### Question 1: What colour is the heading, and why is it not red?
- **Answer**: The heading is **black** (default browser font color), NOT red.
- **Why**: Look at the CSS selector: `title { color: red; }`. 
  - `title` is written as a **type selector** (matching a tag `<title>`).
  - However, in the HTML, the heading is `<h1 class="title">`.
  - To match a class, the selector must begin with a dot: `.title`. Because the dot was omitted, the selector searched for a non-existent `<title>` tag in the body and failed to match the `<h1>`.

#### Question 2: One character is missing in the second rule. Which one?
- **Answer**: The **semicolon (`;`)** is missing after `color: green`.
- **Code with error**:
  ```css
  .price {
    color: green          /* <-- Missing semicolon ';' here! */
    font-size: 20px;
  }
  ```

#### Question 3: Because of that, will the price be green? Will it be 20px?
- **Answer**: 
  - **Color**: It will **NOT be green**.
  - **Font size**: It will **NOT be 20px**.
- **Why**: When a semicolon is omitted in CSS, the parser treats `color: green font-size: 20px;` as a single property-value pair. Because `green font-size: 20px` is an invalid value for the `color` property, the CSS parser discards the entire declaration. The browser displays the price in default black font at default paragraph size (16px).

#### Question 4: How wide is `.card` on screen?
- **Answer**: **324px** wide.
- **Step-by-Step Calculation**:
  - The rule does not specify `box-sizing: border-box`, so it defaults to `box-sizing: content-box`.
  - Content width = `300px`
  - Padding (left 10px + right 10px) = `20px`
  - Border (left 2px + right 2px) = `4px`
  - Total drawn width on screen = `300 + 20 + 4 = 324px`.

---

### Slide 41: Conclusion
```text
Thank you for listening!
KIEU Quoc Viet, HUYNH Vinh Nam | HTML + CSS | Hanoi, August 2024 | 40 / 40
```
Concludes Lecture 02.

---

# Midterm Exam Master Review: Key Traps, Calculations & Formulas

---

### 1. The CSS Box Model Formula

For any block element under default `box-sizing: content-box`:
```text
Total Drawn Width = width + padding-left + padding-right + border-left + border-right
Total Occupied Width = Total Drawn Width + margin-left + margin-right
```

Under `box-sizing: border-box`:
```text
Total Drawn Width = width (Fixed)
Content Width = width - (padding-left + padding-right + border-left + border-right)
```

---

### 2. Specificity Ranking Hierarchy

When multiple CSS selectors target the exact same HTML element:
```text
Inline style="..." (1,0,0,0)  >  #id (0,1,0,0)  >  .class (0,0,1,0)  >  tag (0,0,0,1)
```
- **Rule 1**: Higher category wins regardless of count (1 ID beats 100 classes).
- **Rule 2**: If specificity is tied, the rule declared **later** in the stylesheet wins.
- **Rule 3**: `!important` overrides everything.

---

### 3. Shorthand Margin & Padding Clockwise Rule

```text
margin: [Top] [Right] [Bottom] [Left];   (Clockwise: 12h -> 3h -> 6h -> 9h)
```
- 1 value: `margin: 10px;` (All 4 sides)
- 2 values: `margin: 10px 20px;` (Top/Bottom, Left/Right)
- 3 values: `margin: 10px 20px 30px;` (Top, Left/Right, Bottom)
- 4 values: `margin: 10px 20px 30px 40px;` (Top, Right, Bottom, Left)
