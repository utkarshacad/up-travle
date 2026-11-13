# Terrain Travle

A geography-learning spin-off of [UP Travle](../README.md). Instead of chaining districts
together, each round asks you to identify every district belonging to one of Uttar Pradesh's
seven physiographic regions — and along the way you get real facts about the districts you
guess right, and a reference legend for the state's soil types and regions.

The whole game is a single self-contained HTML file: no build step, no server, no dependencies
to install.

## Play

Open `index.html` in any modern browser, or play it online at
https://utkarshacad.github.io/up-travle/terrain-travle/

## How to play

1. **Read the prompt.** At the top of the side panel you'll see a region name and a short
   blurb — for example, *"Which districts belong to: Central Ganga Plain (Awadh)?"*
2. **Guess districts.** You can:
   - Click districts directly on the map, or
   - Type a district name into the text box and press **Enter** to add it (common alternate
     spellings like "Allahabad" for "Prayagraj" are recognised).
   There's no limit on how many guesses you can make before submitting.
3. **Check facts as you go.** Clicking any district shows a short fact about it at the top of
   the side panel. Clicking a different district swaps the fact shown — it doesn't stack up.
4. **Submit.** Press **Enter** on an empty input box, or click **Submit Guesses**, once you're
   done selecting.
5. **See your results.**
   - Districts you got right turn gold-bordered and show their true region color.
   - Districts you missed show up in the true region color with a plain border, so you can see
     what you missed.
   - Districts you guessed wrong turn grey.
   - Everything outside the asked region stays hidden, so the map doesn't give away other
     regions' shapes.
6. **Next region.** Click **Next Region** (or press Enter again) to get a new, randomly picked
   region to identify. Click **Reveal Solution** at any point if you're stuck and want the
   target region highlighted for you.

## Reference tools

- **Legend** — below the map, a two-column key shows all six soil-type textures and all seven
  region colors used on the map, so you can cross-reference while you play.
- **Reveal Full Map** — the button next to Reset switches the entire map into a true-color,
  fully-textured reference view (every district, every region, all at once), independent of
  whatever round is in progress. Click it again (or start/reset a round) to go back to normal
  play.

## How it works

- Built on the same SVG district geometry as UP Travle, with each district rendered as a pair
  of stacked paths: a region-colored base shape and a semi-transparent soil-texture overlay.
- Seven physiographic regions (Bhabar-Tarai, Tarai, Upper Ganga Plain, Central Ganga Plain /
  Awadh, Eastern Ganga Plain / Purvanchal, Bundelkhand Plateau, Vindhyan Region) and six soil
  types (Bhabar, Tarai, Bangar/Older Alluvium, Khadar/Newer Alluvium, Black & Red, Red &
  Yellow) are mapped to all 75 UP districts.
- District facts (history, culture, GI-tagged crafts, notable people, recent news) are shown
  on click, written in an editorial, magazine-style tone to match the rest of the game's look.
- Data is scaffolded to support additional state maps later (`TERRAIN_MAPS`), though only
  Uttar Pradesh has data right now.

## Known simplifications

- Region and soil-type boundaries are drawn at district-dominant level — a whole district is
  assigned to the region/soil type that covers most of its area, not split at sub-district
  precision.
- Boundaries are simplified from 2011 census district geometry, same as the main game.

## Ideas for later

- A second round mode to guess UP's 18 administrative divisions instead of physiographic
  regions (data for this has already been drafted, just not wired in yet).
- Additional state maps once their region/soil data is researched.

## Related

The main chain-guessing game, UP Travle, lives at the [repository root](../README.md).
