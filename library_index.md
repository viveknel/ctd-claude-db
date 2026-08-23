# Changeling: The Dreaming (C20) — Cross-Book Index

## Books in this collection
- `c20-core/` — *Changeling: The Dreaming 20th Anniversary Edition*
  (core rulebook), 503 pages. Official Onyx Path/White Wolf product.
- `realms-of-gods-and-dreams/` — *In the Realm of Gods and Dreams* by
  Sebastian Noh (v2.1), 331 pages. Licensed Storyteller's Vault
  supplement covering the "Little Gods" of East/South/Southeast Asian
  myth, explicitly designed as a companion volume to the core rulebook.

## How to use this file
This file synthesizes themes across the two books above. For details on
either book alone, read that book's own `book_index.md` in its
subdirectory. For exact quotes or facts, query that book's
`book_chunks.db`, or use `scripts/query_library.py` to search both
books' databases at once (see usage below).

## Provenance note
These two books are not peers in publishing status: `c20-core` is the
official Onyx Path core rulebook, while `realms-of-gods-and-dreams` is
licensed fan content (Storyteller's Vault) that reworks the core
rulebook's concepts under new terminology while explicitly designing
itself to interoperate with it. Treat the core rulebook as the baseline
and the Gods and Dreams book as a compatible but independently-authored
regional expansion — where the two disagree on a specific fact (see
"Points of disagreement" below), the core rulebook is the more
authoritative source for Concordia/Kithain-focused questions, while the
Gods and Dreams book is authoritative for its own Little Gods material.

## Cross-cutting themes

### The Banality/Defilement axis
- **c20-core** treats **Banality** as a 1-10 dot scale with a detailed
  flavor gloss at every point, explicit Triggers (a fixed list plus each
  character's personal Antithesis), a Mists forgetting-severity chart,
  and Quests as the *only* way to permanently remove a dot (see
  `c20-core/book_index.md`, Chapter Six section).
- **realms-of-gods-and-dreams** renames the same concept **Defilement**
  and explicitly notes it is meant to run *lower* by default than
  Banality typically does — most ordinary mortals sit at only 3-4 dots,
  and a permanent rating of 6+ is meant to be noteworthy even among
  humans (Appendix II, p.321, which directly compares itself to "the
  Banality scale in Changeling: the Dreaming 20th Anniversary Edition").
  It also adds mechanics the core book doesn't have: **Echoes**
  (crystallizing Defilement into a fixed taboo/deformity instead of
  risking a full Curse) and **Glamour Zero: the Prayerless** (a mortal
  state of total apathetic disconnection).
- Both books agree on the underlying metaphor (a spiritual poison that
  blinds humanity to magic and erodes magical beings) and on Quests/
  epic action being the only path back from high corruption — the
  difference is calibration and added texture, not philosophy.

### Magic: cantrips vs. Weaving/Unleashing
- **c20-core** casts ordinary magic as a "cantrip" (Art + Realm) and
  reserves **Unleashing** for raw, riskier, Realm-free magic.
- **realms-of-gods-and-dreams** renames the ordinary-magic half
  **Weaving** but keeps **Unleashing** as the term for its own
  raw-magic option — a direct terminological match between the two
  books for this one concept, unlike most of its other renames.
- Both books also share a "theatrical action lowers difficulty" idea:
  c20-core's **Bunks** and Realms-and-Dreams' **Fortunes** work
  similarly, and the latter book explicitly cites C20's Bunk mechanic by
  name as the origin of one of its two competing in-fiction philosophies
  of how Fortunes work (the "Theory of Bunks," p.139) — a rare case of
  the newer book directly naming its mechanical debt to the older one.

### Kith/Kinship and social structure
- **c20-core** organizes Kithain identity around **kith** (13 core
  types) plus a binary **Seelie/Unseelie Court** (expressed via 24
  Legacies) and separately, for nobility, **House**.
- **realms-of-gods-and-dreams** organizes Little God identity around
  **Kinship** (grouped into three broader **tribes** — Celestial,
  Earthblooded, Dreamborn) crossed with **Karma**, a five-school
  philosophy system (Blood Garlands, Dancing Bells, Lions of Heaven,
  Uncrowned Thunders, Wandering Pearls) that explicitly is *not* a
  binary and that a character can freely change over time — a richer,
  two-axis alternative to c20-core's Court binary. Both books reuse the
  *same* 24-26 Legacy list (Beast, Bumpkin, Paladin, etc.) as a
  Willpower-regain mechanic, just attached to different overarching
  frameworks.

### Trods, Freeholds, and the Dreaming itself
- Both books use **Trods**, **Freeholds**, and **Balefires** as
  essentially the same concepts with the same names and largely the
  same function (magical roads; Glamour-generating social hubs powered
  by a hearth-fire). The Realms book's Lower Heavens are explicitly
  identified in its own text as "the other name for the Lower Heavens,
  which has significantly more traction in the west: the Dreaming...
  [the term] favored by the Dreamborn and by the Kithain further west"
  (Ch.1, p.37) — an explicit in-fiction handshake between the two
  books' cosmologies rather than a coincidental naming overlap.
- c20-core's three-plane **Near/Far/Deep Dreaming** structure has a
  loose parallel in the Realms book's **Shallows/Depths** distinction
  within its own Lower Heavens, though the two aren't mapped onto each
  other explicitly.

### Shared chronology — and where it diverges
- Both books agree on the same anchor date for the setting's central
  positive turning point: the **1969 Moon Landing**, called the
  **Resurgence** in both books, which reopened magic to the world after
  centuries of decline.
- The books *diverge* on the dating and specific triggering event of
  the setting's central *negative* turning point since then. c20-core
  ties its "Evanescence" — the event that let the Thallain and Dark-kin
  flood back in force — to **September 11, 2001** (see `c20-core/
  book_index.md`, Chapter One). The Gods and Dreams book instead dates
  its parallel "turning of the age" to **1999**, tied to the death of a
  named demon prince, Zapathasura, in Bangladesh (see `realms-of-gods-
  and-dreams/book_index.md`, Chapter One). Both mark roughly thirty
  years after the Resurgence as the moment things darkened, but land on
  different real-world years and different specific causal events. This
  is the clearest point of factual tension between the two books — see
  "Points of disagreement" below.

## Points of agreement
- The 1969 Resurgence/Moon Landing as the shared origin of the modern
  setting's magical revival.
- The core metaphor of Banality/Defilement as a corrupting,
  perception-blinding force that both mortals and magical beings can
  carry, with Quests/epic action as the standard route to shedding it.
- Trods, Freeholds, and Balefires as shared infrastructure with the same
  names and functions.
- The Thallain's ultimate origin: both books trace the Thallain back to
  the **Fomorians**/the "Elder Dark" — c20-core through the Tessarakonta/
  War of Trees and the Silver Ban (Chapter Nine), and the Gods and
  Dreams book through a cursed text tradition ("The Illuminations of the
  Three Courts") that the Thallain read as "a revelation of the
  Fomorians" (Appendix I, p.312-313). The two books differ in
  *mechanical* execution (c20-core's 19 kiths and per-kith Nightmare
  Legacies vs. the Gods and Dreams book's three-Court "Court Mantle"
  system tied to "Emanations of the Goddess of Defilement," used for
  converting Thallain characters into that book's rules) but not in the
  underlying origin story.
- Weaving/cantrips vs. Unleashing as parallel "controlled vs. raw magic"
  systems, using the term "Unleashing" identically.

## Points of disagreement or tension
- **The Evanescence/"turning of the age" date and trigger** (see above)
  — c20-core: September 11, 2001, caused by the weakening Silver Ban;
  Gods and Dreams: 1999, caused by the rise and defeat of the demon
  prince Zapathasura. If running a game that uses material from both
  books, this is worth resolving explicitly at the table rather than
  assuming the two timelines slot together automatically.
- **Defilement's calibration relative to Banality** is an intentional,
  named difference rather than an oversight (Gods and Dreams, Appendix
  II, p.321) — a mortal NPC built to c20-core's Banality norms may read
  as unusually corrupted if ported directly into Gods and Dreams' scale,
  and vice versa.
- **Thallain mechanical framing**: c20-core's Thallain material assumes
  play as one of 19 named kiths with Nightmare Legacies; the Gods and
  Dreams conversion assumes play (or NPC-building) via its own Court
  Mantle Background instead. The two are not designed to be used
  together for the same character without picking one system.

## Chronology / influence
`realms-of-gods-and-dreams` is written after and explicitly for use with
`c20-core` (its own introduction recommends the 20th Anniversary Edition
core book by name as the ideal companion, and notes compatibility back
through Second and Revised Edition World of Darkness core books as
well). It is not a revision or replacement of any part of the core
rulebook — both remain independently usable, and the Gods and Dreams
book's Appendix I and Chapter Five conversion guide exist specifically
to let material move between the two.

## Same author, different library
`realms-of-gods-and-dreams` shares an author with a book in a separate
*Kindred of the East* library that may be present alongside this one:
*Kindred of the East: The Relentless Age*, a fan-made Vampire: The
Masquerade supplement credited to "hsienfan." The credits pages of both
books match closely — "Written by: Sebastian Noh (Hsienfan) / Developed
by: Sebastian Noh, with assistance from RPGnet" here versus "Written By:
hsienfan / Developed By: hsienfan, with assistance from RPGnet" there,
plus the same named collaborators (Coco Vanille, Tommy Lee) — and
`realms-of-gods-and-dreams` itself cites *The Relentless Age*'s
Storytelling chapter by name for cultural-sensitivity guidance. This is
authorial/stylistic connective tissue only, not a setting link: the two
books are unrelated continuities (one Changeling-line, one Vampire-
line), and nothing in either implies shared canon. See
`realms-of-gods-and-dreams/book_index.md` and
`realms-of-gods-and-dreams/README.md` for the full comparison.

## Cross-book query examples
```
python3 scripts/query_library.py c20-core/book_chunks.db realms-of-gods-and-dreams/book_chunks.db "search terms"
```

## Adding another book later
See the top-level `README.md`'s "Adding another related book later"
section for the exact workflow. In short: index the new book into its
own `<slug>/` bundle, then revisit this file's "Cross-cutting themes,"
"Points of agreement," and "Points of disagreement or tension" sections
— informed by having read all three books' `book_index.md` files —
before re-zipping the whole library. Pay particular attention to whether
a new book uses c20-core's terminology, the Gods and Dreams book's
terminology, or introduces yet another vocabulary of its own, and note
which existing books (if any) it explicitly positions itself as
compatible with.
