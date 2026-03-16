# HTML Tables and Forms Review – Quick Notes

## HTML Form Elements and Attributes

### `<form>` – The Form Container
- **`action`**: URL where form data is sent.
- **`method`**: HTTP method (`GET` or `POST`).

```html
<form action="/submit" method="POST">
  <!-- form fields go here -->
</form>
```

### `<input>` – User Input Field
The `type` attribute defines the input type. Common types: `text`, `email`, `number`, `radio`, `checkbox`, `button`, etc.

| Attribute | Description |
|-----------|-------------|
| `type` | Specifies input type (text, email, radio, etc.) |
| `placeholder` | Hint text inside the field |
| `value` | Default value or button text (for button types) |
| `name` | Key for submitted data; groups radio buttons |
| `size` | Visible character width |
| `min` / `max` | Min/max values for number inputs |
| `minlength` / `maxlength` | Min/max character length |
| `required` | Field must be filled |
| `disabled` | Field is disabled (not interactive) |
| `readonly` | Field is read-only (can't edit) |

```html
<!-- Text input -->
<input type="text" name="username" placeholder="e.g., Quincy Larson" 
       size="20" minlength="5" maxlength="30" required>

<!-- Number input with limits -->
<input type="number" name="quantity" min="2" max="10" disabled>

<!-- Button input -->
<input type="button" value="Click Me">
```

### `<label>` – Associate Text with Input
- **`for`**: Links to input `id` (explicit association).
- **Implicit association**: Wrap input inside `<label>`.

```html
<!-- Explicit -->
<label for="email">Email:</label>
<input type="email" id="email" name="email">

<!-- Implicit -->
<label>
  Full Name:
  <input type="text" name="fullname">
</label>
```

### `<button>` – Clickable Button
- **`type`**: `submit`, `reset`, or `button` (default is `submit` inside a form).

```html
<button type="button">Show Form</button>
<button type="submit">Submit</button>
<button type="reset">Reset</button>
```

### Grouping with `<fieldset>` and `<legend>`
- `<fieldset>` groups related inputs.
- `<legend>` provides a caption for the group.

```html
<fieldset>
  <legend>Was this your first visit?</legend>
  <label for="yes">Yes</label>
  <input type="radio" id="yes" name="first-visit" value="yes">
  <label for="no">No</label>
  <input type="radio" id="no" name="first-visit" value="no">
</fieldset>
```

### Radio Buttons vs. Checkboxes
- **Radio**: Same `name` → only one selectable.
- **Checkbox**: Multiple choices allowed.

```html
<!-- Radio group -->
<input type="radio" name="stay" value="yes" id="yes">
<label for="yes">Yes</label>
<input type="radio" name="stay" value="no" id="no">
<label for="no">No</label>

<!-- Checkbox group -->
<input type="checkbox" name="interest" value="sports" id="sports">
<label for="sports">Sports</label>
<input type="checkbox" name="interest" value="music" id="music">
<label for="music">Music</label>
```

---

## Working with HTML Table Elements and Attributes

### Table Structure

| Element | Description |
|---------|-------------|
| `<table>` | Container for the table |
| `<caption>` | Title / caption of the table |
| `<thead>` | Groups header rows |
| `<tbody>` | Groups body rows |
| `<tfoot>` | Groups footer rows |
| `<tr>` | Table row |
| `<th>` | Header cell (bold, centered by default) |
| `<td>` | Data cell |
| `colspan` | Attribute to span a cell across multiple columns |

### Example Table

```html
<table>
  <caption>Exam Grades</caption>
  <thead>
    <tr>
      <th>Last Name</th>
      <th>First Name</th>
      <th>Grade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Davis</td>
      <td>Alex</td>
      <td>54</td>
    </tr>
    <tr>
      <td>Doe</td>
      <td>Samantha</td>
      <td>92</td>
    </tr>
    <tr>
      <td>Rodriguez</td>
      <td>Marcus</td>
      <td>88</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Average Grade</td>
      <td>78</td>
    </tr>
  </tfoot>
</table>
```

### Important Notes
- Use `<th>` for headers (scope attributes like `scope="col"` or `scope="row"` improve accessibility).
- `colspan` merges cells horizontally. Use `rowspan` to merge vertically.
- Always maintain proper nesting: `<tr>` inside `<thead>`, `<tbody>`, or `<tfoot>`.

---

## Working with HTML Tools

- **HTML Validator** – Checks syntax and compliance (e.g., W3C Validator).
- **DOM Inspector** – View and edit live HTML structure in browser.
- **DevTools** – Built-in browser tools (F12) for debugging, profiling, and analyzing HTML/CSS/JS.

---

## Summary
- Forms use `<form>` with `action` and `method`, containing `<input>`, `<label>`, `<button>`, etc.
- Group related form controls with `<fieldset>` and `<legend>`.
- Tables are built with `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, and cells `<th>`/`<td>`.
- Use `colspan`/`rowspan` to merge cells.
- Browser DevTools are essential for inspecting and debugging HTML.
