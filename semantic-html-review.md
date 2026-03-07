# Semantic HTML Review – Quick Notes

## Importance of Semantic HTML
- **Structural hierarchy**: Use correct heading levels (`<h1>` to `<h6>`) to maintain document outline.
- **Presentational HTML elements** (deprecated): `<center>`, `<big>`, `<font>` – these only affect appearance, not meaning. Avoid them.
- **Semantic HTML elements**: Provide meaning and structure (e.g., `<header>`, `<nav>`, `<article>`, `<figure>`). They improve accessibility, SEO, and code readability.

---

## Semantic HTML Elements

### `<header>`
Defines the header of a document or section. Usually contains introductory content or navigation.
```html
<header>
  <h1>CatPhotoApp</h1>
  <p>Welcome to our cat gallery.</p>
</header>
```

### `<main>`
Contains the main content unique to the page. Use only once per document.
```html
<main>
  <section>
    <h2>Cat Photos</h2>
    <p>Browse adorable cat pictures.</p>
  </section>
</main>
```

### `<section>`
Groups related content, typically with a heading.
```html
<section>
  <h2>About Me</h2>
  <p>Hi, I am Jane Doe and I am a web developer.</p>
</section>
```

### `<nav>`
Represents a section with navigation links.
```html
<nav>
  <ul>
    <li><a href="#photos">Photos</a></li>
    <li><a href="#videos">Videos</a></li>
  </ul>
</nav>
```

### `<figure>` & `<figcaption>`
Groups self-contained content (images, diagrams, code) with an optional caption.
```html
<figure>
  <img src="cats.jpg" alt="Two tabby kittens sleeping.">
  <figcaption>Cats <strong>hate</strong> other cats.</figcaption>
</figure>
```

### `<em>` – Emphasis
Indicates stress emphasis. Typically italicized.
```html
<p>Never give up on <em>your</em> dreams.</p>
```

### `<i>` – Idiomatic Text
Used for alternative voice, technical terms, thoughts, or foreign words. Does **not** imply importance.
```html
<p>There is a certain <i lang="fr">je ne sais quoi</i> in the air.</p>
```
*Use `lang` attribute to specify language.*

### `<strong>` – Strong Importance
Indicates strong importance, seriousness, or urgency. Typically bold.
```html
<p><strong>Warning:</strong> This product may cause allergic reactions.</p>
```

### `<b>` – Bring Attention To
Brings attention to text without implying importance (e.g., keywords, product names).
```html
<p>Try the <b>SuperSound 3000</b> for great audio.</p>
```

### Description List: `<dl>`, `<dt>`, `<dd>`
For term-description groups (like a dictionary).
```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

### `<blockquote>` – Block Quotation
For longer quotes from another source. Use `cite` attribute for source URL.
```html
<blockquote cite="https://www.freecodecamp.org/news/learn-to-code-book/">
  "Can you imagine what it would be like to be a successful developer?"
</blockquote>
```

### `<cite>` – Citation
Title of a referenced work (book, article, etc.).
```html
<p>—Quincy Larson, <cite>How to Learn to Code and Get a Developer Job</cite>.</p>
```

### `<q>` – Inline Quotation
Short inline quote. Browser typically adds quotation marks.
```html
<p>As Quincy Larson said, <q cite="...">Momentum is everything.</q></p>
```

### `<abbr>` – Abbreviation / Acronym
Use `title` attribute to provide full expansion.
```html
<p><abbr title="HyperText Markup Language">HTML</abbr> is the foundation.</p>
```

### `<address>`
Contact information for the author/owner of the document.
```html
<address>
  Written by <a href="mailto:webmaster@example.com">Jon Doe</a>.<br>
  Visit us at: Example.com<br>
  Box 564, Disneyland<br>
  USA
</address>
```

### `<time>` – Date / Time
Machine-readable date/time using `datetime` attribute (ISO 8601 format).
```html
<p>Reservation for <time datetime="20:00">8:00 PM</time>.</p>
<p>Published on <time datetime="2025-03-06">March 6, 2025</time>.</p>
```
*ISO 8601 format: `YYYY-MM-DDThh:mm:ss` (e.g., `2025-03-06T14:30:00`).*

### `<sup>` – Superscript
For exponents, ordinal numbers, etc.
```html
<p>2<sup>2</sup> = 4</p>
<p>Today is March 6<sup>th</sup>.</p>
```

### `<sub>` – Subscript
For chemical formulas, footnotes, etc.
```html
<p>CO<sub>2</sub> is carbon dioxide.</p>
```

### `<code>` & `<pre>` – Code Blocks
`<code>` for inline code; `<pre>` preserves whitespace and formatting.
```html
<pre>
<code>
body {
  color: red;
}
</code>
</pre>
```

### `<u>` – Unarticulated Annotation
Text with a non-textual annotation (e.g., misspelled words, proper names in Chinese).
```html
<p>You can highlight <u>inccccort</u> <u>spling</u>.</p>
```
*By default underlined, but meaning should not be conveyed by style alone.*

### Ruby Annotations: `<ruby>`, `<rp>`, `<rt>`
Used for East Asian typography to show pronunciation (furigana).
```html
<ruby>
  明日 <rp>(</rp><rt>Ashita</rt><rp>)</rp>
</ruby>
```
- `<ruby>`: container.
- `<rt>`: ruby text (pronunciation).
- `<rp>`: fallback parentheses for browsers that don't support ruby.

### `<s>` – Strikethrough
Represents content that is no longer accurate or relevant.
```html
<p><s>Tomorrow's hike will meet at noon.</s></p>
<p>Due to weather, the hike is canceled.</p>
```

---

## Internal Links (Page Anchors)
Link to a specific section within the same page using `href="#id"` and matching `id` on target element.
```html
<a href="#contact">Jump to Contact</a>

<!-- ... later in the page ... -->
<section id="contact">
  <h2>Contact Us</h2>
  <!-- content -->
</section>
```

---

## Summary
- Semantic HTML gives meaning to content, improving accessibility and SEO.
- Choose elements based on **purpose**, not appearance.
- Use headings (`h1`–`h6`) to create a logical outline.
- Replace presentational tags with semantic alternatives.
