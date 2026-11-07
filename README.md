# CNC plasma table (JD's Garage Gen 2.0)

A CNC plasma table built from [JD's Garage Gen 2.0 plans](https://jdsgarage.bigcartel.com/product/cnc-plasma-cutter-plans), built together by DW and Stefan.
Once it works, it becomes the maker space's steel-cutting machine; the hub's `plasma-cut` skill covers designing parts for it.

| | |
|---|---|
| Status | planning: plans not yet bought |
| Cutting area | 28 × 32 in (711 × 812 mm) |
| Frame | 2 × 2 in steel tube (imperial build) or 50 × 50 mm (metric) |
| Controller | ESP32, open-source firmware (the plans cover flashing it) |
| Axes | X/Y; Z optional; optional rotary axis for tube notching |
| Torch | **low-frequency, blowback-start** plasma cutter, ideally with a CNC port (no HF start: it wrecks the electronics) |
| Budget | about $400-550 for the machine (JD's estimate) + $50-75 control box + the plasma cutter |

Specs are from the product page and FAQ (read 2026-11-07); the plans are the authority.

## The plans: not in this repo
The plans are a paid, online-only package (a Google-Drive-style link that JD keeps current). It has 3D drawings of the metal parts,
STLs for the printed parts, a linked BOM, wiring, grounding and EMI notes, and assembly instructions.
No licence is published for them, so **don't commit them, or files from them, to git**: `plans/` is ignored.
See [plans/README.md](plans/README.md) for what goes there locally.

## Layout
| Path | What |
|---|---|
| `bom.csv` | our purchase tracker: transcribe from the plans' BOM, then fill in status, who's buying and cost |
| `decisions.md` | choices to make before buying, with the options |
| `safety.md` | read before the first cut: fire, fumes, electrical, air |
| `build-log.md` | dated notes, photos, problems and fixes |
| `parts/` | **our own** designs for the table (SolidCraft, built with the hub): control box, cable mounts, torch adapters… |
| `plans/` | local only, git-ignored: the plans, their STLs, our print/cut notes on them |

## Working with the hub
This repo lives inside the maker hub so `parts/` can use its tools:
```sh
git clone git@github.com:weaties/maker-hub.git ~/src/solidcraft
cd ~/src/solidcraft && tools/update-solidcraft.sh
git clone git@github.com:weaties/plasma-cutter.git projects/plasma-cutter
```
New part: `cp -R ~/src/solidcraft/templates/part parts/<slug>` (IDs `PC-001`…); see the hub's `new-part` skill.

## Phases
| # | Phase | Owner | Done |
|---|---|---|---|
| 1 | Decide build options (`decisions.md`) and buy the plans | | ☐ |
| 2 | Transcribe the BOM into `bom.csv`, split purchasing | | ☐ |
| 3 | Print the plans' 3D parts (Bambu, PETG/ASA, see `plans/README.md`) | DW | ☐ |
| 4 | Plates: buy JD's pre-cut set ($95-100) or cut them | | ☐ |
| 5 | Cut and weld/bolt the frame (1-2 days with parts on hand) | | ☐ |
| 6 | Electronics: control box, ESP32 firmware, limit switches, grounding (½ day) | | ☐ |
| 7 | Square the gantry, calibrate steps/mm, air-cut a test file | | ☐ |
| 8 | Water table / fume extraction / fire kit (`safety.md`) before the first live cut | | ☐ |
| 9 | First cuts: kerf test, cut chart for our cutter and material | | ☐ |

Fill in Owner and tick ☐ → ☑ as you go; consider GitHub issues per phase once it's busy.

## Links
- Build video playlist: https://www.youtube.com/watch?v=lhejn2-bwxc&list=PLWACT6mAqAyVz0Aqc3zoBX9DPsVudicCc
- Recommended plasma cutters: https://jdsgarage.bigcartel.com/recommended-plasma-cutters
- FAQ: https://jdsgarage.bigcartel.com/frequently-asked-question
- Facebook group: https://www.facebook.com/groups/jdsgarage/
