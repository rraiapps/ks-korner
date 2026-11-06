# K's Korner – notes for Claude

- Audience: a 5th grader (age 10). Keep language simple, fun and encouraging.
- Site is ONE self-contained file: `index.html` (no build step). Served by GitHub Pages from `main` / root at https://kskornerapp.com (`CNAME` file — do not delete).
- Pages: `#home` → `#contents` → one `<section id="guide-id" class="page g-xxx">` per guide.
- Adding a guide:
  1. Add its `<section class="page guide g-xxx">` (with the topbar: logo → home, "📚 Contents" button). Shared look comes from `.guide` styles (tabs, learn cards, flashcards, quiz, match); put only guide-specific colors/CSS under `.g-xxx`. Prefix element ids (e.g. `ss1-`) and put its JS in its own IIFE.
  2. Add an entry to the `GUIDES` array (id, subject, emoji, color, title, desc). TOC (simple list: SUBJECT heading, then topic links) + homepage count build from it. Name each guide after its topic only (no "Unit 1" etc.).
  3. Update the Guides list in README.md.
  4. Test in headless Chromium (no page errors; enter → contents → guide → back), then commit and push to `main`.
- Guides so far: `figurative-language`, `early-americans` (Social Studies), `three-branches` (Social Studies), `decimal-forms` (Math), `appositives`, `sentence-combining` (Reading & Writing), `multiplication`, `comparing-decimals`, `decimals-fractions` (Math), `matter` (Science).
- NEW GUIDES: use the `makeGuide(cfg)` engine (search "GUIDE ENGINE" in index.html). cfg = id, prefix, color, h1, sub, cards[{n,e,c,facts|html,t}], vocab, flash(level), quiz(level), match(level), optional levels + practice{tip, rows(level)}. Helpers: staticQuiz, staticFlash, fracH, KW. Add the GUIDES entry too. Stress-test generated math in node before pushing.
- Every guide uses the same style: Learn (topic cards with underlined key words + "Remember" tip + Word Bank), Flashcards, Quiz, Match. User prefers this over other formats (e.g. no 5 W's layout). Math guides may add a "✏️ Practice Sheet" tab (homework-style, auto-checked) and generate fresh problems with level buttons — see `decimal-forms`.
- Stay politically neutral: no current officeholders' names or opinions.
- Never put the child's full name, school or other personal info on the site (repo is public).
