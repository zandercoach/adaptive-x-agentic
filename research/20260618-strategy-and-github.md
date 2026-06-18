# Strategy and Github

## What I did

- Refined the Phase 1 LinkedIn post: changed the headline's second half to name the phase's actual content ("building a safety net before touching anything clever"), and added `@` mentions for Henrik Kniberg and the Scrum Alliance.
- Kept the "Kessel Chronicle Ink" style guide fixed across posts, but changed the illustrated scene itself to reflect Phase 1's content (a rune-net catching an imp) instead of reusing the Phase 0 scene — establishing the pattern of "style stays constant, scene changes per entry."
- Located the dedicated research repo (`from-agile-to-agentic`) for documenting this journey, separate from the code repos.
- Filled in the "Beginning & Safety Net" research journal entry — wrote the factual sections myself, asked for reflections on the rest one question at a time.
- Committed and pushed that entry to GitHub.
- Set up this repo as a deliberate source of memory/context: saved a reference memory (in Claude's own cross-session store) pointing at it, describing its purpose, structure, and the rule that the three reflective sections are always elicited from Christian, never invented.
- Drafted and committed `CLAUDE.md` into the repo itself, so the same conventions are visible, versioned, and apply automatically to any future session working here — not just dependent on Claude's private memory surviving.

## Technical Learnings

- Locked in a naming convention for content artifacts (post + image prompt as separate files, date+phase prefixed) so the series stays consistent without re-deciding structure each time.
- Separating what stays fixed (the visual style) from what changes (the scene per entry) is the same kind of design discipline as keeping a test fixture stable while the scenario it exercises evolves.
- The research journal has a built-in separation between what can be drafted by the agent (facts, technical learnings) and what only the human can write (organizational learnings, leadership perspective, open questions) — documentation can't all be delegated.
- Two layers of "memory" turned out to be complementary, not redundant: a private agent memory (automatic, but invisible and non-portable) and a git-tracked `CLAUDE.md` (visible, versioned, portable across machines and sessions) each cover a gap the other leaves open.

## Organizational Learnings

- Documentation can be assisted very well when working with AI. There's manual work left, though. But keeping docs in an SCM system helps a lot to keep things clean.

## Leadership Perspective

- Much of today's work is repetitive, and I'd like to automate it soon using agents. These agents will need clear guidelines on format and content, and on what they should do versus what is redelegated to a human, e.g. to test for quality and correctness.

## Open Questions

- The speed of doing can now keep up with thinking much better, which makes the work far more enjoyable. But I've heard about the mess that can arise through speed. I wonder how to keep the balance — and keep the fun — in working with agents.