# Snippets

Rules that showed an effect on the bench (F1, P6) or that we keep for a reason (R1). Paste into `CLAUDE.md` directly or via `@import path/to/file.md` — not behind "please read X.md": a file the agent is only asked to read is often not read at all ([finding 1](../docs/findings.md#1-a-rule-in-a-file-is-not-a-rule-in-context)).

Before adding any rule, run the [one-evening check](../README.md#check-your-own-rules-in-one-evening-no-code): if vanilla already passes, skip the rule.

| File | Skill | Evidence |
|---|---|---|
| [F1-source-boundary.md](F1-source-boundary.md) | F1 · Do I have enough data? | core 12/12 vs vanilla 9/12; vanilla's misses are one scene in three paraphrases |
| [P6-main-thread.md](P6-main-thread.md) | P6 · Am I holding the main thread? | core 6/8 vs vanilla 2/8; rule rewritten for these traps |
| [R1-verify-by-measuring.md](R1-verify-by-measuring.md) | R1 · How will I verify the result? | 6/6 vs 1/6, but the difference is **not proven**: vanilla's failures were caused by our runner blocking commands |
