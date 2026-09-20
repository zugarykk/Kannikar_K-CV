# Kannikar Kangwanpanich — Portfolio

A single-page personal portfolio website built with plain HTML, CSS, and JavaScript
(no frameworks, no build tools), generated from CV data with the help of Claude Code.

## 🌐 Live Preview

Open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## 📁 Project Structure

```
.
├── index.html                    # Page markup (Hero, About, Competencies, Experience, Education, Footer)
├── style.css                     # Styling, layout, responsive rules, animations
├── script.js                     # Smooth scroll, active nav highlighting, fade-in-on-scroll
├── input/
│   └── cv_kannikar.md            # Source CV data (badges, tables, collapsible experience)
└── instructions/
    └── instruction_prompt.md     # Lab prompt template used to generate the site
```

## ✨ Features

- Sticky navigation bar with smooth scroll and active-section highlighting
- Responsive layout (mobile / tablet / desktop) via CSS Grid & Flexbox
- Fade-in-on-scroll animations
- Navy (`#0B3D91`) and gold (`#E0A800`) color palette
- Semantic HTML5 (`<header>`, `<nav>`, `<section>`, `<footer>`)

## 📝 Note

The original source CV (PDF) is intentionally excluded from this repository via
`.gitignore` since it contains personal contact details (home address, phone number).
Only the sanitized `input/cv_kannikar.md` is tracked.
