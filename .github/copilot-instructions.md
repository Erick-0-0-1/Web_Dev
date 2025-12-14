<!-- Copilot instructions for AI coding agents -->
# Copilot Instructions — web_dev (single-page portfolio)

Purpose: Help an AI agent be immediately productive editing this small static portfolio site.

Overview
- This is a single-page static website: `index.html` + `css/index.css` + images in `img/`.
- No build system, no package.json, no test suite, and no server-side code.

Big picture
- Architecture: flat static site. HTML defines structure; CSS controls layout and look. All assets are referenced with relative paths (e.g., `css/index.css`, `img/bg.png`).
- Typical changes are edits to `index.html` (structure/content) and `css/index.css` (styling). Adding JS: place files in a new `js/` folder and include them via a `<script>` tag before `</body>`.

Key files (examples)
- `index.html` — page content, nav, hero, about, skills list.
- `css/index.css` — all present styling; notable selectors: `.nav`, `.nav-ul`, `.h1`, `.child`, `.child1`, `.skills`.
- `img/bg.png` — background used in `.child`.

Project-specific conventions & patterns
- No framework conventions (vanilla HTML/CSS). Keep edits minimal and explicit.
- Use relative asset paths (do not convert to absolute URLs).
- Naming is class-focused (e.g., `.child`, `.child1`, `.hero-section`). Follow existing names when modifying or extending.
- Keep layout changes responsive: current CSS uses fixed margins (e.g., `margin: 0 500px 0 500px;`). If you replace these, include media queries to preserve mobile behavior.

How to run / preview
- Open `index.html` in a browser for quick checks.
- Or run a simple HTTP server for better asset behaviour:

  - Python 3: `python -m http.server 8000`
  - VS Code: use the Live Server extension and open the workspace root.

Adding features
- Add CSS to `css/index.css` (avoid creating multiple CSS files unless necessary). If adding JS, create `js/main.js` and include `<script src="js/main.js"></script>` just before `</body>`.
- When adding images, place them in `img/` and reference relatively: `url(../img/your-file.png)` from CSS or `img/your-file.png` in HTML.

Quality and PR guidance (project-specific)
- Keep changes small and focused: update `index.html` and `css/index.css` together when changing layout or content.
- Check pages in desktop and mobile widths. Because there is no automated test, include screenshots in PRs for significant visual changes.

Common example tasks (prompts you can use)
- "Make the nav responsive: collapse to a vertical stack under 600px and add appropriate spacing, using existing `.nav` and `.nav-ul` selectors and a media query in `css/index.css`."
- "Add a `footer` section with two columns: contact and social links. Place HTML in `index.html` and styles in `css/index.css` keeping the current visual style."

Notes for maintainers
- There is no CI or linter configuration. If adding one, include config files at project root and document usage in README.

If anything here is unclear or missing, tell me which parts you want expanded (e.g., preferred mobile breakpoints, color tokens, or a style-guide addition).
