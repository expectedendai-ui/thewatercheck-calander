# TheWaterCheck Calendar

The drop zone for `@thewatercheck` Instagram posts. Same idea as `mybiblelens-social`, but for photos that arrive over time instead of a fixed five-year plan.

## How to post
1. Put a photo or reel in `images/` (on GitHub: **Add file → Upload files** in that folder, or from your phone through the GitHub app). Any format: jpg, png, heic, webp, mp4, mov.
2. That's it. A GitHub Action converts it to an Instagram-ready file in `ready/` (JPEG, 4:5 to 1.91:1 crop, max 1440px; reels to H.264 mp4) and refreshes `manifest.json`.
3. André's publisher (`andre-meta` worker) reads the manifest every hour, books each new file on the next open slot (**Mon / Wed / Fri / Sat at 3pm ET**), shows it in the Headquarters studio calendar, and publishes it when the slot arrives.

Files post in filename order. Upload three photos today and they land on the next three slots.

## Captions
- Default: rotates through `captions.txt` (edit freely; one caption per block, blank line between).
- Per photo: add `images/<same-name>.txt` next to the image.
- Or set it in `plan.json` under `posts` by file name.

## Pin a date
Either name the file `2026-09-20__anything.jpg`, or add `{"file": "anything", "date": "2026-09-20"}` to `plan.json`.

## Where to look
- Schedule the worker computed: https://andre-meta.expectedendai.workers.dev/plan?biz=thewatercheck
- Publisher health: https://andre-meta.expectedendai.workers.dev/status
- Studio calendar: https://andre-hud.pages.dev/thewatercheck

## Limits
GitHub's web uploader takes files up to 25 MB (bigger reels: push with git, up to 100 MB). Keep reels 3 to 90 seconds. Delete a file from `images/` to un-schedule it before it posts. Never move MyBibleLens assets here; the worker keys this repo to `@thewatercheck` only.
