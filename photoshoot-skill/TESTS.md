# Test log

## Status — 2026-11-20
| | |
|---|---|
| Version | v4 |
| Coverage | All 12 RETOUCH garments × Casual + High-Fashion (24 sets, 240 images, all Pass) |
| First-try pass | 25/30 yield test, 47/50 full run, 140/140 on the last 7 garments |
| Cost | 2.75 credits per image (10 images per board = 27.5) |
| Output | Drive "SHER PHOTOSHOOT SKILL - OUTPUT", one folder per garment with Casual/ and High-Fashion/. Sheet tab PHOTOSHOOT rows 3–306 |

### Still to test
- A face-hold line for close and sunset shots (face drift was the main Borderline cause).
- Casual Low still reads only mildly low on some shots.
- A run with Inspiration.

## A/B test — 2026-11-16

2026-11-16. Four shots, two garments (Cocoa Quinn Midi Dress × Claire, Beige Julia Mini Dress × Kristy), both boards. 18 images, 42.5 credits. None blocked, none sideways. Sheets are in `tests/`.

| Way | Garment | Face | Cost per image |
|---|---|---|---|
| A. Soul 2.0 with her Soul ID, then swap in GPT Image 2.6 | Right in 4 of 4 | Drifted from Kristy in 2 of 4 | about 3.75 |
| **B1. One pass, GPT Image 2.6** | Right in 4 of 4 | Right in 4 of 4 | 2.75 |
| B2. One pass, Nano Banana Pro | Wrong in 2 of 4 (neckline, length) | Right in 3 of 4 | 2 |

B1 was picked. Not tested yet: a back-view shot, a third garment, and a run with Inspiration.

A single front shot (the garment's Element in Higgs) gave the same garment as the five shots on two front-facing images. Back views were not tried with it.

## Run1 — first full batch

2026-11-16. Peony Valen Maxi Dress × Kristy, Casual, 10 images plus 3 remakes: 13 images, 35.75 credits. None blocked, none sideways. The garment held in all 13.

| | Count | Rows |
|---|---|---|
| Pass on the first try | 4 of 10 | 001, 002, 003, 007 |
| Borderline on the first try (face a little off) | 2 of 10 | 005, 008 |
| Fail on the first try | 4 of 10 | 004 face, 006 pose, 009 brand logo, 010 pose |
| Pass after one remake | 2 | 006, 010 |
| Borderline after one remake | 1 | 009 |
| Still to remake | 1 | 004 |

What it changed in this file:

- **Pose "Low" and Camera "Low" were read as nothing.** 006 and 010 came back standing. The options now say what they are. The Pose fix worked on both remakes. The Camera fix did not: 010 is still not shot from low, and 007 never was.
- **A bag came back with a real brand's logo** (009). "No logos or brand marks on props." is now in `<Don't>`, and it held on the remake.
- **Faces drift most on Close and Low cameras in hard sun or after dark** (004, 005, 008, 009). Run2 tried the fix that worked in RETOUCH.

## Run2 — the same ten shots, with her face close-up as a second reference

2026-11-16. Same garment, Character, Board and mixes as Run1, with the prompt as it stands after Run1. 10 images, 27.5 credits, no remakes. None blocked, none sideways. The garment held in all 10.

| | Run1, first try | Run2, first try |
|---|---|---|
| Pass | 4 | 7 |
| Borderline | 2 | 3 (003 and 008 face, 010 camera) |
| Fail | 4 | 0 |

- **The face close-up is now a standard Reference.** The four faces that drifted in Run1 came back as Kristy or close to her. Faces were judged by eye from crops next to her sheet.
- The Low pose held on both rows, and no logos came back. Those two come from the prompt changes after Run1, not from the face close-up.
- The Low camera worked on 004 and 007 and not on 010.
- Ten images are too few to call this a yield. The next runs measure it on 80.

Kristy's and Claire's face close-ups are already uploaded to Higgs.

## Yield study — v2 (2026-11-17)

Prompt frozen as it stands after Run2. First try only, no remakes. Plan: 80 images over 8 batches (2 Boards × 4 garments). Run2 counts as the first batch.

| Run | Garment × Character | Board | Pass | Borderline | Fail |
|---|---|---|---|---|---|
| Run2 | Peony Valen Maxi Dress × Kristy | Casual | 7 | 3 | 0 |
| Run3 | Cocoa Quinn Midi Dress × Claire | Casual | 8 | 2 | 0 |
| Run4 | White Julia Mini Dress × Claire | Casual | 4 | 4 | 2 |
| **So far** | | | **19 of 30** | **9** | **2** |

- None of the 30 was blocked or sideways. The garment held in all 30, and no face failed. Run4's faces were checked at sheet size, not cropped.
- **The Low camera** is the main borderline reason: it came out at eye level in 4 of 8 tries.
- **A mini dress with Sitting or Low** is the only reason for a Fail. In Run4, 5 of the 6 rows that sat, knelt or were shot from low came back with the hem riding too high, and in 2 the camera looks up it. The Mix rule only kept short garments away from a low camera. It is not enough.

## Yield study — v3 (2026-11-19)

v3 = v2 plus the short-garment rule (Standing or Leaning only, Eye level or Close only on Casual; lean, mid-stride or symmetry and no Low angle on High-Fashion). Target: 80% first-try Pass over 30 images, both Boards.

| Run | Garment × Character | Board | Pass | Borderline | Fail |
|---|---|---|---|---|---|
| Run6 | Beige Julia Mini Dress × Kristy | Casual | 9 | 1 | 0 |
| Run7 | Cocoa Quinn Midi Dress × Claire | High-Fashion | 7 | 3 | 0 |
| Run8 | White Julia Mini Dress × Claire | High-Fashion | 6 | 4 | 0 |
| **v3 total** | | | **22 of 30 (73%)** | **8** | **0** |

- No Fail, no block, nothing sideways. The garment held in all 30 and no mini hem rode up: the short-garment rule works.
- 6 of the 8 Borderlines are the camera. **True profile came out in 0 of 5 tries** (3/4 or frontal instead). Very tight crop missed once in 4.
- One of those was a planning error: True profile paired with Rigid frontal symmetry, which cannot both happen.
- 2 Borderlines are face drift (Run6-004, Run7-005).
- v4 changes only the camera option text (True profile, Very tight crop) and bans the profile + symmetry pair.

## Yield study — v4 (2026-11-19) — target reached

v4 = v3 plus the reworded True profile and Very tight crop options, and no True profile with Rigid frontal symmetry. Casual is unchanged from v3.

| Run | Garment × Character | Board | Pass | Borderline | Fail |
|---|---|---|---|---|---|
| Run9 | Peony Valen Maxi Dress × Kristy | High-Fashion | 8 | 2 | 0 |
| Run10 | Beige Julia Mini Dress × Kristy | High-Fashion | 9 | 1 | 0 |
| Run11 | Cocoa Quinn Midi Dress × Claire | Casual | 8 | 2 | 0 |
| **v4 total** | | | **25 of 30 (83%)** | **5** | **0** |

- True profile now works 6 of 6, Very tight crop 6 of 6.
- No Fail, no block, nothing sideways. The garment held in all 30.
- What is left: face drift in 4 of 30 (the face comes out older or heavier, mostly in close or sunset shots), and the Casual Low camera missed once in 3.
- Cost: 2.75 credits an image, so about 3.3 credits per first-try Pass.

## Full set on v4 (2026-11-19)

All five garments on both Boards. The 50 new images (Run12–16) gave 47 Pass (94%), 3 Borderline (face drift), 0 Fail. Output is in Drive, folder "SHER PHOTOSHOOT SKILL - OUTPUT", one folder per garment.

**Remakes (same day).** The 12 Borderlines across all sets were rerun with the same plan. Round 1: 12 images, 9 Pass (33 credits). Round 2: the last 3, all Pass (8.25 credits). Two of them were Casual Low shots where the camera stayed at eye level; the longer Low wording above fixed both, so it is now the Casual Low option. Every set is now 10/10 Pass, and the Drive files carry no `_Borderline` suffix.


## Remakes — 2026-11-19
The 12 Borderlines were rerun: round 1, 9 of 12 Pass (33 credits); round 2, the last 3 Pass (8.25 credits). Two were Casual Low shots that stayed at eye level; the longer Low line now in SKILL.md fixed both. Every set 10/10.

## The 7 missing RETOUCH garments — 2026-11-20
Runs 17–30, 140 images, 385 credits, 140/140 Pass first try.

| Garment | Character | Casual | High-Fashion |
|---|---|---|---|
| Sienna Maxi Dress | Claire | Run17 | Run18 |
| Midnight Valen Maxi Dress | Kristy | Run19 | Run20 |
| Beige Valen Maxi Dress | Claire | Run21 | Run22 |
| Blue Julia Mini Dress | Kristy | Run23 | Run24 |
| Blush Iva Mini Dress | Kristy | Run25 | Run26 |
| Gold Clara Set | Claire | Run27 | Run28 |
| Camo Lunar Set | Claire | Run29 | Run30 |

Character follows the RETOUCH file name. Camo Lunar Set has no Front-3/4 shot, so its slots are FF, Side-Full, 3/4-Side, Back, CU, and the Input lines name Image 4 "PRODUCT SIDE, FULL" and Image 5 "PRODUCT 3/4 SIDE".
