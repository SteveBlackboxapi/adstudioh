# AdStudioh Best Ads — import schema (v2)

Cosmos-inspired card format for the Elements / Explore lane: every entry is one legendary ad/campaign with credits, links, and JEV/Reve/Explore axes.

Inspired by **Cosmos** (density/taste), **Reve** (actionable detail + reference boards), and **JEV** (format × awareness).

## Core fields (v1)
| Field | Type | Notes |
|---|---|---|
| id | string | slug, e.g. `apple-1984` |
| title | string | Campaign / spot name |
| brand | string | Advertiser |
| product | string\|null | Product or line |
| year | int\|null | Launch year |
| country | string\|null | Primary market |
| medium | string[] | TV, print, OOH, digital, experiential, film, social |
| agency | string\|null | Lead agency |
| agency_network | string\|null | Network / holding if useful |
| creatives | {name, role}[] | CD, writer, AD, director, photographer, etc. |
| production_company | string\|null | |
| music | string\|null | |
| awards | string[] | Notable awards |
| tags | string[] | Era, style, mood for filtering |
| style_notes | string | One-line art-direction / style-bar note |
| why_iconic | string | 1–2 sentences |
| links.primary | url | Best single page |
| links.case_study | url\|null | Agency/brand case |
| links.video | url\|null | Watch |
| links.archive | url\|null | Award/museum |
| links.wikipedia | url\|null | |
| links.image_ref | url\|null | Page that shows the creative |
| sources | url[] | Verification sources |

## Explore / JEV / Reve extensions (v2)
| Field | Type | Notes |
|---|---|---|
| style_bar | bool | Curated Style bar feed (`true` ≈ 35–45 craft heroes) |
| source | enum | Provenance of `links.primary`: `award_archive` \| `brand` \| `museum` \| `agency` \| `publication` \| `wikipedia` \| `other` |
| format | enum | JEV format axis — see allowed values below |
| awareness_primary | enum | Dominant Eugene Schwartz stage |
| awareness_mix | object | Soft mix `{unaware, problem, solution, product, most}` floats summing ≈ 1.0 |
| dissection | object | Advertising layers stub (Reve Soleil equivalent). Keys: `headline`, `super`, `product`, `talent`, `setting`, `logo`, `end_card`, `vo` — values string\|null |
| boards | string[] | Reference board ids from `explore/reference-boards.json` (e.g. `board-apple-restraint`) |
| thumbnail | string\|null | Local/cached thumb path; null until assets are pulled |

### format (allowed)
`Static image` · `UGC testimonial` · `Talking head` · `Product demo` · `Cinematic film` · `Print poster` · `OOH` · `Mashup / compilation` · `Interactive / digital` · `Identity / logo` · `Other`

### awareness_primary (allowed)
`Unaware` · `Problem aware` · `Solution aware` · `Product aware` · `Most aware`

### awareness_mix
Soft distribution preferred over a hard single bucket. Peak on `awareness_primary`; remainder distributed to adjacent stages. Keys are lowercase short names: `unaware`, `problem`, `solution`, `product`, `most`.

### dissection
Empty/null fields are OK at v1 — fill over time. Prefer null over invented copy. Only set `headline` when the campaign title clearly *is* the headline lockup.

### style_bar
Hand-picked craft heroes for the default Explore feed. Prefer strong agency + named creatives + clear `why_iconic`. Board membership alone does not force `style_bar: true`.

### source inference (heuristic)
| Domain pattern | source |
|---|---|
| lovethework / dandad / clios / oneclub / luerzers / adsoftheworld | award_archive |
| wikipedia.org | wikipedia |
| si.edu / moma / cooperhewitt / vam.ac.uk | museum |
| wk.com / ddb / bbdo / ogilvy / tbwa / agency sites | agency |
| brand.com (apple, nike, ibm, …) | brand |
| adage / adweek / campaign / guardian / wwd / … | publication |
| else | other |

## Files
- `best-ads.json` — canonical array for import
- `best-ads.csv` — spreadsheet-friendly flatten (includes v2 columns)
- `best-ads.md` — human-readable cards
- `ANNOTATION-NOTES.md` — annotation pass stats
- `../explore/reference-boards.json` — board membership source of truth
- `../explore/ADSTUDIOH-EXPLORE-SPEC.md` — product spec
