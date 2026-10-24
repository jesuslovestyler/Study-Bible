# Study Bible — the Bible in its original words, public domain

A word-by-word interlinear study Bible in Greek, Hebrew, and Aramaic — **released into the public domain** so that no one ever has to redo this tagging work again.

**Live app:** https://jesuslovestyler.github.io/Study-Bible/
**Home page:** https://jesuslovestyler.com/

## What this is

62 books are here so far — 441,791 original-language words — and the library keeps growing, book by book. The Greek Testament is complete: all 27 of its books are here.

- **Hebrew and Aramaic (35):** Genesis, Exodus, Leviticus, Numbers, Deuteronomy, Joshua, Judges, Ruth, 1 Samuel, 2 Samuel, 1 Kings, 2 Kings, 1 Chronicles, 2 Chronicles, Ezra, Nehemiah, Job, Psalms, Proverbs, Ecclesiastes, Song of Songs, Isaiah, Jeremiah, Lamentations, Ezekiel, Daniel, Esther, Hosea, Joel, Jonah, Micah, Nahum, Zephaniah, Haggai, Zechariah
- **Greek (27 — complete):** Matthew, Mark, Luke, John, Acts, Romans, 1 Corinthians, 2 Corinthians, Galatians, Ephesians, Philippians, Colossians, 1 Thessalonians, 2 Thessalonians, 1 Timothy, 2 Timothy, Titus, Philemon, Hebrews, James, 1 Peter, 2 Peter, 1 John, 2 John, 3 John, Jude, Revelation

**Every single word carries all of this:**

- the original word itself, with transliteration and pronunciation
- its **translation in its verse**
- its **Strong's number**, linking to its dictionary entry
- a **definition**
- **synonyms and related words**
- its **parsing** (part of speech, tense, case, person — what the form is doing in the sentence)

The app also has a word search: search by Greek or Hebrew script (accents optional), by transliteration, by English word, or by Strong's number, and find every occurrence across every book in the app.

## Why public domain

Tagged original-language texts exist elsewhere, but they carry Creative Commons conditions. This one doesn't. The tagging labor — hundreds of thousands of words, each with a translation, a definition, and synonyms — is given away outright, under the Unlicense (full text below). Copy it, sell it, build an app on it, print it, translate with it. No permission needed, no attribution required, no strings. If it helps translators and seminary students learn, it has done its job.

One honesty rule runs through the whole work: **if a word form has no dictionary entry of its own, it is left unlinked and its entry says why.** Nothing is invented to make the coverage look complete.

## Sources — all public domain

- **Hebrew text:** the pointed Westminster Leningrad Codex
- **Greek text:** the Robinson–Pierpont Byzantine Greek Textform 2018
- **Hebrew tagging:** our own, worked from Brown–Driver–Briggs (1906) and Strong's Hebrew Dictionary (1890)
- **Greek definitions:** Strong's Greek Dictionary (1890), enriched with Thayer's Greek–English Lexicon (1889)
- **English verse text shown with each verse:** the World English Bible (public domain)

## The data — take it and build

Everything lives in plain JavaScript files under `assets/`. No build step, no database.

- **One file per book** — `assets/data-<book>.js` sets `window.SB_<BOOK>`: the book's chapters and verses. Each verse holds `web` (the World English Bible text of the verse) and `w`, its words in order. Each word entry is `[word, Strong's number, parsing code, gloss]` — for example, in Titus 1:1, `["θεοῦ,", 2316, "N-GSM", "God"]`.
- **Hebrew books add a tagging file** — `assets/data-<book>-tags.js` sets `window.SB_HEB_TAGS_<BOOK>`, mapping each word form to its full entry: `g` its gloss, `n` its Strong's number, `p` its parsing in plain words, and `s` its notes — the dictionary word it comes from, its prefixes and suffixes, and its synonyms and related words.
- **The dictionaries** — `assets/data-lex-greek.js`, `assets/data-lex-hebrew.js`, and `assets/data-thayer.js` hold the dictionary entries (definition and synonyms) behind every Strong's number.
- `index.html` is the reader app itself — one page that loads the data files and renders the interlinear text, the word panels, and the search.

The files are JSON-shaped data in `.js` wrappers, so they convert to plain JSON or any other format in a few lines.

## License

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.

In jurisdictions that recognize copyright laws, the author or authors of this software dedicate any and all copyright interest in the software to the public domain. We make this dedication for the benefit of the public at large and to the detriment of our heirs and successors. We intend this dedication to be an overt act of relinquishment in perpetuity of all present and future rights to this software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <https://unlicense.org>

---

Built by Tyler (jesuslovestyler) with Noki, as part of the free ministry pages at jesuslovestyler.com — everything there is free, always.
