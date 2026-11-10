# Election Rig Rebuild

Research-to-build workspace for rebuilding **Election Rig**, MediaNews Group / Tribune's in-house election results tool, into one tool every newsroom can adopt on its own: set up races and charts without a ticket, publish live results to web, apps and print, and present them clearly to readers.

Owner: Karl Uschold (CRUX). Kickoff: Nov 10, 2026. Target: pilot on off-year 2027 races, ready for the 2028 general.

## Where things are

| Folder | What's in it |
|---|---|
| [`docs/`](docs/) | Project brief (source of truth for context), decision records |
| [`research/`](research/) | Team assumptions, internal staff interviews, reader (customer) research, synthesis |
| [`design/`](design/) | Workflow maps, wireframes, prototypes, design specs |
| [`backend/`](backend/) | Election admin service: AP import, races, Collections, overrides, live updates, print export |
| [`frontend/`](frontend/) | Admin UI for newsrooms and reader-facing results (Gutenberg blocks, app embeds) |

## Phases

| Phase | When | Gate | Main work |
|---|---|---|---|
| Align | Now – Dec 2026 | Workflow defined, platform decided | Internal staff interviews (UserZoom, Nov 16 – Dec 4), timed walkthrough, synthesis → requirements v1 |
| Discover | Early 2027 | Go / no-go | Reader research (analytics + Maze), technical spikes |
| Build | 2–3 quarters | Pilot ready | Backend + frontend build; prototype tests with newsrooms and readers |
| Pilot | Off-year 2027 races | Ready for 2028 | A few newsrooms first, today's tool alongside |

## Key links

- [Kickoff deck](https://docs.google.com/presentation/d/1V6BpDQUagaLIEXtUIo7EbSf61FTEPEqmJKHmHFBg6y4/edit?usp=sharing)
- [2025-26 Elections sheet](https://docs.google.com/spreadsheets/d/1x7uhjdZNAFvJeiE_sufHbs5ZAYo9HwY2An9ERMOkjHE/edit?usp=sharing)
- [Drive project folder](https://drive.google.com/drive/folders/1AXoTjbr93oz0es7emp635n4xrvLGb5Tm)
- Live research docs (Claude Docs, editable): [Heather and UserZoom](https://claude.ai/artifact/9hzYn3rc9nNNTvpvQhBAV4) · [Case for Editor Interviews](https://claude.ai/artifact/LPBWA3AfSnNeLY4SqWji9f) · [Moderator Guide](https://claude.ai/artifact/QUErbZ4u28WjTZ3y2n8FhT)

## Ground rules

- **No participant data in git.** Recordings, raw transcripts and real names stay in UserZoom and the restricted Drive folder. Only anonymized notes (participant IDs like `N03`, `C01`, `P02`) are committed.
- **Ground claims in sources.** Label anything simulated or estimated.
- See [`CLAUDE.md`](CLAUDE.md) for working conventions.
