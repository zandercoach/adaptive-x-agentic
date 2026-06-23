# 20260623 - Publish Before Refactor

## What I did

- Decided to generalize the engine: it stops being "Chroniken des Fliegenden Kessels"-specific and becomes "chronicler," a reusable static-site generator for any RPG group's campaign chronicle. Mapped out the German→English domain translation this requires (Held→Hero, Kreatur→Creature, Nsc→NPC, Ort→Location, Abenteuer→Adventure, Ereignis→Event, Charakter→Character) across roughly 80 engine files, plus the matching element/file names in the private data repo.
- Created two new GitHub repos under the zandercoach account — `chronicler` (public, engine) and `chronicler-data-cfk` (private, campaign content, kept the `-cfk` suffix since this specific data stays tied to this campaign even after the engine goes generic) — and pushed both local repos to them exactly as they were, before writing a single line of rename code.
- Started sketching the refactor as a reviewable plan (package rename, class-by-class translation, template renames, XML migration, build verification), then paused before locking in specifics — deliberately deferred to an upcoming session rather than rushed.
- Added a `CLAUDE.md` to the parent workspace folder, turning it into its own small local-only git repo (not pushed) that documents how the two project repos relate and that the rename is in progress.
- Renamed the parent workspace folder itself from `agentic` to `chronicler` to match the new engine name, and migrated the AI agent's own cross-session memory of this project over to the new folder path.

## Technical Learnings

- Publishing the repos to GitHub before touching any rename code turned "rewrite a Java package across ~80 files" from a risky in-place rewrite into a reversible operation with a remote safety net — the same instinct as the Phase 1 characterization tests, applied one level up.
- A workspace-level git repo, sitting one directory above both code repos, turned out to be a clean place for context that belongs to neither repo alone: how they relate, and the status of work-in-progress that spans both.
- Renaming a working directory after an AI agent has already built up memory keyed to the old path is its own small failure mode: the memory doesn't move with the folder automatically. A future session has to notice the mismatch and go looking for the orphaned memory rather than assume it's gone.

## Organizational Learnings

- Documentation now comes at almost no cost. Keep it and use it!

## Leadership Perspective

- It's hard to maintain cross-reference working with different projects. Clear context and boundaries needed.

## Other Learnings

- None for now.

## Open Questions

- None.
