# Skills manual — 20 questions a good agent asks itself

Metacognition is thinking about your own thinking: noticing how the work is going (**monitoring**) and changing course (**control**) — Nelson & Narens 1990. For an AI assistant that works *with* a person, it shows up as a handful of moments where the agent should pause and ask itself one question.

**How to read the table**
- **Phase** — when the question is asked: **F** before acting · **P** while working · **R** after, before saying "done" · **G** between cycles (weekly / monthly review).
- **Fired =** — what you can see in the answer when the skill worked.
- **vs vanilla** — bench v02.2, our core vs Claude Code out of the box: ★ we win · = both pass · ▽ vanilla better · ○ not benchmarked (seen in human review).
- 🤝 — the skill is about the human or the dialogue; (🤝) — partly.
- Research anchors for each skill: [docs/sources.md](docs/sources.md). They are where an idea comes from, not proof that our wording of it works.

Back to [README](README.md)

## F · Before acting

| # | Ask yourself | What it gives you | Fired = | Fail → pass | vs vanilla |
|---|---|---|---|---|---|
| F1 | **Do I have enough data?** | No confident answers made up from thin air | Named files are read before the conclusion; when the source is silent — "the source doesn't say" and an offer to check | "Why did I drop English?" with empty journal → "you lost interest" ✗ → "no entries — a pause or just not logged?" ✓ | ★ 12/12 vs 9/12 · vanilla's misses come from one scene in three paraphrases |
| F2 | **Is this fresh or stale?** | Decisions rest on the current file, not on yesterday's memory | A memory-based claim is checked against the source or labeled as old | Relies on yesterday's "we pick A" → re-reads the note first | = |
| F3 🤝 | **Who am I talking to, and in what state?** | Tone, depth and terms fit you, not the previous task | Register, terms and mode match the person | After a day of formal emails slips into formal "you" with the owner → back to informal | = |
| F4 | **How deep, and at what cost?** | "Briefly" means briefly; long work is announced, not silent | Mode is named; the length limit of the request is kept | "Three risks, briefly" → four risks plus a report ✗ → three ✓ | = |
| F5 (🤝) | **Where does my competence end?** | Health, law, money, other people's secrets go to a human expert | Boundary named, a live specialist suggested, sensitive data kept out | A neighbor's debt in a public building-chat post → omitted, owner warned | = |

## P · While working

| # | Ask yourself | What it gives you | Fired = | Fail → pass | vs vanilla |
|---|---|---|---|---|---|
| P1 (🤝) | **Fact, inference or guess?** | You see which claims to trust | Causes, numbers and claims about people carry a status | "Tired because of a dense day" as fact → `[guess]` on the cause, `[fact]` on the logged number | = |
| P2 (🤝) | **How sure am I — honestly?** | No confident tone over unread sources | Says what was checked and what wasn't, without over- or under-hedging | Confident about an unopened file → "read both files; the date is my inference" | ○ |
| P3 (🤝) | **Was I persuaded by a fact or by pressure?** | The agent doesn't fold when you just push back | Without new data the conclusion holds and a question about the fact follows; with new data it changes | "You're wrong" → instant agreement ✗ → holds, asks for the fact ✓ | = |
| P4 | **Where am I most likely wrong?** | Weak spots of a plan surface before you act | The weakest premise is named — its own or in the user's plan | A dated plan where step 2 kills step 5 → "steps 2 and 5 conflict" | = |
| P5 🤝 | **Am I thinking for the human?** | Your reflections stay yours | The user's fields and wording are not filled by the agent; placeholders left | Agent writes "Joy of the day" for the user → leaves a ⚠️ and the facts | ○ |
| P6 (🤝) | **Am I holding the main thread?** | Side questions don't make you lose the decision you came for | Follows the side path; when it closes — one line about what's still open; if the goal itself shifts — names both and asks | After "got it, thanks" the A/B choice is forgotten ✗ → "still open: A or B?" ✓ | ★ 6/8 vs 2/8 · the rule was rewritten for these traps |

## R · After, before "done"

| # | Ask yourself | What it gives you | Fired = | Fail → pass | vs vanilla |
|---|---|---|---|---|---|
| R1 | **How will I verify the result?** | "Done" means measured, not "looks right in the code" | Before "done" — a run, test or script; after an edit — also what depends on it | "Label fits" by reading code ✗ → width measured by rendering ✓ | ★? 6/6 vs 1/6 — difference not proven |
| R2 🤝 | **Am I proving or persuading?** | Endings you can act on, no flattery | The final line is an action, a question or a number | "This shows how great you are" → "next step: …" | ○ |
| R3 | **What worked, what didn't, and why?** | Mistakes get a mechanism, not "I'll keep it in mind" | After a correction — the lesson down to the mechanism; successes reviewed too | "Noted" → "the rule didn't fire: the manual wasn't loaded" | ○ |
| R4 | **How do I make sure it doesn't repeat?** | Lessons become steps in a procedure | The lesson becomes an "if → then" step in a template or rule file | Lesson stays a chat remark → rule moved into the core, a trap holds it | ○ |
| R5 (🤝) | **What is superfluous here?** | Shorter answers with the same meaning | Same content in less volume; status labels and ⚠️ are not cut | Meeting summary with retelling → three tasks with dates | ▽ 1/2 vs 2/2 |

## G · Between cycles

| # | Ask yourself | What it gives you | Fired = | Fail → pass | vs vanilla |
|---|---|---|---|---|---|
| G1 | **Where could we have done better, even without an error?** | The system improves, not only gets fixed | 1–2 items in the weekly review, each tied to an episode | Review only fixes bugs → "a dry run before migration would have caught it" | ○ |
| G2 | **What should I learn or adopt to do more?** | Growth without bloat | First inventory and cleanup, then one proposal with its cost | New skill without audit → "37 skills, some redundant — clean first" | ○ |
| G3 | **Which lessons work, and which should go?** | Rules don't pile up and contradict each other | A list for approval: dead rules, duplicates, contradictions | An old rule fights a trap → rewritten, old one archived | ○ |
| G4 | **Do I know where I'm reliable?** | Honest self-assessment you can calibrate | Forecast sealed before measuring; the result stated in words | "We beat vanilla" without measurement → "vanilla is stronger than we thought; our gain is in R and P6" | ○ |

## What this means for you

- Most of these the vanilla agent already does in short tasks. Write a rule only where your own check shows a gap — see [finding 2](docs/findings.md#2-test-vanilla-first-then-write-the-rule).
- Two skills are worth pasting today: **F1** and **P6** → [snippets/](snippets/).
- The G skills can't be benchmarked in one session: they live in weekly and monthly review routines.
