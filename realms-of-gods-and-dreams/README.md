# In the Realm of Gods and Dreams — Searchable Index Bundle

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

Book: *In the Realm of Gods and Dreams* (v2.1) by Sebastian Noh — a
licensed Storyteller's Vault supplement for Changeling: The Dreaming,
covering the "Little Gods" of East/South/Southeast Asian myth — 331
pages, indexed 2026-08-23.

## Before you use this bundle

This is **licensed fan/community content (Storyteller's Vault)**, not an
Onyx Path-published core sourcebook — unlike this library's other book,
the C20 core rulebook. It is explicitly designed to be used *alongside*
a core Changeling rulebook (ideally Changeling: The Dreaming 20th
Anniversary Edition) rather than standalone, and it reworks core
terminology wholesale: Banality→Defilement, kith→Kinship, cantrip→
Weaving/Unleashing, Court→Karma, and so on. It also dates its version of
the "turning of the age" to 1999, which does not match the C20 core
book's own dating of the equivalent event (the Evanescence) to September
11, 2001 — see this library's top-level `library_index.md` for the full
discussion of how these two books relate and where they diverge.

**Same author as *Kindred of the East: The Relentless Age*.** This
book's credits page (p.4) lists "Written by: Sebastian Noh (Hsienfan) ...
Developed by: Sebastian Noh, with assistance from RPGnet." *Kindred of
the East: The Relentless Age* — a separate fan-made Vampire: The
Masquerade supplement — carries the matching credit "Written By:
hsienfan / Developed By: hsienfan, with assistance from RPGnet," plus
the same collaborators (Coco Vanille on logo/layout, Tommy Lee on cover
art). This book's own Introduction (p.9) even cites *The Relentless
Age*'s Storytelling chapter by name for cultural-sensitivity guidance,
and both books independently use the term "Hungry Dead" for their
vampire-equivalent beings. Together this is strong internal evidence
that "Sebastian Noh" and "hsienfan" are the same author across both
books — worth knowing if tracing thematic or stylistic influence between
this book and *The Relentless Age* (indexed separately in the Kindred of
the East library).

## For a future Claude session: how to use this bundle

1. Read `book_index.md` in full — it's small and gives you orientation
   plus answers to most broad/thematic questions directly.
2. For precise facts, exact numbers, or verifying a quote, query the
   chunk database instead of guessing from the summary:

   ```bash
   python3 scripts/query_chunks.py book_chunks.db "search terms here"
   python3 scripts/query_chunks.py book_chunks.db --page 254
   python3 scripts/query_chunks.py book_chunks.db --chapter "Chapter Two: Families of the Gods"
   ```

   Full-text search supports phrase queries (`"exact phrase"`), boolean
   operators (`term1 AND term2`, `term1 NOT term2`), and prefix matching
   (`term*`).
3. Cite page numbers from the chunk results when quoting or referencing
   specific facts. Unlike the C20 core rulebook in this library, this
   book's PDF page numbers match its own printed page numbers exactly —
   there is no offset to account for.
4. Only fall back to the original PDF if both files fail to answer the
   question (e.g. a question about a full-page art spread or other
   visual layout not captured by text extraction).

Note: Chapters Three (character creation mechanics), Four (the 8-Art
Weaving/Unleashing catalog), and Six (the large regional Kinship/prayer
catalog) are primarily reference/procedural material — `book_index.md`
notes these as such rather than padding out an exhaustive power-by-power
or entity-by-entity summary. Query `book_chunks.db` directly for a
specific Weaving's exact text, a specific regional Kinship's full
write-up, or specific character-creation steps.

## Part of a library

This book is part of a Changeling: The Dreaming (C20) library alongside
the core rulebook (`../c20-core/`). See `../library_index.md` at the top
of the library directory for cross-book synthesis — including the
terminology crosswalk between this book's vocabulary and the core
rulebook's, and the specific points where the two books' shared
metaplot timeline diverges — and `../scripts/query_library.py` to search
across all books' chunk databases at once.
