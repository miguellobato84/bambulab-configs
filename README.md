# 467121856

## Creality CR-PETG tuning (A1 mini 0.4 nozzle)

This profile started from a generic PETG preset and was adjusted for Creality CR-PETG behavior.

| Setting | Previous | Current | Expected outcome (plain language) |
|---|---:|---:|---|
| Nozzle temperature | 255 C | 245 C | Reduces stringing and blobs while keeping good layer bonding. |
| Initial layer nozzle temperature | 255 C | 250 C | Helps the first layer stick better without overheating the whole print. |
| Nozzle range | 220-270 C | 230-260 C | Narrows to a more realistic window for this filament, making tuning easier. |
| Bed temperature (all plate types, normal + first layer) | 70 C | 80 C | Improves bed adhesion and lowers corner lifting/warping risk. |
| Fan minimum speed | 40% | 30% | Keeps layers warmer so parts are less brittle. |
| Fan maximum speed | 90% | 60% | Prevents over-cooling, improving layer-to-layer bonding. |
| Overhang fan speed | 90% | 70% | Better balance between detail on overhangs and layer strength. |
| Fan off for first X layers | 3 | 4 | First layers fuse better to the bed and to each other. |
| Flow ratio | 0.95 | 0.98 | Reduces under-extrusion (small gaps/weak walls). |
| Max volumetric speed | 8 mm^3/s | 10 mm^3/s | Slightly faster prints while staying conservative for reliability. |
| Filament notes | empty | Added drying + calibration guidance | Reminds users of the most common PETG quality issue (moisture). |

## Why this should help

PETG often fails from three causes: too much cooling, moisture in the spool, and under-extrusion. These changes specifically target those points, so beginners should see:

- better first-layer stick
- fewer strings and blobs
- stronger walls/layers
- fewer random surface defects caused by wet filament

## References used

- Reddit Creality PETG community thread: https://www.reddit.com/r/Creality/comments/1d9ld0x/creality_petg/
- Community profile examples and discussions for CR-PETG temperature/speed:
  - https://forum.creality.com/t/creality-print-5-1-and-petg-no-profiles/12224
  - https://www.reddit.com/r/BambuLab/comments/1k6qghd/printing_creality_hyper_petg_with_bambu_lab_a1/
- General PETG guidance (typical nozzle/bed/fan ranges):
  - https://store.creality.com/blog/creality-filament-printing-settings
  - https://www.crealityexperts.com/printing-with-petg-tips-tricks
