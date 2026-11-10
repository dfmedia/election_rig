# Backend

Placeholder until the platform decision (see [`../docs/decisions/0001-platform.md`](../docs/decisions/0001-platform.md)).

## What it must do (MVP as proposed at kickoff)

1. Import every AP race, all fields, every state, several elections at once — no developer ticket.
2. Let editors override any AP field, including race calls.
3. Organize races into Collections; reorder; edit headings.
4. Serve charts to sites and apps, reusable across sites.
5. Live updates on election night with no manual refresh (no hand-edited CloudWatch rules).
6. Print export (agate print1/print2/print3) as today.
7. Let newsrooms and print set up and test before election night.
8. Keep local Google Sheets races working in today's tool until migrated.

## Prior work to build on

- CI-14557 dynamic AP race discovery (done)
- CI-14877 Enhanced Voting scraper (pulled all Virginia races live on Nov 3)
- CI-15597 print FTP export (proven live)
- Election-night 500s were database connection limits; the Python serverless refresh code is sound.

## Guardrails

Results match AP; charts update quickly; no election-night downtime.
