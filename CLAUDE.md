# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

Markdown-only repo holding Anders Karlsson's career data and the documents derived from it. No build, test, or tooling — edits are made directly to the Markdown.

## Architecture: source of truth → derived documents

`Resume-Master-Data.md` is the **generic source of truth** — a comprehensive, audience-neutral data store about Anders (facts, roles, scope, achievements, voice statements, public links). It is not itself the document Anders sends out.

Every other career-facing document is a **derived output** generated from `Resume-Master-Data.md` for a specific audience or channel:
- LinkedIn copy (headline, About, experience entries) → `LinkedIn.md`
- Per-position CVs tailored for a specific job application → e.g. `CV-<company>-<role>.md`
- Speaker bios / conference profiles → e.g. `speaker-<event>.md`
- Pitch decks, advisor profiles, etc.

When generating a derived doc, treat `Resume-Master-Data.md` as the canonical input. Pull only what is relevant for the audience, reorder for emphasis, and adapt voice — but never invent facts that aren't in `Resume-Master-Data.md`. If a fact is missing, add it to `Resume-Master-Data.md` first, then generate.

**Forward sync rule (master → derived):** when a fact changes (role, date, scope, metric, link), update `Resume-Master-Data.md` first. Then refresh any derived doc whose content depends on it. Voice and emphasis can differ between docs; facts must not.

**Reverse sync rule (anywhere → master):** any career update Anders makes outside this repo — editing LinkedIn directly, sending a tailored CV, giving a talk, getting a recommendation, surfacing a new metric or proof point in conversation, taking on a new client, finishing an engagement — must be reflected back into `Resume-Master-Data.md`. The master is the canonical store; if a fact lives only in a derived doc, on LinkedIn, or in chat, it will be lost. When Anders mentions any new career fact in conversation, capture it in `Resume-Master-Data.md` before continuing.

## Files

- `Resume-Master-Data.md` — generic source of truth. Top comment declares it "citation-free for LLM parsing" — preserve that property. Do not introduce footnote-style citations or reference markers.
- `LinkedIn.md` — derived doc for LinkedIn (headline, About, visibility posture, experience-update checklist, coaching notes).
- `aardvark-webpage-review1.md` — derived brief for the team building / refreshing aardvark.pm. Self-contained for handoff. Consulting/exec-level scope only — founder/builder content lives on a future Aardvark Labs site, not here.
- `actions.md` — Anders's working to-do list for this whole career-refresh project. Holds active actions (e.g., recommendation requests with drafted asks), backlog, and a Done log. Update as items complete; do not let it become stale.
- `Resources/` — supporting source material (e.g., the latest sent CV PDF). Treat as inputs, not outputs.
- Future derived docs should use a clear filename pattern (`CV-<company>-<role>.md`, `speaker-<event>.md`, etc.) so the master/derived relationship stays obvious.

## Conventions for `Resume-Master-Data.md`

- **`[TBD ...]` markers** indicate intentionally missing or unverified data (metrics, dates, examples, links). Do not invent values to replace them — either ask Anders or leave the marker. The "Open Questions / Missing Data" section at the bottom tracks the canonical list of gaps.
- **NDA scope is explicit.** Rebtel entries and parts of Electrolux work are marked under NDA. Do not fabricate metrics, client names, system names, or outcomes for NDA-bound roles. Bullets there describe scope/deliverables only — keep that posture.
- **Section structure for experience entries:** `### Company | Title | Location | Date range`, followed by a `**Scope:**` line, then bullets. Match this when adding entries.
- **Date ranges** use `Month YYYY – Month YYYY` or `YYYY – Present`. Keep consistent.
- **Comprehensive, not tailored.** Resume-Master-Data.md should be richer than any single derived doc — include facts even if they wouldn't appear on a typical CV (e.g., self-identity statements, longer bio paragraphs, full lists of talks/launches/links). Derived docs trim and tailor; the master grows.

## When editing

- Preserve existing ordering: most-recent-first within each section, with sub-roles (e.g., the Electrolux AI Lead PM assignment) nested under their parent role.
- If you add a metric, verify it appears in the file already or was supplied in conversation. Otherwise mark `[TBD]`.
- The "Open Questions / Missing Data" section is the source of truth for known gaps — update it when a TBD is resolved or a new gap is identified.
