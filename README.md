# Changeling: The Dreaming (C20) — Searchable Library

A searchable index of *Changeling: The Dreaming* 20th Anniversary
Edition sourcebooks, built so that questions can be answered without
re-reading the original PDFs. Each book has its own self-contained
bundle (thematic index + full-text search database), and a top-level
synthesis layer ties themes together as more books are added.

Built with Anthropic's [book-indexer skill](https://github.com/anthropics/skills)
(Claude reads each source PDF once, extracts and tags its text, then
writes a thematic index and a queryable chunk database from it).

## Before you use this library

This library currently holds a single book — the C20 core rulebook —
and is explicitly meant to grow. There is no cross-book synthesis to
speak of yet (`library_index.md` is a placeholder), so don't expect it
to answer comparative questions until more books are added. For any
question right now, go straight to `c20-core/book_index.md`.

## What's in here

| Book | Folder | Pages |
|---|---|---|
| Changeling: The Dreaming 20th Anniversary Edition (core rulebook) | `c20-core/` | 503 |

```
.
├── README.md                ← you are here
├── library_index.md          ← cross-book synthesis (placeholder until
│                                a second book is added)
├── scripts/
│   └── query_library.py      ← search several books' databases at once
└── c20-core/
    ├── book_index.md         ← thematic index (read this for broad questions)
    ├── book_chunks.db        ← full-text search database (query for exact facts/quotes)
    ├── README.md              ← usage instructions for this book's bundle
    └── scripts/
        └── query_chunks.py    ← search this book's database alone
```

Every book folder is a complete, self-contained bundle — any one of
them (e.g. `c20-core/`) can be copied out and used entirely on its own,
with its own README explaining how.

## Quick start

**Broad or thematic question about the core rulebook** ("what does C20
say about the Thallain," "how do trods work," "what are the Noble
Houses") — read `c20-core/book_index.md` directly; it's small enough to
load in full and answers most questions without any querying.

**Exact quote, precise fact, or page-number lookup** — query the book's
chunk database:

```bash
python3 c20-core/scripts/query_chunks.py c20-core/book_chunks.db "search terms here"
python3 c20-core/scripts/query_chunks.py c20-core/book_chunks.db --page 254
python3 c20-core/scripts/query_chunks.py c20-core/book_chunks.db --chapter "Chapter Nine: Nightmares & Stranger Things"
```

**Question that spans multiple books** — not yet meaningful with a
single-book library; once a second book is added, read
`library_index.md` first, then search across the specific books it
names if you need exact wording:

```bash
python3 scripts/query_library.py c20-core/book_chunks.db <other-book>/book_chunks.db "search terms"
```

Full-text search (both scripts) supports phrase queries (`"exact
phrase"`), boolean operators (`term1 AND term2`, `term1 NOT term2`),
and prefix matching (`term*`).

## Requirements

Python 3 with the standard library only (`sqlite3` is built in — no
extra packages to install).

## Notes on scope

- This bundle contains **summaries and short paragraph-level excerpts**
  for search/citation purposes, not the core rulebook's full text. It's
  a research aid for someone who already owns the source PDF, not a
  substitute for it.
- Mechanically dense chapters/sections (character creation mechanics,
  the 18-Art cantrip catalog, dice rules, Storytelling advice) are noted
  in `c20-core/book_index.md` as reference material rather than
  summarized exhaustively — query `c20-core/book_chunks.db` directly for
  that content.
- Page numbers throughout this bundle are **PDF page numbers**, which
  run exactly one higher than the book's own printed page numbers for
  its entire length (e.g. printed page 254 is PDF/chunk-DB page 255).

## Adding another related book later

Bring the new C20-line PDF plus this repo's `library_index.md` and
`c20-core/book_index.md` (the chunk database and original PDF aren't
needed again). Run the indexing workflow on just the new book to produce
its own `<slug>/` bundle, then update `library_index.md`'s synthesis
sections to fold in what the new book adds, confirms, or complicates —
including, if relevant, whether it belongs to the same 20th Anniversary
continuity or a different Changeling-line edition. Re-zip and re-verify
the whole library before presenting it again — see
`references/cross_book_index.md` in the book-indexer skill for the exact
packaging steps.
