# Photoshoot SKILL — checkpoint

Saved 2026-11-16 18:50, updated 2026-11-19 (Bangkok). Read this first when picking the work back up.

## Update 2026-11-19 — v3 yield

Rows: Run6 57–66, Run7 67–76, Run8 77–86 in PHOTOSHOOT. Next free row: 87.

| Run | Garment × Character | Board | Pass | Borderline | Fail |
|---|---|---|---|---|---|
| Run6 | Beige Julia Mini × Kristy | Casual | 9 | 1 | 0 |
| Run7 | Cocoa Quinn Midi × Claire | High-Fashion | 7 | 3 | 0 |
| Run8 | White Julia Mini × Claire | High-Fashion | 6 | 4 | 0 |
| v3 total | 30 images | 22 (73%) | 8 | 0 |

Target 80% not reached. Main cause: True profile camera ignored 5 of 5. v4 rewords True profile and Very tight crop and bans profile + frontal symmetry. Next: 30 images on v4. Spent on v3: 82.5 credits.

## Update 2026-11-19 — v4 yield: target reached

Rows: Run9 87–96, Run10 97–106, Run11 107–116. Next free row: 117.

| Run | Garment × Character | Board | Pass | Borderline | Fail |
|---|---|---|---|---|---|
| Run9 | Peony Valen Maxi × Kristy | High-Fashion | 8 | 2 | 0 |
| Run10 | Beige Julia Mini × Kristy | High-Fashion | 9 | 1 | 0 |
| Run11 | Cocoa Quinn Midi × Claire | Casual | 8 | 2 | 0 |
| v4 total | 30 images | 25 (83%) | 5 | 0 |

v4 is the version to use. Study spend today: 165 credits (v3 82.5 + v4 82.5). Credits left: 2,751.
Open: face drift 4 of 30; Casual Low camera 1 miss in 3. Pink Clara upload still half done.

## Update 2026-11-19 — full set on v4

Every garment now has both boards on v4 (or its Casual equivalent). Rows: Run12–16 117–166. Next free row: 167.

| Garment × Character | Casual | High-Fashion |
|---|---|---|
| Peony Valen Maxi × Kristy | Run2 7/10 (Casual = v4 for a maxi) | Run9 8/10 |
| Cocoa Quinn Midi × Claire | Run11 8/10 | Run12 10/10 |
| White Julia Mini × Claire | Run14 10/10 | Run13 9/10 |
| Beige Julia Mini × Kristy | Run6 9/10 | Run10 9/10 |
| Pink Clara Set × Kristy | Run15 9/10 | Run16 9/10 |

New today on v4: 50 images, 47 Pass (94%), 3 Borderline (all face drift), 0 Fail. 137.5 credits. Credits left: 2,613.
Pink Clara Higgs ids: FF 8c5aaeba-888c-4ef4-be91-a750d6e2310e, F34 75fa258f-b2a2-4649-91b6-4ed5a1493996, Side bb509ce9-1a28-47b0-8815-af46e128078d, Back 16f188c0-13cb-4979-abe6-ae1ce2e4691a, CU c68ec8b5-f1f7-49fc-86ae-995267cdaaac.
Drive output: "SHER PHOTOSHOOT SKILL - OUTPUT" (id 1Qe3QefkpATCW7u6vwClzv2hTQE0dY88X), one folder per garment, 20 PNGs each, named <Garment>_<Character>_<Board>_<NN>[_Borderline].png. Uploaded through Claude in Chrome (fetch from the Higgs CDN, then a synthetic drop onto the Drive folder), because the Drive connector caps a call at about 3 MB.
Optional: remake the 12 Borderlines across all sets once (33 credits) so every set has 10 Pass.

## Where it stands

- **Skill**: `business/SKILL-photoshoot.md`, v0.1. One pass on Higgs GPT Image 2.6 (Sunburst), high, 2k, 3:4, with seven References: character sheet, face close-up, five `_BG` garment shots.
- **Sheet**: prompt sheet `1Nm6SlnYxADAhz7KFNeiTh60WWHM9AfkSx_5iu417UYk`, tab `PHOTOSHOOT`. Rows 3–6 Test, 7–16 Run1, 17–26 Run2, 27–36 Run3, 37–46 Run4. Next free row: 47. Prompt template v2 is in cell N1; the Prompt column is a formula on it.
- **Credits**: 2,971 left. Spent so far on this skill: about 161.

## Yield study v2 (superseded by v3/v4 above)

Prompt frozen after Run2. First try only, no remakes. Board Casual so far.

| Run | Garment × Character | Pass | Borderline | Fail |
|---|---|---|---|---|
| Run2 | Peony Valen Maxi Dress × Kristy | 7 | 3 | 0 |
| Run3 | Cocoa Quinn Midi Dress × Claire | 8 | 2 | 0 |
| Run4 | White Julia Mini Dress × Claire | 4 | 4 | 2 |
| Total | 30 images | 19 | 9 | 2 |

Open findings:

1. **Mini dress with Sitting or Low** is the only cause of a Fail (Run4-006, Run4-009), and of three Borderlines.
2. **The Low camera** comes out at eye level about half the time (4 of 8).

## Next

- The study is done; v4 is the version to use.
- Optional: try a stronger Casual Low-camera line and a face-hold line for close and sunset shots (the 4 face drifts).

## Pink Clara Set × Kristy — uploaded (done 2026-11-19)

The five `_BG` files are in Drive (folder `Pink-Clara-Set`, id `1_Q1ObW59eQ3e-hA_LJk931NDXDtCyjp1`) and not in recent Higgs history. Getting them into Higgs works through Claude in Chrome: open any drive.google.com page, then in page JavaScript fetch `https://lh3.googleusercontent.com/d/<fileId>=s0` with credentials and PUT the blob to a Higgs upload URL (headers `Content-Type: image/png`, `If-None-Match: *`), then `media_confirm`.

| Angle | Drive file id | Higgs media id | State |
|---|---|---|---|
| Front-Full | 1reM5X77I949Qx2OL9X6NJAxZgSX8e9qg | 8c5aaeba-888c-4ef4-be91-a750d6e2310e | Uploaded and confirmed |
| Front-3-4 | 1CB_h9ka8vW4A7x_H9cXDgYzi1fXLPLzR | — | To do |
| 3-4-Side | 1vGE33X71SFAkDh9PEOpyyKvOBPgqA04T | — | To do |
| Back | 1AooRDfN4FAgUUzTqFFE6z9KkIsaNMSdO | — | To do |
| Close-up | 1YYtWtFPYCUPyPwLVO-Qo9G_gaFm9PNXS | — | To do |

The four upload URLs made on 2026-11-16 were not used. Ask Higgs for new ones with `media_upload`.

## Reference ids in Higgs

Characters:

| | Sheet (media id) | Face close-up (media id) |
|---|---|---|
| Claire | 60e60b89-e7f4-48a7-9493-0c05732bef69 | 150f85ef-c4fe-419f-b8d5-292f71ca1345 |
| Kristy | 85f045cf-fd53-44e5-8ee0-6e0457546418 | 069bb8d4-1a91-4857-b557-b41b2b7a0d6d |

Garments (job ids of the BG SWAP outputs):

| Garment × Character | Front-Full | Front-3-4 | 3-4-Side | Back | Close-up |
|---|---|---|---|---|---|
| Cocoa Quinn Midi × Claire | 2cebac39-c16c-4323-aed9-5c33be4916f1 | b203e180-ec85-4525-b096-662f60d59159 | fafbef97-ed3b-4837-af3b-85ce3c0005db | eb3b693a-05a7-4e65-8d49-675065329698 | 3ad642f1-9fd1-4490-a4f3-516f4ca898af |
| White Julia Mini × Claire | c741b1df-d1d5-4391-8831-b275dc8aafcd | ed905a7c-7c57-4730-988d-23c898bfda81 | 3c5ccca4-7f88-41a9-869f-61ce9ae20246 | ec91b9c3-f4e8-42cc-8d4c-ff49c8804693 | 57ed008b-0de0-480c-8304-cc6a2f895949 |
| Beige Julia Mini × Kristy | f558dd8c-ae12-4b0c-9730-432777a92b95 | 1d7e6802-3a9c-49b4-af0c-710eebc61dff | bd2bc87d-bd71-4606-a04b-97b24f603147 | 36449072-b182-4b0b-82b5-525a3fe67492 | 7c2eb550-1ed2-4d49-86b9-47079ab70082 |
| Peony Valen Maxi × Kristy | 6d152497-a5fd-4fa1-ba59-ac14dd8289af | bfeddc94-d6b9-4c4d-a716-7fb4a1f3ca79 | 645babdb-b9b9-4190-b029-38b8c54858d8 | 9639e8a8-60fc-492a-a4a2-8edd57733ba6 | 79d220ee-89d2-48fc-b28d-88f65d092483 |

Also in Higgs history, not used yet: Blue Julia Mini × Kristy (five Nano Banana jobs, 2026-11-11 17:18 UTC) and a beige satin halter maxi × Claire (2026-11-11 17:00 UTC, name not confirmed).

## Locations used so far on Casual

Run1 and Run2: 1, 8, 14, 15, 18, 21, 22, 24, 27, 31. Run3: 2, 5, 10, 13, 16, 17, 20, 23, 26, 33. Run4: 3, 7, 11, 13, 16, 19, 23, 25, 29, 32. Not used yet: 4, 6, 9, 12, 28, 30.

## Open items for Pat

- Camera and Pose are picked by the skill, so three Runbook lines that let the model choose are gone.
- Size is 3:4, not auto.
- Garment source is the five `_BG` shots, not the single garment Element on the REF tab.
