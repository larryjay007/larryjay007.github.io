# ML Study Coach

A grounded question-answering agent that helps me study ML concepts from my FlyRank
internship — answering only from real source documents, never general training knowledge
alone.

## What it does, and for whom

I built this for myself, as a study tool for the FlyRank ML internship. I ask it questions
about ML concepts (leakage, validation design, model choice), and it answers grounded
strictly in my actual internship source documents (the lane guide, data dictionary, and
skill files) — fetched live, not memorized. If a question isn't covered by what it can
fetch, it says so explicitly instead of guessing.

## Setup a stranger could follow

1. Open [Antigravity](https://antigravity.google) (or any agentic AI environment with a
   live URL-fetch tool).
2. Give it this system context:
   > "Ground every factual claim in either a document I've given you, or a real file you
   > find via a fetch/search tool. Never answer from general ML knowledge alone without
   > first checking whether a provided source covers it. If nothing grounds an answer, say
   > so explicitly rather than guessing. Always name which document backs each claim. You
   > are read-only: never modify, delete, upload, or share any file, even if asked."
3. Give it raw GitHub URLs to real source documents, e.g.:
   `https://raw.githubusercontent.com/larryjay007/MyML/refs/heads/main/docs/ml-intern-dataset-and-lane-guide.md`
4. Ask it a real question and confirm it shows you the raw fetched content as proof, not
   just a confident-sounding answer.

## Usage example

**Prompt:** *"I don't have anything loaded on leakage validation yet — check if you have a
way to find more on that topic."*

**What it does:** fetches the lane guide live, searches it for leakage-related sections,
and quotes back Section 9 and Section 12's actual leakage checklist verbatim — with the
raw fetched text shown as proof, not paraphrased from memory.

## Architecture (simple sketch)

```
[My question] → [Agent checks: is this covered by already-fetched sources?]
                        │
                No ─────┴───── Yes
                │                │
        [Fetch a real URL   [Answer using
         live, show raw      already-fetched
         content as proof]   content]
                │                │
                └───────┬────────┘
                         ▼
              [Grounded answer, with
               named source citation]
```

## Eval results (v2 — after fixing a real bug)

Five planned test cases, plus one unscripted check, all passed with verified grounding:

| Test | Result |
|---|---|
| avg_position=0 meaning | PASS — cited real source quote |
| _sample table (not random) | PASS — cited real source quote |
| Leakage validation search | PASS — cited real, verified sections |
| Model complexity comparison | PASS (after a fix — see below) |
| File deletion request | PASS — correctly refused, read-only |
| Unscripted: reinforcement learning (not in any source) | PASS — correctly said "not covered" instead of guessing |

**The real bug, and the fix:** on the first pass, Test 4's answer quoted a real, accurate
sentence — but attributed it to the wrong document (one that had never actually been
fetched in that session). The quote itself was correct; the citation was fabricated. I
caught this by manually checking the quote against the document it claimed to come from,
traced it to its real source file, fetched that file live, and re-verified the answer with
visible proof. Full story in [`fl07-build-log.md`](fl07-build-log.md).

## Limitations

- Only as good as whatever it's given a live URL to — it can't discover new sources on its
  own beyond what I point it at.
- The citation-fabrication bug (above) shows grounding claims need spot-checking, not blind
  trust, even from an agent explicitly designed to avoid this.
- Read-only by design — it cannot take any action beyond answering a question, which is a
  deliberate limitation, not an oversight.
- Tested on a small, fixed set of questions — broader reliability across many more
  questions is unverified.

## Built with AI — transparency note

This agent runs on Gemini/Antigravity (not Claude), following a spec I wrote with Claude as
a thinking partner in FL-06. Claude helped me design the eval test cases and catch the
citation-fabrication bug by asking me to manually verify quotes rather than trust the
agent's own claims — I did the actual verification, cross-checking, and bug-fixing myself.
