# 20260617 - Beginning & Safety Net

## What I did

- Set up a JDK 21 / Maven 3.9.9 toolchain and split the project into a public engine repo (MIT-licensed) and a private content repo — DSA/Aventuria is Ulisses Spiele's IP, and most of the artwork isn't mine to redistribute.
- Found and fixed two real bugs during verification of the split: the static-site generator silently never copied css/js/index.html/notfound.html into its output, and an XML entity-resolution bug that only worked by working-directory coincidence.
- Verified end-to-end against the real data: 377 HTML pages, 250 images — matching the pre-split baseline.
- Added a Maven Wrapper so the build no longer depends on a Maven install that only exists on this machine.
- Added JUnit 5 and wrote four characterization tests against the live generator, using a small self-contained fixture rather than the private data repo, so the public engine repo can test itself standalone.
- Writing those tests surfaced a third real bug: an unclosed `FileWriter` leaking file handles. Fixed it, then re-ran the full generator and confirmed output was still byte-for-byte equivalent to the known baseline.

## Technical Learnings

- Verifying empirically beat reasoning theoretically about path/file resolution — twice in the same session, both times the "obvious" theoretical answer was wrong.
- Tests aren't only insurance against future regressions — writing one surfaced a live bug immediately, before a single regression had even happened.
- Deciding what a test should depend on is itself a design decision: building a fixture instead of relying on the private data repo kept the public engine repo self-testing.
- A reproducible build is a safety net in its own right — it removes "works on my machine" as a variable before you trust anything built on top of it.

## Organizational Learnings

- I had to trust the verification steps more than I expected to — but I was very surprised about the quality of the outcome.
- Working with Claude Code can really performance, if you know what to do and how to use the tools. I wonder what the tradeoffs are, atm.

## Leadership Perspective

- With this rather simple task, Claude Code was capable of keeping context, analyzing and understanding the task and the arising problems, and finding and testing appropriate solutions. Moreover, handling the legacy code with respect and care, building a safety net before changing things helped build trust.

## Open Questions

- Along the way, some repetitive tasks emerged (posting on LinkedIn, creating this journal, ...) that I would like to automate as soon as possible.
- How will I balance doing vs. reflecting on the learnings? There will be more questions (and problems), once my first excitement fades.