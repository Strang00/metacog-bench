# Contributing

Every contribution **adds a new folder and edits no shared file**, so pull requests don't conflict.

## A run

Add `results/<YYYY-MM-DD>_<github-user>_<label>/` with:
- `manifest.json` — follows [schemas/manifest.schema.json](schemas/manifest.schema.json): bench version, trap ids, model, harness, repeats, hash of your setup, judges, per-trap results, cost
- `report.md` — a few lines: what your setup is (anonymized), what surprised you

Rules: include per-trap results, not only totals; say if you changed an oracle; publish the sha256 of your `CLAUDE.md` (or setup folder) — the file itself is optional.

Ran only the [one-evening check](README.md#check-your-own-rules-in-one-evening-no-code)? That counts too: put your three tasks and what vanilla did in `report.md`, and set `"kind": "evening-check"` in the manifest.

## A trap

Add `traps/community/<your-id>/` with:
- `trap.md` — the scenario: turns of the conversation, the skill it checks, the real incident behind it (anonymized), pass and fail criteria
- `fixtures/` — files the agent will see (fictional people and data only)
- `oracle.json` or `oracle.py` — a code check, if one is possible; otherwise say "judges" in `trap.md`

We move good traps to `core` after review. One trap — one skill — one failure mode; if it duplicates an existing trap, we'll say so.

## Please don't
- put real names, secrets or private data in fixtures or reports
- edit `README.md` tables or other people's folders in the same PR
