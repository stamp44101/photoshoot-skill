---
name: photoshoot
description: "Turn a retouched garment into on-location photos of the same character wearing it. Takes the five RETOUCH shots of a garment, mixes Location, Light, Palette, Camera and Pose evenly, and makes each image in one pass on Higgs GPT Image 2.6. Covers two boards: Lifestyle Casual and Lifestyle High-Fashion. Given Inspiration, rewrites the options to match it first. Adds each image to the PHOTOSHOOT tab."
---

# Photoshoot

Turn the five RETOUCH shots of a garment into photos of the same character wearing it on location, one per row.

Based on Runbook F.Weave, step 3 (Generate 'Product + Location'). Claude runs it on Higgs. Nothing is pasted into Figma Weave.

## Run in Chat

With no CLAUDE.md, hand your work back in chat: read the inputs that are here, ask for any required one that's missing, then give back every new file and edit, and say which file each belongs in.

## Inputs

Ask for everything missing in one message, and say what you will assume for anything left unanswered.

- **Garment** — the five RETOUCH shots of one garment on one Character, after BG SWAP (the `_BG` files): Front-Full, Front-3-4, 3-4-Side, Back, Close-up
- **Character** — the Character in those shots. Never a different one
- **Board** — Lifestyle Casual or Lifestyle High-Fashion
- **The prompt sheet** — a Google Sheet shared with edit access. Its PHOTOSHOOT tab holds every past run. When that tab has rows, read Iteration first
- **[Optional] Count** — how many images. With none, make 10
- **[Optional] Inspiration** — the Instagram account the Character's photos draw from

## Workflow

### 1. Read the Inspiration

Skip this step when there is none.

Open the account in Claude in Chrome. The built-in browser isn't signed in to Instagram. Read the photos fresh each run.

Rewrite the options of each Variable on the Board to match what the photos show, where possible, in the same shape as the ones they replace. The prompts stay as they are.

### 2. Mix the options

Give each image one option from each Variable on its Board: Location, Light, Palette, Camera, Pose.

- Use each option about as often as the others.
- Spread the Locations across their groups first (Hotel, Suite, Pool and so on): no group comes up twice in a run until every group on the Board has come up once. Inside a group, pick the place used least so far.
- Never give two images the same mix.
- Never mix options that cannot happen together, like indoor daylight on a beach.
- In a short skirt or dress, never mix Sitting or Low with a low camera looking up.

### 3. Find the References

Seven images, in this order.

1. The Character's sheet: the image of her Element in Higgs (`show_reference_elements`).
2. Her face, close up: the top-left panel of her sheet, cropped (x 0 to 29.8%, y 0 to 44.5%) and uploaded to Higgs once. Use the same upload on every run.
3. Front-Full
4. Front-3-4
5. 3-4-Side
6. Back
7. Close-up

The five garment shots are already in Higgs as the BG SWAP outputs (`show_generations`, model Nano Banana, five in a row). Look at them to tell the garment and the angle, and pass their job IDs. When they are not there, upload the `_BG` files from the Drive folder SHER RETOUCH SKILL - OUTPUT.

### 4. Write the prompts

Take the Board's prompt from Project Inputs. Put each option from step 2 on the first line of its block. Change nothing else.

### 5. Make the images

Send each prompt to Higgs GPT Image 2.6 (Sunburst), at high quality, 2k, 3:4, with the seven References. One image per prompt. Tell the person the credit cost before the run.

When an image is blocked by the safety filter:

1. Send it again once.
2. Still blocked: send the same prompt and References to Nano Banana Pro at 2k, 3:4, and check its garment twice as hard.
3. Still blocked: change the Camera or Pose option to one that shows less, and say so in chat.

### 6. Check every image

Open each image next to Front-Full, and crop her face next to the close-up on her sheet. A small preview hides face drift. Make it again when any of these is true.

- The garment is not the garment: its neckline, trim, length, colour or fabric changed.
- Her face or hair is not the Character's.
- A body is broken: hands, limbs, proportions.
- The frame is sideways.
- It does not show its Camera and Pose.
- Someone near her can be recognized, or shares her face.
- A prop carries a real brand's logo.

Make an image again at most twice. Then leave the row's Preview blank and say why in chat.

## Output

Add the rows to the PHOTOSHOOT tab. Put each value under the column with the same name. Leave every other column as it is. When there is no PHOTOSHOOT tab, create it with the columns below. Never change the other tabs.

| Column | What goes in |
|---|---|
| ID | The run and its row number, like Run3-001. The run counts on from the last run in the tab |
| Character | The run's Character, as @ and its Element name in Higgs |
| Garment | The garment's name, as its RETOUCH folder is named |
| Board | Casual or High-Fashion |
| Location, Light, Palette, Camera, Pose | The option picked for each |
| Prompt | The prompt from step 4 |
| Preview | The image, shown in the cell from its Higgs image URL: `=IMAGE("<url>")` |
| QA | Pass, Borderline or Fail, with the reason and how many times it was made again |

When step 1 ran, also give the new options in chat, in the same shape as the ones in Project Inputs.

## Iteration

The sheet is the memory. Each run adds to it.

When the PHOTOSHOOT tab has rows, read this section before the workflow.

- **Read the tab.** Count its options with this run's: favor the ones used least so far, and never write a mix that is already there for the same Garment.
- **Nothing is overwritten.** New rows go below the old ones.
- **To change a prompt, run Fixer SKILL** against a run that went wrong. Do not hand-edit a prompt in this file.

---

## Project Inputs - SHER

### Variables — Lifestyle Casual

**Location**

- Hotel — (1) the Rosewood Bangkok lobby, (2) a guest corridor, (3) the driveway and entrance, (4) the sweeping central stair at the Park Hyatt Bangkok Penthouse
- Suite — (5) a Capella Bangkok river suite, (6) its marble bathroom, (7) its dressing room, (8) its balcony over the river, (9) a Cheval Blanc St-Tropez sea room
- Rooftop Bar — (10) the Moon Bar deck at Banyan Tree Bangkok, (11) the open-air top floor at Octave, (12) the Park Hyatt Bangkok rooftop terrace
- Restaurant — (13) Penthouse Bar + Grill at the Park Hyatt Bangkok, (14) the arched courtyard side of BKK Social Club
- Pool — (15) the black-tiled pool at Amanpuri Phuket, (16) the seawater pool cut into the rock at Hôtel du Cap-Eden-Roc
- Villa — (17) an Amanpuri pool pavilion, (18) its sala, (19) its outdoor shower and sundeck
- Beach Club — (20) Scorpios Mykonos and its terraces, (21) the pine-grove cabanas at Hôtel du Cap-Eden-Roc
- Beach — (22) the private beach at Cheval Blanc St-Tropez, (23) the sand below Scorpios Mykonos
- Boat — (24) the deck of a yacht in the bay off St-Tropez, (25) its cabin, (26) the swim platform
- Car — (27) the back seat of a black sedan, (28) the driver's seat, (29) a convertible on a coast road
- Apartment — (30) the open kitchen, (31) the hall by the door, (32) the bedroom, (33) the balcony

**Camera**

- Eye level — mid-distance
- Low — the camera near the floor, looking up at her
- Close — close in

**Pose**

- Standing
- Leaning
- Sitting
- Low — crouched, kneeling or sitting close to the ground

### Variables — Lifestyle High-Fashion

**Location**

- Classical — (1) the porticos and steps at Villa La Rotonda, (2) the Hundred Fountains promenade at Villa d'Este
- Terrace — (3) the Terrace of Infinity at Villa Cimbrone, (4) the roof terrace and its stair at Casa Malaparte
- Urban — (5) the Barbican highwalks, (6) the Barbican Lakeside Terrace
- Colonnade — (7) the travertine arcade of the Palazzo della Civiltà Italiana, (8) the Canopus colonnade at Hadrian's Villa
- Pool — (9) the Canopus basin at Hadrian's Villa, (10) the horse pool at Cuadra San Cristóbal, (11) the garden pool at Villa Necchi Campiglio
- Ruin — (12) the Maritime Theatre at Hadrian's Villa, (13) the domed exedra of the Canopus
- Colonial — (14) the street verandah at Amangalla, (15) the Chequerboard terrace at the Galle Face Hotel, (16) its sea-facing verandah restaurant, (17) the verandah terrace at the Eastern & Oriental, Penang
- Garden — (18) the garden paths and pavilions at Villa Cimbrone, (19) the garden at Villa Necchi Campiglio, (20) the terraced slopes at Villa d'Este
- Minimal — (21) the travertine plaza at the Salk Institute, (22) the walled court at Cuadra San Cristóbal, (23) the red masonry block at Casa Malaparte

**Camera**

- Very tight crop — the frame cuts her at mid-thigh or higher; her head and the garment fill it
- Full body small in a large field of negative space
- Low angle looking up
- True profile — the camera at her side, square to her: head, chest and feet all point to the edge of the frame, one eye showing

True profile never goes with Rigid frontal symmetry; they cannot both happen.

**Pose**

- Extreme lean off-axis
- Folded at the waist
- Compressed and crouched
- Draped along a surface
- Caught mid-stride
- Rigid frontal symmetry

### Variables — both boards

**Light**

- Outdoor by day — hard sun.
- Outdoor at sunset — low sun from one side, the sky still bright.
- In the shade — no direct sun, light from the open side.
- After dark — the lights the location runs on, left as they are.
- Indoors by day — daylight through a window, or from the next room when there is none.

**Palette**

Pick 4 to 6 from across these.

- Warm neutral — ivory, greige, taupe, clay, grey, charcoal.
- Location's own — the colors the place already has, kept as they are: greens, sand, water.
- Materials — only the ones the location would really have: limestone · pale plaster · veined marble · travertine · terracotta tile · black tile · natural stone · gravel · concrete · glass · mirror · timber · dark stained wood · pale painted wood · woven cane · linen · velvet · leather · brass · aged bronze · blackened iron

### Prompt — Lifestyle Casual

`{Location}`, `{Light}`, `{Palette}`, `{Camera}` and `{Pose}` are the options from step 2.

```
<Role & Objective>
You are a photographer who shoots 'Modern Influencer' fashion content: real and clean enough for her social media feed. Turn the reference images into ONE photograph, shot on location, at high realism.
</Role & Objective>

<Input>
Image 1: CHARACTER — Person truth: face, hair and skin
Image 2: CHARACTER FACE — Person truth: her face, close up
Image 3: PRODUCT FRONT — Garment truth
Image 4: PRODUCT FRONT 3/4 — Garment truth
Image 5: PRODUCT SIDE — Garment truth
Image 6: PRODUCT BACK — Garment truth
Image 7: PRODUCT CLOSE-UP — Garment truth
Never deviate from Garment truths. Take nothing else from Images 3 to 7: not their background, pose or light.
</Input>

<shot — Location>
{Location}
- Shoot from any spot of the Location that will allow the light to shine on the Garment.
- Shoot from a spot where the garment will have maximum contrast with the Location's color/Palette behind it.
</shot — Location>

<shot — Light>
{Light}
- The light comes from one direction, and the shadows show it.
- This light stays where it is as the main light.
- If it is not enough to make the garment the brightest thing in the frame, add a secondary source from a smartphone flashlight at the camera side to lift it.
- If that is not enough, add a smartphone flash from the camera side: close and hard, the background dropping to dark just behind her.
- Nothing casts a shadow across the garment. Keep soft shading on folds and seams.
</shot — Light>

<shot — Palette>
{Palette}
</shot — Palette>

<shot — Camera>
{Camera}
- iPhone main camera, 24mm equivalent, deep focus — the room stays as sharp as she is.
- An upright vertical frame. She fills a good part of it.
- Slightly imperfect — a little off-centre, a limb clipped by the edge.
- A touch of motion blur from the slow indoor shutter, on one small thing that moved: a hand, a hem, a strand of hair. Her face and the garment stay sharp.
- The image is processed the way a phone processes it — shadows lifted flat, highlights clipping abruptly, edges over-sharpened, fine texture smeared where the light runs out, luminance noise sitting in the shadows. Noise, not film grain.
</shot — Camera>

<shot — Pose>
{Pose}
A shape she fell into, not one she is holding.
She may meet the lens or not.
The pose never hides the garment.
</shot — Pose>

<Do's>
- Reproduce the Product exactly as it appears in the Inputs
- The garment sits on the body with natural weight: slight creasing and fold where fabric meets the figure. It is worn, not floating.
- Add props to the character that would match the garment and Location.
- Add everyday things or people (related to the Location, making it realistic), around the edges or in the background. Everyone else is far from her and does something that makes sense in that place.
- Her skin is real skin: pores, small marks and uneven tone, with the light falling on her face as it falls on the rest of the scene.
- Where the same thing shows up more than once, make each one different in shape, size, spacing and wear.
</Do's>

<Don't>
No invented garment details
No stiff, hovering, mannequin-like fabric.
No over-smoothed skin, no distorted proportions.
No exaggerated filter or grade.
No one close enough to be recognized. No one else shares her face or hair.
No sideways or rotated frame.
No logos or brand marks on props.
</Don't>

<Output>
ONE photograph. Maximum resolution.
</Output>
```

### Prompt — Lifestyle High-Fashion

`<Role & Objective>`, `<shot — Light>`, `<shot — Camera>`, `<shot — Pose>` and `<Do's>` swap for these. Everything else is the same on both boards.

```
<Role & Objective>
You are an award-winning fashion photographer who focuses on 'High-Fashion'. Turn the reference images into ONE editorial luxury photograph: a lifestyle frame, shot on location, at high realism.
</Role & Objective>

<shot — Light>
{Light}
- The light comes from one direction, and the shadows show it.
- This light stays where it is as the main light.
- If it is not enough to make the garment the brightest thing in the frame, add a secondary source as if from a smartphone flashlight to lift it.
- Nothing casts a shadow across the garment. Keep soft shading on folds and seams.
</shot — Light>

<shot — Camera>
{Camera}
Commit to an extreme. Never eye-level, centred, mid-distance three-quarter.
An upright vertical frame.
Analogue grain and shallow depth of field where the framing calls for it.
</shot — Camera>

<shot — Pose>
{Pose}
One held shape: the body under tension, a position she is holding rather than one she has fallen into.
The garment stays fully legible in whatever shape you choose.
</shot — Pose>

<Do's>
- Reproduce the Product exactly as it appears in the Inputs
- The garment sits on the body with natural weight: slight creasing and fold where fabric meets the figure. It is worn, not floating.
- Add props to the character that would match the garment and Location.
- Her skin is real skin: pores, small marks and uneven tone, with the light falling on her face as it falls on the rest of the scene.
- Where the same thing shows up more than once, make each one different in shape, size, spacing and wear.
</Do's>
```

### Inspiration accounts

- @Hanna: instagram.com/xgyeon
- @Amii: instagram.com/johannaelisefischer
- @Kristy: instagram.com/claraalinnea
- @Claire: instagram.com/nina.sazina

---

## What changed from Runbook F.Weave step 3

- **Location is words, not an image.** `Image 1: LOCATION` is gone. Location, Light and Palette go into the prompt, with the options from the Runbook's step 1.
- **"Image 1's light" became "This light".** The Light option is the main light.
- **The Character's sheet is Image 1, and her face close-up is Image 2.** GPT Image cannot take a Soul ID, so she goes in as reference images.
- **Five garment shots instead of three.** RETOUCH makes five.
- **Camera and Pose are Variables.** Claude picks one option per image, so each is used about as often as the others. Three lines that let the model choose are gone: "Eye-level and mid-distance, or low looking up, or close in.", "Vary the level and the turn: standing, leaning, sitting, low.", and the High-Fashion "Choose one —" and "Choose freely —" lists. Their options are in Project Inputs.
- **"a little tilted" is gone**, and "An upright vertical frame." is in.
- **Size is 3:4**, not auto, so every image in a run has the same shape.
- **Model is GPT Image 2.6, not Nano Banana Pro.** Run5 tested the Weave setup (Nano Banana Pro, front/side/back only, no face references): 5 of 10 came back, faces drifted and Close/Low camera was ignored. GPT 2.6 with seven references held the garment and face far better.
- **Short garments have their own rule.** Mini dresses and sets get Standing or Leaning only, and Eye level or Close camera on Casual. On High-Fashion they get lean, mid-stride or symmetry, never Low angle. Sitting and low shots rode the hem up (Run4).
- **Two High-Fashion Camera options are spelled out.** "True profile" and "Very tight crop" say what the frame must show; as bare words the model ignored True profile 5 of 5. True profile is never paired with Rigid frontal symmetry.
- **The Don'ts gained "No logos or brand marks on props."** Run1 put a brand logo on a bag.

## Learnings

Used:

- Upright vertical frame instead of "a little tilted" (Higgs Soul 2.0 turned frames 90°).
- Check every image and make it again when it is sideways, a body is broken, or it does not show its camera and pose.
- GPT Image 2.6 at high quality, 2k, with the garment as References.
- The safety-filter warning: step 5 has a fallback, and step 2 keeps short garments away from low cameras.
- The Clean & Swap fix list: skin, things that repeat, strangers, clones of her, what people in the background do. Folded into `<Do's>` and `<Don't>`.

Left out:

- "Don't write friends or other women near her." It is a Soul 2.0 fault, and this skill does not use Soul 2.0. The prompt still keeps everyone far from her.
- Size auto. It is for editing an image that already has a shape.
- The video steps and the Location image step, as the brief asked.

## Test log

2026-11-16. Four shots, two garments (Cocoa Quinn Midi Dress × Claire, Beige Julia Mini Dress × Kristy), both boards. 18 images, 42.5 credits. None blocked, none sideways. Sheets are in `tests/`.

| Way | Garment | Face | Cost per image |
|---|---|---|---|
| A. Soul 2.0 with her Soul ID, then swap in GPT Image 2.6 | Right in 4 of 4 | Drifted from Kristy in 2 of 4 | about 3.75 |
| **B1. One pass, GPT Image 2.6** | Right in 4 of 4 | Right in 4 of 4 | 2.75 |
| B2. One pass, Nano Banana Pro | Wrong in 2 of 4 (neckline, length) | Right in 3 of 4 | 2 |

B1 was picked. Not tested yet: a back-view shot, a third garment, and a run with Inspiration.

A single front shot (the garment's Element in Higgs) gave the same garment as the five shots on two front-facing images. Back views were not tried with it.

### Run1 — first full batch

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

### Run2 — the same ten shots, with her face close-up as a second reference

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

### Yield study — in progress

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

### Yield study — v3 (2026-11-19)

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

### Yield study — v4 (2026-11-19) — target reached

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

### Full set on v4 (2026-11-19)

All five garments on both Boards. The 50 new images (Run12–16) gave 47 Pass (94%), 3 Borderline (face drift), 0 Fail. Output is in Drive, folder "SHER PHOTOSHOOT SKILL - OUTPUT", one folder per garment.
