# Callum Meme DB

Shared meme library for [@CallumMullooly](https://x.com/CallumMullooly) image-only X replies.

**Storage split (efficient):**
- **This repo** — schema, LLM fill instructions, sync notes (small, public).
- **Google Drive** — image files + live `index.jsonl` (bulk storage).

| Drive item | Link |
|---|---|
| Root folder | https://drive.google.com/drive/folders/1miS5A5vdbW_LP-TY_Auaaywej6sDmxct |
| `memes/` images | https://drive.google.com/drive/folders/1Y7dSoM2TLBAll-ZNRWXpDxD3A9uY23Ck |
| `index.jsonl` | https://drive.google.com/file/d/1WAhLelMeA3JL_hx3OpcuMkrtkTrPIACE/view |

Drive folder id: `1miS5A5vdbW_LP-TY_Auaaywej6sDmxct`  
Memes folder id: `1Y7dSoM2TLBAll-ZNRWXpDxD3A9uY23Ck`  
Index file id: `1WAhLelMeA3JL_hx3OpcuMkrtkTrPIACE`

## Docs in this repo

- [SCHEMA.md](SCHEMA.md) — one JSONL row per meme
- [FILL.md](FILL.md) — instructions for another LLM/service that populates Drive
- [USAGE.md](USAGE.md) — how Callum picks a meme for an image-only reply

## Theme

Prefer funny **cyber / AI / computer-tech** memes (deploy fails, prompt injection, “temporary” fixes, SecOps life). Tone lean: dry, internet-native — not corporate, not NZ politics.

## Licence / rights

Only add memes you have rights to use (own work, clear licence, or fair-use-safe for reply context). Record `source` and `licence` on every row. Do not upload copyrighted packs wholesale without permission.

— callummullooly / Kym, 3 Nov 2026 NZDT. Re-check against the wiki/live system if this is more than 2 weeks old.
