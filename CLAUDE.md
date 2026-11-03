# K's Korner – notes for Claude

- Audience: a 5th grader (age 10). Keep language simple, fun and encouraging.
- Site is ONE self-contained file: `index.html` (no build step). Served by GitHub Pages from `main` / root.
- Pages: `#home` → `#contents` → one `<section id="guide-id" class="page g-xxx">` per guide.
- Adding a guide:
  1. Add its `<section>` (with the topbar: logo → home, "📚 Contents" button) and scoped CSS (`.g-xxx ...`) and its JS in its own IIFE.
  2. Add an entry to the `GUIDES` array (id, subject, emoji, color, title, desc). TOC + homepage count build from it.
  3. Update the Guides list in README.md.
  4. Test in headless Chromium (no page errors; enter → contents → guide → back), then commit and push to `main`.
- Never put the child's full name, school or other personal info on the site (repo is public).
