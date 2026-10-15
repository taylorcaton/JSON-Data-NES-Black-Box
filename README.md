# Sample JSON data - NES Black Box edition

## WORK IN PROGRESS

Sample JSON data to use with your projects: the original Nintendo Entertainment System "black box" games, in [`NES-Blackbox-Games.json`](NES-Blackbox-Games.json).

30 of the 33 games are black box titles. Kid Icarus, Metroid and Rad Racer are included as well, but flagged `"blackBox": false` (they came in silver boxes).

Sample Array Object

```json
{
  "name": "Donkey Kong",
  "blackBox": true,
  "released": {
    "US": "6-1-1986",
    "JPN": "7-15-1983",
    "EUR": "10-15-1986"
  },
  "releasedPrecision": "month",
  "developers": ["Nintendo R&D2"],
  "publishers": ["Nintendo"],
  "series": "Arcade Classics",
  "players": {
    "min": 1,
    "max": 2,
    "mode": "alternating"
  },
  "copy": {
    "description": "Donkey Kong was a port of the 1981 arcade game of the same name, hailed at the time as the most popular video game.",
    "story": "As the story goes, an escaped ape known as Donkey Kong has kidnapped a woman named Pauline, and takes her to a construction site. With Pauline's boyfriend, Mario, in pursuit after she yells in help for him, Donkey Kong uses his surroundings to try to stop Mario from saving his girlfriend. Along the way, Mario also finds tools and items of which can help him on his journey upwards."
  }
}
```

## Fields

| Field | Type | Meaning |
|---|---|---|
| `name` | string | The name as printed on the box, e.g. `"Super Mario Bros."`. |
| `blackBox` | boolean | `true` for the black box titles; `false` for Kid Icarus, Metroid and Rad Racer. |
| `released` | object | Release dates for `US`, `JPN` and `EUR` (see the date convention below). |
| `releasedPrecision` | `"day"` or `"month"` | How precise the **US** date is. |
| `releasedPrecisionEUR` | `"year"` (optional) | How precise the **EUR** date is. Omitted when the EUR date is exact or unknown. |
| `confidence` | `"likely"` or `"disputed"` (optional) | Present only when the US date is debated: `"likely"` means the date follows the weight of the sources, `"disputed"` that reliable sources disagree. |
| `developers`, `publishers` | string array | |
| `series` | string | The series named on the box banner, e.g. `"Arcade Classics"` for "ARCADE CLASSICS SERIES". |
| `players` | object | `{ "min", "max", "mode"?, "note"? }`, for example `{ "min": 1, "max": 2, "mode": "versus" }`. |
| `copy` | object | `description`, and `story` for some games. |

### Dates

- Dates are `"M-D-YYYY"` strings with no zero padding, e.g. `"10-18-1985"`, `"6-1-1986"`.
- An empty string, `""`, means the date is unknown.
- When only the month of the US release is known, the date is the 1st of that month and `releasedPrecision` is `"month"`. For example, Donkey Kong's `"6-1-1986"` means June 1986.
- When only the year of the EUR release is known, the date is January 1 of that year and `releasedPrecisionEUR` is `"year"`. For example, Urban Champion's EUR `"1-1-1986"` means 1986.

### Players

- `min` and `max` are the number of players.
- `mode` says how a two-player game plays: `"versus"`, `"simultaneous"` (together, at the same time), `"alternating"` (taking turns), `"cooperative"` (on the same side) or `"special"` (explained in `note`). Single-player games have no `mode`.
- `note` explains anything unusual, such as Duck Hunt's second player flying the duck in Game A.

Games included:

```text
10-Yard Fight
Balloon Fight
Baseball
Clu Clu Land
Donkey Kong
Donkey Kong 3
Donkey Kong Jr.
Donkey Kong Jr. Math
Duck Hunt
Excitebike
Golf
Gumshoe
Gyromite
Hogan’s Alley
Ice Climber
Kid Icarus (not a black box game)
Kung Fu
Mach Rider
Mario Bros.
Metroid (not a black box game)
Pinball
Popeye
Pro Wrestling
Rad Racer (not a black box game)
Slalom
Soccer
Stack-Up
Super Mario Bros.
Tennis
Urban Champion
Volleyball
Wild Gunman
Wrecking Crew
```

## Sources

Release dates, names, player counts and box details were checked against:

- Wikipedia, [Nintendo Entertainment System](https://en.wikipedia.org/wiki/Nintendo_Entertainment_System)
- Wikipedia, [List of Nintendo Entertainment System games](https://en.wikipedia.org/wiki/List_of_Nintendo_Entertainment_System_games)
- Each game's own Wikipedia article (infobox release dates and modes)
- Video Game Gem Vault, [Piecing together the history of Nintendo games: clues to use when dating and authenticating NES box games and cartridges](https://www.videogamegemvault.com/blogs/video-game-gem-vault-blog/piecing-together-the-history-of-nintendo-games-clues-to-use-when-dating-authenticating-nes-box-games-cartridges)
- The Legend of NES, [Black Box Games](https://www.thelegendofnes.com/black-box-games)
- Racketboy, [Collecting NES Black Box Sprite Art Games](https://racketboy.com/retro/collecting-nes-black-box-sprite-art-games)
- NES Wiki (Fandom), [Nintendo Entertainment System Launch Titles](https://nes.fandom.com/wiki/Nintendo_Entertainment_System_Launch_Titles)
- The Stack-Up instruction manual, [NESWorld](https://www.nesworld.com/manuals/rob/stackup.htm)
- StrategyWiki, [Gyromite](https://strategywiki.org/wiki/Gyromite)
- The series labels on physical boxes
