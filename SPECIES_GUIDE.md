# Species Selection Guide

A reference for tuning the parametric bird feeder to your target species.

The model exposes geometry as parameters — port diameter, perch length, perch angle, roof overhang, and port height from base. This document explains how those parameters map to bird anatomy and behavior, so you can fork the file, set a region preset, and confidently invite the species you want while excluding the ones you don't.

These are starting values based on published body measurements and field-tested cage-mesh selectivity research. They are not field-validated calibrations. Tune based on observed visitors in your yard.

---

## Methodology

Geometric selectivity rests on five primary levers. Understanding what each one does makes it easy to design for species not listed here.

**Port diameter** tracks beak-plus-head width. Too small and the target bird can't reach in; too large and unwanted species gain access. The exclusion threshold matters more than the target — set the diameter just below the head width of the smallest unwanted species.

**Perch length** tracks body length and feeding stance. Short perches (10–18 mm) support feet only and favor small clingy birds; long perches (30+ mm) let larger birds settle their full body weight and feed comfortably. If your target is a chickadee, you want a perch a chickadee can grip but a grackle can't balance on.

**Perch angle** is the most underused selectivity tool in commercial feeders. Level perches (0°) accept most species. Downward-angled perches (−10° to −20°) favor birds that naturally feed inverted — chickadees, nuthatches, titmice — and physically exclude grackles, starlings, and most blackbirds, which cannot stabilize while inverted. Vertical or absent perches (90° / no perch) favor woodpeckers and clinging species only.

**Roof overhang** has two functions. It keeps seed dry, which matters for both bird health and feeder maintenance. It also prevents larger hover-capable birds from approaching ports from above. A roof overhang roughly 1.5× the perch projection blocks most aerial approach angles.

**Port height from base** determines where ports sit vertically on the cylinder. Higher placement (50 mm+) suits clinging species that approach from above; lower placement (35 mm) suits perched feeders reaching in from the side. This parameter is less commonly tuned but worth setting if you're optimizing for a specific bird's natural approach angle.

Geometric exclusion is statistical, not absolute. Juvenile birds are smaller than adults and may pass through openings rated for adults of the same species. Treat these values as starting points, observe what actually visits, and adjust.

---

## Eastern US Songbirds

Target species: black-capped and Carolina chickadees, tufted titmouse, white-breasted nuthatch, American goldfinch, house finch, downy woodpecker (with vertical variant).

Excluding: house sparrow, European starling, common grackle, brown-headed cowbird.

| Species                 | Body Mass (g) | Body Length (cm) | Feeding Posture   | Port Ø (mm) | Perch Length (mm) | Perch Angle (°) | Notes                                                   |
| ----------------------- | ------------- | ---------------- | ----------------- | ----------- | ----------------- | --------------- | ------------------------------------------------------- |
| Black-capped Chickadee  | 11            | 13               | Inverted-capable  | 28–32       | 14–18             | −10 to −15      | Hero species for downward-perch design                  |
| Tufted Titmouse         | 21            | 16               | Upright, agile    | 30–32       | 16–20             | −5 to −10       | Slightly larger than chickadee, similar handling        |
| White-breasted Nuthatch | 20            | 14               | Head-down clinger | 28–32       | 12 (or none)      | −15 to vertical | Often feeds without perching at all                     |
| American Goldfinch      | 13            | 12               | Cling and upright | 25–30       | 14                | 0 to −10        | Use nyjer-port variant (2–3 mm slot) for goldfinch-only |
| House Finch             | 21            | 14               | Upright           | 30–32       | 18                | 0               | Will accept most small-port designs                     |
| Downy Woodpecker        | 27            | 16               | Vertical clinger  | n/a (suet)  | none — tail prop  | vertical        | Use suet-cake variant; not a seed-port species          |

**Recommended preset starting values:**
`portDiameter = 30`, `perchLength = 22`, `perchAngleDeg = -15`, `numPorts = 4`, `roofOverhang = 18`, `portHeightFromBase = 35`

Source: Cornell Lab All About Birds species accounts; body measurements cross-checked with Sibley.

---

## UK Garden Birds

Target species: blue tit, great tit, coal tit, European robin, goldfinch, chaffinch, dunnock, greenfinch.

Excluding: starling (introduced and invasive in some contexts), feral pigeon, magpie, gray squirrel.

| Species        | Body Mass (g) | Body Length (cm) | Feeding Posture         | Port Ø (mm) | Perch Length (mm) | Perch Angle (°) | Notes                                          |
| -------------- | ------------- | ---------------- | ----------------------- | ----------- | ----------------- | --------------- | ---------------------------------------------- |
| Blue Tit       | 11            | 12               | Inverted-capable        | 28–32       | 14–18             | −10 to −15      | UK equivalent of chickadee for design purposes |
| Great Tit      | 18            | 14               | Inverted-capable        | 30–34       | 18–22             | −5 to −10       | Larger than blue tit, handles wider ports      |
| Coal Tit       | 9             | 11               | Inverted-capable        | 26–30       | 14                | −10 to −15      | Smallest of the regulars                       |
| European Robin | 18            | 14               | Upright                 | 30–34       | 22                | 0               | Prefers level perches; ground-feeder leaning   |
| Goldfinch      | 16            | 13               | Cling and upright       | 26–30       | 14                | 0 to −5         | Nyjer-port variant works well                  |
| Chaffinch      | 24            | 15               | Upright                 | 32–34       | 22–25             | 0               | Larger; needs slightly more perch              |
| Dunnock        | 21            | 14               | Upright, ground-leaning | 32          | 22                | 0               | Prefers low feeders or platforms               |
| Greenfinch     | 28            | 15               | Upright                 | 32–34       | 22                | 0               | Robust bird; handles standard tube feeders     |

**Recommended preset starting values:**
`portDiameter = 32`, `perchLength = 22`, `perchAngleDeg = 0`, `numPorts = 4`, `roofOverhang = 22`, `portHeightFromBase = 35`

Source: BTO (British Trust for Ornithology) Bird Facts; RSPB species guides.

---

## Pacific Northwest

Target species: chestnut-backed chickadee, red-breasted nuthatch, pine siskin, Anna's hummingbird (nectar variant), dark-eyed junco, Steller's jay (size-permitting variant).

Excluding: house sparrow, European starling, brown-headed cowbird.

This region's signature design move is **no perches at all** — chestnut-backed chickadees and red-breasted nuthatches prefer to cling and feed inverted, and removing perches entirely is one of the cleanest exclusion mechanisms for sparrows and starlings, which need a perching surface. Ports are also smaller and raised higher on the cylinder to suit clinging approach.

| Species                   | Body Mass (g) | Body Length (cm) | Feeding Posture   | Port Ø (mm)       | Perch Length (mm) | Perch Angle (°) | Notes                                                |
| ------------------------- | ------------- | ---------------- | ----------------- | ----------------- | ----------------- | --------------- | ---------------------------------------------------- |
| Chestnut-backed Chickadee | 9             | 12               | Inverted-capable  | 22                | 0                 | n/a             | No-perch design; clings to port edge                 |
| Red-breasted Nuthatch     | 10            | 11               | Head-down clinger | 22                | 0                 | n/a             | Will use port without any perch                      |
| Pine Siskin               | 14            | 12               | Cling and upright | 22                | 0                 | n/a             | Mixed flocks with goldfinches                        |
| Dark-eyed Junco           | 19            | 15               | Ground-leaning    | n/a               | platform          | 0               | Platform feeder variant; not a tube-port species     |
| Anna's Hummingbird        | 4             | 10               | Hovering          | 8 mm × 30 mm tube | n/a               | n/a             | Nectar-port variant; entirely separate parameter set |

**Recommended preset starting values:**
`portDiameter = 22`, `perchLength = 0`, `perchAngleDeg = 0`, `numPorts = 3`, `roofOverhang = 15`, `portHeightFromBase = 50`

Source: Cornell Lab All About Birds; Burke Museum bird checklists.

---

## Australian Honeyeaters

Target species: New Holland honeyeater, eastern spinebill, white-plumed honeyeater, brown honeyeater, silvereye.

Excluding: common myna (highly invasive), house sparrow, European starling, noisy miner (native but highly aggressive — controversial to exclude; user's call).

Honeyeaters have **longer slender beaks** adapted for nectar feeding, which calls for wider ports than you'd use elsewhere. The current preset uses a 38 mm round port — large enough for a New Holland honeyeater's beak-and-head reach, with longer perches to support the bird's larger body.

| Species                 | Body Mass (g) | Body Length (cm) | Beak Length (mm) | Port Shape | Port Ø / Dim (mm) | Perch Length (mm) | Notes                                          |
| ----------------------- | ------------- | ---------------- | ---------------- | ---------- | ----------------- | ----------------- | ---------------------------------------------- |
| New Holland Honeyeater  | 20            | 18               | 22               | Round      | 38                | 25                | Common at feeders; bold                        |
| Eastern Spinebill       | 11            | 15               | 30               | Round      | 38                | 25                | Long curved beak; larger port helps            |
| White-plumed Honeyeater | 19            | 17               | 18               | Round      | 38                | 25                | Common in southeastern AU                      |
| Brown Honeyeater        | 11            | 13               | 16               | Round      | 38                | 25                | Smaller, more cautious                         |
| Silvereye               | 10            | 12               | 9                | Round      | 38                | 25                | Not a true honeyeater but co-occurs at feeders |

**Recommended preset starting values:**
`portDiameter = 38`, `perchLength = 25`, `perchAngleDeg = 0`, `numPorts = 3`, `roofOverhang = 28`, `portHeightFromBase = 35`

A nectar-feeder variant is also worth building for this region — vertical tube with small ports near the base, holds a sugar-water solution rather than seed. Different parameter set entirely; treat as a sibling design.

Source: Birdlife Australia; CSIRO bird measurements; HANZAB (Handbook of Australian, New Zealand and Antarctic Birds) where accessible.

---

## Exclusion Reference

If you know what you want to _exclude_, work backward from these thresholds.

| Unwanted Species     | Body Mass (g) | Head Width (approx, mm) | Set Port Ø Below                                               | Set Perch Length Below | Set Perch Angle Below               | Other Notes                                                                     |
| -------------------- | ------------- | ----------------------- | -------------------------------------------------------------- | ---------------------- | ----------------------------------- | ------------------------------------------------------------------------------- |
| House Sparrow        | 28            | 18                      | — (port size alone won't exclude; combine with perch geometry) | 18 mm                  | —                                   | Sparrows can use most ports; exclusion comes from perch geometry and seed type  |
| European Starling    | 75–90         | 28                      | 32 mm                                                          | 22 mm                  | −5° (cannot feed inverted reliably) | Cage-mesh field testing supports ~28 mm gap as effective adult-starling barrier |
| Common Grackle       | 115           | 32                      | 34 mm                                                          | 25 mm                  | −5°                                 | Long tail destabilizes them on short or angled perches                          |
| Brown-headed Cowbird | 44            | 22                      | 30 mm                                                          | 20 mm                  | 0°                                  | Often follows other flocking birds; perch length matters                        |
| Common Myna (AU)     | 110           | 30                      | 32 mm                                                          | 22 mm                  | 0°                                  | Highly invasive; exclude aggressively where present                             |
| Feral Pigeon         | 350           | 35                      | — (size alone excludes from any tube feeder)                   | —                      | —                                   | Tube feeders inherently exclude pigeons; no special tuning needed               |

**Caveat:** Juveniles are smaller than adults of the same species. A port rated to exclude adult starlings may admit juveniles for the few weeks they're at fledgling size. This is not a design flaw — it's a property of geometric exclusion that any honest birder will recognize.

---

## Designing for a Species Not Listed

The methodology generalizes. To add a new target species:

1. Look up body mass, body length, and beak length in Cornell Birds of the World, your regional ornithological handbook, or a peer-reviewed source. Avoid Wikipedia-only numbers for design decisions; cross-check at least one source.
2. Estimate head width as roughly 60–70% of body width at the shoulders, or use direct measurements where available.
3. Set port diameter to head width + 4–6 mm clearance for comfortable head insertion, _unless_ a smaller unwanted species shares your area, in which case set port diameter just below that species' head width.
4. Set perch length to roughly 1.0–1.3× the foot-to-shoulder distance — long enough to grip, short enough that the bird's body weight doesn't fully settle.
5. Set perch angle based on feeding posture: 0° for upright feeders, −10° to −15° for inverted-capable species, vertical or no perch for clingers.
6. Set roof overhang to roughly 1.5× perch projection, or larger in high-rainfall regions.
7. Print, install, observe for two weeks, iterate.

If you build a region preset that works well in your area, contribute it back. Fork the KCL file, add your preset object, document your target species in this guide, and open a pull request.

---

## Sources and Further Reading

- Cornell Lab of Ornithology, _All About Birds_ — species accounts with body measurements
- British Trust for Ornithology (BTO), _Bird Facts_ — UK species data
- Birdlife Australia — Australian species data and conservation status
- HANZAB (Handbook of Australian, New Zealand and Antarctic Birds) — comprehensive AU/NZ reference where accessible
- Project FeederWatch (Cornell) — field data on species at feeders, useful for understanding actual visitor patterns
- _Sibley Guide to Birds_ — standard field reference for North American measurements

For exclusion research specifically, search for cage-mesh selectivity studies and "starling-proof feeder" field testing. Commercial selective-feeder manufacturers publish some exclusion data; treat their numbers as marketing-tuned but directionally correct.
