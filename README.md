# K's Korner – School Study Guides

A kid-friendly study guide website (5th grade), hosted on GitHub Pages at https://kskornerapp.com (custom domain set in `CNAME`; DNS at Squarespace).

- `index.html` – the whole site: homepage → table of contents → study guides.
- To add a guide: add a `<section id="...">` for it in `index.html` and one entry in the `GUIDES` list near the top of the `<script>`. The table of contents and guide count update automatically.

## Guides
1. Figurative Language (Reading & Writing)
2. Early Peoples & Native Americans (Social Studies)
3. The Three Branches of Government (Social Studies)
4. Decimal Number Forms (Math) – generates new numbers every time; includes a Practice Sheet
5. Appositives (Reading & Writing)
6. Sentence Combining (Reading & Writing)
7. Multiplication Facts (Math) – tables 1–16, Practice Sheet
8. Comparing Decimals (Math) – <, >, =, Practice Sheet
9. Decimals and Fractions (Math) – Practice Sheet
10. Matter (Science)
11. Properties of Matter (Science)

New guides are built with the `makeGuide(cfg)` engine in index.html (see the 6 guides above for examples).
