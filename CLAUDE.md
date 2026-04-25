# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

Single-file repo containing `Resume.md` — Anders Karlsson's master resume in Markdown. There is no build, test, or tooling; edits are made directly to the Markdown.

The file's top comment declares it is "citation-free for LLM parsing" — preserve that property. Do not introduce footnote-style citations, reference markers, or other syntax that breaks plain-text parsing.

## Conventions

- **`[TBD ...]` markers** indicate intentionally missing or unverified data (metrics, dates, examples, links). Do not invent values to replace them — either ask Anders or leave the marker. The "Open Questions / Missing Data" section at the bottom tracks the canonical list of gaps.
- **NDA scope is explicit.** Rebtel entries and parts of Electrolux work are marked under NDA. Do not fabricate metrics, client names, system names, or outcomes for NDA-bound roles. Bullets there describe scope/deliverables only — keep that posture.
- **Section structure for experience entries:** `### Company | Title | Location | Date range`, followed by a `**Scope:**` line, then bullets. Match this when adding entries.
- **Date ranges** use `Month YYYY – Month YYYY` or `YYYY – Present`. Keep consistent.
- **This is a master resume**, not a tailored one. Bullets are deliberately broad to be reused across tailored variants. Avoid narrowing wording unless asked.

## When editing

- Preserve existing ordering: most-recent-first within each section, with sub-roles (e.g., the Electrolux AI Lead PM assignment) nested under their parent role.
- If you add a metric, verify it appears in the file already or was supplied in conversation. Otherwise mark `[TBD]`.
- The "Open Questions / Missing Data" section is the source of truth for known gaps — update it when a TBD is resolved or a new gap is identified.
