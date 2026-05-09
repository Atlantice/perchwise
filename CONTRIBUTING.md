# Contributing a preset

Perchwise ships with four region presets — Eastern US Songbirds, UK Garden Birds, Pacific Northwest, and Australian Honeyeaters. Adding more regions is the most useful contribution you can make to this project right now.

This document covers preset proposals only. For bug reports, geometry suggestions, KCL changes, or anything else, please [open an issue](https://github.com/atlantice/perchwise/issues) instead.

## What a preset is

A preset is a tuned set of six parameters that tells the parametric KCL model what feeder geometry to produce for a specific group of target species in a specific region. It's not a finished product — it's a set of starting values, derived from species body measurements and feeding behaviour, that someone can fork and field-tune in their own yard.

Each preset answers two questions:

1. **Which birds do I want to feed?** (the _target_ species list)
2. **Which birds do I want to exclude?** (the _exclusion_ list)

The parameter values are then chosen so the resulting feeder is geometrically permissive of the targets and geometrically restrictive of the exclusions.

## What to include in a proposal

Open an issue using the **"New preset"** template (or, if the template hasn't loaded, include the sections below manually). A complete proposal has:

### Region

A short, geographically meaningful name. "Eastern US Songbirds," "UK Garden Birds," and "Pacific Northwest" are good models — they're specific enough to be useful, general enough to cover a coherent set of species. Avoid presets that are too narrow ("My backyard in Tucson") or too broad ("All of Africa").

### Target species

A list of 4–10 bird species you want the preset to permit. Include common name and scientific name. Cite a source for each species' relevant body measurements — typically:

- head/bill width
- body mass
- typical perching posture
- foraging behaviour at feeders (clinging, hanging, perched, hovering)

Acceptable sources include Cornell Lab All About Birds, BTO Bird Facts, Birdlife Australia, HANZAB, regional ornithological atlases, and peer-reviewed literature. Anecdotal observations are useful supporting context but shouldn't be the only basis.

### Exclusion species

A list of 2–6 species you want the preset to _exclude_, with the same body measurements and source citations. The exclusion list is what makes the preset interesting — geometric selectivity only matters if there's something being selected against.

### Parameter values

Six numbers, with brief reasoning for each:

| Parameter            | Unit    | What it controls                                         |
| -------------------- | ------- | -------------------------------------------------------- |
| `portDiameter`       | mm      | The opening size that gates head/body access             |
| `perchLength`        | mm      | How much landing surface is provided (0 = no perch)      |
| `perchAngleDeg`      | degrees | Perch tilt; negative = downward, favouring hanging birds |
| `numPorts`           | count   | How many feeding stations around the cylinder            |
| `roofOverhang`       | mm      | Weather protection and approach geometry                 |
| `portHeightFromBase` | mm      | Vertical placement on the cylinder                       |

For each value, briefly explain _why_ you chose it. "Port diameter set at 22mm to admit chickadees (~15mm head width) while excluding house sparrows (~22–25mm head width)" is the right level of detail.

### Validation notes (optional but encouraged)

If you've actually built and tested a feeder with these parameters, include observation notes: which targets visited, which exclusions tried and failed, how long the trial ran, what season, what climate. Field-validated presets are the most valuable, even if the validation is informal.

## What I'm looking for

- **Geographic and ecological coherence.** The targets should plausibly co-occur and share enough behavioural traits that a single feeder geometry is meaningful for them.
- **A real exclusion problem.** "I want to feed every bird in my area" doesn't need geometric selectivity. Strong presets exist because the contributor has a specific bird they're trying to keep out.
- **Sourced measurements.** Numbers without citations get sent back for sources. This is a reference document; values need to be verifiable.
- **Honest framing.** Don't oversell. "Tested for two weeks in summer with 8 chickadee visits and 4 sparrow rejections" is more useful than "works perfectly."

## What gets accepted

I review proposals as time allows and accept the ones that meet the bar above. Accepted presets are added to the KCL model, the species guide page, and the regional GLTF exports. You'll be credited in the commit and in the species guide source notes.

If a proposal needs work, I'll comment with what's missing rather than closing the issue. Most rejections are for missing source citations or for region scopes that are too narrow to generalise.

## Questions

For anything not covered here, [open an issue](https://github.com/atlantice/perchwise/issues) and tag it `question`.
