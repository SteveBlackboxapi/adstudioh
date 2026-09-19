# AdStudioh Explore — static prototype

Self-contained clickable Explore UI reading the best-ads catalog and reference boards (Cosmos density × Reve actionability).

## Open it

**Recommended — local static server**

From this folder:

```bash
cd /path/to/adstudioh-refs/explore/prototype
python3 -m http.server 8765
```

Then open [http://127.0.0.1:8765/](http://127.0.0.1:8765/).

Or from the parent `explore/` folder (also fine):

```bash
cd /path/to/adstudioh-refs/explore
python3 -m http.server 8765
```

Then open [http://127.0.0.1:8765/prototype/](http://127.0.0.1:8765/prototype/).

**File open**

You can open `index.html` directly in a browser. Data loads from `data.js` (bundled snapshot), so no CORS issues.

## Data

| Path | Role |
|---|---|
| `data/best-ads.json` | Catalog snapshot (copy of `../../best-ads/best-ads.json`) |
| `data/reference-boards.json` | Boards snapshot (copy of `../reference-boards.json`) |
| `data/explore-config.json` | Chip rails + feed config (copy of `../explore-config.json`) |
| `data.js` | Same three files bundled as `window.ADSTUDIOH_DATA` for offline / `file://` |

Refresh copies after editing upstream JSON:

```bash
cd explore/prototype
cp ../../best-ads/best-ads.json data/
cp ../reference-boards.json data/
cp ../explore-config.json data/
python3 -c "
import json
from pathlib import Path
root = Path('data')
bundle = {
  'bestAds': json.loads((root/'best-ads.json').read_text()),
  'boards': json.loads((root/'reference-boards.json').read_text()),
  'config': {k:v for k,v in json.loads((root/'explore-config.json').read_text()).items() if k != 'reference_boards'},
}
Path('data.js').write_text('window.ADSTUDIOH_DATA = ' + json.dumps(bundle, ensure_ascii=False) + ';\n')
print('refreshed')
```

## UI map

- **Style bar** — items with `style_bar === true`, else anything on a reference board
- **Library** — full catalog + search (title / brand / agency / tags)
- **Boards** — grid of `@handles`; open a board for filtered cards
- Sticky chip rails (job · medium · era · format · awareness · movement) — multi-select, client-side AND across rails
- Card → detail drawer (Esc to close): credits, why iconic, style notes, dissection keys, links, board membership

Guest-friendly — no login. en-GB chrome. Optional catalog fields (`style_bar`, `format`, `awareness_primary`, `dissection`, …) are safe when missing.
