# UP Travle

A browser-based district-chain puzzle game, inspired by [Travle](https://travle.earth/), built around Indian district maps. You are given a start and an end district and must guess a chain of neighbouring districts that connects them, using as few guesses as possible.

The whole game is a single self-contained HTML file: no build step, no server, no dependencies to install.

## Play

Open `up-travle.html` in any modern browser.

## Maps

| Map | Districts |
| --- | --- |
| Uttar Pradesh | 75 |
| Punjab | 22 |
| Jammu & Kashmir (full claimed territory) | 22 |

Maps are switched from the config modal using the map picker.

## Features

- Route puzzles between a start and end district on the selected map
- Win condition based on the shortest possible path length (any valid shortest chain wins, not one specific stored path)
- Guess districts by name, including common alternate names (e.g. Allahabad for Prayagraj)
- Guess districts by RTO code (e.g. `UP70`); optional "RTO Suggestions" toggle shows matching codes in autocomplete
- Reveal Solution animation that highlights the route on the map step by step
- Manual route entry and a New Route button in the config modal
- Editorial, magazine-style dark theme (Playfair Display, Lora, Outfit, IBM Plex Mono)

## How it works

- Map boundaries are SVG paths derived from 2011 census district geometry, embedded in the HTML file.
- Adjacency between districts drives all game logic. False neighbours caused by districts touching only at a corner were removed by checking shared boundary length.
- The state outline is decorative only and does not affect gameplay.
- Among equally short routes, the generated solution is the straightest one between start and end.
- Punjab uses the 2011 census baseline, so Malerkotla (created in 2021) is not a separate district.

## Known issues

- Some J&K district connections are not always recognised by the game. A concrete example (start, end and the district that was rejected) is needed to track this down.

## Ideas for later

- Daily puzzle mode with a date-seeded route
- Stats and streak tracking in localStorage
- Mobile layout refinement
- Difficulty presets as named buttons
- Wordle-style shareable results card

## Related

A separate game, Terrain Travle (a physiographic region and soil quiz for UP), is developed alongside this one and is not part of this repository yet.
