# K's Korner – notes for Claude

- Audience: a 5th grader (age 10). Keep language simple, fun and encouraging.
- Site is ONE self-contained file: `index.html` (no build step). Served by GitHub Pages from `main` / root at https://kskornerapp.com (`CNAME` file — do not delete).
- Pages: `#home` → `#contents` → one `<section id="guide-id" class="page g-xxx">` per guide.
- Adding a guide:
  1. Add its `<section class="page guide g-xxx">` (with the topbar: logo → home, "📚 Contents" button). Shared look comes from `.guide` styles (tabs, learn cards, flashcards, quiz, match); put only guide-specific colors/CSS under `.g-xxx`. Prefix element ids (e.g. `ss1-`) and put its JS in its own IIFE.
  2. Add an entry to the `GUIDES` array (id, subject, emoji, color, title, desc). TOC (simple list: SUBJECT heading, then topic links) + homepage count build from it. Name each guide after its topic only (no "Unit 1" etc.).
  3. Update the Guides list in README.md.
  4. Test in headless Chromium (no page errors; enter → contents → guide → back), then commit and push to `main`.
- Guides so far: `figurative-language`, `early-americans` (Social Studies), `three-branches` (Social Studies), `decimal-forms` (Math), `appositives`, `sentence-combining` (Reading & Writing), `multiplication`, `comparing-decimals`, `decimals-fractions` (Math), `matter`, `properties-of-matter` (Science).
- NEW GUIDES: use the `makeGuide(cfg)` engine (search "GUIDE ENGINE" in index.html). cfg = id, prefix, color, h1, sub, cards[{n,e,c,facts|html,t}], vocab, flash(level), quiz(level), match(level), optional levels + practice{tip, rows(level)}. Helpers: staticQuiz, staticFlash, fracH, KW. Add the GUIDES entry too. Stress-test generated math in node before pushing.
- Every guide uses the same style: Learn (topic cards with underlined key words + "Remember" tip + Word Bank), Flashcards, Quiz, Match. User prefers this over other formats (e.g. no 5 W's layout). Math guides may add a "✏️ Practice Sheet" tab (homework-style, auto-checked) and generate fresh problems with level buttons — see `decimal-forms`.
- Stay politically neutral: no current officeholders' names or opinions.
- Never put the child's full name, school or other personal info on the site (repo is public).

## Prize system (search "PRIZES" and "REWARDS" in index.html)
- 100 plushies in PRIZE_SERIES: 1 special (top shelf) + 5 core series. Each item has a PERMANENT id — never renumber or reuse ids (save codes depend on them).
- Rotating the special (only when the user asks): add a new series with NEW ids at the end and status:'special' (20 items: 11 C, 5 R, 3 U, 1 G); change the old special to status:'past'. Past specials drop to the bottom shelf, are no longer in boxes, and can only be bought in the Swap Shop at 1.5x (Goldens never for sale).
- Earning: one Mystery Box per guide per day for quiz >= 70% or Practice Sheet >= 10/12; daily badges (On a Roll 3, Brain Blast 5, Perfect 10, Subject Hopper) give +1 box. Every guide calls KK.earn(id, 'quiz'|'practice', score, total) — new engine guides get this automatically.
- Odds: C 60 / R 28 / U 10 / G 2; 1/3 of boxes come from the special series. Duplicates -> Fluff Points (1/3/8/20).
- Save My Stash code encodes owned items, points, unopened boxes and redeemed tickets with a checksum. Parent Corner PIN is set on the device (hashed in localStorage) — never put a PIN in the code.
