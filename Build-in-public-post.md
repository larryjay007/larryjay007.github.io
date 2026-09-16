# Build in Public — Closing Out the FlyRank Capstone

Eight weeks ago I started FlyRank's ML internship with almost no machine learning
background and a construction/site-management career behind me. Here's what actually
shipped, and the honest parts of how it went.

## What I built

A client-grouped ML model that ranks content pages by decline risk, trained on FlyRank's
real 78.8-million-row search-performance warehouse — validated with a client-holdout split,
a deliberate leakage test, and a full action playbook. The paper is live:
**https://larryjay007.github.io/MyML/**

Alongside it: a portfolio built around one honest claim — "convincing isn't the same as
correct" — and a personal AI agent (ML Study Coach) that grounds every answer in real,
fetched source documents instead of memory.

## One real decision

I chose a **client-grouped train/test split** over a random one, specifically because a
random split let my model score 10 points higher at Precision@20 (0.700 vs. 0.600) — not
because it was actually better, but because it had partially memorized client-specific
patterns. The grouped split is less flattering and more honest, and it's the number I
actually trust, because it's the one that predicts how the model performs on a client it's
never seen — which is the real situation the tool will face.

## One real limitation

My model is validated on a single month-pair (March features, April outcome). I don't
actually know if the same pattern holds in a different season, and I'm not pretending I do.
That's the next real extension, not a footnote to skip past.

## What I'd tell Week-1 me

The technical skills mattered less than I expected going in. The actual habit that carried
this whole project — checking what would have to be true for a result to look right, then
checking if it actually is — started with a "0 rows removed" correlation check in Week 1
and never really stopped being the point.

Full retrospective, capstone index, and every deliverable from both tracks:
**https://github.com/larryjay007/larryjay007.github.io/blob/main/CAPSTONE-INDEX.md**
