# Imperium

Where and when? A daily history puzzle on an old explorer's chart.

- `index.html`: the whole game
- `empires.csv`: the archive, one row per entry
- `map.json`: the world map (Natural Earth country shapes, simplified)
- `territories.json`: each realm's borders near its greatest extent, from Cliopatria
  (Seshat Global History Databank, CC BY 4.0), simplified

## Adding entries
Add rows to `empires.csv` with the next `batch` number. Don't rename or delete rows once the daily is live.
`aliases`, `modern_places` and `map_places` are `;`-separated. Negative years are BCE. `approx_dates` = yes adds "c.".
`map_capital` is the single city the capital pin marks. New entries without a match in `territories.json`
fall back to washing the modern countries in `map_places` (or `modern_places`).

## Hosting
Serve the four files together from a web server (GitHub Pages works).
