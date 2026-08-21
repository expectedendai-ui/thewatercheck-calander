# TheWaterCheck Calendar

Dedicated media and schedule source for `@thewatercheck` Instagram content.

## Files

- `plan.json` — publishing manifest consumed by the shared Instagram worker.
- `images/` — WaterCheck post images and reels thumbnails.

Keep this repository separate from MyBibleLens so a brand asset cannot be scheduled for the wrong account. Add media files under `images/`, then reference their raw GitHub URLs in `plan.json`.

When photos are ready, provide them to Claude/Codex with the desired dates and captions. The assistant can add the files, update `plan.json`, and verify the calendar before any publishing is enabled.

Publishing is intentionally empty until WaterCheck content is approved and the Instagram account is connected.
