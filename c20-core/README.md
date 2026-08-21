# Changeling: The Dreaming 20th Anniversary Edition — Searchable Index Bundle

This bundle lets Claude answer questions about this book without
re-reading the original PDF.

## Files

- **`book_index.md`** — thematic index: chapter summaries, themes, key
  terms, cross-cutting arguments. Read this first, in full, for any
  broad/thematic question.
- **`book_chunks.db`** — SQLite database of paragraph-level chunks with
  full-text search, for precise fact lookup, exact figures, or quote
  verification. Query it, don't load it in full.
- **`scripts/query_chunks.py`** — command-line helper for querying the DB.

Book: Changeling: The Dreaming 20th Anniversary Edition (core rulebook)
— 503 pages, indexed 2026-08-21.

## For a future Claude session: how to use this bundle

1. Read `book_index.md` in full — it's small and gives you orientation
   plus answers to most broad/thematic questions directly.
2. For precise facts, exact numbers, or verifying a quote, query the
   chunk database instead of guessing from the summary:

   ```bash
   python3 scripts/query_chunks.py book_chunks.db "search terms here"
   python3 scripts/query_chunks.py book_chunks.db --page 254
   python3 scripts/query_chunks.py book_chunks.db --chapter "Chapter Nine: Nightmares & Stranger Things"
   ```

   Full-text search supports phrase queries (`"exact phrase"`), boolean
   operators (`term1 AND term2`, `term1 NOT term2`), and prefix matching
   (`term*`).
3. Cite page numbers from the chunk results when quoting or referencing
   specific facts — this is the audit trail back to the source PDF. Page
   numbers in this bundle are PDF page numbers, which run exactly one
   higher than the book's own printed page numbers for the whole book
   (e.g. printed page 254 is PDF/chunk-DB page 255).
4. Only fall back to the original PDF if both files fail to answer the
   question (e.g. the question is about a figure, chart, map, or visual
   layout that text extraction wouldn't have captured — this book has
   several full-page character-art spreads and a large illustrated world
   map that are not represented in the text).

Note: Chapters Three (mechanics only), Four (the 18-Art cantrip catalog),
Five (dice rules), and Eight (Storytelling advice) are primarily
mechanical/procedural with little narrative content — `book_index.md`
flags these as such rather than padding out a power-by-power summary.
Query `book_chunks.db` directly for specific cantrip text, character
creation steps, or dice-pool rules. The large catalog sections (Chapter
Two's 13 Kiths/14 Houses, Chapter Nine's Prodigals/Nightmare Chimera/
Thallain, and Appendix I's Nunnehi/Menehune/Hsien/Inanimae) are
summarized in `book_index.md` at a compact one-to-a-few-sentence-per-
entry level with page citations — query the chunk DB for full
Birthright/Frailty/Endowment mechanical text on any specific entry.

## Part of a library

This book is the founding volume of a Changeling: The Dreaming
library that will grow as more C20-line sourcebooks are indexed. See
`../library_index.md` at the top of the library directory for
cross-book synthesis once additional books are added, and
`../scripts/query_library.py` to search across all books' chunk
databases at once.
