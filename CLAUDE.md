# Zorbit Service: zorbit-app-help_support

## Purpose

Scaffold-only placeholder module that populates the **Support Center** L1 scaffold in the sidebar.

Created 2026-04-27 (cycle-106 by soldier (ll)) per owner directive MSG-101 + MSG-105 to make the Support Center scaffold non-empty.

## Status

`scaffold-only` — no backend code, no DB, no events. The manifest carries:
- `placement.scaffold = "support_center"` (slug, lowercase, canonical)
- `placement.scaffoldSortOrder = 50`
- `placement.capabilityArea = "submit_a_ticket"`

When the SPA pulls the menu, this manifest causes the Support Center bucket to render with one Coming-Soon module entry.

## Future scope

When the real ticketing / knowledge-base implementation lands, replace this manifest's `_status` field and add:
- ticket CRUD entities
- knowledge-base articles
- community-forum integration
- JAYNA-driven first-line support

## Architecture rules (when filled in)

- REST API grammar: `/api/help_support/api/v1/{namespace}/...`
- Namespace: G for catalog, O for tenant tickets
- Events: `help_support.ticket.created/updated/resolved`
- PII: contact details via PII Vault tokens only
