# How this repository was made (New Brunswick)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Legislative Assembly of New Brunswick: Status of Legislation, per session | <https://www.legnb.ca/en/legislation/bills> | 2026-10-30 | Facts only (bill number, title, Royal Assent date). The Assembly states that the information "may be reproduced in part or in whole, and by any means, without charge or further permission" for personal and public non-commercial use; no text of the bills is reproduced |
| Wikidata | <https://www.wikidata.org/wiki/Q1965> | 2026-10-30 | CC0 1.0 |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `catalogue` | Catalogue of New Brunswick bills given Royal Assent (title, bill number and assent date only) | 106 | 1996-12-19 to 2026-06-12 |
| `legal-system` | New Brunswick: legal system facts (Wikidata) | 2 | 1867-07-01 to 2026-09-03 |

The build made 108 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 106 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 1 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 107 laws in the record.
- 214 tags.

## Dates

Each commit is dated at noon (America/Moncton) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Catalogue entries are dated by the day of Royal Assent recorded by the Legislative Assembly; they describe bills and are not law text. https://www.legnb.ca/en/legislation/bills

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `824c069a03a0cddfad98598561ea7750abcad54180ac57de0f855d650d5059e9` (771514 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a97ff7ea62c3c7595c5668a297d533da0b74373c`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

108 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- No law text is published. The official consolidated Acts and Regulations of New Brunswick could not be read by automated means, so nothing was taken from them.
- The catalogue holds facts only: bill number, English title, legislature and session, and the Royal Assent date, as the Legislative Assembly's Status of Legislation gives them. Chapter numbers in the annual statutes are not on those pages and are not given.
- Coverage: every bill marked as having received Royal Assent from the 53rd Legislature, 1st session to the 61st Legislature, 3rd session (1996-12-19 to 2026-06-12): 1637 bills on 106 assent days. Each session's count matches the Assembly's own "Received Royal Assent" total.
- New Brunswick is officially bilingual; the English titles are used. The French titles are equally authoritative.
- Wikidata facts (CC0) form the "legal-system" act: the province's inception (1867-07-01) is day-precision, so it is the oldest version; the other facts are dated by the latest revision of the Wikidata item before retrieval (2026-09-03; retrieved 2026-10-30), so no commit lies after the build.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code with Claude Opus 5.5 wrote Lexifina's code and chose the sources; it did not write or alter any legal text. The code is deterministic and runs no model.
