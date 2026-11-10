# Frontend

Placeholder until the platform decision (see [`../docs/decisions/0001-platform.md`](../docs/decisions/0001-platform.md)).

Two surfaces:

- **Admin UI** for newsroom editors, central setup staff and print editors: import races, build Collections, override results and calls, test before election night, export print.
- **Reader-facing results:** charts as native Gutenberg blocks (not iframes) for performance and SEO, plus native support in the mobile apps and app home-screen widgets.

Guardrails: no drop in Core Web Vitals; accessible, legible results on mobile.
