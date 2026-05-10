# rfi-design

Dark monospace design system. IBM Plex Mono, terminal aesthetic, minimal chrome.

Used across [Workspace](https://workspace.rfisolns.org) and [Tourist](https://tourist.rfisolns.org).

---

## Usage

Copy the three CSS files into your project and link them in order:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@300;400;500;600&display=swap" rel="stylesheet">

<link rel="stylesheet" href="tokens.css">
<link rel="stylesheet" href="base.css">
<link rel="stylesheet" href="components.css">
```

Or start from `template.html` for a working single-page app shell.

---

## Files

| File | Purpose |
|---|---|
| `tokens.css` | CSS custom properties — colors, spacing, typography, radii |
| `base.css` | Reset, body defaults, scrollbars |
| `components.css` | Buttons, inputs, cards, modal, sidebar, tabs, tags, markdown |
| `template.html` | Minimal starter with app shell and interactive examples |

---

## Design tokens

```css
/* Backgrounds */
--bg-base:      #0d0d0d   /* page background */
--bg-raised:    #111111   /* header, sidebar */
--bg-surface:   #141414   /* kanban columns */
--bg-overlay:   #161616   /* modals, code blocks */
--bg-input:     #1a1a1a   /* inputs, search */
--bg-hover:     #1e1e1e   /* hover state */

/* Accent */
--accent:       #5fc83b   /* primary green */
--accent-bright:#8ce870   /* highlight / active text */
--accent-tint:  #0d1a0a   /* selected background */

/* Text */
--text-primary:   #e0e0e0
--text-secondary: #cccccc
--text-muted:     #888888
--text-dim:       #666666
```

---

## Components

### Buttons
```html
<button class="btn btn-primary">Save</button>
<button class="btn">Default</button>
<button class="btn btn-danger">Delete</button>
<button class="btn btn-ghost">Ghost</button>
<button class="btn btn-pill">Pill</button>
<button class="icon-btn">+</button>
```

### Inputs
```html
<input class="input" placeholder="Default input">
<input class="input input-underline" placeholder="Underline style">
```

### Cards
```html
<div class="card">Content</div>
<div class="card selected">Selected state</div>
```

### Tabs
```html
<nav class="tab-bar">
  <button class="tab active">Tab 1</button>
  <button class="tab">Tab 2</button>
</nav>
```

### Pills
```html
<button class="pill active">Selected</button>
<button class="pill">Option</button>
```

### Tags
```html
<!-- Set --tag-color to any hex for per-tag coloring -->
<span class="tag" style="--tag-color: #5fc83b">feature</span>
<span class="tag" style="--tag-color: #f87171">bug</span>
```

### Modal
```html
<div class="modal-backdrop">
  <div class="modal">
    <div class="modal-header">
      <span>Title</span>
      <button class="icon-btn modal-close">✕</button>
    </div>
    <div class="modal-body">...</div>
    <div class="modal-footer">
      <button class="btn btn-danger">Delete</button>
      <button class="btn btn-primary">Save</button>
    </div>
  </div>
</div>
```

### Toast
```html
<div class="toast" id="toast">Saved</div>
<script>
  function showToast(msg, duration = 2000) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), duration);
  }
</script>
```

### Sidebar
```html
<aside class="sidebar" style="width: 220px;">
  <div class="sidebar-header">
    <span class="sidebar-label">Notes</span>
    <button class="icon-btn">+</button>
  </div>
  <div class="sidebar-item active">
    <div class="sidebar-item-title">My note</div>
    <div class="sidebar-item-meta">2 days ago</div>
  </div>
  <div class="sidebar-item">...</div>
</aside>
```

---

## Typography

IBM Plex Mono ships in four weights used in this system:

| Weight | Class / usage |
|---|---|
| 300 | Large display numbers, hero text |
| 400 | Body text |
| 500 | Labels, buttons |
| 600 | Headings, card titles |

Letter-spacing convention: `0.2em` for uppercase display, `0.08–0.15em` for labels.
