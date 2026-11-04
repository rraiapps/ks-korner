# K's Korner – notes for Claude

- Audience: a 5th grader (age 10). Keep language simple, fun and encouraging.
- Site is ONE self-contained file: `index.html` (no build step). Served by GitHub Pages from `main` / root.
- Pages: `#home` → `#contents` → one `<section id="guide-id" class="page g-xxx">` per guide.
- Adding a guide:
  1. Add its `<section class="page guide g-xxx">` (with the topbar: logo → home, "📚 Contents" button). Shared look comes from `.guide` styles (tabs, learn cards, flashcards, quiz, match); put only guide-specific colors/CSS under `.g-xxx`. Prefix element ids (e.g. `ss1-`) and put its JS in its own IIFE.
  2. Add an entry to the `GUIDES` array (id, subject, emoji, color, title, desc). TOC (simple list: SUBJECT heading, then topic links) + homepage count build from it. Use a short topic title.
  3. Update the Guides list in README.md.
  4. Test in headless Chromium (no page errors; enter → contents → guide → back), then commit and push to `main`.
- Guides so far: `figurative-language`, `early-americans` (Social Studies Unit 1), `three-branches` (Social Studies; has a "Which Branch?" sorting game).
- Stay politically neutral: no current officeholders' names or opinions.
- Never put the child's full name, school or other personal info on the site (repo is public).
