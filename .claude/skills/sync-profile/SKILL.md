---
name: sync-profile
description: Compare README.md and README_es.md in this repo against ../source/ (the canonical professional facts) and report or apply the differences. Use when the user asks to sync, update, review, or check alignment of the GitHub profile against source, or after source/ changes and the profile may be stale.
---

# Sync Profile

Keep `README.md` and `README_es.md` in this repository aligned with the
canonical facts in `../source/` (sibling directory, not a git repo). This
skill only edits files in this repo (`github-profile/`) — never `../source/`
or `../website/`.

Before doing anything, read the rules that already govern this work — do not
re-derive them:

1. `../AGENTS.md` — workspace-wide rules (source of truth flow, positioning,
   change boundaries).
2. `../source/AGENTS.md` — what counts as canonical, what must never be
   invented.
3. `./AGENTS.md` — GitHub profile positioning, style, and bilingual-alignment
   rules.

## Procedure

1. **Read canonical source**: `../source/profile.yaml`,
   `../source/experience.md`, `../source/skills.md`, `../source/projects.md`.
   Treat these as ground truth. Note `TODO` markers — those are explicitly
   unverified and must not be propagated as fact.
2. **Read current profile**: `README.md` and `README_es.md`.
3. **Diff for drift**, specifically:
   - Positioning/tagline mismatch vs. the canonical positioning in
     `../source/AGENTS.md` and `./AGENTS.md`.
   - Technologies, employers, dates, metrics, or achievements in the profile
     that are absent from `../source/` (never invent — flag instead).
   - New or updated facts in `../source/` (e.g. `CHANGELOG.md` entries, new
     projects in `projects.md`) not yet reflected in the profile.
   - Projects described as completed/production in the profile that
     `../source/` marks as draft, planned, or unfinished.
   - Semantic misalignment between `README.md` and `README_es.md` (they
     don't need literal translation, but must say the same things — same
     links, same project status, same section order unless there's a clear
     audience reason otherwise).
4. **Report findings** before editing: list each drift item as
   source-says-X / profile-says-Y, and separately list anything the profile
   claims that has no support in `../source/` at all (conflict — do not
   silently resolve, ask Cesar per `../source/AGENTS.md` rule 3).
5. **Propose or apply changes** only to `README.md` and `README_es.md`,
   keeping both in sync. Do not touch `../source/` (facts flow one
   direction: `source/` → `github-profile/`, never the reverse) or
   `../website/`.
6. **Validate**: check Markdown structure and that both language files stay
   semantically aligned after edits. Show the diff.
7. **Do not commit or push** unless explicitly asked, per the Git boundaries
   in both `AGENTS.md` files.

## Output when just checking (no edit requested)

If the user only asked to check/review alignment, stop after step 4 with a
concise drift report — don't edit files unless asked to apply the changes.
