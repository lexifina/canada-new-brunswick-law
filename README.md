# New Brunswick: law history in git

The law of New Brunswick as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Metadata only, no law text, because the official site for New Brunswick's Acts and Regulations sits behind an automated-access challenge, so it could not be read by automated means.** This repository records which bills received Royal Assent and when, and a handful of open facts about the province's legal system. To read a statute, go to [New Brunswick Acts and Regulations](https://laws.gnb.ca). Law text will be added if the official site becomes readable.

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `catalogue/` | Catalogue of bills given Royal Assent: title, bill number and assent date only | 106 | 106 assent days from 19 December 1996 to 12 June 2026 (1637 bills, 53rd to 61st Legislatures) |
| `legal-system/` | Legal system facts from Wikidata (CC0) | 2 | The province's inception (1 July 1867), then the facts as Wikidata held them on 3 September 2026 |

## Source

The catalogue's bill numbers, English titles and Royal Assent dates are facts taken from the [Legislative Assembly of New Brunswick](https://www.legnb.ca/en/legislation/bills)'s Status of Legislation for each session, from the 53rd Legislature, 1st session to the 61st Legislature, 3rd session; no text of the bills is reproduced. New Brunswick legislates in English and French; the English titles are used. The Wikidata facts are from [Wikidata](https://www.wikidata.org/wiki/Q1965) (CC0).

## Dates

A catalogue entry is dated by the day of Royal Assent the Assembly records, not by commencement (many New Brunswick Acts come into force on proclamation), and is credited to a `catalogue-<date>` entry. Commits are at noon, New Brunswick time (America/Moncton, Atlantic time with daylight saving time). The Wikidata facts are dated by the province's inception (1 July 1867) and otherwise by the latest revision of the Wikidata item (3 September 2026; retrieved 30 October 2026).

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law (or, for facts, the retrieval) that made the change, with an e-mail address that cannot exist (`<law key>@legnb.ca.invalid`). The committer is always Lexifina.

## Limits

Only bills assented in the sessions listed above (53rd Legislature, 1st session to the 61st Legislature, 3rd session) are included; earlier statutes and the consolidated Acts are not. Chapter numbers are not given. Entries do not record later amendment or repeal. Nothing here is an official record of the statutes.
