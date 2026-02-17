# Product Release Notes

This project is a PoC for a release notes website using MkDocs. Each version is documented in Markdown and the site is generated automatically.

---

## 🔹 Prerequisites

- Python 3.8+
- `pip` installed
- Windows / Linux / Mac

---

## 🔹 Installation

Install MkDocs and the Material theme:
```bash
pip install mkdocs mkdocs-material
```

---

## 🔹 Project Structure
```
docs/
├─ index.md          # Home page
└─ releases/
    ├─ v1.0.md
    └─ v1.1.md
mkdocs.yml            # Site configuration
```

> All Markdown files must be placed inside the `docs/` folder to be recognized by MkDocs.

---

## 🔹 Run the Site Locally
```bash
py -m mkdocs serve
```

Open in your browser: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

> Pages are automatically reloaded when you edit a Markdown file.

---

## 🔹 Build the Static Site

To generate the HTML files (ready for GitHub Pages):
```bash
py -m mkdocs build
```

The generated site will be located in the `site/` folder.

---

## 🔹 Add a New Version

1. Create a new Markdown file in `docs/releases/`:
```
vX.Y.md
```

2. Add the version in `mkdocs.yml` under `nav`:
```yaml
- Version X.Y: releases/vX.Y.md
```

3. Restart the local server or push to GitHub for automatic deployment.