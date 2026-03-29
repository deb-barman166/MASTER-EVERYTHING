# 🏗️ HTML — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Tag, Attribute, Secret & Hidden Power

> 📘 **The most complete HTML guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing HTML to **mastering** HTML.
> ⏱️ *Time to complete:* Self-paced — days to weeks
> 🛠️ *What you'll gain:* Every element, attribute, hidden secret, semantic pattern, accessibility technique, and performance trick that separates a 0.01% HTML developer from the rest.

---

## Table of Contents

1. [🧠 What is HTML?](#1-what-is-html-super-simple)
2. [🌍 Why HTML Exists & Still Matters](#2-why-html-exists--still-matters)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete Element System Breakdown](#4-complete-element-system-breakdown)
5. [🔄 Real-World Workflow](#5-real-world-workflow)
6. [🧪 Hands-on Practice Projects](#6-hands-on-practice-projects)
7. [⚠️ Common Mistakes](#7-common-mistakes)
8. [🔥 Pro Tips & Hidden Tricks](#8-pro-tips--hidden-tricks)
9. [🚀 Advanced Concepts](#9-advanced-concepts-expert-level)
10. [💀 0.01% Hidden Secrets](#10-001-hidden-secrets-ultra-elite)
11. [🗺️ Complete Roadmap](#11-complete-roadmap)
12. [🧩 Bonus Deep Insights](#12-bonus-deep-insights)
13. [📌 Summary & Cheat Sheet](#13-summary-quick-revision--cheat-sheet)

---

## 🧠 1. What is HTML? (Super Simple)

### The 12-Year-Old Explanation

Imagine you are building a house. Before you paint the walls, buy furniture, or install electricity — you first need a **skeleton**. Beams, walls, floors, doors, windows. That structure is what holds everything else together.

**HTML is the skeleton of every webpage.** It stands for **HyperText Markup Language**. It tells the web browser: "Here is a heading. Here is a paragraph. Here is an image. Here is a link to another page." The browser reads those instructions and builds the visible structure on your screen.

Every website you have ever visited — Google, YouTube, Instagram, Wikipedia — is built on HTML at its foundation. No matter how complex the technology, every webpage ultimately becomes HTML that your browser reads and displays.

HTML was invented by **Sir Tim Berners-Lee** in 1991 when he was at CERN (the particle physics lab in Switzerland). He wanted scientists to share documents over the internet. What he created accidentally became the foundation of the entire modern web.

### Real-Life Analogy

💡 **Think of it like this:**
Building a website is like writing a book.

- **HTML** = The words and chapters — the actual content and structure
- **CSS** = The typography, colors, and layout — how it looks
- **JavaScript** = Interactive features — like flip-out quizzes or clickable maps

You cannot have CSS or JavaScript without HTML. HTML is always first. Always the foundation.

### One-Line Definition

> **HTML** is a markup language that uses tags to define the structure and meaning of content on the web — telling browsers what each piece of content IS, not just how it looks.

---

## 🌍 2. Why HTML Exists & Still Matters

### The Problem It Solved

Before HTML, sharing information over the internet required both parties to use the same software. There was no universal format. Tim Berners-Lee needed a way for scientists at CERN — using different computers and operating systems — to share research documents with each other.

He invented HTML as a **universal document format** that any computer with a browser could render. The revolutionary addition was **hyperlinks** — text that, when clicked, loaded a completely different document from anywhere in the world. This was the birth of the World Wide Web.

### Where HTML Is Used Today

| Context                     | How HTML Is Used                                                  |
|-----------------------------|-------------------------------------------------------------------|
| Every website on Earth      | The structural layer of all web pages                             |
| Web Applications            | React, Vue, Angular — all generate HTML at runtime                |
| Email Clients               | HTML emails (Gmail, Outlook) use a subset of HTML                 |
| Progressive Web Apps        | PWAs are HTML apps installable on phones                          |
| Electron Desktop Apps       | VS Code, Slack, Discord — HTML/JS wrapped as desktop apps         |
| PDF Generation              | Tools like WeasyPrint convert HTML to PDF                         |
| Browser Extensions          | Popup UIs are HTML                                                |
| Documentation Tools         | GitHub README rendering, MkDocs, Docusaurus                       |
| eBooks (EPUB)               | EPUB format is ZIP files containing HTML                          |
| Game UIs                    | Godot, Unity WebGL — overlays built with HTML                     |

### Why YOU Should Master It Deeply

1. **You cannot build anything for the web without it.** React, Django templates, FastAPI responses — they all generate HTML.
2. **Bad HTML breaks accessibility** — blind users, screen readers, and keyboard users depend on correct HTML to use your site.
3. **HTML directly affects SEO** — search engines read your HTML structure to rank your pages.
4. **Performance starts with HTML** — a bloated HTML document slows every page load.
5. **The 90% who use HTML casually never learn its real depth** — mastering it puts you in the 0.01%.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build a rock-solid understanding of how HTML works.*

---

### Concept 1: Anatomy of an HTML Element

Every piece of content in HTML is wrapped in a **tag**. A tag is a keyword surrounded by angle brackets `< >`.

```html
<!-- Full element anatomy: -->
<tagname attribute="value">Content goes here</tagname>
    │         │       │          │
    │         │       │          └── Content (text, other elements, or empty)
    │         │       └───────────── Attribute value
    │         └───────────────────── Attribute name
    └─────────────────────────────── Tag name

<!-- Opening tag + Content + Closing tag = Element -->
<p>This is a paragraph.</p>

<!-- Self-closing (void) elements — no closing tag, no content: -->
<img src="photo.jpg" alt="A photo">
<br>
<hr>
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

---

### Concept 2: The HTML Boilerplate — Every Page Needs This

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta information — NOT displayed on the page -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A description of this page for search engines.">
    <title>Page Title — Shown in Browser Tab</title>
    <link rel="stylesheet" href="style.css">
    <link rel="icon" href="favicon.ico" type="image/x-icon">
</head>
<body>
    <!-- Visible content goes here -->
    <h1>Hello, World!</h1>
    <p>This is my first webpage.</p>

    <script src="app.js" defer></script>
</body>
</html>
```

**Line-by-line explanation:**

| Line | What It Does |
|------|--------------|
| `<!DOCTYPE html>` | Tells browser this is HTML5 (not HTML4 or XHTML). Always first. |
| `<html lang="en">` | Root element. `lang` tells screen readers and search engines the language. |
| `<head>` | Container for metadata — nothing inside is visible on the page. |
| `<meta charset="UTF-8">` | Character encoding — supports ALL languages, emoji. Always include. |
| `<meta name="viewport" ...>` | Makes the page responsive on mobile. Without this, phones zoom out. |
| `<meta name="description">` | Text shown in Google search results under your page title. |
| `<title>` | Text shown in the browser tab and in search engine results. |
| `<link rel="stylesheet">` | Loads your CSS file. |
| `<body>` | Everything visible to the user goes inside here. |
| `<script defer>` | Loads JS after HTML is parsed. `defer` is key for performance. |

---

### Concept 3: Headings — h1 Through h6

```html
<h1>Main Title — Only ONE per page (like the title of a book)</h1>
<h2>Section Heading (like chapter titles)</h2>
<h3>Subsection Heading</h3>
<h4>Sub-subsection</h4>
<h5>Rarely used — minor heading</h5>
<h6>Smallest heading — very rarely used</h6>
```

💡 **Critical Rules:**
- There should be **only ONE `<h1>` per page** — it represents the main topic
- Headings create the **document outline** — screen readers and search engines navigate by headings
- Never skip heading levels (don't jump from `<h2>` to `<h4>`)
- Don't use headings just to make text big — use CSS for visual size
- Headings create an **implicit table of contents** for your page

---

### Concept 4: Text Content Elements

```html
<!-- Paragraph: -->
<p>A paragraph of text. This is the most common text container.</p>

<!-- Line break (inside a paragraph): -->
<p>Line one.<br>Line two.</p>

<!-- Horizontal rule (thematic break): -->
<hr>

<!-- Inline semantic text elements: -->
<strong>Bold and semantically IMPORTANT</strong>  <!-- ≠ just bold -->
<em>Italic and semantically emphasized</em>        <!-- ≠ just italic -->
<b>Bold for stylistic only — no semantic weight</b>
<i>Italic for stylistic only (foreign words, technical terms)</i>
<u>Underline</u>                   <!-- Avoid — looks like a link -->
<s>Strikethrough — no longer accurate</s>
<mark>Highlighted text</mark>
<small>Fine print, legal text, copyright</small>
<sub>Subscript: H<sub>2</sub>O</sub>
<sup>Superscript: E = mc<sup>2</sup></sup>
<code>Inline code: const x = 5;</code>
<kbd>Keyboard input: Press <kbd>Ctrl</kbd> + <kbd>C</kbd></kbd>
<samp>Sample output from a program</samp>
<var>Variable name: <var>x</var> = 5</var>
<abbr title="HyperText Markup Language">HTML</abbr>  <!-- Hover to see title -->
<cite>Book Title</cite>             <!-- Reference to a creative work -->
<q>Short inline quotation</q>      <!-- Browser adds quotation marks -->
<dfn>Term being defined</dfn>

<!-- Blockquote for long quotes: -->
<blockquote cite="https://source.com">
    <p>A long quotation from an external source.</p>
    <footer>— <cite>Author Name</cite></footer>
</blockquote>

<!-- Preformatted text (preserves whitespace and line breaks): -->
<pre><code>
function hello() {
    console.log("Hello!");
}
</code></pre>
```

---

### Concept 5: Links — The Hypertext in HTML

```html
<!-- Basic link: -->
<a href="https://www.example.com">Visit Example.com</a>

<!-- Open in new tab (always add rel for security!): -->
<a href="https://www.example.com" target="_blank" rel="noopener noreferrer">
    External Link
</a>

<!-- Link to another page on your site (relative URL): -->
<a href="/about">About Us</a>
<a href="../index.html">Home</a>
<a href="./contact.html">Contact</a>

<!-- Link to a section on the SAME page (anchor link): -->
<a href="#section-2">Jump to Section 2</a>
<section id="section-2">...</section>

<!-- Email link: -->
<a href="mailto:hello@example.com">Send Email</a>

<!-- Phone link (mobile): -->
<a href="tel:+919876543210">Call Us</a>

<!-- Download link: -->
<a href="/files/report.pdf" download="Annual-Report-2025.pdf">
    Download Report
</a>

<!-- Link that goes nowhere (use for JS-driven actions): -->
<a href="#" onclick="doSomething()">Click Me</a>  <!-- Avoid — use button instead -->
<button type="button" onclick="doSomething()">Better: Use a Button</button>
```

---

### Concept 6: Images

```html
<!-- Basic image — alt text is MANDATORY: -->
<img src="photo.jpg" alt="A golden retriever puppy playing in a park">

<!-- With dimensions (speeds up rendering by reserving space): -->
<img src="photo.jpg" alt="Description" width="800" height="600">

<!-- Responsive image (CSS will handle sizing): -->
<img src="photo.jpg" alt="Description" style="max-width: 100%; height: auto;">

<!-- Modern responsive images with srcset: -->
<img
    src="photo-800.jpg"
    srcset="photo-400.jpg 400w, photo-800.jpg 800w, photo-1600.jpg 1600w"
    sizes="(max-width: 600px) 400px, (max-width: 1200px) 800px, 1600px"
    alt="Description"
    loading="lazy"
    decoding="async"
>

<!-- Figure with caption: -->
<figure>
    <img src="chart.png" alt="Bar chart showing revenue growth from 2020 to 2025">
    <figcaption>Figure 1: Annual revenue growth over 5 years</figcaption>
</figure>

<!-- Decorative image (no alt needed — empty alt tells screen reader to skip it): -->
<img src="decorative-swirl.png" alt="">
```

💡 **Alt text rules:**
- Describe what the image shows, not what it is ("dog playing fetch" not "image of dog")
- For decorative images: `alt=""`
- For images that are links: describe the destination ("Go to homepage")
- Never say "image of" or "picture of" — screen readers already say that

---

### Concept 7: Lists

```html
<!-- Unordered list (bullets): -->
<ul>
    <li>Python</li>
    <li>JavaScript</li>
    <li>
        HTML
        <ul>
            <li>Semantic HTML</li>
            <li>Accessibility</li>
        </ul>
    </li>
</ul>

<!-- Ordered list (numbers): -->
<ol>
    <li>Install VS Code</li>
    <li>Create index.html</li>
    <li>Write your code</li>
</ol>

<!-- Ordered list attributes: -->
<ol start="5" reversed type="A">
    <li>Item A (starts at E, goes backward)</li>
    <li>Item B</li>
</ol>
<!-- type values: "1" (default), "A", "a", "I", "i" -->

<!-- Description list (term + definition pairs): -->
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language — the structure of web pages.</dd>

    <dt>CSS</dt>
    <dd>Cascading Style Sheets — the visual styling of web pages.</dd>

    <dt>JavaScript</dt>
    <dd>The programming language of the web.</dd>
</dl>
```

---

🧪 **Mini Task 1:**
> Build a personal profile card in HTML only (no CSS). Include: your name as `<h1>`, a profile image, a short bio paragraph, a list of your top 3 skills, and links to your GitHub and LinkedIn.
> ✅ *Expected: Validates with no errors on validator.w3.org*

🧪 **Mini Task 2:**
> Mark up a recipe page. Use correct heading hierarchy, an ordered list for steps, an unordered list for ingredients, and a `<figure>` with `<figcaption>` for the food photo.

---

## ⚙️ 4. Complete Element System Breakdown

> 🎯 *Goal: Know every category of HTML elements — nothing skipped.*

---

### Part 1: Semantic Structural Elements (HTML5)

**What they are:** Elements that communicate the *meaning* of content — not just its appearance.
**Why they matter:** Screen readers, search engines, and developer tools all depend on semantic structure.

```html
<!DOCTYPE html>
<html lang="en">
<head>...</head>
<body>

<!-- PAGE STRUCTURE LANDMARKS (one of each per page, usually): -->

<header>
    <!-- Site or section header: logo, site title, primary navigation -->
    <a href="/" class="logo"><img src="logo.svg" alt="Acme Corp"></a>
    <nav aria-label="Primary">
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
    </nav>
</header>

<main>
    <!-- The MAIN content of the page — only ONE per page -->
    <!-- Skip links jump here: <a href="#main-content">Skip to content</a> -->

    <article>
        <!-- Self-contained, reusable content: blog post, news article, forum post -->
        <header>
            <h1>Article Title</h1>
            <p>Published on <time datetime="2025-03-29">March 29, 2025</time>
               by <address><a rel="author" href="/authors/aryan">Aryan</a></address>
            </p>
        </header>

        <p>Article introduction paragraph...</p>

        <section>
            <!-- Thematic grouping of content WITHIN an article or page -->
            <h2>Section One</h2>
            <p>Section content...</p>
        </section>

        <section>
            <h2>Section Two</h2>
            <p>More content...</p>
        </section>

        <footer>
            <!-- Article footer: tags, comments link, share buttons -->
            <p>Tags: <a href="/tag/html">HTML</a>, <a href="/tag/web">Web Dev</a></p>
        </footer>
    </article>

    <aside>
        <!-- Tangentially related content: sidebar, pull quotes, ads, related links -->
        <h2>Related Articles</h2>
        <ul>
            <li><a href="/css-guide">CSS Master Guide</a></li>
        </ul>
    </aside>

</main>

<footer>
    <!-- Site footer: copyright, secondary nav, social links -->
    <nav aria-label="Footer">
        <a href="/privacy">Privacy Policy</a>
        <a href="/terms">Terms of Service</a>
    </nav>
    <p><small>© 2025 Acme Corp. All rights reserved.</small></p>
</footer>

</body>
</html>
```

---

### Part 2: Forms — The Most Complex Part of HTML

Forms are how users send data to servers. Master every part.

```html
<form
    action="/submit"
    method="POST"
    enctype="multipart/form-data"
    novalidate
    autocomplete="on"
    id="registration-form"
>

<!-- ── TEXT INPUTS ──────────────────────────────────────────────────────── -->

    <div class="field-group">
        <label for="username">
            Username <span aria-hidden="true">*</span>
            <span class="sr-only">(required)</span>
        </label>
        <input
            type="text"
            id="username"
            name="username"
            required
            minlength="3"
            maxlength="20"
            pattern="[a-zA-Z0-9_]+"
            placeholder="e.g. aryan_dev"
            autocomplete="username"
            aria-describedby="username-hint username-error"
        >
        <p id="username-hint" class="hint">
            3-20 characters. Letters, numbers, underscores only.
        </p>
        <p id="username-error" role="alert" hidden>
            Username is required and must be 3-20 characters.
        </p>
    </div>

    <!-- Email: -->
    <label for="email">Email Address</label>
    <input type="email" id="email" name="email" required autocomplete="email">

    <!-- Password: -->
    <label for="password">Password</label>
    <input
        type="password"
        id="password"
        name="password"
        required
        minlength="8"
        autocomplete="new-password"
        aria-describedby="password-hint"
    >
    <p id="password-hint">At least 8 characters.</p>

<!-- ── NUMBER INPUTS ─────────────────────────────────────────────────────── -->

    <label for="age">Age</label>
    <input type="number" id="age" name="age" min="1" max="150" step="1">

    <label for="price">Price (₹)</label>
    <input type="number" id="price" name="price" min="0" step="0.01">

    <label for="rating">Rating</label>
    <input type="range" id="rating" name="rating" min="1" max="10" step="1" value="5">

<!-- ── DATE & TIME INPUTS ────────────────────────────────────────────────── -->

    <label for="dob">Date of Birth</label>
    <input type="date" id="dob" name="dob" min="1900-01-01" max="2025-12-31">

    <label for="meeting">Meeting Time</label>
    <input type="datetime-local" id="meeting" name="meeting">

    <label for="birth-month">Birth Month</label>
    <input type="month" id="birth-month" name="birth-month">

    <label for="alarm">Alarm</label>
    <input type="time" id="alarm" name="alarm">

<!-- ── SPECIAL INPUTS ────────────────────────────────────────────────────── -->

    <label for="website">Website URL</label>
    <input type="url" id="website" name="website" placeholder="https://example.com">

    <label for="phone">Phone Number</label>
    <input type="tel" id="phone" name="phone" pattern="[0-9]{10}" placeholder="9876543210">

    <label for="search-field">Search</label>
    <input type="search" id="search-field" name="q" placeholder="Search...">

    <label for="fav-color">Favorite Color</label>
    <input type="color" id="fav-color" name="fav-color" value="#0066cc">

    <label for="avatar">Profile Picture</label>
    <input
        type="file"
        id="avatar"
        name="avatar"
        accept="image/png, image/jpeg, image/webp"
        capture="user"
    >

<!-- ── TEXTAREA ──────────────────────────────────────────────────────────── -->

    <label for="bio">Bio</label>
    <textarea
        id="bio"
        name="bio"
        rows="5"
        cols="40"
        maxlength="500"
        placeholder="Tell us about yourself..."
        aria-describedby="bio-count"
    ></textarea>
    <span id="bio-count">0/500 characters</span>

<!-- ── SELECT DROPDOWNS ──────────────────────────────────────────────────── -->

    <label for="country">Country</label>
    <select id="country" name="country" required>
        <option value="">-- Select a country --</option>
        <optgroup label="South Asia">
            <option value="IN" selected>India</option>
            <option value="PK">Pakistan</option>
            <option value="BD">Bangladesh</option>
        </optgroup>
        <optgroup label="Europe">
            <option value="DE">Germany</option>
            <option value="FR">France</option>
        </optgroup>
    </select>

    <!-- Multi-select: -->
    <label for="skills">Skills (hold Ctrl to select multiple)</label>
    <select id="skills" name="skills" multiple size="4">
        <option value="html">HTML</option>
        <option value="css">CSS</option>
        <option value="js">JavaScript</option>
        <option value="python">Python</option>
    </select>

<!-- ── CHECKBOXES ───────────────────────────────────────────────────────── -->

    <fieldset>
        <legend>Preferred Notifications</legend>

        <label>
            <input type="checkbox" name="notify" value="email" checked>
            Email notifications
        </label>
        <label>
            <input type="checkbox" name="notify" value="sms">
            SMS notifications
        </label>
        <label>
            <input type="checkbox" name="notify" value="push">
            Push notifications
        </label>
    </fieldset>

<!-- ── RADIO BUTTONS ────────────────────────────────────────────────────── -->

    <fieldset>
        <legend>Account Type</legend>

        <label>
            <input type="radio" name="account-type" value="student" required>
            Student
        </label>
        <label>
            <input type="radio" name="account-type" value="teacher">
            Teacher
        </label>
        <label>
            <input type="radio" name="account-type" value="professional">
            Professional
        </label>
    </fieldset>

<!-- ── HIDDEN & SPECIAL ──────────────────────────────────────────────────── -->

    <!-- Hidden input — passes data without user seeing it: -->
    <input type="hidden" name="csrf_token" value="abc123xyz">
    <input type="hidden" name="referral_code" value="FRIEND50">

<!-- ── BUTTONS ──────────────────────────────────────────────────────────── -->

    <!-- Submit (default behavior inside form): -->
    <button type="submit">Create Account</button>

    <!-- Reset form to defaults: -->
    <button type="reset">Reset</button>

    <!-- Generic button (for JS): -->
    <button type="button" id="preview-btn">Preview</button>

    <!-- Disabled state: -->
    <button type="submit" disabled>Submit (Disabled)</button>

    <!-- Image button (submits form): -->
    <input type="image" src="submit-btn.png" alt="Submit the form">

</form>

<!-- ── DATALIST — autocomplete suggestions ──────────────────────────────── -->
<label for="framework">Favorite Framework</label>
<input type="text" id="framework" name="framework" list="frameworks">
<datalist id="frameworks">
    <option value="React">
    <option value="Vue">
    <option value="Angular">
    <option value="Svelte">
    <option value="Next.js">
</datalist>

<!-- ── OUTPUT — displays calculated result ──────────────────────────────── -->
<form oninput="result.value = parseInt(a.value) + parseInt(b.value)">
    <input type="number" id="a" value="0"> +
    <input type="number" id="b" value="0"> =
    <output name="result" for="a b">0</output>
</form>
```

---

### Part 3: Tables — Structured Data

```html
<!-- A CORRECT, accessible data table: -->
<table>
    <caption>Student Grades — Term 1 2025</caption>

    <colgroup>
        <col span="1" style="background-color: #f5f5f5;">
        <col span="3">
    </colgroup>

    <thead>
        <tr>
            <th scope="col">Student Name</th>
            <th scope="col">Math</th>
            <th scope="col">Science</th>
            <th scope="col">English</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <th scope="row">Aryan</th>
            <td>98</td>
            <td>95</td>
            <td>92</td>
        </tr>
        <tr>
            <th scope="row">Priya</th>
            <td>88</td>
            <td>91</td>
            <td>94</td>
        </tr>
    </tbody>

    <tfoot>
        <tr>
            <th scope="row">Class Average</th>
            <td>93</td>
            <td>93</td>
            <td>93</td>
        </tr>
    </tfoot>
</table>

<!-- Cell spanning: -->
<table>
    <tr>
        <td colspan="2">Spans 2 columns</td>
        <td>Normal</td>
    </tr>
    <tr>
        <td rowspan="2">Spans 2 rows</td>
        <td>Cell</td>
        <td>Cell</td>
    </tr>
    <tr>
        <td>Cell</td>
        <td>Cell</td>
    </tr>
</table>
```

⚠️ **Never use tables for layout!** Tables are ONLY for tabular data (spreadsheet-like content). Use CSS Grid or Flexbox for page layout.

---

### Part 4: Media Elements

```html
<!-- ── VIDEO ─────────────────────────────────────────────────────────────── -->
<video
    controls
    width="800"
    height="450"
    poster="thumbnail.jpg"
    preload="metadata"
    muted
    playsinline
    loop
    aria-label="Demo of the new feature"
>
    <source src="video.webm" type="video/webm">
    <source src="video.mp4" type="video/mp4">
    <track
        kind="subtitles"
        src="subtitles-en.vtt"
        srclang="en"
        label="English"
        default
    >
    <track kind="captions" src="captions-en.vtt" srclang="en" label="English CC">
    <p>Your browser doesn't support video. <a href="video.mp4">Download it</a>.</p>
</video>

<!-- ── AUDIO ─────────────────────────────────────────────────────────────── -->
<audio controls preload="none" aria-label="Podcast Episode 42">
    <source src="podcast.ogg" type="audio/ogg">
    <source src="podcast.mp3" type="audio/mpeg">
    <p>Your browser doesn't support audio. <a href="podcast.mp3">Download</a>.</p>
</audio>

<!-- ── PICTURE — art direction responsive images ────────────────────────── -->
<picture>
    <!-- Use WebP for supporting browsers: -->
    <source
        type="image/webp"
        srcset="hero-small.webp 480w, hero-large.webp 1200w"
        sizes="(max-width: 768px) 480px, 1200px"
    >
    <!-- Mobile: show a portrait-cropped version: -->
    <source
        media="(max-width: 768px)"
        srcset="hero-portrait.jpg"
    >
    <!-- Default fallback: -->
    <img src="hero-large.jpg" alt="Team working on a project in a modern office">
</picture>

<!-- ── IFRAME — embed external content ──────────────────────────────────── -->
<iframe
    src="https://www.youtube.com/embed/VIDEO_ID"
    title="Introduction to HTML — Tutorial Video"
    width="560"
    height="315"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope"
    allowfullscreen
    loading="lazy"
    sandbox="allow-scripts allow-same-origin"
></iframe>

<!-- ── CANVAS — 2D drawing surface (JavaScript draws on it) ─────────────── -->
<canvas
    id="my-canvas"
    width="800"
    height="400"
    aria-label="A bar chart showing monthly sales"
    role="img"
>
    <!-- Fallback for screen readers: -->
    <p>Monthly sales: Jan: ₹10,000, Feb: ₹15,000, Mar: ₹12,000</p>
</canvas>

<!-- ── SVG — inline scalable vector graphics ────────────────────────────── -->
<svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox="0 0 100 100"
    width="100"
    height="100"
    aria-label="Company logo"
    role="img"
>
    <title>Company Logo</title>
    <circle cx="50" cy="50" r="40" fill="#0066cc"/>
    <text x="50" y="55" text-anchor="middle" fill="white" font-size="20">AC</text>
</svg>
```

---

### Part 5: Interactive Elements

```html
<!-- ── DETAILS & SUMMARY — native accordion ────────────────────────────── -->
<details>
    <summary>Click to expand: What is HTML?</summary>
    <p>HTML stands for HyperText Markup Language and is the foundation of all web pages.</p>
</details>

<details open>
    <!-- open attribute makes it expanded by default -->
    <summary>Section 2 (starts open)</summary>
    <p>Content of section 2.</p>
</details>

<!-- ── DIALOG — native modal dialog ─────────────────────────────────────── -->
<dialog id="confirm-dialog" aria-labelledby="dialog-title">
    <h2 id="dialog-title">Confirm Deletion</h2>
    <p>Are you sure you want to delete this item? This cannot be undone.</p>
    <div class="dialog-actions">
        <button type="button" id="cancel-btn">Cancel</button>
        <button type="button" id="confirm-btn">Delete</button>
    </div>
</dialog>

<button type="button" onclick="document.getElementById('confirm-dialog').showModal()">
    Open Dialog
</button>

<script>
    document.getElementById('cancel-btn').addEventListener('click', () => {
        document.getElementById('confirm-dialog').close();
    });
    // dialog.show()       → non-modal
    // dialog.showModal()  → modal (backdrop + focus trap)
    // dialog.close()      → close
</script>

<!-- ── MENU — context menu (experimental) ───────────────────────────────── -->

<!-- ── PROGRESS & METER ──────────────────────────────────────────────────── -->

<!-- Progress bar (task completion): -->
<label for="upload">Uploading file:</label>
<progress id="upload" value="70" max="100">70%</progress>

<!-- Meter (scalar value within known range): -->
<label for="disk">Disk Usage:</label>
<meter
    id="disk"
    value="8"
    min="0"
    max="10"
    low="3"
    high="7"
    optimum="2"
    title="8 GB used out of 10 GB"
>8 out of 10 GB</meter>
```

---

### 📊 Full Element Reference Table

| Category              | Key Elements                                                     |
|-----------------------|------------------------------------------------------------------|
| Document Structure    | `html`, `head`, `body`, `title`, `meta`, `link`, `style`, `script` |
| Sectioning            | `header`, `nav`, `main`, `article`, `section`, `aside`, `footer`, `h1-h6` |
| Text Content          | `p`, `blockquote`, `pre`, `hr`, `ul`, `ol`, `li`, `dl`, `dt`, `dd`, `figure`, `figcaption`, `div` |
| Inline Text           | `a`, `strong`, `em`, `code`, `kbd`, `mark`, `small`, `span`, `time`, `abbr`, `cite`, `q` |
| Forms                 | `form`, `label`, `input`, `button`, `select`, `option`, `textarea`, `fieldset`, `legend`, `datalist`, `output` |
| Tables                | `table`, `caption`, `thead`, `tbody`, `tfoot`, `tr`, `th`, `td`, `colgroup`, `col` |
| Media                 | `img`, `video`, `audio`, `picture`, `source`, `track`, `canvas`, `svg`, `iframe` |
| Interactive           | `details`, `summary`, `dialog`, `menu`, `progress`, `meter` |
| Metadata              | `meta`, `link`, `base`, `title` |
| Scripting             | `script`, `noscript`, `template`, `slot` |
| Deprecated (AVOID)    | `center`, `font`, `b` (for bold), `i` (for italics), `frame`, `frameset`, `marquee` |

---

## 🔄 5. Real-World Workflow

### 🟢 Beginner Workflow: Personal Portfolio Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Aryan — Python Developer and AI Enthusiast from Kolkata">
    <meta name="author" content="Aryan">
    <title>Aryan | Python Developer & AI Enthusiast</title>
    <link rel="stylesheet" href="style.css">
    <link rel="canonical" href="https://aryan.dev/">
</head>
<body>

    <a href="#main-content" class="skip-link">Skip to main content</a>

    <header>
        <nav aria-label="Primary navigation">
            <a href="/" aria-current="page">Home</a>
            <a href="#about">About</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main id="main-content">

        <section id="hero" aria-labelledby="hero-heading">
            <h1 id="hero-heading">Hi, I'm Aryan 👋</h1>
            <p>Python Developer · AI Enthusiast · Class XI Student from Kolkata</p>
            <a href="#projects" class="btn-primary">See My Work</a>
            <a href="#contact" class="btn-secondary">Get in Touch</a>
        </section>

        <section id="about" aria-labelledby="about-heading">
            <h2 id="about-heading">About Me</h2>
            <figure>
                <img
                    src="profile.jpg"
                    alt="Aryan smiling, sitting at a desk with multiple monitors"
                    width="300"
                    height="300"
                    loading="lazy"
                >
            </figure>
            <p>
                I'm a <strong>Class XI student</strong> from Siliguri, West Bengal with a passion
                for building AI agents, training ML models, and automating everything.
            </p>
            <h3>Skills</h3>
            <ul>
                <li>Python (NumPy, pandas, PyTorch)</li>
                <li>Machine Learning & Deep Learning</li>
                <li>AI Agent Development</li>
                <li>HTML, CSS, JavaScript</li>
                <li>Video & Photo Editing</li>
            </ul>
        </section>

        <section id="projects" aria-labelledby="projects-heading">
            <h2 id="projects-heading">Projects</h2>
            <ul class="project-grid" role="list">
                <li>
                    <article>
                        <h3><a href="/projects/ai-agent">AI Research Agent</a></h3>
                        <p>An autonomous AI agent that browses the web and summarizes research papers.</p>
                        <p>
                            <strong>Tech:</strong>
                            <abbr title="Python">Py</abbr>,
                            <abbr title="LangChain">LC</abbr>,
                            <abbr title="Claude API">Claude</abbr>
                        </p>
                        <a href="https://github.com/aryan/ai-agent" rel="noopener noreferrer" target="_blank">
                            View on GitHub
                        </a>
                    </article>
                </li>
            </ul>
        </section>

        <section id="contact" aria-labelledby="contact-heading">
            <h2 id="contact-heading">Get In Touch</h2>
            <address>
                <p>Email: <a href="mailto:aryan@example.com">aryan@example.com</a></p>
                <p>GitHub: <a href="https://github.com/aryan" target="_blank" rel="noopener noreferrer">github.com/aryan</a></p>
            </address>
        </section>

    </main>

    <footer>
        <p><small>© 2025 Aryan. Built with ❤️ and pure HTML.</small></p>
    </footer>

</body>
</html>
```

---

### 🔵 Professional Workflow: Full Accessible Web App Layout

```html
<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Dashboard — Manage your projects and tasks">
    <meta name="theme-color" content="#0066cc">

    <!-- Open Graph (social sharing preview): -->
    <meta property="og:title" content="Project Dashboard">
    <meta property="og:description" content="Manage your projects and tasks efficiently.">
    <meta property="og:image" content="https://app.example.com/og-image.png">
    <meta property="og:url" content="https://app.example.com/dashboard">
    <meta property="og:type" content="website">

    <!-- Twitter Card: -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Project Dashboard">

    <!-- Preload critical resources: -->
    <link rel="preload" href="fonts/inter.woff2" as="font" type="font/woff2" crossorigin>
    <link rel="preload" href="critical.css" as="style">
    <link rel="preload" href="app.js" as="script">

    <!-- Prefetch next likely page: -->
    <link rel="prefetch" href="/projects/new">

    <link rel="stylesheet" href="critical.css">
    <link rel="stylesheet" href="app.css" media="print" onload="this.media='all'">

    <title>Dashboard — Project Manager</title>

    <!-- Structured Data (JSON-LD): -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "WebApplication",
        "name": "Project Manager",
        "url": "https://app.example.com",
        "applicationCategory": "BusinessApplication"
    }
    </script>
</head>
<body>

    <!-- Skip navigation link (ESSENTIAL for accessibility): -->
    <a href="#main-content" class="skip-link">Skip to main content</a>

    <!-- Notification region (live region for dynamic updates): -->
    <div id="notification" role="status" aria-live="polite" aria-atomic="true" class="sr-only"></div>

    <div class="app-layout">

        <header class="app-header" role="banner">
            <a href="/dashboard" class="brand">
                <img src="logo.svg" alt="" aria-hidden="true" width="32" height="32">
                <span>Project Manager</span>
            </a>

            <nav class="app-nav" aria-label="Primary">
                <ul role="list">
                    <li><a href="/dashboard" aria-current="page">Dashboard</a></li>
                    <li><a href="/projects">Projects</a></li>
                    <li><a href="/tasks">Tasks</a></li>
                    <li><a href="/team">Team</a></li>
                </ul>
            </nav>

            <div class="user-menu">
                <button
                    type="button"
                    aria-haspopup="menu"
                    aria-expanded="false"
                    aria-controls="user-dropdown"
                    id="user-menu-button"
                >
                    <img src="avatar.jpg" alt="" aria-hidden="true" width="32" height="32">
                    <span>Aryan</span>
                    <span aria-hidden="true">▾</span>
                </button>

                <ul
                    id="user-dropdown"
                    role="menu"
                    aria-labelledby="user-menu-button"
                    hidden
                >
                    <li role="none">
                        <a href="/profile" role="menuitem">Profile</a>
                    </li>
                    <li role="none">
                        <a href="/settings" role="menuitem">Settings</a>
                    </li>
                    <li role="separator" aria-hidden="true"></li>
                    <li role="none">
                        <button type="button" role="menuitem">Sign Out</button>
                    </li>
                </ul>
            </div>

            <!-- Mobile menu toggle: -->
            <button
                type="button"
                class="mobile-menu-toggle"
                aria-label="Open main menu"
                aria-controls="mobile-nav"
                aria-expanded="false"
            >
                <span aria-hidden="true">☰</span>
            </button>
        </header>

        <nav id="sidebar" class="sidebar" aria-label="Sidebar">
            <section aria-labelledby="projects-nav-heading">
                <h2 id="projects-nav-heading" class="sidebar-heading">Projects</h2>
                <ul role="list">
                    <li><a href="/projects/1">AI Research Tool</a></li>
                    <li><a href="/projects/2">Portfolio Website</a></li>
                </ul>
            </section>
        </nav>

        <main id="main-content" class="main-content" tabindex="-1">
            <h1>Dashboard</h1>
            <!-- Content -->
        </main>

    </div>

    <script src="app.js" type="module" defer></script>
</body>
</html>
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Accessible Registration Form

**Goal:** Build a complete, accessible signup form with all input types and proper ARIA.
**Estimated Time:** 1-2 hours

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Create Account</title>
</head>
<body>
    <main>
        <h1>Create Your Account</h1>

        <form id="signup-form" action="/register" method="POST" novalidate>
            <fieldset>
                <legend>Personal Information</legend>

                <div>
                    <label for="full-name">Full Name <span aria-hidden="true">*</span></label>
                    <input
                        type="text"
                        id="full-name"
                        name="full_name"
                        required
                        autocomplete="name"
                        aria-required="true"
                    >
                </div>

                <div>
                    <label for="reg-email">Email Address <span aria-hidden="true">*</span></label>
                    <input
                        type="email"
                        id="reg-email"
                        name="email"
                        required
                        autocomplete="email"
                        aria-required="true"
                        aria-describedby="email-hint"
                    >
                    <p id="email-hint" class="hint">We'll never share your email.</p>
                </div>

                <div>
                    <label for="dob-field">Date of Birth</label>
                    <input type="date" id="dob-field" name="dob" max="2025-12-31">
                </div>
            </fieldset>

            <fieldset>
                <legend>Account Security</legend>

                <div>
                    <label for="reg-password">Password <span aria-hidden="true">*</span></label>
                    <input
                        type="password"
                        id="reg-password"
                        name="password"
                        required
                        minlength="8"
                        autocomplete="new-password"
                        aria-describedby="password-requirements"
                    >
                    <ul id="password-requirements">
                        <li>At least 8 characters</li>
                        <li>At least one number</li>
                        <li>At least one symbol</li>
                    </ul>
                </div>
            </fieldset>

            <fieldset>
                <legend>Preferences</legend>

                <p>How did you hear about us?</p>
                <label>
                    <input type="radio" name="referral" value="social" required>
                    Social Media
                </label>
                <label>
                    <input type="radio" name="referral" value="friend">
                    A Friend
                </label>
                <label>
                    <input type="radio" name="referral" value="search">
                    Search Engine
                </label>

                <label>
                    <input type="checkbox" name="newsletter" value="yes">
                    Subscribe to our newsletter
                </label>

                <label>
                    <input type="checkbox" name="terms" required aria-required="true">
                    I agree to the
                    <a href="/terms" target="_blank" rel="noopener noreferrer">
                        Terms of Service
                    </a>
                    <span aria-hidden="true">*</span>
                </label>
            </fieldset>

            <button type="submit">Create Account</button>
            <p><a href="/login">Already have an account? Sign in</a></p>
        </form>
    </main>
</body>
</html>
```

✅ **You've succeeded when:** The form validates with no errors at validator.w3.org AND passes an accessibility audit in Chrome DevTools (Lighthouse score > 90).

---

### 🔵 Intermediate Project: Blog with Full Schema Markup

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Building Your First AI Agent — Aryan's Blog</title>
    <meta name="description" content="A step-by-step guide to building an autonomous AI agent using Python and the Claude API.">
    <link rel="canonical" href="https://aryan.dev/blog/first-ai-agent">

    <!-- Article Open Graph: -->
    <meta property="og:type" content="article">
    <meta property="og:title" content="Building Your First AI Agent">
    <meta property="og:image" content="https://aryan.dev/blog/ai-agent-cover.jpg">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="article:published_time" content="2025-03-29T10:00:00+05:30">
    <meta property="article:author" content="https://aryan.dev">
    <meta property="article:tag" content="AI, Python, Machine Learning">

    <!-- Article schema (rich search result): -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "BlogPosting",
        "headline": "Building Your First AI Agent",
        "description": "A step-by-step guide to building an autonomous AI agent.",
        "image": "https://aryan.dev/blog/ai-agent-cover.jpg",
        "datePublished": "2025-03-29",
        "dateModified": "2025-03-29",
        "author": {
            "@type": "Person",
            "name": "Aryan",
            "url": "https://aryan.dev"
        },
        "publisher": {
            "@type": "Person",
            "name": "Aryan"
        }
    }
    </script>
</head>
<body>
    <header>
        <nav aria-label="Breadcrumb">
            <ol>
                <li><a href="/">Home</a></li>
                <li><a href="/blog">Blog</a></li>
                <li aria-current="page">Building Your First AI Agent</li>
            </ol>
        </nav>
    </header>

    <main>
        <article itemscope itemtype="https://schema.org/BlogPosting">

            <header>
                <h1 itemprop="headline">Building Your First AI Agent</h1>

                <p class="meta">
                    Published
                    <time itemprop="datePublished" datetime="2025-03-29">March 29, 2025</time>
                    by
                    <address>
                        <a rel="author" href="/about" itemprop="author">Aryan</a>
                    </address>
                    · <span>8 min read</span>
                </p>

                <figure>
                    <img
                        itemprop="image"
                        src="ai-agent-cover.jpg"
                        alt="A diagram showing an AI agent loop: perceive, think, act"
                        width="1200"
                        height="630"
                        loading="eager"
                        fetchpriority="high"
                    >
                    <figcaption>The ReAct agent loop: perceive → think → act → observe.</figcaption>
                </figure>
            </header>

            <nav aria-label="Table of contents">
                <h2>Contents</h2>
                <ol>
                    <li><a href="#introduction">Introduction</a></li>
                    <li><a href="#what-is-an-agent">What is an AI Agent?</a></li>
                    <li><a href="#building">Building the Agent</a></li>
                    <li><a href="#conclusion">Conclusion</a></li>
                </ol>
            </nav>

            <section id="introduction" itemprop="articleBody">
                <h2>Introduction</h2>
                <p>
                    AI agents are programs that perceive their environment, make decisions,
                    and take actions autonomously. In this guide, we'll build one from scratch
                    using Python and the
                    <a href="https://docs.anthropic.com" rel="noopener noreferrer" target="_blank">
                        Claude API
                    </a>.
                </p>
            </section>

            <section id="building">
                <h2>Building the Agent</h2>
                <h3>Step 1: Set Up the Environment</h3>
                <pre><code class="language-bash">pip install anthropic
export ANTHROPIC_API_KEY="your-key-here"
</code></pre>
            </section>

            <footer class="article-footer">
                <section aria-labelledby="tags-heading">
                    <h2 id="tags-heading">Tags</h2>
                    <ul>
                        <li><a href="/tag/ai" rel="tag">AI</a></li>
                        <li><a href="/tag/python" rel="tag">Python</a></li>
                    </ul>
                </section>
            </footer>
        </article>
    </main>
</body>
</html>
```

---

### 🔴 Advanced Project: Full PWA Shell with Service Worker Registration

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <meta name="description" content="AI Tools — Your personal AI assistant suite">
    <meta name="theme-color" content="#0066cc" media="(prefers-color-scheme: light)">
    <meta name="theme-color" content="#003399" media="(prefers-color-scheme: dark)">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="apple-mobile-web-app-title" content="AI Tools">

    <!-- PWA manifest: -->
    <link rel="manifest" href="/manifest.json">

    <!-- Apple touch icons: -->
    <link rel="apple-touch-icon" href="/icons/apple-touch-icon.png">
    <link rel="apple-touch-icon" sizes="152x152" href="/icons/icon-152.png">
    <link rel="apple-touch-icon" sizes="180x180" href="/icons/icon-180.png">

    <!-- Standard icons: -->
    <link rel="icon" type="image/svg+xml" href="/icons/icon.svg">
    <link rel="icon" type="image/png" sizes="32x32" href="/icons/icon-32.png">

    <!-- Performance: preconnect to critical origins: -->
    <link rel="preconnect" href="https://api.anthropic.com">
    <link rel="dns-prefetch" href="https://fonts.googleapis.com">

    <title>AI Tools</title>
</head>
<body>
    <div id="app" role="application" aria-label="AI Tools Application">
        <!-- App shell renders here -->
        <noscript>
            <p>This application requires JavaScript. Please enable it in your browser settings.</p>
        </noscript>
    </div>

    <script type="module">
        // Register Service Worker:
        if ('serviceWorker' in navigator) {
            navigator.serviceWorker.register('/sw.js', { scope: '/' })
                .then(reg => console.log('SW registered:', reg.scope))
                .catch(err => console.error('SW failed:', err));
        }
    </script>

    <script type="module" src="/app.js" defer></script>
</body>
</html>
```

🔥 **Challenge:** Add a web app manifest (`manifest.json`) with all icon sizes, screenshots for app store listing, and shortcuts for quick actions.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Using `<div>` and `<span>` for Everything (Divitis)

```html
<!-- ❌ WRONG — meaningless soup of divs: -->
<div class="header">
    <div class="nav">
        <div class="nav-item"><a href="/">Home</a></div>
    </div>
</div>
<div class="main">
    <div class="article">
        <div class="title">My Blog Post</div>
        <div class="text">Content here...</div>
    </div>
</div>

<!-- ✅ RIGHT — semantic elements: -->
<header>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
        </ul>
    </nav>
</header>
<main>
    <article>
        <h1>My Blog Post</h1>
        <p>Content here...</p>
    </article>
</main>
```

---

### ❌ Mistake 2: Missing or Wrong Alt Text

```html
<!-- ❌ WRONG — no alt: -->
<img src="chart.png">

<!-- ❌ WRONG — useless alt: -->
<img src="chart.png" alt="image">
<img src="chart.png" alt="chart.png">

<!-- ❌ WRONG — "image of" is redundant (screen reader says "image" already): -->
<img src="dog.jpg" alt="Image of a dog">

<!-- ✅ RIGHT — descriptive: -->
<img src="chart.png" alt="Bar chart showing 40% increase in sales from Q1 to Q4 2025">

<!-- ✅ RIGHT — decorative image gets empty alt: -->
<img src="decorative-wave.svg" alt="">

<!-- ✅ RIGHT — icon used as button: -->
<button type="button" aria-label="Search">
    <img src="search-icon.svg" alt="">  <!-- alt="" because aria-label covers it -->
</button>
```

---

### ❌ Mistake 3: Using `<table>` for Layout

```html
<!-- ❌ WRONG — 1999 called: -->
<table>
    <tr>
        <td width="200"><nav>Sidebar</nav></td>
        <td><main>Content</main></td>
    </tr>
</table>

<!-- ✅ RIGHT — CSS Grid or Flexbox: -->
<div class="layout">
    <nav class="sidebar">Sidebar</nav>
    <main class="content">Content</main>
</div>
<!-- .layout { display: grid; grid-template-columns: 200px 1fr; } -->
```

---

### ❌ Mistake 4: Labels Not Associated with Inputs

```html
<!-- ❌ WRONG — label and input not connected: -->
<label>Username</label>
<input type="text" name="username">

<!-- ❌ WRONG — placeholder is NOT a label: -->
<input type="text" name="email" placeholder="Enter email">
<!-- Placeholder disappears when typing — user forgets what field is for! -->

<!-- ✅ RIGHT — explicit label association via for/id: -->
<label for="username">Username</label>
<input type="text" id="username" name="username">

<!-- ✅ RIGHT — implicit association (wrapping): -->
<label>
    Username
    <input type="text" name="username">
</label>
```

---

### ❌ Mistake 5: Using `<br>` for Spacing

```html
<!-- ❌ WRONG — abusing br for visual spacing: -->
<p>Paragraph one.</p>
<br><br><br>
<p>Paragraph two.</p>

<!-- ✅ RIGHT — use CSS margin/padding for spacing: -->
<p>Paragraph one.</p>
<p>Paragraph two.</p>
<!-- p { margin-bottom: 1.5rem; } -->

<!-- ✅ br is correct ONLY within flowing text (poetry, addresses): -->
<address>
    123 Main Street<br>
    Siliguri, West Bengal<br>
    India 734001
</address>
```

---

### ❌ Mistake 6: Not Using `<button>` for Clickable Actions

```html
<!-- ❌ WRONG — div is not interactive: -->
<div class="btn" onclick="submit()">Submit</div>
<!-- Not keyboard-accessible! Tab focus doesn't reach it.
     Screen readers don't know it's a button. No Enter/Space activation. -->

<!-- ❌ WRONG — anchor without href for actions: -->
<a onclick="openModal()">Open Modal</a>

<!-- ✅ RIGHT — button is semantic, keyboard-accessible, and correctly announced: -->
<button type="button" onclick="openModal()">Open Modal</button>
<button type="submit">Submit Form</button>
```

---

### ❌ Mistake 7: Wrong Viewport Meta Tag

```html
<!-- ❌ WRONG — prevents user zooming (accessibility violation!): -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">

<!-- ✅ RIGHT — allow zooming: -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

### ❌ Mistake 8: Skipping Heading Levels

```html
<!-- ❌ WRONG — jumps from h1 to h4: -->
<h1>Page Title</h1>
<h4>First Section</h4>
<h6>Subsection</h6>

<!-- ✅ RIGHT — sequential hierarchy: -->
<h1>Page Title</h1>
<h2>First Section</h2>
<h3>Subsection</h3>
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: `loading="lazy"` and `fetchpriority` — Zero-Config Performance

```html
<!-- Lazy load images below the fold: -->
<img src="thumbnail.jpg" alt="..." loading="lazy">
<iframe src="youtube.com/embed/..." loading="lazy"></iframe>

<!-- Prioritize the most important image (hero/LCP element): -->
<img
    src="hero.jpg"
    alt="..."
    loading="eager"
    fetchpriority="high"
    decoding="sync"
>

<!-- Low priority for non-critical images: -->
<img src="sidebar-ad.jpg" alt="..." fetchpriority="low" loading="lazy">
```

This single attribute can improve your **Largest Contentful Paint (LCP)** score significantly — a Core Web Vital.

---

### 💎 Tip 2: `<template>` — Inert HTML Fragments

```html
<!-- Template content is NOT rendered, NOT accessible, NOT requested
     — perfect for HTML you want to clone via JavaScript -->
<template id="card-template">
    <article class="card">
        <img src="" alt="" class="card-img">
        <div class="card-body">
            <h3 class="card-title"></h3>
            <p class="card-desc"></p>
            <a href="#" class="card-link">Read More</a>
        </div>
    </article>
</template>

<script>
function createCard(title, desc, url, imgSrc) {
    const template = document.getElementById("card-template");
    const clone = template.content.cloneNode(true);  // Deep clone

    clone.querySelector(".card-title").textContent = title;
    clone.querySelector(".card-desc").textContent = desc;
    clone.querySelector(".card-link").href = url;
    clone.querySelector(".card-img").src = imgSrc;
    clone.querySelector(".card-img").alt = title;

    document.getElementById("card-container").appendChild(clone);
}

createCard("AI Agent Tutorial", "Build agents from scratch", "/blog/ai-agent", "ai.jpg");
</script>
```

---

### 💎 Tip 3: Content Security Policy via Meta Tag

```html
<!-- Define what resources your page can load — prevents XSS attacks: -->
<meta
    http-equiv="Content-Security-Policy"
    content="
        default-src 'self';
        script-src 'self' https://trusted-cdn.com;
        style-src 'self' 'unsafe-inline';
        img-src 'self' data: https:;
        connect-src 'self' https://api.anthropic.com;
        font-src 'self' https://fonts.gstatic.com;
        frame-ancestors 'none';
    "
>
```

---

### 💎 Tip 4: `<link rel="preload">` — Critical Resource Hints

```html
<!-- Preload critical font before CSS discovers it (prevents FOUT): -->
<link
    rel="preload"
    href="/fonts/inter-variable.woff2"
    as="font"
    type="font/woff2"
    crossorigin
>

<!-- Preload hero image for LCP: -->
<link
    rel="preload"
    href="/images/hero.webp"
    as="image"
    imagesrcset="hero-400.webp 400w, hero-800.webp 800w"
    imagesizes="100vw"
>

<!-- Preload critical JS module: -->
<link rel="preload" href="/app.js" as="script">

<!-- Prefetch — likely next page (low priority, runs in idle time): -->
<link rel="prefetch" href="/about">

<!-- Prerender — definitely next page (renders it in background!): -->
<link rel="prerender" href="/checkout">

<!-- Preconnect — open TCP connection early to external server: -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://api.example.com" crossorigin>

<!-- DNS prefetch — resolve DNS early (lighter than preconnect): -->
<link rel="dns-prefetch" href="https://analytics.example.com">
```

---

### 💎 Tip 5: ARIA Live Regions — Announce Dynamic Changes

```html
<!-- Dynamic content that changes without page reload must be announced to screen readers: -->

<!-- Polite — wait for user to be idle, then announce: -->
<div aria-live="polite" aria-atomic="true" id="status-msg"></div>

<!-- Assertive — interrupt immediately (use sparingly — for errors only): -->
<div aria-live="assertive" role="alert" id="error-msg"></div>

<!-- Status role (implied polite live region): -->
<p role="status" id="form-status">Form saved successfully.</p>

<!-- Alert role (implied assertive): -->
<p role="alert" id="error">Error: Invalid email address.</p>

<!-- Timer (announces countdown): -->
<div role="timer" aria-live="off" aria-atomic="true" id="countdown">
    05:00
</div>

<script>
// Announce search results count:
function updateResults(count) {
    const status = document.getElementById("status-msg");
    status.textContent = `${count} results found`;
    // Screen reader announces this when user pauses!
}
</script>
```

---

### 💎 Tip 6: `inputmode` — Control Mobile Keyboard

```html
<!-- Show numeric keypad (no decimal): -->
<input type="text" inputmode="numeric" pattern="[0-9]*" placeholder="PIN">

<!-- Show phone keypad: -->
<input type="text" inputmode="tel" placeholder="Phone number">

<!-- Show email keyboard (@ and . easily accessible): -->
<input type="text" inputmode="email" placeholder="Email">

<!-- Show URL keyboard: -->
<input type="text" inputmode="url" placeholder="Website">

<!-- Show search keyboard (search key instead of enter): -->
<input type="text" inputmode="search" placeholder="Search...">

<!-- Hide keyboard (custom date picker): -->
<input type="text" inputmode="none" id="custom-datepicker">
```

---

### 💎 Tip 7: The `<base>` Element — Global URL Base

```html
<head>
    <!-- All relative URLs on this page resolve relative to this base: -->
    <base href="https://www.example.com/blog/" target="_blank">
</head>
<body>
    <a href="post.html">Post</a>
    <!-- Resolves to: https://www.example.com/blog/post.html -->
    <!-- Opens in new tab (_blank target inherited from base) -->

    <!-- Override base target: -->
    <a href="/contact" target="_self">Contact</a>
</body>
```

⚠️ Use `<base>` carefully — it affects ALL relative URLs on the page including CSS `url()` paths and JS `fetch()` calls.

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Web Components — Custom HTML Elements

```html
<!-- You can define your own HTML elements! -->

<!-- Usage (before or after definition): -->
<user-avatar
    src="/avatars/aryan.jpg"
    name="Aryan"
    size="large"
    status="online"
></user-avatar>

<script>
class UserAvatar extends HTMLElement {
    // Observed attributes — browser calls attributeChangedCallback when these change:
    static get observedAttributes() {
        return ['src', 'name', 'size', 'status'];
    }

    constructor() {
        super();
        // Attach Shadow DOM — encapsulated DOM tree:
        this.attachShadow({ mode: 'open' });
    }

    // Called when element is inserted into the DOM:
    connectedCallback() {
        this.render();
    }

    // Called when an observed attribute changes:
    attributeChangedCallback(name, oldValue, newValue) {
        if (oldValue !== newValue) this.render();
    }

    // Called when element is removed from DOM:
    disconnectedCallback() {
        // Cleanup: remove event listeners, cancel timers
    }

    render() {
        const src = this.getAttribute('src') || '/default-avatar.png';
        const name = this.getAttribute('name') || 'User';
        const size = this.getAttribute('size') || 'medium';
        const status = this.getAttribute('status') || 'offline';

        // Shadow DOM — fully encapsulated styles!
        this.shadowRoot.innerHTML = `
            <style>
                :host { display: inline-block; }
                :host([size="large"]) img { width: 64px; height: 64px; }
                :host([size="medium"]) img { width: 40px; height: 40px; }

                .container { position: relative; display: inline-block; }
                img { border-radius: 50%; }
                .status {
                    position: absolute;
                    bottom: 0; right: 0;
                    width: 12px; height: 12px;
                    border-radius: 50%;
                    border: 2px solid white;
                    background: ${status === 'online' ? '#22c55e' : '#6b7280'};
                }
            </style>
            <div class="container">
                <img src="${src}" alt="${name}'s avatar">
                <span class="status" aria-label="${name} is ${status}"></span>
            </div>
        `;
    }
}

customElements.define('user-avatar', UserAvatar);
</script>
```

---

### Advanced Concept 2: Shadow DOM — Encapsulated Components

```html
<!-- Shadow DOM creates a separate DOM tree with its own styles -->
<!-- Styles inside Shadow DOM don't leak out. Outside styles don't leak in (mostly). -->

<div id="host"></div>

<script>
const host = document.getElementById('host');
const shadow = host.attachShadow({ mode: 'open' });
// mode: 'open' = shadowRoot accessible via JS
// mode: 'closed' = shadowRoot not accessible from outside (private)

shadow.innerHTML = `
    <style>
        /* These styles ONLY apply inside this shadow root: */
        p { color: red; font-family: monospace; }
        :host { display: block; padding: 1rem; border: 1px solid #ccc; }
        /* :host — style the custom element itself */
        /* ::slotted(p) — style slotted content */
    </style>
    <p>This text is red inside shadow DOM.</p>
    <slot></slot>
    <!-- <slot> renders content passed into the element from outside -->
`;
</script>

<!-- Slots — pass content INTO a web component: -->
<my-card>
    <span slot="title">Card Title</span>
    <p slot="body">Card body content goes here.</p>
    <img slot="image" src="thumb.jpg" alt="Thumbnail">
</my-card>

<template id="my-card-template">
    <style>/* styles */</style>
    <div class="card">
        <div class="card-image"><slot name="image"></slot></div>
        <h3><slot name="title">Default Title</slot></h3>
        <div class="card-body"><slot name="body">Default body text.</slot></div>
    </div>
</template>
```

---

### Advanced Concept 3: ARIA — Accessibility Beyond Semantics

```html
<!-- ARIA (Accessible Rich Internet Applications) fills semantic gaps
     for complex widgets that have no native HTML equivalent -->

<!-- ── ARIA ROLES ──────────────────────────────────────────────────────── -->

<!-- Landmark roles (supplement semantic HTML): -->
<div role="banner">        <!-- header -->
<div role="navigation">    <!-- nav -->
<div role="main">          <!-- main -->
<div role="complementary"> <!-- aside -->
<div role="contentinfo">   <!-- footer -->
<div role="search">        <!-- search form container -->

<!-- Widget roles: -->
<div role="tablist" aria-label="Dashboard sections">
    <button
        role="tab"
        aria-selected="true"
        aria-controls="panel-overview"
        id="tab-overview"
    >Overview</button>
    <button
        role="tab"
        aria-selected="false"
        aria-controls="panel-details"
        id="tab-details"
        tabindex="-1"
    >Details</button>
</div>
<div
    role="tabpanel"
    id="panel-overview"
    aria-labelledby="tab-overview"
>Overview content</div>
<div
    role="tabpanel"
    id="panel-details"
    aria-labelledby="tab-details"
    hidden
>Details content</div>

<!-- ── ARIA STATES & PROPERTIES ────────────────────────────────────────── -->

<!-- aria-expanded — collapsible element: -->
<button
    type="button"
    aria-expanded="false"
    aria-controls="menu-list"
>Open Menu</button>
<ul id="menu-list" hidden>...</ul>

<!-- aria-haspopup — reveals a popup: -->
<button type="button" aria-haspopup="listbox">Select Color</button>
<button type="button" aria-haspopup="dialog">Open Modal</button>
<button type="button" aria-haspopup="menu">Actions</button>
<button type="button" aria-haspopup="tree">File Browser</button>
<button type="button" aria-haspopup="grid">Date Picker</button>

<!-- aria-describedby — points to element that describes this element: -->
<input
    type="password"
    aria-describedby="pw-requirements pw-strength"
>
<p id="pw-requirements">Must be 8+ chars with a number and symbol.</p>
<p id="pw-strength">Strength: Strong</p>

<!-- aria-labelledby — points to element that labels this element: -->
<section aria-labelledby="section-title">
    <h2 id="section-title">Team Members</h2>
    ...
</section>

<!-- aria-current — current item in navigation: -->
<nav>
    <a href="/" aria-current="page">Home</a>
    <a href="/about">About</a>
</nav>

<!-- aria-invalid and aria-errormessage — form validation: -->
<input
    type="email"
    aria-invalid="true"
    aria-errormessage="email-error"
>
<p id="email-error" role="alert">Please enter a valid email address.</p>

<!-- aria-busy — dynamic loading indicator: -->
<div aria-live="polite" aria-busy="true" id="results">
    <span>Loading...</span>
</div>

<!-- aria-hidden — hide from accessibility tree: -->
<i class="icon-star" aria-hidden="true"></i>
<span>Favorite</span>

<!-- Keyboard focus management: -->
<div tabindex="0">Focusable div (use for custom interactive elements)</div>
<div tabindex="-1">Programmatically focusable (not in tab order)</div>
<!-- tabindex="1" or higher — DON'T USE — breaks natural tab order -->
```

---

### Advanced Concept 4: Microdata & JSON-LD Schema Markup

```html
<!-- Microdata — inline schema on elements: -->
<article itemscope itemtype="https://schema.org/Product">
    <img itemprop="image" src="laptop.jpg" alt="Gaming Laptop">
    <h2 itemprop="name">Gaming Laptop Pro X</h2>
    <p itemprop="description">High performance laptop for gaming and AI work.</p>

    <div itemprop="offers" itemscope itemtype="https://schema.org/Offer">
        <span itemprop="priceCurrency" content="INR">₹</span>
        <span itemprop="price" content="89999">89,999</span>
        <link itemprop="availability" href="https://schema.org/InStock">In Stock
    </div>

    <div itemprop="aggregateRating" itemscope itemtype="https://schema.org/AggregateRating">
        <span itemprop="ratingValue">4.7</span> / 5
        (<span itemprop="reviewCount">342</span> reviews)
    </div>
</article>

<!-- JSON-LD — preferred by Google: -->
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [
        {
            "@type": "Question",
            "name": "What is HTML?",
            "acceptedAnswer": {
                "@type": "Answer",
                "text": "HTML (HyperText Markup Language) is the standard markup language for creating web pages."
            }
        },
        {
            "@type": "Question",
            "name": "Is HTML a programming language?",
            "acceptedAnswer": {
                "@type": "Answer",
                "text": "HTML is a markup language, not a programming language. It describes structure, not logic."
            }
        }
    ]
}
</script>

<!-- Breadcrumb schema: -->
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "BreadcrumbList",
    "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://example.com" },
        { "@type": "ListItem", "position": 2, "name": "Blog", "item": "https://example.com/blog" },
        { "@type": "ListItem", "position": 3, "name": "HTML Guide", "item": "https://example.com/blog/html" }
    ]
}
</script>
```

---

### ⚡ Performance & SEO Optimization Table

| Technique                         | Impact   | Implementation                                        |
|-----------------------------------|----------|-------------------------------------------------------|
| `loading="lazy"` on images        | High     | Add to all below-fold images                          |
| `fetchpriority="high"` on hero    | High     | Add to LCP image                                      |
| `<link rel="preload">` fonts      | High     | Prevents invisible text flash (FOUT)                  |
| `<link rel="preconnect">`         | Medium   | Add for CDN, font servers, API origins                |
| `defer` on scripts                | High     | Prevents render blocking                              |
| `type="module"` on scripts        | Medium   | Automatically deferred, better caching                |
| `width` + `height` on images      | High     | Prevents layout shift (CLS)                           |
| `decoding="async"` on images      | Medium   | Decodes image off main thread                         |
| JSON-LD schema markup             | High     | Rich results in Google search                         |
| `<meta name="description">`       | High     | Appears in search results                             |
| Semantic HTML structure           | High     | Better crawlability, accessibility, maintainability   |
| `<link rel="canonical">`          | High     | Prevents duplicate content SEO penalties             |
| Open Graph meta tags              | Medium   | Social media sharing previews                         |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `contenteditable` — Make Any Element Editable

```html
<!-- Any element can become a rich text editor: -->
<div
    contenteditable="true"
    role="textbox"
    aria-multiline="true"
    aria-label="Blog post content"
    spellcheck="true"
>
    Click here and start typing...
</div>

<!-- contenteditable="plaintext-only" — text only, no formatting (Chrome 115+): -->
<div contenteditable="plaintext-only" role="textbox">Plain text only</div>

<!-- Make a table editable: -->
<table>
    <tr>
        <td contenteditable="true">Edit me</td>
        <td contenteditable="true">And me</td>
    </tr>
</table>

<!-- Real use cases: Notion-like editors, in-place editing, Google Docs-style apps -->
<!-- document.execCommand is deprecated — use Selection/Range APIs instead -->
```

---

### 🔮 Secret 2: `<meta http-equiv>` — HTTP Headers in HTML

```html
<!-- These behave like HTTP response headers! -->

<!-- Force browser refresh after N seconds: -->
<meta http-equiv="refresh" content="30">

<!-- Redirect after N seconds to URL: -->
<meta http-equiv="refresh" content="5; url=https://new-domain.com">

<!-- Content Security Policy (when you can't set real HTTP headers): -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">

<!-- X-UA-Compatible — force IE compatibility mode (legacy): -->
<meta http-equiv="X-UA-Compatible" content="IE=edge">

<!-- Cache control (prefer real HTTP headers over this): -->
<meta http-equiv="cache-control" content="no-cache">
<meta http-equiv="pragma" content="no-cache">
```

---

### 🔮 Secret 3: `<data>` and `<time>` — Machine-Readable Values

```html
<!-- <data> links human text to machine-readable value: -->
<ul>
    <li><data value="21053">Product SKU-21053</data></li>
    <li>Price: <data value="89999">₹89,999</data></li>
</ul>

<!-- <time> links human text to ISO datetime: -->
<p>Published <time datetime="2025-03-29T10:30:00+05:30">March 29, 2025 at 10:30 AM IST</time></p>
<p>The event runs from <time datetime="PT2H30M">2 hours and 30 minutes</time>.</p>
<p>Doors open at <time datetime="19:00">7pm</time>.</p>
<p>Happy <time datetime="2025">New Year!</time></p>
<p>The meeting is <time datetime="2025-04-01">next week</time>.</p>

<!-- JavaScript can read datetime: -->
<script>
const times = document.querySelectorAll("time[datetime]");
times.forEach(el => {
    const dt = new Date(el.dateTime);
    // Format with Intl.DateTimeFormat for localization
});
</script>
```

---

### 🔮 Secret 4: The `translate` Attribute — Control Translation Tools

```html
<!-- Prevent Google Translate, browser translation from translating specific content: -->

<!-- Brand names, technical terms, code: -->
<p>To install <span translate="no">TensorFlow</span>, run:</p>
<code translate="no">pip install tensorflow</code>

<!-- The whole page: -->
<html lang="en" translate="no">

<!-- On a specific block: -->
<blockquote translate="no" lang="fr">
    Bonjour le monde — this won't be translated
</blockquote>

<!-- Override parent's no-translate: -->
<div translate="no">
    Don't translate this.
    <span translate="yes">But translate THIS part.</span>
</div>
```

---

### 🔮 Secret 5: `<link rel="modulepreload">` — Preload ES Modules

```html
<!-- Preload ES modules AND their dependencies in one go: -->
<link rel="modulepreload" href="/app.js">
<link rel="modulepreload" href="/modules/api-client.js">
<link rel="modulepreload" href="/modules/state.js">

<!-- Unlike rel="preload" as="script", modulepreload:
     - Parses and compiles the module immediately (not just fetches)
     - Puts it in the module map (no double fetch when script imports it)
     - Also preloads static imports automatically in modern browsers -->

<script type="module" src="/app.js"></script>
<!-- /app.js is already compiled and ready — instant execution! -->
```

---

### 🔮 Secret 6: `<link rel="alternate">` — Content Negotiation

```html
<!-- RSS/Atom feed discovery (browser shows subscribe button): -->
<link rel="alternate" type="application/rss+xml" title="Aryan's Blog RSS" href="/feed.rss">
<link rel="alternate" type="application/atom+xml" title="Aryan's Blog Atom" href="/feed.atom">

<!-- Alternate language versions (hreflang): -->
<link rel="alternate" hreflang="hi" href="https://aryan.dev/hi/">
<link rel="alternate" hreflang="en" href="https://aryan.dev/en/">
<link rel="alternate" hreflang="x-default" href="https://aryan.dev/">

<!-- Alternate media (e.g., print stylesheet): -->
<link rel="alternate stylesheet" media="print" href="print.css" title="Print">
<link rel="alternate stylesheet" href="high-contrast.css" title="High Contrast">

<!-- AMP version of the page (Accelerated Mobile Pages): -->
<link rel="amphtml" href="https://aryan.dev/blog/post?amp=1">
```

---

### 🔮 Secret 7: `<output>`, `<meter>`, `<progress>` — Semantic UI Elements

```html
<!-- <output> — live calculation result (auto-updates with oninput!): -->
<form oninput="total.value = Number(qty.value) * Number(price.value)">
    <label>Quantity: <input type="number" id="qty" name="qty" value="1" min="1"></label>
    <label>Price: <input type="number" id="price" name="price" value="100"></label>
    Total: <output name="total" for="qty price">₹100</output>
</form>

<!-- <meter> — gauge for known ranges: -->
<!-- optimum: where you WANT the value to be -->
<!-- low/high: thresholds that trigger "warning" color changes -->
<meter
    value="35"
    min="0"
    max="100"
    low="25"
    high="75"
    optimum="50"
>35%</meter>
<!-- value < low → red/yellow (below low AND optimum is above low)
     value between low and high → yellow/green
     value > high → red/yellow (above high AND optimum is below high)
     Browser applies colors automatically! -->

<!-- <progress> — task completion: -->
<progress max="100" value="75">75% complete</progress>
<!-- No value = indeterminate (animated bar): -->
<progress>Loading...</progress>
```

---

### 🔮 Secret 8: The `is` Attribute — Customized Built-in Elements

```html
<!-- Extend native elements while keeping their semantics and behaviors! -->

<script>
class FancyButton extends HTMLButtonElement {
    constructor() {
        super();
    }

    connectedCallback() {
        this.addEventListener('click', () => {
            this.style.transform = 'scale(0.95)';
            setTimeout(() => this.style.transform = '', 150);
        });
    }
}

customElements.define('fancy-button', FancyButton, { extends: 'button' });
</script>

<!-- Use with 'is' attribute: -->
<button is="fancy-button" type="submit">Submit</button>
<!-- This is STILL a real <button> — keyboard accessible, form submittable,
     correctly announced by screen readers — but with fancy behavior added -->

<!-- Other examples: -->
<a is="external-link" href="https://example.com">External</a>
<img is="lazy-image" src="photo.jpg" alt="...">
<!-- ⚠️ Safari doesn't support customized built-ins — use a polyfill -->
```

---

### 🔮 Secret 9: `<noscript>` Is More Powerful Than You Think

```html
<!-- noscript only renders when JavaScript is disabled OR unavailable -->

<!-- Fallback content: -->
<noscript>
    <p>This app requires JavaScript. Please enable it.</p>
</noscript>

<!-- Redirect if no JS (in <head>): -->
<noscript>
    <meta http-equiv="refresh" content="0; url=/no-js-version">
</noscript>

<!-- Fallback stylesheet for no-JS: -->
<noscript>
    <link rel="stylesheet" href="no-js.css">
</noscript>

<!-- Tracking pixels that work without JS: -->
<noscript>
    <img src="https://analytics.example.com/pixel.gif?page=home" alt="" width="1" height="1">
</noscript>

<!-- SSR (Server-Side Rendering) pattern — show full content even if JS fails: -->
<noscript id="ssr-content">
    <!-- Full page HTML rendered server-side, hydrated by JS if available -->
</noscript>
```

---

### 🔮 Secret 10: The `ping` Attribute on Links — Analytics Without JS

```html
<!-- When clicked, browser sends a POST request to the ping URLs silently: -->
<a
    href="https://example.com"
    ping="https://analytics.example.com/link-clicked https://monitoring.example.com/track"
>
    Visit Example
</a>

<!-- Browser sends POST to each ping URL with:
     - Content-Type: text/ping
     - Body: "PING"
     - Ping-From: current page URL
     - Ping-To: href URL
     Zero JavaScript required for basic click tracking!
     ⚠️ Can be blocked by browsers and privacy settings -->
```

---

### 🔮 Secret 11: `spellcheck`, `autocorrect`, `autocapitalize` — Input Behavior Control

```html
<!-- Spellcheck: -->
<textarea spellcheck="true">Browser checks spelling here</textarea>
<code spellcheck="false">No spell-check on code</code>
<input type="text" spellcheck="false">  <!-- Disable for username fields -->

<!-- autocorrect (Safari/iOS specific): -->
<input type="text" autocorrect="off">   <!-- Disable auto-correction -->
<textarea autocorrect="on"></textarea>

<!-- autocapitalize — control mobile auto-capitalization: -->
<input type="text" autocapitalize="words">       <!-- Capitalize each word -->
<input type="text" autocapitalize="sentences">   <!-- Capitalize sentences -->
<input type="text" autocapitalize="characters">  <!-- ALL CAPS -->
<input type="text" autocapitalize="off">         <!-- No capitalization (for usernames) -->
<input type="email" autocapitalize="none">       <!-- ALWAYS off for email -->

<!-- enterkeyhint — control mobile keyboard Enter key label: -->
<input type="text" enterkeyhint="search">   <!-- Shows "Search" on Enter key -->
<input type="text" enterkeyhint="go">       <!-- Shows "Go" -->
<input type="text" enterkeyhint="done">     <!-- Shows "Done" -->
<input type="text" enterkeyhint="next">     <!-- Shows "Next" -->
<input type="text" enterkeyhint="send">     <!-- Shows "Send" -->
```

---

### 🔮 Secret 12: `<script type="application/json">` — Embed Data in HTML

```html
<!-- Embed server-rendered data directly in HTML — no extra fetch needed! -->
<script type="application/json" id="page-data">
{
    "user": { "id": 123, "name": "Aryan", "role": "admin" },
    "config": { "apiUrl": "https://api.example.com", "debug": false },
    "initialState": { "todos": [], "theme": "dark" }
}
</script>

<script>
// Read it immediately — no fetch, no async!
const pageData = JSON.parse(document.getElementById('page-data').textContent);
console.log(pageData.user.name);  // "Aryan"
</script>

<!-- This is how Next.js, Nuxt, and SvelteKit pass server state to the client -->
<!-- Also works with other type values: -->
<script type="text/x-template" id="my-template">
    <!-- Your template HTML here — browser ignores content but you can read .textContent -->
</script>
```

---

### 🔮 Secret 13: `<slot>` and `<template>` in Web Components — Composable UI

```html
<!-- slot="name" — named slots: -->
<fancy-card>
    <img slot="image" src="product.jpg" alt="Product">
    <h2 slot="title">Product Name</h2>
    <p slot="description">Product description here.</p>
    <div slot="actions">
        <button>Buy Now</button>
        <button>Wishlist</button>
    </div>
</fancy-card>

<template id="fancy-card">
    <style>
        .card { border: 1px solid #ddd; border-radius: 8px; overflow: hidden; }
        ::slotted(img) { width: 100%; height: auto; }   /* Style slotted img */
        ::slotted(h2) { padding: 0.5rem 1rem; }
    </style>
    <div class="card">
        <slot name="image"></slot>
        <div class="card-body">
            <slot name="title"><h2>Default Title</h2></slot>
            <slot name="description"><p>No description provided.</p></slot>
        </div>
        <div class="card-footer">
            <slot name="actions"></slot>
        </div>
    </div>
</template>
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-2)
├── Day 1-2:  HTML boilerplate, DOCTYPE, head metadata, body structure
├── Day 3-4:  Headings, paragraphs, links, images, lists
├── Day 5-6:  Semantic elements (header, nav, main, article, section, aside, footer)
└── Day 7:    Mini project: personal profile page, validate at validator.w3.org

PHASE 2 — CORE SKILLS (Week 3-4)
├── Day 8-10: Forms — every input type, labels, fieldset, validation attributes
├── Day 11-12: Tables, media elements (video, audio, picture, canvas, svg)
├── Day 13-14: Interactive elements (details, dialog, progress, meter)
└── Project:  Accessible registration form + blog post page

PHASE 3 — ADVANCED (Week 5-7)
├── Week 5:  Accessibility — ARIA roles, states, properties, skip links, focus management
├── Week 6:  SEO — meta tags, Open Graph, JSON-LD structured data, canonical URLs
└── Week 7:  Performance — preload, prefetch, lazy loading, script defer/async
    └── Project: Full portfolio site with perfect Lighthouse score (100)

PHASE 4 — EXPERT / 0.01% (Month 3+)
├── Web Components — custom elements, Shadow DOM, slots, templates
├── Advanced ARIA — complex widgets (combobox, grid, tree, dialog patterns)
├── Performance — Core Web Vitals optimization (LCP, CLS, FID/INP)
├── PWA HTML setup — manifest, service worker, installability
└── Schema markup — rich results, FAQ, breadcrumb, product, review schemas
    └── Project: Fully accessible, SEO-optimized, PWA-ready web app
```

---

### 🏁 Milestone Checklist

- [ ] I can write a proper HTML boilerplate from memory
- [ ] I use semantic elements correctly (article vs section vs div)
- [ ] My forms have proper labels for every input
- [ ] My images always have meaningful alt text
- [ ] My heading hierarchy never skips levels
- [ ] My pages pass HTML validation at validator.w3.org
- [ ] I've added JSON-LD schema markup to a page
- [ ] My pages have proper Open Graph meta tags
- [ ] I understand all ARIA roles, states, and properties
- [ ] I've built a Web Component with Shadow DOM
- [ ] My pages score 100 on Lighthouse accessibility audit
- [ ] I understand how browsers parse HTML (the parsing algorithm)
- [ ] I've built a Progressive Web App HTML shell

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "HTML is a Contract with Browsers AND People"

When you write `<button type="submit">`, you're making a promise:
- **To the browser:** "This activates when pressed, submits the form, receives focus, responds to Enter/Space."
- **To screen readers:** "Announce this as a button. Tell users what it does."
- **To search engines:** "This is an action, not navigation content."
- **To future developers:** "This is interactive — not decorative."

Every semantic element is a contract. A `<nav>` promises "this is navigation." A `<main>` promises "this is the primary content." When you use `<div>` for everything, you break every contract — the browser doesn't know, the screen reader doesn't know, and the next developer doesn't know.

**Write HTML as documentation for both machines and humans.**

---

### 🤫 Deep Insight 1: HTML is the Only Language That Never Breaks

JavaScript throws errors. CSS silently ignores unknown properties. But HTML has **error-correction** built in. If you write invalid HTML, the browser **fixes it and renders anyway** — it never crashes.

This sounds good but hides a trap: **your invalid HTML might be "fixed" differently by different browsers.** The correction algorithm is specified, but edge cases vary. Always validate your HTML.

```html
<!-- Invalid HTML — browser "fixes" it (differently per browser): -->
<p>First <div>Inside div</div> After div</p>
<!-- Browser might render this as: -->
<!-- <p>First</p><div>Inside div</div><p> After div</p> -->
<!-- Because <p> cannot contain <div> — block inside inline! -->
```

---

### 🤫 Deep Insight 2: The Browser Builds TWO Trees from HTML

When the browser parses HTML, it builds:

1. **DOM (Document Object Model)** — the tree of nodes your JavaScript manipulates
2. **Accessibility Tree** — a parallel tree derived from DOM + ARIA, used by screen readers

The accessibility tree:
- Hides elements with `display: none`, `visibility: hidden`, `aria-hidden="true"`
- Computes accessible names from labels, alt text, aria-label, aria-labelledby
- Assigns roles to elements (button, link, heading, list, etc.)
- Exposes states (checked, expanded, selected, disabled)

Bad HTML = broken accessibility tree = broken screen reader experience.

---

### 🤫 Deep Insight 3: HTML Parsing is Not XML Parsing

HTML is **not** XML. The HTML5 parser is specified to handle invalid markup gracefully. This means:
- Optional closing tags (`</li>`, `</p>`, `</td>` etc.) can be omitted
- Attribute values don't need quotes (in some cases)
- Unknown tags are treated as generic `HTMLUnknownElement` — not errors
- Mismatched tags are auto-corrected

But XML/XHTML is strict — any error is fatal. This is why HTML is more forgiving to write but harder to predict when invalid.

---

### 🧠 The Big Picture — HTML in the Modern Stack

```
Browser receives bytes from server
        ↓
HTML parser builds DOM tree (incrementally — starts before full download!)
        ↓
CSS parser builds CSSOM tree (separate)
        ↓
DOM + CSSOM → Render Tree (only visible elements)
        ↓
Layout (calculate positions and sizes)
        ↓
Paint (fill in pixels)
        ↓
Composite (layer management for GPU)
        ↓
Display

HTML in the modern stack:
  Static HTML      → Fastest possible — served as files from CDN
  Server-side HTML → Django, FastAPI, Rails — generated per request
  Client-side HTML → React, Vue — generated by JS in browser
  Hybrid           → Next.js, Nuxt — generated on server, enhanced on client

The trend is back to the server: React Server Components, Astro Islands,
HTMX — all rediscover that HTML from the server is simpler, faster, and
more accessible than giant JavaScript bundles generating HTML client-side.
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept               | What It Means                                                              |
|-----------------------|----------------------------------------------------------------------------|
| DOCTYPE               | Declares HTML5 — always `<!DOCTYPE html>` — must be first line            |
| Semantic HTML         | Use elements that describe MEANING, not just visual appearance             |
| Accessibility tree    | Parallel tree from DOM used by screen readers — built from semantic HTML   |
| Alt text              | Describes images for screen readers — required on all meaningful images    |
| ARIA                  | Fills semantic gaps for complex widgets with no native HTML equivalent     |
| Form labels           | Every input MUST have an associated label — no exceptions                  |
| Heading hierarchy     | h1 → h2 → h3 — never skip levels — one h1 per page                        |
| Meta viewport         | Required for responsive design — never disable zoom                        |
| JSON-LD               | Machine-readable structured data for search engine rich results            |
| Web Components        | Custom HTML elements with encapsulated Shadow DOM — native browser feature |

---

### The 10 Things to Remember

1. ✅ **Always start with `<!DOCTYPE html>`** — no exceptions
2. ✅ **Every `<img>` must have `alt` attribute** — empty string for decorative images
3. ✅ **Every form input must have a `<label>`** — connected via `for`/`id`
4. ✅ **One `<h1>` per page** — it represents the document's main topic
5. ✅ **Use `<button>` for actions, `<a>` for navigation** — never confuse them
6. ✅ **Use semantic elements** — `<nav>`, `<main>`, `<article>`, `<section>` instead of `<div>` everywhere
7. ✅ **Add `defer` to scripts** — prevents render blocking
8. ✅ **Never use tables for layout** — tables are for tabular data only
9. ✅ **Add `lang` to `<html>`** — essential for screen readers and search engines
10. ✅ **Validate your HTML** — use validator.w3.org regularly

---

### Quick Reference Cheat Sheet

```html
<!-- ── MINIMUM VALID PAGE ─────────────────────────────────────────────────── -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <header>
        <nav aria-label="Primary">...</nav>
    </header>
    <main id="main-content">
        <h1>Main Heading</h1>
    </main>
    <footer>...</footer>
</body>
</html>

<!-- ── COMPLETE HEAD FOR PRODUCTION ──────────────────────────────────────── -->
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Page description (150-160 chars)">
    <meta name="author" content="Name">
    <title>Page Title | Site Name</title>
    <link rel="canonical" href="https://example.com/page">
    <!-- OG -->
    <meta property="og:title" content="Title">
    <meta property="og:description" content="Description">
    <meta property="og:image" content="https://example.com/og.jpg">
    <meta property="og:url" content="https://example.com/page">
    <meta property="og:type" content="website">
    <!-- Twitter -->
    <meta name="twitter:card" content="summary_large_image">
    <!-- Preload critical resources -->
    <link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
    <link rel="preconnect" href="https://api.example.com">
    <!-- Icons -->
    <link rel="icon" type="image/svg+xml" href="/icon.svg">
    <link rel="apple-touch-icon" href="/apple-touch-icon.png">
    <link rel="manifest" href="/manifest.json">
    <!-- Styles -->
    <link rel="stylesheet" href="style.css">
</head>

<!-- ── INPUT TYPE REFERENCE ───────────────────────────────────────────────── -->
type="text"          → general text
type="email"         → email (mobile shows @)
type="password"      → masked input
type="number"        → numeric (min/max/step)
type="range"         → slider
type="date"          → date picker
type="datetime-local"→ date + time picker
type="time"          → time picker
type="month"         → month picker
type="week"          → week picker
type="url"           → URL (mobile shows .com key)
type="tel"           → phone (mobile shows number pad)
type="search"        → search (shows × to clear)
type="color"         → color picker
type="file"          → file upload (accept, multiple, capture)
type="checkbox"      → multi-select toggle
type="radio"         → single-select from group (same name)
type="hidden"        → invisible data
type="submit"        → submit form
type="reset"         → reset form fields
type="button"        → no default action (for JS)
type="image"         → image that submits form

<!-- ── SEMANTIC STRUCTURE ─────────────────────────────────────────────────── -->
<header>          → site/section header (logo, nav)
<nav>             → navigation links
<main>            → primary content (ONE per page)
<article>         → self-contained, distributable content
<section>         → thematic group with heading
<aside>           → tangentially related (sidebar)
<footer>          → site/section footer
<address>         → contact info for nearest article/body
<figure>          → image/diagram with caption
<figcaption>      → caption for figure
<time>            → machine-readable date/time
<mark>            → highlighted/relevant text
<details>/<summary>→ native collapsible (no JS!)
<dialog>          → native modal (no JS library needed!)

<!-- ── ARIA ESSENTIALS ────────────────────────────────────────────────────── -->
aria-label="..."           → accessible name (when no visible label)
aria-labelledby="id"       → label from another element
aria-describedby="id"      → additional description
aria-hidden="true"         → hide from accessibility tree
aria-live="polite"         → announce dynamic changes
aria-expanded="true/false" → collapsible state
aria-haspopup="..."        → reveals popup type
aria-current="page"        → current item in set
aria-invalid="true"        → validation error state
aria-required="true"       → required field (supplement to required attr)
role="alert"               → announce immediately
role="status"              → announce when idle
role="search"              → search landmark
tabindex="0"               → add to tab order
tabindex="-1"              → programmatic focus only

<!-- ── PERFORMANCE ATTRIBUTES ────────────────────────────────────────────── -->
loading="lazy"             → defer loading until near viewport
loading="eager"            → load immediately (default)
fetchpriority="high"       → boost resource priority (LCP image)
fetchpriority="low"        → de-prioritize resource
decoding="async"           → decode image off main thread
defer                      → script: execute after parsing
async                      → script: execute as soon as loaded
type="module"              → script: always deferred, supports ESM
crossorigin="anonymous"    → CORS request without credentials
```

---

### What's Next?

After mastering HTML deeply, your natural path forward:

- 📘 **CSS** — Now make everything look incredible (Flexbox, Grid, Custom Properties, Animations)
- 📘 **Accessibility (a11y) Deep Dive** — WCAG 2.2, ARIA Authoring Practices Guide, screen reader testing
- 📘 **SEO & Core Web Vitals** — LCP, CLS, FID/INP — score 100 on Lighthouse
- 📘 **Web Performance** — Critical rendering path, HTTP/2 push, resource hints, CDN strategy
- 📘 **JavaScript** — Bring the structure alive with interactivity
- 📘 **Web Components** — Build your own design system with native browser APIs

---

> 💬 *"The Web is for everyone — and accessibility is not a feature, it is a social trend."*
> — Tim Berners-Lee, inventor of HTML

> 💬 *"Good HTML is invisible. Bad HTML announces itself with every broken screen reader, every failed form, every zero-score audit."*

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: HTML — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
