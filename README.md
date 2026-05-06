# Perchwise

![Perchwise: Four region presets, tuned to target species.](./hero.jpg)

**Parametric bird feeder. Tune by species and region.**

A KCL parametric model for 3D-printed bird feeders, with geometric selectivity tuned to target specific bird species while excluding unwanted visitors. Fork the file, set a region preset, and print.

## Features

- **Four region presets**: Eastern US Songbirds, UK Garden Birds, Pacific Northwest, Australian Honeyeaters
- **Five geometric parameters**: Port diameter, perch length, perch angle, roof overhang, port height from base — each tuned to bird anatomy and behavior
- **Parametric source**: One KCL model, four distinct feeder geometries. Change a preset object, regenerate
- **Removable roof and cleanout plug**: Print separate parts for easy assembly, refilling, and maintenance
- **Species guide**: Interactive HTML reference with data tables, selectivity methodology, and tuning guidance

## Getting Started

1. **Choose or customize a region preset** in `feeder.kcl`:

   ```kcl
   regionPreset = easternUsSongbirds  // or ukGardenBirds, pacificNorthwest, australianHoneyeaters
   ```

2. **Generate the 3D model** in your KCL modeler

3. **Export STL files** for the three parts:
   - Tube body (fillable seed reservoir with ports)
   - Roof assembly (removable cap with friction-fit lip and hanging hook)
   - Cleanout plug (removable bottom plug for draining seed and debris)

4. **3D print** each part in your preferred filament

5. **Observe and iterate** — tune parameters based on what birds actually visit your yard

## Documentation

### Interactive Species Guide

Browse the live reference at **[perchwise.github.io](https://atlantice.github.io/perchwise/)** — preset values, species tables, selectivity methodology, and exclusion thresholds.

### Markdown Guide

Read **[SPECIES_GUIDE.md](./SPECIES_GUIDE.md)** for the full selectivity framework — how to design for a species not listed, how each parameter maps to bird anatomy, and field-validated ranges.

### Parametric Source

Edit **[feeder.kcl](./feeder.kcl)** directly — the region presets are simple objects you can fork and customize:

```kcl
customPreset = {
  portDiameter = 32,
  perchLength = 20,
  perchAngleDeg = -12,
  numPorts = 4,
  roofOverhang = 20,
  portHeightFromBase = 40
}
```

## Region Presets

| Region         | Target Species                              | Excludes                      | Signature Move                               |
| -------------- | ------------------------------------------- | ----------------------------- | -------------------------------------------- |
| **Eastern US** | Chickadees, titmice, nuthatches, finches    | Grackles, starlings, sparrows | Downward-angled perches for inverted feeders |
| **UK**         | Tits, robins, goldfinches, chaffinches      | Starlings, magpies, pigeons   | Level perches for upright feeders            |
| **Pacific NW** | Chestnut-backed chickadee, nuthatch, siskin | Sparrows, starlings           | No perches — clinging access only            |
| **Australia**  | Honeyeaters, silvereye                      | Mynas, sparrows               | Wider ports for long slender beaks           |

## Design Notes

- These are **starting points**, not final calibrations. Geometric selectivity is statistical, not absolute.
- **Juveniles are smaller** than adults of the same species and may pass through openings rated for adults. This is a property of geometric exclusion, not a design flaw.
- **Tune based on observation** — if unwanted species visit, tighten the exclusion parameters. If target species struggle to access, widen the ports or adjust perch geometry.
- The **tube height and diameter** are also tunable if you want different seed capacity or proportions. See `feeder.kcl` for all exposed parameters.

## Contributing

Found a region that works well in your area? Contributions are welcome:

1. Fork the repository
2. Add your preset to `feeder.kcl` (e.g., `myRegionPreset = { ... }`)
3. Add a row to the region table in `SPECIES_GUIDE.md` and `README.md`
4. Test and observe for at least two weeks
5. Open a pull request with your region name, target species, and any tuning notes

## License

This project is licensed under the **[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/)** — you are free to use, modify, and distribute this work, provided you give credit and share your improvements under the same license.

Parametric source code (`feeder.kcl`) is provided as-is for personal and commercial use.

## Credits

- **Methodology** based on cage-mesh selectivity research and ornithological field guides
- **Species data** from Cornell Lab of Ornithology, British Trust for Ornithology, Birdlife Australia, and regional bird checklists
- **Design** by [Your Name/Studio] — parametric model in KCL
- **Renders** by [Artist/Tool] — showing region presets and target species

---

**Questions?** Check the [Species Guide](./SPECIES_GUIDE.md), open an [issue](https://github.com/atlantice/perchwise/issues), or start a [discussion](https://github.com/atlantice/perchwise/discussions).

**Want to contribute a region?** See [CONTRIBUTING.md](./CONTRIBUTING.md) (if you add one).
