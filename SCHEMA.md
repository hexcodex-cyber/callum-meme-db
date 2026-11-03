# Schema — `index.jsonl`

One JSON object per line. No trailing commas. UTF-8.

## Required fields

| Field | Type | Notes |
|---|---|---|
| `id` | string | Stable slug, unique. Pattern: `kebab-case`, e.g. `temp-fix-heritage` |
| `file` | string | Filename only under Drive `memes/`, e.g. `temp-fix-heritage.webp` |
| `drive_file_id` | string | Google Drive file id of the image (fill after upload) |
| `tags` | string[] | Lowercase. Prefer: `cyber`, `ai`, `devops`, `security`, `coding`, `ops`, `fail`, `win` |
| `topics` | string[] | Free-form topics for matching a post, e.g. `temporary fix`, `prod outage` |
| `caption_ocr` | string | Visible text on the image, or `""` |
| `when_to_use` | string | One sentence: situations this meme answers |
| `source` | string | URL or short credit |
| `licence` | string | e.g. `own`, `CC0`, `fair-use-reply`, `unknown` |
| `added_at` | string | ISO-8601 date, e.g. `2026-11-03` |
| `last_used_at` | string \| null | ISO-8601 or `null` until first reply use |

## Optional fields

| Field | Type | Notes |
|---|---|---|
| `nsfw` | boolean | Default `false`. Skip if true unless Kym says otherwise |
| `format` | string | `png` \| `jpg` \| `webp` \| `gif` |
| `width` | number | pixels |
| `height` | number | pixels |
| `sha256` | string | Content hash for dedupe |
| `notes` | string | Internal |

## Example row

```json
{"id":"temp-fix-heritage","file":"temp-fix-heritage.webp","drive_file_id":"REPLACE_AFTER_UPLOAD","tags":["coding","devops","fail"],"topics":["temporary fix","tech debt","legacy"],"caption_ocr":"Nothing in production is as permanent as a temporary fix","when_to_use":"Reply to posts about hacky fixes that somehow survived years.","source":"https://x.com/example/status/0","licence":"fair-use-reply","added_at":"2026-11-03","last_used_at":null,"nsfw":false,"format":"webp"}
```

## Matching rules (Callum)

1. Prefer tag/topic overlap with the target post.
2. Skip `nsfw: true`.
3. Prefer `last_used_at` null or oldest.
4. Reply with **image only** (blank caption) unless Kym asks otherwise.
5. After a successful reply, set `last_used_at` on that row in Drive `index.jsonl`.

— 3 Nov 2026 NZDT. Re-check against the wiki/live system if this is more than 2 weeks old.
