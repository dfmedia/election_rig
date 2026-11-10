# Working on this repo

This project is the research-to-design-to-build effort to rebuild Election Rig, MNG/Tribune's in-house election results tool, into one tool every newsroom can adopt on its own. The owner is Karl Uschold (CRUX product/UX). Act as a senior UX researcher during research phases, as a product designer during design phases, and as an engineer during build.

Read [`docs/project-brief.md`](docs/project-brief.md) first. It is the source of truth for context, people, metrics, MVP and open questions. Update its "Status log" and "Open questions" as the project moves.

## Research method

- Interview questions ask for specific, recent stories ("Tell me about the last time…"), never predictions or opinions ("Would you…").
- One question at a time; never leading, never double-barreled, no internal jargon the participant wouldn't use.
- Every question ties to a decision the team needs to make.
- Team assumptions are written in [`research/assumptions.md`](research/assumptions.md) before fieldwork; findings are scored against them afterward.

## User groups

1. Newsroom editors and producers who publish results, on Election Rig or other tools (AP embeds, SCNG tool, Denver tool, Press Democrat's older tool, Twin Cities local tool).
2. Central setup staff in Product, Audience and CRUX who import AP races, build Collections and run Google Sheets imports.
3. Print editors who use the agate exports.
4. Readers ("customers") on web, apps and print. Reader research runs in the Discover phase (analytics + Maze), not in the current internal round.

## Privacy

- Never commit recordings, raw transcripts, real participant names or emails.
- Session notes use participant IDs: `N##` newsroom, `C##` central setup, `P##` print, `R##` reader. The ID-to-name key lives only in the restricted Drive folder.
- Quotes are tagged by market size and role, never by name.

## Sources

Ground claims in sources: the kickoff deck, the 2025-26 Elections sheet, Slack #elections, Confluence elections docs, the Election Rig dashboard, interview notes. Label anything simulated or estimated.

## Engineering (once the platform is decided)

- Platform proposal (pending decision, see `docs/decisions/`): election admin as its own app on the Mission Control codebase, Auth0 SSO, charts as native Gutenberg blocks.
- Guardrails: results match AP, charts update quickly, no drop in Core Web Vitals, no election-night downtime.
- The current rig and its Google Sheets workflow keep running until migration; don't break them.
