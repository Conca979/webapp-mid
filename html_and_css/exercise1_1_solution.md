# Web Application Development — Exercise 1.1 Solution & Code Guide
**University of Science and Technology of Hanoi (USTH)**  
**Module:** Web Application Development (HTML & CSS Basic Labwork)  
**File Reference:** `Exercise1.1 - HTML+CSS (Basic).pdf`  
**Purpose:** Complete reference solutions and line-by-line code explanation for midterm exam preparation.

---

## Table of Contents
1. [Overview & Lab Objectives](#overview--lab-objectives)
2. [Question 1: `task1.html` — Document Skeleton & Headings](#question-1-task1html--document-skeleton--headings)
3. [Question 2: `task2.html` — Ordered & Unordered Lists](#question-2-task2html--ordered--unordered-lists)
4. [Question 3: `task3.html` — Images & Thumbnail Sizing](#question-3-task3html--images--thumbnail-sizing)
5. [Question 4: `task4.html` — Image Hyperlinks](#question-4-task4html--image-hyperlinks)
6. [Question 5: `task5.html` — Timetable with `rowspan`](#question-5-task5html--timetable-with-rowspan)
7. [Question 6: `task6.html` — 3 Ways to Attach CSS & Selectors](#question-6-task6html--3-ways-to-attach-css--selectors)
8. [Question 7: `task7.html` — Image Border & `:hover` Pseudo-class](#question-7-task7html--image-border--hover-pseudo-class)
9. [Question 8: `task8.html` — Hyperlinks, `:visited` & `:hover`](#question-8-task8html--hyperlinks-visited--hover)
10. [Question 9: `task9.html` — Styled Table with Row Hover](#question-9-task9html--styled-table-with-row-hover)
11. [Question 10: `task10.html` — Multi-column Page Layout with `<div>`](#question-10-task10html--multi-column-page-layout-with-div)
12. [Question 11: `task11.html` — Categorized Photo Gallery Website](#question-11-task11html--categorized-photo-gallery-website)
13. [Midterm Exam Cheat Sheet for Lab 1.1](#midterm-exam-cheat-sheet-for-lab-11)

---

## Overview & Lab Objectives
This lab covers the essential building blocks of web development:
- HTML document structure and semantic tags (`<h1>`, `<p>`, `<a>`, `<img>`).
- Lists (`<ul>`, `<ol>`, `<li>`).
- Complex tables with merged cells (`rowspan`, `colspan`).
- CSS inclusion methods (Inline, Internal, External).
- Selectors (Type, Class `.`, ID `#`) and Specificity.
- Interactive link states using CSS pseudo-classes (`:hover`, `:visited`).
- CSS Box Model, borders, padding, and basic multi-column page layout.

---

## Question 1: `task1.html` — Document Skeleton & Headings

### Requirement
Create a web page named `task1.html` displaying:
- A prominent heading: **"The Bachelor program is a important part of USTH."**
- A paragraph: *"It is applying the European Credit Transfer and Accumulation System (ECTS) as in most of European countries, with the study program corresponds to 180 Credits in 3 years (60 Credits/year)."*

### Complete Code (`task1.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>USTH Bachelor Program</title>
  </head>
  <body>
    <h1>The Bachelor program is a important part of USTH.</h1>
    <p>
      It is applying the European Credit Transfer and Accumulation System (ECTS) 
      as in most of European countries, with the study program corresponds to 
      180 Credits in 3 years (60 Credits/year).
    </p>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 1: <!DOCTYPE html>`: Declares HTML5 document type. Tells the browser rendering engine to parse the file using standard mode rather than quirks mode.
- `Line 2: <html lang="en">`: The root container element. The `lang="en"` attribute specifies the human language for search engines, screen readers, and translation tools.
- `Line 3-6: <head>...</head>`: Houses metadata and page settings that are not displayed directly on the webpage canvas.
- `Line 4: <meta charset="UTF-8">`: Declares character encoding as UTF-8, ensuring special characters and accents render properly.
- `Line 5: <title>USTH Bachelor Program</title>`: Sets the text shown on the browser tab, bookmark title, and search engine results.
- `Line 7-14: <body>...</body>`: Contains all visible webpage content.
- `Line 8: <h1>...</h1>`: The top-level heading. Block-level element rendered in large, bold font.
- `Line 9-13: <p>...</p>`: Paragraph block. The browser automatically collapses the line breaks inside the code into single spaces on the screen.

---

## Question 2: `task2.html` — Ordered & Unordered Lists

### Requirement
Create a web page named `task2.html` containing:
- An **ordered list** (`<ol>`) of your most favorite movies.
- An **unordered list** (`<ul>`) of subjects you are studying this semester.

### Complete Code (`task2.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Favorite Movies & Subjects</title>
  </head>
  <body>
    <h2>My Favorite Movies</h2>
    <ol>
      <li>Interstellar</li>
      <li>Inception</li>
      <li>The Dark Knight</li>
      <li>Spirited Away</li>
    </ol>

    <h2>Subjects in This Semester</h2>
    <ul>
      <li>Web Application Development</li>
      <li>Mobile Application Development</li>
      <li>Introduction to Databases</li>
      <li>Computer Networks</li>
    </ul>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 8: <h2>My Favorite Movies</h2>`: Section heading.
- `Line 9: <ol>`: Ordered List. Instructs the browser to render list items sequentially with auto-generated numbers (`1.`, `2.`, `3.`, ...).
- `Line 10-13: <li>...</li>`: List Item elements. You do **not** type the numbers manually; the browser calculates and renders them.
- `Line 14: </ol>`: Closes the ordered list block.
- `Line 17: <ul>`: Unordered List. Instructs the browser to render items with bullet points (`•`).
- `Line 18-21: <li>...</li>`: List items nested inside the unordered list.

---

## Question 3: `task3.html` — Images & Thumbnail Sizing

### Requirement
- Download about 3 images (dimensions > 300x300px).
- Save them inside a subfolder named `images` located in the same directory as `task3.html`.
- Display all 3 images as thumbnails scaled to **50x50px**.

### Complete Code (`task3.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Image Thumbnails</title>
    <style>
      .thumb {
        width: 50px;
        height: 50px;
        object-fit: cover;
        margin-right: 10px;
      }
    </style>
  </head>
  <body>
    <h2>Photo Gallery Thumbnails (50x50px)</h2>
    <img src="images/photo1.jpg" alt="USTH Campus Building" class="thumb">
    <img src="images/photo2.jpg" alt="Computer Lab" class="thumb">
    <img src="images/photo3.jpg" alt="Student Library" class="thumb">
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 7-14: <style>...</style>`: Internal CSS stylesheet.
- `Line 8-13: .thumb { ... }`:
  - `width: 50px; height: 50px;`: Constrains the display dimensions of the image on the screen, shrinking the original 300px+ image into a thumbnail.
  - `object-fit: cover;`: Prevents the image from being distorted or stretched if its original aspect ratio is not 1:1.
  - `margin-right: 10px;`: Adds horizontal spacing between thumbnails.
- `Line 17-19: <img src="images/photo1.jpg" alt="..." class="thumb">`:
  - `src="images/photo1.jpg"`: Sub-folder relative path. Looks into the `images` folder located in the same directory as `task3.html`.
  - `alt="..."`: Alternative text for accessibility and screen readers.
  - `<img>` is a **void element** (it has no closing tag).

---

## Question 4: `task4.html` — Image Hyperlinks

### Requirement
Create `task4.html` such that clicking each 50x50px thumbnail opens the corresponding full-size image file.

### Complete Code (`task4.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Clickable Thumbnails</title>
    <style>
      .thumb {
        width: 50px;
        height: 50px;
        object-fit: cover;
        border: 1px solid #ccc;
        margin-right: 10px;
      }
    </style>
  </head>
  <body>
    <h2>Click a thumbnail to view full-size image</h2>

    <a href="images/photo1.jpg" target="_blank">
      <img src="images/photo1.jpg" alt="USTH Campus Building" class="thumb">
    </a>

    <a href="images/photo2.jpg" target="_blank">
      <img src="images/photo2.jpg" alt="Computer Lab" class="thumb">
    </a>

    <a href="images/photo3.jpg" target="_blank">
      <img src="images/photo3.jpg" alt="Student Library" class="thumb">
    </a>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 18: <a href="images/photo1.jpg" target="_blank">`:
  - Wraps the `<img>` element inside an anchor tag.
  - `href="images/photo1.jpg"`: Points directly to the full-size image file.
  - `target="_blank"`: Instructs the browser to open the image in a new tab or window instead of replacing the current page.
- `Line 19: <img src="images/photo1.jpg" ...>`: Acts as the clickable trigger for the enclosing hyperlink.

---

## Question 5: `task5.html` — Timetable with `rowspan`

### Requirement
Create a web page named `task5.html` containing the schedule table:
- 6 columns: First column for time slots (`Morning`, `Afternoon`), followed by `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday`.
- `Chemistry` on Tuesday spans across **both Morning and Afternoon** (`rowspan="2"`).

### Complete Code (`task5.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>USTH Timetable</title>
    <style>
      table {
        border-collapse: collapse;
        width: 80%;
        margin: 20px auto;
        text-align: center;
      }
      th, td {
        border: 1px solid black;
        padding: 10px;
      }
      th {
        background-color: #f2f2f2;
      }
    </style>
  </head>
  <body>
    <h2 style="text-align: center;">Weekly Schedule</h2>
    <table>
      <!-- Row 1: Header Row -->
      <tr>
        <th></th>
        <th>Monday</th>
        <th>Tuesday</th>
        <th>Wednesday</th>
        <th>Thursday</th>
        <th>Friday</th>
      </tr>

      <!-- Row 2: Morning Slot -->
      <tr>
        <td>Morning</td>
        <td>Math</td>
        <td rowspan="2">Chemistry</td>
        <td>Mobile</td>
        <td></td>
        <td>History</td>
      </tr>

      <!-- Row 3: Afternoon Slot -->
      <tr>
        <td>Afternoon</td>
        <td>Physics</td>
        <!-- Tuesday cell is omitted here because Chemistry spans down from Row 2! -->
        <td></td>
        <td></td>
        <td></td>
      </tr>
    </table>
  </body>
</html>
```

### Line-by-Line Explanation & Midterm Trap
- `Line 7: border-collapse: collapse;`: Merges individual cell borders into single lines. Without this, borders appear doubled.
- `Line 28-35: <tr> (Row 1)`: Contains 6 `<th>` header cells. The top-left cell `<th></th>` is intentionally left blank to align with the time-slot column below.
- `Line 38-45: <tr> (Row 2)`:
  - `<td>Morning</td>`: Slot identifier.
  - `<td>Math</td>`: Monday morning.
  - `<td rowspan="2">Chemistry</td>`: **Rowspan definition**. This cell occupies 2 rows vertically (Row 2 and Row 3).
  - `<td>Mobile</td>`, `<td></td>`, `<td>History</td>`: Wednesday, Thursday, Friday.
- `Line 48-55: <tr> (Row 3)`:
  - `<td>Afternoon</td>`: Slot identifier.
  - `<td>Physics</td>`: Monday afternoon.
  - **Notice**: There is **NO `<td>` for Tuesday** in Row 3! Because `Chemistry` was defined with `rowspan="2"` in Row 2, it already occupies the Tuesday column of Row 3. Adding another `<td>` here would push the table out to 7 columns!
  - `<td></td>`, `<td></td>`, `<td></td>`: 3 empty cells for Wednesday, Thursday, Friday afternoons.

---

## Question 6: `task6.html` — 3 Ways to Attach CSS & Selectors

### Requirement
Write `task6.html` with three paragraphs demonstrating:
1. First paragraph: Text size is 0.5 of normal font size (`0.5em`). Target with an **ID selector**.
2. Second paragraph: Text color is red. Target with a **class selector**.
3. Third paragraph: Also has red text, sharing the same class.
4. Demonstrate all three ways of attaching CSS: **inline style**, **embedded style (`<style>`)**, and **external style (`<link>`)**.

### External Stylesheet (`task6_style.css`)
```css
/* External CSS file */
.red-text {
  color: red;
}
```

### Complete Code (`task6.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>CSS Attachment & Selectors</title>
    <!-- Method 1: External Style -->
    <link rel="stylesheet" href="task6_style.css">

    <!-- Method 2: Embedded / Internal Style -->
    <style>
      #first-para {
        font-size: 0.5em; /* 0.5 of normal font size (1em) */
      }
    </style>
  </head>
  <body>
    <!-- Target with ID selector (#first-para) -->
    <p id="first-para">
      This is the first paragraph. Its text size is half the normal size (0.5em).
    </p>

    <!-- Target with Class selector (.red-text) via external stylesheet -->
    <p class="red-text">
      This is the second paragraph. Its text color is red via a class selector.
    </p>

    <!-- Method 3: Inline style on the tag -->
    <p class="red-text" style="font-weight: bold;">
      This is the third paragraph. It shares the red-text class and uses an inline style for bold text.
    </p>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 7: <link rel="stylesheet" href="task6_style.css">`: Attaches the external stylesheet where `.red-text { color: red; }` is defined.
- `Line 10-14: <style> #first-para { font-size: 0.5em; } </style>`: Embedded CSS in `<head>`. Uses the ID selector `#first-para` (`#` prefix) to set font size to half of the base font size (`1em * 0.5 = 0.5em`).
- `Line 22: <p class="red-text">`: Uses class selector `.red-text` (`.` prefix). Reusable across multiple elements.
- `Line 27: <p class="red-text" style="font-weight: bold;">`: Demonstrates inline styling via the `style="..."` attribute. It receives red color from the external class and bold weight from the inline style.

---

## Question 7: `task7.html` — Image Border & `:hover` Pseudo-class

### Requirement
Create `task7.html` containing an image:
- Border: `color: red`, `size: 5px`, `solid`.
- Use the `:hover` pseudo-class to change the image's appearance when hovered.

### Complete Code (`task7.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Image Border & Hover</title>
    <style>
      .interactive-img {
        width: 300px;
        height: 200px;
        object-fit: cover;
        border: 5px solid red; /* 5px size, solid style, red color */
        transition: all 0.3s ease; /* Smooth visual transition */
      }

      /* Pseudo-class hover */
      .interactive-img:hover {
        border-color: blue;
        opacity: 0.8;
        transform: scale(1.05); /* Slightly enlarges image on hover */
      }
    </style>
  </head>
  <body>
    <h2>Hover over the image</h2>
    <img src="images/photo1.jpg" alt="Sample Campus Photo" class="interactive-img">
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 11: border: 5px solid red;`: Shorthand property setting border width (`5px`), border style (`solid`), and border color (`red`).
- `Line 12: transition: all 0.3s ease;`: Smooths the CSS property changes when the hover state activates or deactivates.
- `Line 16-20: .interactive-img:hover { ... }`: The `:hover` pseudo-class activates only when the user's mouse cursor is placed over the image. It changes the border color to blue, dims opacity to 80%, and scales the element up by 5%.

---

## Question 8: `task8.html` — Hyperlinks, `:visited` & `:hover`

### Requirement
Create `task8.html` containing three links to other pages:
- Use `text-decoration: none` to remove underlines.
- Visited links become **red** (`a:visited`).
- Hovered links become **green** (`a:hover`).

### Complete Code (`task8.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Styled Hyperlinks</title>
    <style>
      /* Base link styling */
      a {
        text-decoration: none; /* Removes default browser underline */
        color: blue;           /* Default unvisited link color */
        font-size: 18px;
        margin-right: 20px;
      }

      /* Visited link state */
      a:visited {
        color: red;            /* Turns red after being visited */
      }

      /* Hover link state */
      a:hover {
        color: green;          /* Turns green when hovered */
        text-decoration: underline; /* Optional: restores underline on hover */
      }
    </style>
  </head>
  <body>
    <h2>Navigation Links</h2>
    <p>
      <a href="https://usth.edu.vn">USTH Homepage</a>
      <a href="https://google.com">Google Search</a>
      <a href="https://wikipedia.org">Wikipedia</a>
    </p>
  </body>
</html>
```

### Line-by-Line Explanation & The LVHA Order Rule
- `Line 9: text-decoration: none;`: Strips the default browser underline from the anchor tags.
- `Line 16: a:visited { color: red; }`: Targets links whose destination URL is present in the browser's local browsing history.
- `Line 21: a:hover { color: green; }`: Targets the link when the mouse cursor hovers over it.
- **Critical Exam Rule (The LVHA Rule)**:
  - Selectors must be declared in this exact order: `:link` $\rightarrow$ `:visited` $\rightarrow$ `:hover` $\rightarrow$ `:active`.
  - If `a:hover` were placed *before* `a:visited`, then once a link was visited, the `:visited` rule would override `:hover`, preventing the link from ever turning green!

---

## Question 9: `task9.html` — Styled Table with Row Hover

### Requirement
Create `task9.html` containing the table:
- Headers: `Subject`, `ECTS`.
- Data rows:
  - Math: 3
  - Physics: 5
  - Chemistry: 4
  - English: 3
- Header with dark blue background, white text.
- Row pointed by mouse cursor is highlighted via CSS (`tr:hover`).

### Complete Code (`task9.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>ECTS Credits Table</title>
    <style>
      table {
        border-collapse: collapse;
        width: 60%;
        margin: 30px auto;
        font-family: Arial, sans-serif;
      }
      th, td {
        border: 1px solid #ddd;
        padding: 12px;
        text-align: center;
      }
      /* Dark blue header with white text */
      th {
        background-color: #1a4f8b;
        color: white;
      }
      /* Alternating row background for readability */
      tr:nth-child(even) {
        background-color: #f9f9f9;
      }
      /* Highlight the row pointed by mouse */
      tbody tr:hover {
        background-color: #ffe082; /* Highlight color */
        cursor: pointer;
      }
    </style>
  </head>
  <body>
    <h2 style="text-align: center;">Course Credits Table</h2>
    <table>
      <thead>
        <tr>
          <th>Subject</th>
          <th>ECTS</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Math</td>
          <td>3</td>
        </tr>
        <tr>
          <td>Physics</td>
          <td>5</td>
        </tr>
        <tr>
          <td>Chemistry</td>
          <td>4</td>
        </tr>
        <tr>
          <td>English</td>
          <td>3</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 8: border-collapse: collapse;`: Eliminates gaps between table cells.
- `Line 18-21: th { background-color: #1a4f8b; color: white; }`: Sets the header background to dark blue and font to white.
- `Line 27-30: tbody tr:hover { background-color: #ffe082; }`: The pseudo-class `:hover` is applied to `<tr>` table rows. When the mouse hovers over any row in `<tbody>`, its entire background changes to yellow.

---

## Question 10: `task10.html` — Multi-column Page Layout with `<div>`

### Requirement
Create `task10.html` with the layout shown in the diagram:
- Top Header / Banner (`<div>`) in blue.
- Middle section with 2 panels:
  - Left sidebar (`<div>`) in light gray/blue.
  - Right content panel (`<div>`) in light green.
- Bottom Footer (`<div>`) in blue.

### Complete Code (`task10.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>CSS Page Layout</title>
    <style>
      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }
      body {
        font-family: Arial, sans-serif;
        padding: 10px;
      }
      /* Top Banner */
      .banner {
        background-color: #3b71ca;
        color: white;
        text-align: center;
        padding: 25px;
        font-size: 24px;
        font-weight: bold;
      }
      /* Middle Container */
      .main-container {
        display: flex;
        min-height: 400px;
        margin-top: 10px;
        margin-bottom: 10px;
        gap: 10px;
      }
      /* Left Column */
      .sidebar {
        flex: 1; /* 25% to 30% width */
        background-color: #dbeafe;
        padding: 20px;
        border: 1px solid #bfdbfe;
      }
      /* Right Column */
      .content {
        flex: 3; /* 70% to 75% width */
        background-color: #dcfce7; /* Light green */
        padding: 20px;
        border: 1px solid #bbf7d0;
      }
      /* Bottom Footer */
      .footer {
        background-color: #3b71ca;
        color: white;
        text-align: center;
        padding: 15px;
        font-size: 16px;
      }
    </style>
  </head>
  <body>
    <div class="banner">Top Banner</div>
    
    <div class="main-container">
      <div class="sidebar">
        <h3>Sidebar</h3>
        <p>Navigation or additional options.</p>
      </div>
      <div class="content">
        <h3>Main Content</h3>
        <p>Primary information displayed here.</p>
      </div>
    </div>

    <div class="footer">Footer Area</div>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 7-11: * { box-sizing: border-box; ... }`: Universal reset ensuring padding and borders do not expand container widths.
- `Line 23-29: .main-container { display: flex; ... }`: Declares the middle container as a **Flexbox parent**. Its two child `<div>`s (`.sidebar` and `.content`) automatically line up horizontally side-by-side.
- `Line 31: flex: 1;` vs `Line 37: flex: 3;`: Distributes space in a 1:3 ratio (the sidebar takes 25% of available width; the content takes 75%).
- `Line 44-50: .footer`: Block element placed after the flex container, clearing the columns and stretching across the full width.

---

## Question 11: `task11.html` — Categorized Photo Gallery Website

### Requirement
Build a categorized photo gallery website:
- **Top Banner**: Site title.
- **Left Panel**: Links to categories: `Category 1`, `Category 2`, `Category 3`, and an `About` link.
- **Right Panel**: Grid of photo thumbnails with thin borders.
- Clicking a category link displays photos for that category.
- Clicking a thumbnail opens the full-size photo (in a new tab/pop-up window).
- "About" link points to a page containing the developer student's name.
- **Bottom Footer**: Copyright notice.

### File 1: About Page (`about.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>About Developer</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        padding: 40px;
        text-align: center;
      }
      .card {
        display: inline-block;
        border: 1px solid #ccc;
        padding: 30px;
        border-radius: 8px;
        box-shadow: 0 4px 6px rgba(0,0,0,0.1);
      }
    </style>
  </head>
  <body>
    <div class="card">
      <h2>Website Developer</h2>
      <p><strong>Student Name:</strong> Nguyen Van A</p>
      <p><strong>Student ID:</strong> BI12-001</p>
      <p><strong>Institution:</strong> University of Science and Technology of Hanoi (USTH)</p>
      <p><a href="task11.html">Back to Gallery</a></p>
    </div>
  </body>
</html>
```

### File 2: Gallery Page (`task11.html`)
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Categorized Photo Gallery</title>
    <style>
      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }
      body {
        font-family: Arial, sans-serif;
        background-color: #f4f6f8;
      }
      /* Top Banner */
      .banner {
        background-color: #2563eb;
        color: white;
        padding: 20px;
        text-align: center;
      }
      /* Layout Container */
      .gallery-layout {
        display: flex;
        max-width: 1000px;
        margin: 20px auto;
        gap: 20px;
        min-height: 450px;
      }
      /* Left Panel */
      .sidebar {
        width: 200px;
        background-color: #1e293b;
        padding: 20px;
        border-radius: 6px;
      }
      .sidebar h3 {
        color: white;
        margin-bottom: 15px;
      }
      .sidebar a {
        display: block;
        padding: 10px 12px;
        color: #94a3b8;
        text-decoration: none;
        margin-bottom: 8px;
        border-radius: 4px;
        background-color: #334155;
        transition: background 0.2s;
      }
      .sidebar a:hover {
        background-color: #3b82f6;
        color: white;
      }
      /* Right Panel */
      .photo-grid {
        flex: 1;
        background-color: white;
        padding: 20px;
        border-radius: 6px;
        border: 1px solid #e2e8f0;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 15px;
      }
      .photo-card {
        border: 1px solid #cbd5e1;
        padding: 6px;
        border-radius: 4px;
        text-align: center;
        background: #f8fafc;
      }
      .photo-card img {
        width: 100%;
        height: 100px;
        object-fit: cover;
        display: block;
        border-radius: 2px;
        transition: transform 0.2s;
      }
      .photo-card img:hover {
        transform: scale(1.05);
      }
      /* Footer */
      .footer {
        background-color: #2563eb;
        color: white;
        text-align: center;
        padding: 12px;
        font-size: 14px;
      }
    </style>
  </head>
  <body>
    <!-- Top Banner -->
    <header class="banner">
      <h1>USTH Campus Photo Gallery</h1>
    </header>

    <!-- Main Layout -->
    <div class="gallery-layout">
      <!-- Left Panel -->
      <aside class="sidebar">
        <h3>Categories</h3>
        <a href="task11.html?cat=all">All Photos</a>
        <a href="task11.html?cat=campus">Campus</a>
        <a href="task11.html?cat=labs">Research Labs</a>
        <a href="task11.html?cat=activities">Activities</a>
        <a href="about.html">About Developer</a>
      </aside>

      <!-- Right Panel -->
      <main class="photo-grid">
        <div class="photo-card">
          <a href="images/photo1.jpg" target="_blank">
            <img src="images/photo1.jpg" alt="Campus Building">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo2.jpg" target="_blank">
            <img src="images/photo2.jpg" alt="ICT Computer Lab">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo3.jpg" target="_blank">
            <img src="images/photo3.jpg" alt="University Library">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo1.jpg" target="_blank">
            <img src="images/photo1.jpg" alt="Lecture Hall">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo2.jpg" target="_blank">
            <img src="images/photo2.jpg" alt="Conference Room">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo3.jpg" target="_blank">
            <img src="images/photo3.jpg" alt="Sports Field">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo1.jpg" target="_blank">
            <img src="images/photo1.jpg" alt="Main Gate">
          </a>
        </div>
        <div class="photo-card">
          <a href="images/photo2.jpg" target="_blank">
            <img src="images/photo2.jpg" alt="Student Dormitory">
          </a>
        </div>
      </main>
    </div>

    <!-- Bottom Copyright -->
    <footer class="footer">
      <p>&copy; 2026 USTH - University of Science and Technology of Hanoi. All rights reserved.</p>
    </footer>
  </body>
</html>
```

### Line-by-Line Explanation
- `Line 28: display: flex;`: Places the `.sidebar` and `.photo-grid` into a horizontal two-column layout.
- `Line 36: width: 200px;`: Fixes the sidebar at 200px width.
- `Line 44: display: block;` on sidebar links: Converts inline `<a>` tags into clickable full-width buttons.
- `Line 58: display: grid; grid-template-columns: repeat(4, 1fr);`: Organizes thumbnail items into a clean 4-column photo grid.
- `Line 72: target="_blank"`: Opens the full-size image in a new tab when clicked.
- `Line 96: <a href="about.html">`: Fulfills the requirement of linking to the About page displaying the developer student's name.

---

## Midterm Exam Cheat Sheet for Lab 1.1

1. **Table Cell Counting with `rowspan`**:
   - If cell A has `rowspan="N"`, it occupies the current row plus the next $N-1$ rows in that same column position.
   - In subsequent rows, **do not write a `<td>` for that column**.
2. **Anchor Tags around Images**:
   - `<a href="large.jpg"><img src="thumb.jpg"></a>` turns an image into a hyperlink.
3. **Link Pseudo-Class Order**:
   - Always write: `:link` $\rightarrow$ `:visited` $\rightarrow$ `:hover` $\rightarrow$ `:active` (LVHA).
4. **Void Elements**:
   - `<img>`, `<br>`, `<hr>`, `<input>`, `<meta>` never take closing tags (`</img>` is invalid HTML).
