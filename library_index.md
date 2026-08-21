# Changeling: The Dreaming (C20) — Cross-Book Index

## Books in this collection
- `c20-core/` — *Changeling: The Dreaming 20th Anniversary Edition*
  (core rulebook), 503 pages

## How to use this file
This file is meant to synthesize themes *across* the books in this
library. Right now the library holds only its founding volume, the C20
core rulebook, so there is nothing yet to cross-reference — this file is
a placeholder, ready to be filled in once a second C20 book is indexed
and added.

For now, go straight to `c20-core/book_index.md` for any question about
this line — it is small enough to read in full and covers the entire
core rulebook (setting history and cosmology, the 13 Kithain and 14
Noble Houses, the 18 Arts, full game mechanics, the Dreaming/trods/
freeholds/chimera, Storytelling advice, Prodigals/Thallain/the Dauntain,
and the Gallain appendix covering Nunnehi/Menehune/Hsien/Inanimae fae).
For exact quotes or precise facts, query `c20-core/book_chunks.db` (see
`c20-core/README.md` for query examples).

## Cross-cutting themes
*Not yet applicable — only one book in the library so far.* When a
second book is added, this section should identify themes that recur
across both books' `book_index.md` "Cross-cutting themes" or chapter
sections, and describe how each book's specific treatment differs, not
just that both mention a topic.

## Points of agreement
*Not yet applicable.*

## Points of disagreement or tension
*Not yet applicable.* If future C20-line books (or Classic-era Changeling
material, should any get added to this library) genuinely contradict the
core rulebook on some point of setting fact, that should be flagged here
explicitly rather than silently resolved in favor of one source.

## Chronology / influence
*Not yet applicable.* If later additions include material that predates
or postdates the 20th Anniversary line (e.g. 1st/2nd edition Changeling
sourcebooks, or the *Dark Ages: Fae* spinoff referenced in the core
book's own publication history, p.26), note here how they relate —
whether they're an updated retelling of earlier material or a genuinely
separate continuity, following the pattern used in other libraries built
with this same indexing method.

## Cross-book query examples
```
python3 scripts/query_library.py c20-core/book_chunks.db "search terms"
```
(once a second book exists, add its slug directory to the command, e.g.
`c20-core/book_chunks.db c20-second-book/book_chunks.db "search terms"`)

## Adding the next book
See the top-level `README.md`'s "Adding another related book later"
section for the exact workflow. In short: index the new book into its
own `<slug>/` bundle alongside `c20-core/`, then revisit this file's
"Cross-cutting themes," "Points of agreement," and "Points of
disagreement or tension" sections — informed by having read both books'
`book_index.md` files — before re-zipping the whole library.
