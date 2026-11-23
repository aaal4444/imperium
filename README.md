# Imperium

A daily guess-the-empire game. Start with when it reigned; reveal clues for fewer points.

- `index.html`: the whole game
- `empires.csv`: the archive, one row per empire

## Adding empires
Add rows to `empires.csv` with the next `batch` number (batch 1 = launch set, 2 = kingdoms batch, 3 = next).
Don't rename or delete existing rows once the daily is live; that shifts later days in the same batch.
`aliases` and `modern_places` are `;`-separated. Negative years are BCE. `approx_dates` = yes adds "c.".

## Hosting
Must be served from a web server (GitHub Pages works). Opening index.html straight from disk can't load the CSV.
