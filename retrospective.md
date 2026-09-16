# Retrospective — To the Person I Was in Week 1

Eight weeks ago, you sat down with almost no ML experience and a construction background,
trying to figure out how the Delegate/Describe/Discern/Diligent framework was supposed to
actually work in practice, not just as four words on a page. You'd have believed me if I
told you the framework would still be governing decisions in Week 8 — but you wouldn't have
believed *how*.

## What I set out to do

The plan was simple, almost naively so: learn machine learning fast enough to build a real
capstone, and build a portfolio honest enough that it wouldn't embarrass me later. I thought
the hard part would be the math. It wasn't. The hard part — the thing that actually took
eight weeks to get good at — was catching the moment a result *looks* right and pausing
before believing it.

## What changed

The real turning point wasn't technical. It was Week 1, staring at a "0 rows removed"
output, being told something looked off, and having to actually reconstruct *why* — not
just accept a fix. That habit — check what would have to be true for this to look right,
then check if it actually is — ended up being the thread that ran through everything after
it. It showed up again when a decision tree ignored a feature I expected it to use. It
showed up when a random train/test split scored 10 points higher than the honest one, and
I had to explain the gap instead of celebrating the number. It showed up, most sharply, when
my own AI agent gave me a real, accurate quote — attributed to a document it had never
actually fetched. I caught that one myself, by checking instead of trusting.

By the time I built the actual capstone model, "trust but verify" wasn't a slogan I was
performing for a rubric. It was just how I worked. I printed the base rate next to every
metric because I'd learned the hard way that a number means nothing alone. I deliberately
broke my own leakage-detection harness by feeding it a cheat, just to prove it would catch
one. I reported an archetype that turned out empty instead of quietly deleting it to make
the results look cleaner.

## What I'd build next

Two honest gaps I'm not pretending are closed: my model's validation only covers one
month-pair, so I don't actually know if the pattern holds across seasons — that's the first
thing I'd extend, given more time. And my portfolio's central claim still rests on a small
number of examples; two different reviewers independently asked the same question — "can
you do this reliably, or was it luck?" — and the honest answer right now is "ask me again
after more real cases." Building that track record for real, not just writing better copy
about the one I have, is the actual next project.

## Three things that transferred, not just the ML mechanics

**First:** a wrong citation with completely accurate words taught me that verification
means checking the *link* between a claim and its source, not just whether the claim sounds
plausible. That applies to a lot more than AI agents.

**Second:** disagreeing with my own first draft, out loud, in writing — like correcting
"one client engagement's worth of work" to what it actually was, training exercises — is a
skill, not a weakness. The instinct to catch myself before someone else has to is worth more
than getting it right the first time would have been.

**Third:** asking "what would make this wrong?" before asking "is this good?" changes what
you build. Every notebook that ended with real error analysis, every playbook entry with a
named no-go case, every honest limitation section — none of those happened by defaulting to
"looks done." They happened because I kept asking the harder question on purpose.

I don't think you'd recognize how much of this became instinct rather than effort. That's
probably the actual point.
