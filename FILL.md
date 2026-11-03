# FILL.md — instructions for another LLM / service

Goal: populate the **Google Drive** Callum Meme DB so Callum can reply on X with **meme images only**.

## Where to write

| What | Where |
|---|---|
| Images | Drive folder `memes/` — id `1Y7dSoM2TLBAll-ZNRWXpDxD3A9uY23Ck` |
| Index | Drive file `index.jsonl` — id `1WAhLelMeA3JL_hx3OpcuMkrtkTrPIACE` |
| Root | Drive folder — id `1miS5A5vdbW_LP-TY_Auaaywej6sDmxct` |

Do **not** commit large binaries to this git repo. Keep git for docs/schema only.

## Theme filter (hard)

Accept only funny **cyber / AI / computer-tech** memes. Reject politics, pure lifestyle, crypto-shill, or NSFW.

Good: deploy disasters, AI hallucination, prompt injection, “temporary” fix, pager life, code review roast.  
Bad: election memes, random reaction faces with no tech hook, adult content.

## Add one meme (checklist)

1. Download or generate the image (prefer ≤1.5 MB; `webp` or `png`/`gif`).
2. Choose a unique `id` (kebab-case) and filename `{id}.{ext}`.
3. Upload the file into Drive `memes/`; record the new file’s Drive id.
4. Append **one** JSON line to `index.jsonl` per [SCHEMA.md](SCHEMA.md). Fill every required field. Set `drive_file_id` to the uploaded file id. Set `last_used_at` to `null`.
5. Deduplicate: if `sha256` or near-identical OCR already exists, skip.
6. Respect rights: set honest `source` + `licence`. Skip if unclear and commercial reuse would be unsafe.

## Batch tips

- Target quality over volume: start ~50–200 solid tagged memes.
- Prefer memes that answer a *situation* (`when_to_use`), not only keywords.
- Keep OCR accurate — Callum matches topics from post text + OCR.
- After batches, leave a short note in Drive (optional `CHANGELOG.txt`) with count + date.

## What Callum will do later

Read `index.jsonl`, pick a row by tags/topics, download the image by `drive_file_id`, post an **image-only** reply on X as @CallumMullooly, then update `last_used_at`.

## Out of scope

- Do not like, DM, follow, buy, or change X settings.
- Do not post from this fill job unless Kym explicitly asks that service to post.
- Do not put secrets, customer data, or private keys in the index.

— 3 Nov 2026 NZDT. Re-check against the wiki/live system if this is more than 2 weeks old.
