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

## Process profile tuning (A1 mini specific)

Selected mode: `balanced/speed`

After adding `process/0.20mm Standard @Creality PETG CR-PETG.json`, the main print process overrides are:

| Process setting | Base (A1 mini standard) | Current | Why this was changed |
|---|---:|---:|---|
| Initial layer speed | 50 mm/s | 30 mm/s | Still conservative for PETG adhesion, but faster than the quality-first preset. |
| Initial layer infill speed | 105 mm/s | 45 mm/s | Reduces first-layer overload while recovering print time. |
| Initial layer print height | 0.20 mm | 0.22 mm | Adds slight PETG clearance without the full slowdown of 0.24 mm. |
| Initial layer acceleration | 500 mm/s^2 | 500 mm/s^2 | Kept conservative for stable first-layer deposition. |
| Outer wall speed | 200 mm/s | 90 mm/s | Preserves visible-wall quality while reducing total print time. |
| Inner wall speed | 300 mm/s | 170 mm/s | Balanced throughput without pushing PETG flow too hard. |
| Internal solid infill speed | 250 mm/s | 160 mm/s | Faster solid fill while staying in a safer PETG range. |
| Sparse infill speed | 270 mm/s | 220 mm/s | Improves speed but remains less aggressive than default A1 mini values. |
| Top surface speed | 200 mm/s | 70 mm/s | Keeps top quality acceptable with less time penalty. |
| Bridge speed | 50 mm/s | 30 mm/s | Faster than quality-first while still PETG-safe for most bridges. |
| Default acceleration | 6000 mm/s^2 | 5500 mm/s^2 | Near-stock motion for speed, with a small quality margin. |
| Outer wall acceleration | 5000 mm/s^2 | 3000 mm/s^2 | Faster than quality-first but still helps limit wall artifacts. |

These process changes are intentionally balanced between reliability and print time. If needed, tune in small steps (+10 to +20 mm/s on inner/sparse first) while monitoring first layer behavior, bridges, and top surfaces.

## References used

- Reddit Creality PETG community thread: https://www.reddit.com/r/Creality/comments/1d9ld0x/creality_petg/
- Community profile examples and discussions for CR-PETG temperature/speed:
  - https://forum.creality.com/t/creality-print-5-1-and-petg-no-profiles/12224
  - https://forum.creality.com/t/extruder-jamming-printing-cr-petg/41051
  - https://forum.creality.com/t/nozzle-snot-with-petg/36211
  - https://forum.creality.com/t/cr-petg-on-k1-max-print-speed/36393
  - https://www.reddit.com/r/BambuLab/comments/1k6qghd/printing_creality_hyper_petg_with_bambu_lab_a1/
- General PETG guidance (typical nozzle/bed/fan ranges):
  - https://store.creality.com/blog/creality-filament-printing-settings
  - https://www.crealityexperts.com/printing-with-petg-tips-tricks
  - https://bambulab.com/en-us/filament/petg-hf
