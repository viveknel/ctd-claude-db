# Changeling: The Dreaming (C20) — Searchable Library

A searchable index of *Changeling: The Dreaming* 20th Anniversary
Edition sourcebooks and compatible supplements, built so that questions
can be answered without re-reading the original PDFs. Each book has its
own self-contained bundle (thematic index + full-text search database),
and a top-level synthesis layer ties themes together across the
collection.

Built with Anthropic's [book-indexer skill](https://github.com/anthropics/skills)
(Claude reads each source PDF once, extracts and tags its text, then
writes a thematic index and a queryable chunk database from it).

## Before you use this library

The two books here are not peers in publishing status. `c20-core` is
the official Onyx Path core rulebook. `realms-of-gods-and-dreams` is
licensed fan content (Storyteller's Vault) that reworks the core
rulebook's terminology (Banality→Defilement, kith→Kinship, cantrip→
Weaving, and more) while explicitly designing itself to interoperate
with the core book. The two also disagree on one specific setting fact
— the date and cause of the setting's "turning of the age" (c20-core:
September 11, 2001; Gods and Dreams: 1999) — see `library_index.md`'s
"Points of disagreement" section before treating the two as a single
seamless continuity.

## What's in here

| Book | Folder | Pages |
|---|---|---|
| Changeling: The Dreaming 20th Anniversary Edition (core rulebook) | `c20-core/` | 503 |
| In the Realm of Gods and Dreams (Sebastian Noh, v2.1) | `realms-of-gods-and-dreams/` | 331 |

```
.
├── README.md                        ← you are here
├── library_index.md                  ← cross-book synthesis
├── scripts/
│   └── query_library.py              ← search several books' databases at once
├── c20-core/
│   ├── book_index.md                 ← thematic index (read this for broad questions)
│   ├── book_chunks.db                ← full-text search database (query for exact facts/quotes)
│   ├── README.md                      ← usage instructions for this book's bundle
│   └── scripts/
│       └── query_chunks.py            ← search this book's database alone
└── realms-of-gods-and-dreams/
    ├── book_index.md
    ├── book_chunks.db
    ├── README.md
    └── scripts/
        └── query_chunks.py
```

Every book folder is a complete, self-contained bundle — any one of
them can be copied out and used entirely on its own, with its own
README explaining how.

## Quick start

**Broad or thematic question about one book** ("what does C20 say about
the Thallain," "how do trods work," "what are the Karmas in Gods and
Dreams") — read that book's own `book_index.md` directly; it's small
enough to load in full and answers most questions without any querying.

**Exact quote, precise fact, or page-number lookup** — query that
book's chunk database:

```bash
python3 c20-core/scripts/query_chunks.py c20-core/book_chunks.db "search terms here"
python3 c20-core/scripts/query_chunks.py c20-core/book_chunks.db --page 254
python3 realms-of-gods-and-dreams/scripts/query_chunks.py realms-of-gods-and-dreams/book_chunks.db --chapter "Chapter Two: Families of the Gods"
```

**Question that spans both books** ("how does Defilement compare to
Banality," "which fae tribes appear in both books") — read
`library_index.md` first; for exact wording, search across both books at
once:

```bash
python3 scripts/query_library.py c20-core/book_chunks.db realms-of-gods-and-dreams/book_chunks.db "search terms"
```

Full-text search (both scripts) supports phrase queries (`"exact
phrase"`), boolean operators (`term1 AND term2`, `term1 NOT term2`),
and prefix matching (`term*`).

## Requirements

Python 3 with the standard library only (`sqlite3` is built in — no
extra packages to install).

## Notes on scope

- This bundle contains **summaries and short paragraph-level excerpts**
  for search/citation purposes, not either book's full text. It's a
  research aid for someone who already owns the source PDFs, not a
  substitute for them.
- Mechanically dense chapters/sections in either book (character
  creation mechanics, the magic-system power catalogs, dice rules,
  Storytelling advice, large regional/kith catalogs) are noted in the
  relevant `book_index.md` as reference material rather than summarized
  exhaustively — query the matching `book_chunks.db` directly for that
  content.
- Page numbers work differently between the two books: `c20-core`'s PDF
  page numbers run exactly one higher than its own printed page numbers
  throughout (e.g. printed p.254 is PDF/chunk-DB p.255), while
  `realms-of-gods-and-dreams`'s PDF page numbers match its printed page
  numbers exactly (no offset). Each book's own README notes this.

## Adding another related book later

Bring the new PDF plus this repo's `library_index.md` and each existing
book's `book_index.md` (the chunk databases and original PDFs aren't
needed again). Run the indexing workflow on just the new book to produce
its own `<slug>/` bundle, then update `library_index.md`'s synthesis
sections to fold in what the new book adds, confirms, or complicates —
including which existing books' terminology it follows, if any, and
whether it introduces further timeline or setting-fact divergences like
the one already tracked above. Re-zip and re-verify the whole library
before presenting it again — see `references/cross_book_index.md` in
the book-indexer skill for the exact packaging steps.
