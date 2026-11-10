# Election Rig — The Case for Editor Interviews

Nov 10, 2026 · @Karl

## The ask

Interview 10 to 14 people who published election results this cycle, one-on-one on Zoom, 18 minutes each, between Nov 16 and Dec 4. Include newsroom editors on Election Rig and on other tools, the central staff who did most of the setup, and print editors. Bring in Maze later, for reader research and design testing.

The kickoff deck already makes interviews step one. Its first ask is to schedule UX interviews with CRUX, architecture agrees everything starts there, and the December gate is "workflow defined, platform decided." The kickoff notes confirm that editorial UX interviews and discovery run through the end of the year. The open question is how to run them, and Zoom costs under 5 hours of participant time and no new tools.

## Why interview editors one-on-one, now, on Zoom

1. **Leadership already put interviews first.** The kickoff's first ask is UX interviews with CRUX. The platform decision and the database design both wait on the workflow they define.
2. **The deadline is December.** The first gate is "workflow defined, platform decided" by the end of December, and memory of Nov 3 fades by then. Zoom can start next week; buying a new tool can't.
3. **It costs nothing new.** Zoom is already licensed and everyone uses it daily. No procurement, no security review, no training.
4. **Screen share shows the real work.** People walk us through the rig, the Google Sheets and their other tools as they actually use them. A two-minute clip of someone fighting the map tool moves engineering faster than any summary.
5. **We're replacing several tools, not one.** The "2025-26 Elections" sheet lists about 99 results pages in 14 states using at least six tools: Election Rig, AP embeds, the SCNG tool, the Denver tool, Press Democrat's older tool and a Twin Cities local tool. The kickoff notes add that Denver's embed generator and county-by-county results beat company-wide engagement. Each tool exists for a reason, and only conversations surface it.
6. **The success metrics need baselines and reasons.** The rig ran on 44 sites, but only 21 had 100 or more visits, and 5 drove about 70% of views. Interviews explain why sites didn't adopt it and give a first read on setup time, the two numbers the targets depend on.
7. **Maze gives us a path to scale.** When we move to readers and design testing, Maze adds what Zoom lacks, without redoing this phase.

## Pros and cons: Zoom now, Maze later

Zoom wins this phase because we're studying an internal tool and an event that already happened. Maze wins once we're testing designs and talking to readers at scale.

|  | Zoom (now) | Maze (later) |
| --- | --- | --- |
| Cost and approval | Already licensed; no procurement | New seats or plan; procurement and an AI/data review are likely |
| Editor familiarity | Everyone uses it daily | A new link and flow for editors |
| Seeing the real workflow | Live screen share of the rig, sheets and CMS behind logins | Built for prototypes and live sites, less suited to internal admin tools |
| Recording and transcripts | Cloud recording and transcripts, if enabled on our account | Built-in recording, transcripts, summaries and highlights |
| Analysis | Manual tagging in a sheet; slower | Highlights grouped into patterns automatically; faster |
| Scale | One moderator per session; about 12 sessions is the practical ceiling | AI-moderated and unmoderated studies can run many sessions at once |
| Reader research | Weak; hard to recruit and run readers one-on-one | Strong; surveys, prototype tests and live-site tests with readers |
| Design phase | Not built for prototype testing | Figma prototype testing for the rebuilt rig |
| Main risk | Editors may feel recorded or evaluated (see guardrails) | AI moderator reportedly needs a higher-tier plan |

The honest con of starting on Zoom: synthesis is manual, so budget about a week for one researcher to tag and summarize 12 sessions.

## Likely objections and answers

| Objection | Answer |
| --- | --- |
| "We're already doing a postmortem." | Keep it. The retro covers what broke; interviews cover how people work every day. Findings feed straight into the retro. |
| "Diana is already setting up discovery meetings with power users." | Run them as one effort: one participant list, the same guide and shared notes, so power users are asked once. Kalani can co-recruit and observe. |
| "Let architecture decide the platform first." | The kickoff proposal says the interviews will shape the final workflow and whether the database schema changes. Deciding first risks building the wrong workflow. |
| "We already know what's broken." | The deck lists the strains: manual imports, a week of lead time, central setup, a fragile local import. Interviews show what each one costs in hours and which ones keep sites off the rig. |
| "Editors are too busy." | 18 minutes, booked at their convenience after election wrap-up. That's less time than one more round of Slack troubleshooting. |
| "Just send a survey." | A survey tells us what, not how or why. We'll survey later to size the problems the interviews find. |
| "Recording staff makes people uneasy." | Recording is opt-in, quotes are anonymized, and nothing reaches managers as raw footage. See guardrails. |
| "Why not buy Maze now?" | Procurement would push us past the December gate. Maze earns its cost in the reader and design phases. |
| "Let product chat with editors informally." | Informal chats aren't comparable across markets and tools. One guide asked the same way gives evidence we can count. |

## Guardrails for editors

These sessions study the tool, never the person. Saying that clearly, and acting on it, removes most of the pushback.

- **Opt-in recording.** Ask on the call; if an editor declines, take notes only.
- **Anonymized findings.** Quotes are tagged by market size and role, never by name.
- **Restricted recordings.** Kept in the project's Drive folder, research team only, deleted 90 days after synthesis. Managers get findings, not footage.
- **No performance link.** Say it in the opening script and in the invite.
- **Heads-up where needed.** If a participating newsroom has a guild unit, give it a short note before scheduling.

## What we'd ask

Every question asks for a specific, recent moment, not an opinion. The full 18-minute guide is a separate doc.

**Newsroom, central setup and print staff (now, on Zoom)**

| Area | Example question |
| --- | --- |
| Setup before election night | "Walk me through how you got your races ready this fall, starting with the first thing you did." |
| Tool choice | "Tell me about how you ended up using \[tool\] for results." |
| Election night | "Take me back to Nov 3. What were you doing when the first results started coming in?" |
| Data sources | "Tell me about a race that didn't come in the way most of the others did." |
| Workarounds | "Tell me about something you did outside \[tool\] to get your results published." |
| Getting help | "Tell me about the last time you got stuck. Who did you reach out to?" |
| Readers and print | "Tell me about how you decided what readers would see on your results pages." |

**Readers (later, via Maze and analytics)**

- Where they look for results on election night, and what they expect to find there.
- Which results views they could read at a glance, and which they had to puzzle over.
- What made them leave a results page, or come back to it.

Baseline from the kickoff deck, Nov 3 to 6: pages with Election Rig charts drew about 290,000 views and 210,000 visits across about 200 results pages. Visits lasted about 29 seconds, 1 in 6 went on to another story, and the pages started 224 newsletter signups and 13 subscriptions.

## What the interviews will collect

This answers the kickoff action item: what the newsroom interviews would collect, for Diana, Brian and Kalani.

| What we collect | From whom | Decision it feeds |
| --- | --- | --- |
| The steps from AP import to published chart, and who does each one | Central setup staff, newsroom editors | Requirements v1; the admin app's workflow; the December gate |
| Steps newsrooms want to do themselves, and where they wait on tickets or people | Newsroom editors | Adoption target; what to automate first |
| Workarounds outside the tool, and roughly how long each takes | All groups | MVP versus fast-follow list |
| Why sites used AP embeds, the Denver tool or the SCNG tool instead of the rig | Newsroom editors on other tools | What the new tool must match; migration order |
| What Denver's embed generator and county-by-county results do well | Denver Post and Colorado editors | Charts, maps and display spike |
| Local-race data sources and how they get in | Newsroom editors, central setup staff | Data import spike; local-race roadmap |
| Election-night problems: refreshes, errors, corrections, race calls | All groups | Live results spike; override and testing requirements |
| Print and e-edition needs | Print editors | Print and outputs spike |
| What editors saw readers respond to on web, in the apps and in home-screen widgets | Newsroom editors | Display spike; reader research questions |
| Self-reported setup time | All groups | Starting point for the CRUX timed walkthrough |

**What we'll hand over**

- Dec 4: participant list and session notes, shared with Diana, Brian and Kalani.
- Dec 18: findings readout with a current-workflow map, ranked workarounds and pain points, adoption barriers by tool, and recommendations for requirements v1 and the MVP list.
- Recordings stay with the research team; clips go into the readout only with consent.

## Proposed plan

*(The original doc embeds a 5-phase plan graphic here; see "Plan and research phases" in [docs/project-brief.md](../../docs/project-brief.md).)*

This sits inside the kickoff's proposed path: Align now to December 2026 (gate: workflow defined, platform decided), Discover in early 2027 (gate: go or no-go), Build over two to three quarters, then a pilot in off-year 2027 races. The interview window can't slip, because the December gate depends on it.

## Sources

- Slack #elections and #product-and-tech-all, Oct to Nov 2026 (race counts, Virginia automation, missing races, county map issue, Baltimore hand entry)
- [Strategic Product Roundup notes, Nov 9, 2026](https://mail.google.com/mail/?authuser=kuschold@medianewsgroup.com#all/thread-f:1881403706131794002) (rig retirement, postmortem)
- [Election Results Pages: Performance by Page Technology](https://digital1stmedia.atlassian.net/wiki/spaces/DAT/pages/4106878977/Election+Results+Pages+Performance+by+Page+Technology)
- [How to prepopulate local election results for election rig](https://digital1stmedia.atlassian.net/wiki/spaces/AE1/pages/2809102386/How+to+prepopulate+local+election+results+for+election+rig)
- [Maze: Running moderated and AI-moderated interview studies](https://maze.co/guides/maze-101-guide/moderated-studies/)
- [Maze: Comparing AI features of UX research tools](https://maze.co/blog/comparing-ai-features/)
- [Maze vs. Outset feature comparison](https://maze.co/compare/maze-vs-outset/)
- [TheySaid: UserTesting vs Maze vs TheySaid](https://www.theysaid.io/blog/usertesting-vs-maze-vs-theysaid) (AI moderator plan tier)

* [Election Rig Rebuild Kickoff deck, Nov 10, 2026](https://docs.google.com/presentation/d/1V6BpDQUagaLIEXtUIo7EbSf61FTEPEqmJKHmHFBg6y4/edit?usp=sharing) (asks, timeline, adoption and reader figures, platform proposal)
* [2025-26 Elections sheet](https://docs.google.com/spreadsheets/d/1x7uhjdZNAFvJeiE_sufHbs5ZAYo9HwY2An9ERMOkjHE/edit?usp=sharing), "KG - Nov. 2026" and "2026 Requests" tabs (tools and markets)

- [Kickoff: Election rig rebuild, Gemini notes, Nov 10, 2026](https://mail.google.com/mail/?authuser=kuschold@medianewsgroup.com#all/thread-f:1881504193589777538) (action items, Denver engagement, app and widget requirement, timeline)
