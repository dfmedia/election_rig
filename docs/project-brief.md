# Election Rig Rebuild — Project Brief

*Starter file for a new Claude project. Created Nov 10, 2026 by Karl Uschold (CRUX, MediaNews Group / Tribune). Updated Nov 10, 2026 with the kickoff deck, the 2025-26 Elections sheet, the kickoff meeting notes and the decision to run the interviews in UserZoom with Heather Dzierson.*

**How to use this file:** upload it to the new project's knowledge, and paste the "Project instructions" block below into the project's custom instructions. Everything else here is context Claude (and new teammates) should have from day one. Update the "Status" and "Open questions" sections as the project moves.

## Key links

| Document | What it is | Link |
|---|---|---|
| Election Rig Rebuild Kickoff | Google Slides deck from the Nov 10, 2026 kickoff, presented by Diana Dixon: why rebuild, current workflow, MVP, spikes, platform proposal, 2027 path, success metrics | [Open](https://docs.google.com/presentation/d/1V6BpDQUagaLIEXtUIo7EbSf61FTEPEqmJKHmHFBg6y4/edit?usp=sharing) |
| Kickoff: Election rig rebuild, Gemini notes | Auto-generated meeting notes emailed Nov 10, 2026: decisions, action items, timeline | [Open in Gmail](https://mail.google.com/mail/?authuser=kuschold@medianewsgroup.com#all/thread-f:1881504193589777538) |
| Election Rig project folder | Google Drive folder with all project files (brief at the top, research docs in "01 Research") | [Open](https://drive.google.com/drive/folders/1AXoTjbr93oz0es7emp635n4xrvLGb5Tm) |
| 2025-26 Elections | Google Sheet. "2026 Requests" = what each market asked for; "KG - Nov. 2026" = every Nov 2026 results page and the tool it used; "2026-Collex" = Collection IDs by market; plus 2026 Dates, 2025, 2026, 2027 tabs | [Open](https://docs.google.com/spreadsheets/d/1x7uhjdZNAFvJeiE_sufHbs5ZAYo9HwY2An9ERMOkjHE/edit?usp=sharing) |

Link only. Don't copy these files; they live in a shared drive the Google Drive connector can't search, so open them from these links. The Sheets connector can read the spreadsheet by its ID. The deck's text can be read in Chrome at its `/htmlpresent` URL.

---

## Project instructions (paste into the project's custom instructions)

> This project is the research-to-design effort to rebuild Election Rig, MNG/Tribune's in-house election results tool, into one tool every newsroom can adopt on its own. The user is Karl Uschold (CRUX product/UX). Act as a senior UX researcher during research phases and as a product designer during design phases.
>
> Research method: interview questions ask for specific, recent stories ("tell me about the last time…"), never predictions or opinions; one question at a time; never leading, never double-barreled, no internal jargon the participant wouldn't use. Every question ties to a decision the team needs to make. Name team assumptions in writing before fieldwork and score findings against them afterward.
>
> Three internal user groups: (1) newsroom editors and producers who publish results, on Election Rig or on other tools (AP embeds, SCNG tool, Denver tool, Press Democrat's older tool, Twin Cities local tool); (2) central setup staff in Product, Audience and CRUX who import AP races, build Collections and run Google Sheets imports; (3) print editors who use the agate exports. Plus readers on web, apps and print.
>
> Research setup: the newsroom interviews run in UserZoom (contract through December 2026; renewing UserZoom versus moving to Maze is undecided). Heather Dzierson (Customer Experience) builds the study setups in the platform and co-runs sessions with Karl. This round interviews in-house newsroom staff only, not readers.
>
> Ground claims in sources (the kickoff deck, the 2025-26 Elections sheet, Slack #elections, Confluence elections docs, the Election Rig dashboard, interview transcripts). Label anything simulated or estimated as such. Project files live in the Google Drive shared folder "CRUX/Election Rig" (path below).

---

## The project in one paragraph

Rebuild Election Rig into one tool that newsrooms adopt on their own: easy to use, saves time, and matches or beats what we have today. Today, results reach readers through several tools, setup leans on a few central people, and newsrooms with developers have a big advantage on election night. The rebuild should let any newsroom, regardless of size or technical staff, set up its own races and charts without a ticket, and present results to readers clearly, with charts and maps where they help. The kickoff makes UX interviews the first step: they define the workflow that the platform decision, the data model and the spikes build on.

## What Election Rig is today

| Area | What we know | Source |
|---|---|---|
| Scale, 2026 general | 1,800+ races, 39 newspapers, 11 states (a Slack post said 1,834 races and 12 states) | Kickoff deck; Diana Dixon, #product-and-tech-all, Nov 4 |
| Age and code | 7+ years old; written in a language most CMS developers aren't comfortable changing; few people know the code | Kickoff deck |
| Main workflow | AP import by state and election date (central) → Races filtered by state and market → Collections (grouped, ordered, headed) → Chart items embedded in WordPress articles | Kickoff deck |
| Local races | Google Sheets import for races AP doesn't cover; seven-step process on a shared elections account, mostly run by one person | Kickoff deck; Confluence "How to prepopulate local election results" |
| Print | Collections export print1 (race charts), print2 (county by county), print3 (referendums) to FTP for agate | Kickoff deck |
| Election night | AWS Lambdas refresh Collections whose IDs were added to CloudWatch rules by hand about a week ahead (IDs due Oct 26 for Nov 3) | Kickoff deck |
| Election-night errors | 500 errors came from database connection limits; scaling the database fixed them; the Python serverless code is sound | Kickoff deck (Mu Yang) |
| Automation spikes | CI-14557 dynamic AP race discovery (done); CI-14877 Enhanced Voting scraper pulled all Virginia races live on Nov 3; CI-15597 print FTP export proven live | Kickoff deck |
| Future of current rig | The 2026 midterms were its final major use; it keeps running alongside the new tool until migration, and the local Google Sheets workflow must keep working | Kickoff notes; kickoff deck; Product Roundup notes, Nov 9 |

### The other results tools in use (from "KG - Nov. 2026")

About 99 results pages in 14 states, Nov 2026. "Combining existing systems" means these:

| Tool | Where | What it did |
|---|---|---|
| Election Rig (AP statewide and local) | PA, FL, MD, MA (labelled "Mass rig"), NY, OH, VA, CT, and Press Democrat for Napa | Web and print results; local races via Google Sheets or the Virginia scraper |
| AP embeds (iframes) | Chicago (web), Michigan, Twin Cities key races, NY Daily News, NH and RI pages for Boston-area papers, BANG; Norcal pages labelled "AP Statewide - AP" | AP-hosted results; also used for maps and balance of power on rig pages |
| SCNG tool | Southern California papers, San Diego Union-Tribune, parts of BANG and Press Democrat | Separate results pages at /election-results |
| Denver tool | Denver Post and Colorado papers (about 28 pages) | Embed generator; statewide, county-by-county, maps, turnout comparison; beat company-wide engagement per the kickoff notes; rig used for Denver print only |
| Old Press Democrat tool | Press Democrat (Sonoma) | Local and statewide results |
| Twin Cities local tool | Pioneer Press | Local charts |

Chicago used AP embeds for web and the rig for print only.

### Pain points already visible (to explain in interviews)

From the kickoff deck:
- **Manual race imports** — Product/Audience imports AP races, and newsrooms can't build Collections until it lands. Virginia's import landed in the sprint after the Collection deadline.
- **A week of lead time** — Collection IDs due early so a developer can add them to CloudWatch rules in a ticket.
- **Centralized setup** — most of this cycle's Collections were built centrally, not by newsrooms.
- **Fragile local imports** — Google Sheets imports run through a multi-step process on a shared account.
- **Hard to use** — clunky, unintuitive, often no error handling; people don't know what went wrong or how to fix it.
- **Few people know the code.**

From Slack:
- **Maps not loading** — Pennsylvania governor county map stuck on a spinning wheel (John Misinco, Nov 3).
- **Missing local races** — Virginia council, school board and referendum races missing two weeks out (Sean Kennedy, Oct 21 and 26).
- **Unclear setup deadlines** — when sheets and Collections must be done (Steve Earley, Sept 22).
- **Manual entry for non-AP races** — Baltimore (Steve Earley, Mar 18).
- **Confusing metrics** — "Election Rig visits" vs page views (David Schutz, Nov 5).

### Reader data (Election Rig Dashboard, Nov 3–6, 2026, via the kickoff deck)

- Pages with Election Rig charts: about 290,000 views and 210,000 visits on about 200 results pages.
- About 29 seconds per visit; 1 in 6 visits went on to another story.
- 224 newsletter signups and 13 subscriptions started from those pages.
- Biggest pages: Virginian-Pilot Virginia local results (~48,000 views), Sun Sentinel South Florida (~30,000), Orlando Sentinel Florida (~23,000). Local races AP doesn't cover drove the top page.
- Adoption: the rig ran on 44 sites, only 21 had 100+ visits, and 5 sites drove about 70% of views.
- 2025: stories about local races drew about 582,000 views; voter guides about 19,600 views with no tool to support them.

## Goals and success metrics (proposed at kickoff)

The goal: an election tool newsrooms adopt on their own.

| Metric | Measure | Baseline | Proposed target |
|---|---|---|---|
| Adoption (primary) | Sites with 100+ visits to Election Rig pages each election | 21 sites in the 2026 midterms; 5 drove ~70% of views | 30+ sites by the 2028 general |
| Time saved | Time from race import to published chart | To be measured in a CRUX walkthrough | Half the setup time; no developer ticket to import races |
| Reader engagement | Time per visit and onward reading | ~29 seconds; 1 in 6 read another story | Hold or grow as more sites adopt |

Guardrails: results match AP, charts update quickly, no drop in Core Web Vitals, no election-night downtime.

## MVP (as proposed at kickoff)

1. Import every AP race, all fields, every state, several elections at once.
2. Editors can override any AP field, including race calls.
3. Organize races into Collections; reorder; edit headings.
4. Charts on sites and in apps, reusable across sites.
5. Live updates on election night with no manual refresh.
6. Print export (agate) as today.
7. Newsrooms and print can set up and test before election night.
8. Local Google Sheets races keep working in today's tool until migrated.

Added in the kickoff discussion (notes): native support for the mobile apps and app home-screen widgets; charts as native Gutenberg blocks for performance and SEO. Diana and Kalani are finalizing which items are launch requirements and which are fast-follow.

Still open: maps, an e-edition view, uncontested races, runoffs, ranked-choice. Future: voter guides, "last updated" time on charts, chart images for print, local results scraped from county and state sites.

## Platform proposal (blocking decision)

Mu Yang's hybrid: the election admin becomes its own app on the Mission Control codebase, with Auth0 single sign-on so editors log in to WordPress once; charts render as native Gutenberg blocks instead of iframes. The deck says the UX interviews will shape the final workflow and whether the database schema changes. Owner and date for the decision still needed.

## Plan and research phases

| Kickoff phase | When | Gate | Research work |
|---|---|---|---|
| Align | Now – Dec 2026 | Workflow defined, platform decided | Recruit Nov 11–20; UserZoom interviews Nov 16–Dec 4, co-run by Karl and Heather; CRUX timed walkthrough of today's workflow; synthesis Dec 7–18 into requirements v1 |
| Discover | Early 2027 | Go / no-go | Reader research (analytics + Maze survey or test) alongside spikes 1–7 |
| Build | 2–3 quarters, target | Pilot ready | Maze prototype tests with newsrooms and readers before and during build |
| Pilot | Off-year 2027 races | Ready for 2028 | A few newsrooms first, today's tool alongside; measure adoption and setup time |

The kickoff notes confirm editorial UX interviews and discovery run through the end of 2026. They also say the goal is a robust platform for "the 2020 election cycle," which is almost certainly a transcription error for 2028 (the deck says 2028).

### Next steps from the kickoff (Gemini notes)

| Owner | Action |
|---|---|
| Diana Dixon | Finalize the MVP list with Kalani: launch requirements versus fast-follow |
| Diana Dixon | Set up discovery meetings with Kalani and newsroom power users who use the election tool, to gather workflow feedback |
| Karl Uschold | Write up the research plan: what the newsroom interviews would look like and what they'd collect, for Diana, Brian and Kalani. Covered by the "What the interviews will collect" section of the case doc |

**Why UserZoom and Heather (short version):** UserZoom is already paid for through December 2026, we've run moderated sessions in it, and it keeps recordings, consent terms and highlight reels in one place. Heather builds our research setups in it, and two researchers let 10 to 14 sessions fit before Dec 4. Renewing UserZoom versus moving to Maze is undecided; if the interviews have to wait for that decision, either platform has tools for analyzing and visualizing findings that a regular video call recording lacks. Full case for Brian, Diana and Kalani: "Election Rig Research: Heather and UserZoom" doc.

## Team assumptions to test

Written before fieldwork so findings can be scored against them afterward.

1. **Newsrooms want to set up their own races and charts.** The whole adoption goal rests on this; some may prefer central setup.
2. **Setup effort, not reliability, is the biggest pain.** Election-night errors were a database limit that's now fixed.
3. **Sites stay off the rig because setup is hard,** not because their own tool (Denver, SCNG, AP embeds) does something the rig can't. The kickoff notes already point the other way for Denver, whose embed generator and county-by-county results beat company-wide engagement.
4. **Markets differ in configuration, not in workflow** — one tool can serve everyone with settings.
5. **Readers want more charts and maps,** rather than faster, simpler, more legible results.
6. **Local races are where we win readers** — the top rig page was Virginia local results.
7. **Print needs stay as they are today** (agate files) for MVP.
8. **The Virginia scraper approach can scale** to other states' local races.

## The maps problem (open, not MVP)

Every market has different district boundaries, and they change with redistricting. Today maps come from AP embeds and the Denver tool; the rig's county map failed for Pennsylvania on Nov 3. Questions:

- Which map levels do editors need on election night, and which do readers use?
- What does the Denver tool's map and county-by-county work do well that a new tool must match?
- Where do boundary files come from, and who maintains them? (Candidates: Census TIGER/Line for federal and state districts; county and city GIS offices for local.)
- Is a map the right display for every race, or would a ranked table or chart serve readers better?

## People

**Kickoff invitees (Nov 10, 2026, organized by Kit Arper):** Kit Arper, Karl Uschold, Jason Wulkowicz, Mu Yang, Diana Dixon, Tara Murphy, Brian Vigil, Kyle Boggs, Seth Kressmann, Kalani Gordon, Kristen Althoff, Robert Kirkemo, CJ Jacobs.

**Research team:** Karl Uschold (CRUX) and Heather Dzierson (Customer Experience; builds UserZoom study setups, co-moderates).

**Named in the deck and notes:** Diana Dixon (presenter; owns MVP list and discovery meetings), Kalani Gordon (MVP list and discovery meetings with Diana), Brian Vigil (receives the research write-up), Mu Yang (platform proposal), David Leal (AP import spike CI-14557), George Buce (Virginia scraper spike CI-14877), Ian (advice on requirements and a dedicated team).

**Possible interview participants** (confirm role and market before inviting):
- Newsroom, on the rig: Sean Kennedy (Virginia), Steve Earley (Baltimore), John Misinco (Pennsylvania), Sun Sentinel and Orlando Sentinel editors.
- Newsroom, on other tools: Denver Post (Denver tool), an SCNG paper, Press Democrat, Pioneer Press, Chicago Tribune (AP embeds web, rig print), a Michigan paper (AP embeds only).
- Central setup: whoever imported AP races and ran the Google Sheets imports this cycle; the "KG" sheet owner.
- Print: a Chicago or Pennsylvania print editor using agate.
- Small sites that didn't reach 100 visits.

## Interviewer method (Dana Whitfield persona, summarized)

- Stories over opinions: "Tell me about the last time…", never "Would you…".
- Never leading; never name the intended benefit before the participant describes their experience.
- Neutral and warm; no reaction that signals a "right" answer.
- Follow the energy — hesitation, laughter or a pause is where the real material is.
- Comfortable with silence (3–5 seconds).
- One question at a time; any yes/no gets "Tell me more about that."
- Before using any question, check: leading? double-barreled? yes/no trap? asks for a prediction? uses jargon?

## Deliverables so far

- **Election Rig Research: Heather and UserZoom** (Claude Doc) — the short case for Brian, Diana and Kalani: why include Heather and use UserZoom, how the sessions would work, and a note on the UserZoom-or-Maze renewal.
- **Election Rig — The Case for Editor Interviews** (Claude Doc) — the longer case: reasons, platform comparison, objections and answers, guardrails, what the interviews will collect and hand over (Karl's kickoff action item), plan aligned to the kickoff's gates. Note: written before the UserZoom decision, so it compares Zoom (video) with Maze; needs updating to UserZoom.
- **Election Rig — Editor Moderator Guide (18 min)** (Claude Doc) — script for newsroom, central setup and print participants on any tool; probes, cut order, glossary, debrief form. Setup line still says Zoom; switch to UserZoom.
- This brief.

## Key sources

- Google Drive: "Election Rig Rebuild Kickoff" deck and "2025-26 Elections" sheet (see Key links)
- Slack: #elections, #product-and-tech-all
- Confluence: "Important Elections Docs" (AE1), "How to prepopulate local election results for election rig" (AE1), "Elections" and "Cloudwatch Rules" (CI), "Election Results Pages — Performance by Page Technology" (DAT)
- Jira: CI-14557, CI-14877, CI-15597 (spikes); DAT-4049, DAT-4081 (dashboards); DREAMT-3399/3400/3418 (app election embeds)
- Reports cited in the deck: MNTP Election Coverage 2025; Election Rig Dashboard
- Gmail: Kickoff Gemini notes, Nov 10 2026 (see Key links); Strategic Product Roundup notes, Nov 9 2026

## Where files live

- **Drive:** Shared drives › TRB-Digital Subs › Platforms › CRUX › Election Rig (01 Research, 02 Design): https://drive.google.com/drive/folders/1AXoTjbr93oz0es7emp635n4xrvLGb5Tm
- **On Karl's Mac:** ~/Library/CloudStorage/GoogleDrive-kuschold@medianewsgroup.com/Shared drives/TRB-Digital Subs/Platforms/CRUX/Election Rig
- The Google Drive connector can't see shared drives; use the synced folder on the Mac via device tools.

## Open questions

1. The notes record no decision on the platform or the success metrics. Who owns the platform decision, and by when?
2. What exactly is the pushback on editor interviews, and from whom? (The deck and notes both schedule them.)
3. How do Diana's discovery meetings with power users and the CRUX interviews fit together: one participant list and one guide, or separate?
4. Who runs the CRUX timed walkthrough, and when?
5. Which sites count toward the 44 that ran the rig, and which 23 fell under 100 visits?
6. Renew UserZoom or move to Maze when the contract ends in December 2026? Does either need an AI/data review?
7. Heather to confirm our UserZoom plan includes moderated sessions (UserZoom is being folded into UserTesting, where they're called Live Conversations), and her availability Nov 16–Dec 4.
8. The deck and notes say 11 states and a Slack post said 12; which is right?

## Status log

- **Nov 10, 2026** — Project started. Drive folder created; stakeholder case, moderator guide and this brief drafted. Kickoff held. Kickoff deck and 2025-26 Elections sheet reviewed; guide widened to all tools and to central and print staff; case and plan aligned to the kickoff's December gate. Kickoff notes reviewed: added Karl's action item (covered by the case doc's new "What the interviews will collect" section), Diana's parallel discovery meetings, the app and home-screen widget requirement, and Denver's engagement result. Interviews moved to UserZoom, co-run with Heather Dzierson; short case doc for Brian, Diana and Kalani added; Drive folder link added.
