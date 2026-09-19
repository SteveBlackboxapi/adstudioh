# Annotation notes — best-ads Explore pass

Date: 2026-09-19 (Europe/London)

Extended `best-ads.json` (116 entries) with JEV/Reve/Explore fields per `ADSTUDIOH-EXPLORE-SPEC.md`. Original credits/links preserved; no ids removed; no dedupe.

## Counts

- **Total entries:** 116
- **style_bar true:** 44 (target ~35–45)
- **Entries on ≥1 board:** 39
- **dissection.headline filled:** 10 (confident title=headline only; rest null stubs)
- **thumbnail:** all null (stub)

## style_bar ids

- `absolut-bottle-campaign`
- `absolut-perfection`
- `absolut-perfection-1980`
- `absolut-warhol-1985`
- `always-likeagirl`
- `apple-1984`
- `apple-heres-to-the-crazy-ones`
- `apple-ipod-silhouettes`
- `apple-think-different`
- `avis-we-try-harder-1962`
- `benson-hedges-gold-surreal-cdp`
- `bmw-the-hire`
- `bmw-the-hire-series-2001`
- `cadbury-gorilla`
- `cca-great-ideas-of-western-man`
- `chanel-no5-the-film`
- `chanel-no5-the-film-2004`
- `de-beers-a-diamond-is-forever-1948`
- `dior-jadore-charlize`
- `dior-jadore-charlize-theron-2004`
- `dove-evolution`
- `dove-evolution-2006`
- `economist-white-out-of-red-1988`
- `fearless-girl`
- `gucci-ss2003-g-spot`
- `guinness-noitulove`
- `guinness-surfer`
- `honda-cog`
- `honda-grrr`
- `ibm-paul-rand-identity`
- `john-lewis-the-long-wait-2011`
- `levis-launderette`
- `nike-breaking2`
- `nike-dream-crazy`
- `nike-dream-crazy-kaepernick`
- `nike-just-do-it`
- `old-spice-man-your-man-could-smell-like`
- `patagonia-dont-buy-this-jacket`
- `prada-fw1996-glen-luchford`
- `silk-cut-purple-posters-1984`
- `volvo-epic-split`
- `vw-lemon`
- `vw-think-small`
- `ysl-opium-sophie-dahl-2000`

## Format histogram

| format | count |
|---|---|
| Cinematic film | 47 |
| Print poster | 34 |
| Talking head | 6 |
| Interactive / digital | 6 |
| Mashup / compilation | 5 |
| Product demo | 5 |
| OOH | 5 |
| Identity / logo | 3 |
| UGC testimonial | 2 |
| Static image | 2 |
| Other | 1 |

## Awareness histogram (primary)

| awareness_primary | count |
|---|---|
| Most aware | 46 |
| Product aware | 23 |
| Unaware | 22 |
| Problem aware | 17 |
| Solution aware | 8 |

## Source histogram

| source | count |
|---|---|
| wikipedia | 41 |
| publication | 34 |
| award_archive | 21 |
| brand | 9 |
| agency | 5 |
| museum | 4 |
| other | 2 |

## Boards coverage

| board id | annotated membership | seed items in reference-boards.json |
|---|---|---|
| `board-absolut-print` | 6 | 6 |
| `board-apple-restraint` | 6 | 6 |
| `board-fashion-provocation` | 8 | 8 |
| `board-nike-just-do-it` | 6 | 6 |
| `board-print-revolution` | 8 | 8 |
| `board-uk-craft` | 8 | 8 |

Unique catalog entries appearing on boards: **39** / 116.

Note: some seed board item ids appear on multiple boards (e.g. Absolut on print-revolution + absolut-print); `boards[]` lists all.

## Method

- **format / awareness:** judgment from medium, tags, title, why_iconic, style_notes; soft awareness_mix peaked on primary.
- **style_bar:** curated craft heroes (Apple, VW, Nike, Guinness, Dove Evolution, Absolut, Honda Cog, Cadbury Gorilla, Chanel/Dior films, key fashion, UK craft print, Paul Rand IBM identity, etc.).
- **boards:** matched against `explore/reference-boards.json` item ids.
- **source:** inferred from `links.primary` domain.
- **dissection:** schema stub; headlines only when campaign title clearly is the lockup.

## Outputs regenerated

- `best-ads.json` (pretty-printed)
- `best-ads.csv` (v2 columns)
- `best-ads.md` (cards with new sections)
- `SCHEMA.md` / `schema.json` (v2)
- `ANNOTATION-NOTES.md` (this file)
