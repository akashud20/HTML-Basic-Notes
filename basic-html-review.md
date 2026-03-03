# Basic HTML Review – Quick Notes

## HTML Basics

HTML defines the content and structure of a web page.

- **Elements** are building blocks: `<tagname>Content</tagname>`.
- **Void elements** have no content, only a start tag: `<img>`, `<meta>`. (Both `<img>` and `<img/>` are acceptable.)
- **Attributes** provide extra info inside the opening tag: `<tag attribute="value">`.
- **Boolean attributes** are either present (true) or absent (false): `disabled`, `readonly`, `required`.
- **Comments**: `<!-- This is a comment -->`

## Common HTML Elements

| Element           | Purpose                                               | Example                                            |
|-------------------|-------------------------------------------------------|----------------------------------------------------|
| `<h1>`–`<h6>`     | Headings (h1 highest, h6 lowest)                      | `<h1>Title</h1>`                                   |
| `<p>`             | Paragraph                                             | `<p>Text</p>`                                      |
| `<img>`           | Image                                                 | `<img src="url" alt="description">`            |
| `<body>`          | Document content                                      | `<body>...</body>`                                 |
| `<section>`       | Thematic grouping of content                          | `<section><h2>...</h2><p>...</p></section>`        |
| `<div>`           | Generic container (no semantic meaning)               | `<div class="wrapper">...</div>`                 |
| `<a>`             | Hyperlink                                             | `<a href="url">link text</a>`                    |
| `<ul>` / `<ol>`   | Unordered / Ordered list                              | `<ul><li>item</li></ul>`                           |
| `<em>`            | Emphasized text (usually italic)                      | `<p>Cats <em>love</em> lasagna.</p>`               |
| `<strong>`        | Strong importance (bold)                              | `<strong>Warning!</strong>`                        |
| `<figure>` / `<figcaption>` | Group media with caption                   | `<figure><img ...><figcaption>Caption</figcaption></figure>` |
| `<main>`          | Main content of the page                              | `<main>...</main>`                                 |
| `<footer>`        | Footer, usually copyright info                        | `<footer><p>Copyright...</p></footer>`             |

## Identifiers and Grouping

- **id**: Unique identifier for an element (use once per page).
  ```html
  <div id="unique-name"> ... </div>  <!-- no spaces, use hyphens -->
  ```
- **class**: Reusable group for styling/behavior.
  ```html
  <div class="box red-box"> ... </div>  <!-- space-separated multiple classes -->
  ```

## Special Characters & Linking

- HTML entities represent reserved characters: `&amp;` (&), `&lt;` (<), `&gt;` (>), `&copy;` (©).

- `<link>` links external resources (e.g., CSS):
  ```html
  <link rel="stylesheet" href="styles.css">
  ```

- `<script>` embeds or links JavaScript:
  ```html
  <script src="script.js"></script>  <!-- best practice: external file -->
  ```

## HTML Boilerplate (basic template)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Page Title</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <!-- visible content -->
  </body>
</html>
```

- `<!DOCTYPE html>`: declares HTML5.
- `<html lang="en">`: root element with language.
- `<head>`: metadata (not displayed).
- `<meta charset="utf-8">`: character encoding (UTF-8).
- `<title>`: browser tab title.

## SEO & Social Sharing

- **Meta description**: influences search snippets.
  ```html
  <meta name="description" content="Brief summary.">
  ```

- **Open Graph tags** (for social media previews):

  ```html
  <meta property="og:title" content="...">
  <meta property="og:type" content="website">
  <meta property="og:image" content="...">
  <meta property="og:url" content="...">
  ```

## Media Elements & Optimization

- **Replaced elements**: content determined by external resource (e.g., `<iframe>`, `<video>`, `<embed>`, `<input type="image">`).

- `<iframe>` embeds another HTML page:

  ```html
  <iframe src="url" title="description" allowfullscreen></iframe>
  ```

- **Image formats**: prefer modern formats like WEBP or AVIF over PNG/JPG for better compression.

- **Image licenses**:
  - Public Domain (CC0) = no restrictions.
  - Creative Commons = permissive.

- **SVG**: vector graphic, scales without quality loss.

## Multimedia Integration

- `<audio>` with `controls` attribute:

  ```html
  <audio src="file.mp3" controls loop muted></audio>
  ```

- `<video>` with optional `poster` (placeholder image):

  ```html
  <video src="file.mp4" controls loop muted poster="preview.jpg"></video>
  ```

- `<source>` inside `<audio>`/`<video>` for multiple formats (browser picks first supported):

  ```html
  <audio controls>
    <source src="audio.ogg" type="audio/ogg">
    <source src="audio.mp3" type="audio/mpeg">
  </audio>
  ```

## Target Attribute for Links (`<a>`)

- `_self` – default, opens in same tab.
- `_blank` – opens in new tab/window.
- `_parent` – opens in parent frame (if inside iframe).
- `_top` – opens in full browser tab (breaks out of all frames).

## Absolute vs. Relative Paths

- **Absolute path**: full URL including protocol and domain.
  `https://site.com/images/pic.jpg`
- **Relative path**: location relative to current file.
  - `images/pic.jpg` (same folder)
  - `../about.html` (parent folder)
  - `./style.css` (current folder)

## Link States (CSS pseudo-classes)

- `:link` – unvisited link.
- `:visited` – link the user has visited.
- `:hover` – mouse over the link.
- `:focus` – link focused (e.g., via keyboard).
- `:active` – link being clicked.
