# Imperium

Where and when? A daily history game on an old explorer's chart.

Every day brings five rounds, scored out of 500. Most rounds are **realms** (empires, kingdoms, states); most days one round is a **moment** (a battle, a voyage, a turning point). Each round starts with only *when*. Break wax seals for more clues, at a lower prize, and beat the 40-second clock. Practice offers unlimited single rounds and a 10-round run scored out of 1,000.

Play: https://aaal4444.github.io/imperium/

## Files

| File | What it is |
|---|---|
| `index.html` | The whole game: map, clues, daily schedule, saves, sound effects |
| `empires.csv` | The archive, one row per realm or moment |
| `map.json` | The world map (Natural Earth country shapes, simplified) |
| `territories.json` | Each realm's borders near its greatest extent, from Cliopatria (Seshat Global History Databank, CC BY 4.0), simplified |
| `music.mp3` | Background music loop |
| `manifest.webmanifest` | Lets phones add the game to the home screen |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon-32.png` | The wax-seal icon in the sizes browsers and phones ask for |
| `og.jpg` | The image shown when the link is shared |

## The archive (`empires.csv`)

One row per entry. `kind` is `empire` for a realm or `moment` for an event.

- `aliases`, `modern_places` and `map_places` are `;`-separated. Negative years are BCE. `approx_dates` = `y` adds "c.".
- `continent` sets the region the daily balances: Asia, Europe, Africa, the Americas (including Arctic) or Oceania. When a realm spans two, the first one listed counts.
- `difficulty` is 1 (easy), 2 (medium) or 3 (hard).
- `map_capital`, `capital_lat` and `capital_lon` place the pin: the capital for a realm, the exact spot for a moment.
- The clue columns are shared. For a moment, `territory` is the region, `language_faith` is who took part, `fact` is what came of it, `capital` is where exactly, and `ruler` is the key figure.
- A realm with no match in `territories.json` washes the modern countries in `map_places` (or `modern_places`) instead, or a named zone circle defined in `index.html`.

### Adding entries without changing past days

The daily is worked out from the archive, so new rows must not reshuffle days people have already played:

1. Add rows at the end with the next `batch` number.
2. Set `available_from` to a date in the future (YYYY-MM-DD). The row joins the daily from that day on, and every earlier day stays exactly the same.
3. Don't rename or delete rows once they have appeared in a daily.

## Hosting

Serve all the files together from a web server. GitHub Pages works as is.
