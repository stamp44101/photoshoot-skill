# Photoshoot skill (v4)

A Claude skill for SHER on-location photos. It takes the five RETOUCH shots of a garment and puts the same KOL character in it on location, in one pass on Higgsfield GPT Image 2.6 (high, 2k, 3:4). Two boards: **Lifestyle Casual** and **Lifestyle High-Fashion**.

It follows RETOUCH and BG SWAP (`stamp44101/retouch-skill`) and replaces Runbook F.Weave step 3.

> **v4:** all 12 RETOUCH garments × both boards done, 240 images, all Pass. See `photoshoot-skill/TESTS.md`.

## Install
- **Quickest:** add `photoshoot-skill/SKILL.md` as a skill in Claude. It is self-contained.
- **Full:** download this repo (Code → Download ZIP) and install the `photoshoot-skill` folder.

## Before you start
1. Connect the **Higgsfield** connector in Claude with the SHER Higgsfield account.
2. Connect **Google Sheets** (prompt sheet, tab `PHOTOSHOOT`) and **Google Drive**.
3. Have the garment's five `_BG` shots from RETOUCH (Drive: SHER RETOUCH SKILL - OUTPUT).

## Use
Say: "photoshoot [garment] ด้วย [character] casual / high-fashion".

You get:
- 10 images per board, 2.75 credits each (27.5 per board)
- one row per image in the `PHOTOSHOOT` tab, with Preview and QA
- Drive "SHER PHOTOSHOOT SKILL - OUTPUT" → `<Garment>/Casual/` and `<Garment>/High-Fashion/`

## Why GPT Image 2.6
In the A/B test it held the garment in 4 of 4 and the face in 4 of 4. Nano Banana Pro got the garment wrong in 2 of 4. Nano Banana Pro stays as the fallback when GPT blocks a prompt. Details in `TESTS.md`.

## Files
- `photoshoot-skill/SKILL.md`: the skill (source of truth)
- `photoshoot-skill/TESTS.md`: test log and status
- `photoshoot-skill/tests/`: side-by-side sheets from the A/B test and early runs
