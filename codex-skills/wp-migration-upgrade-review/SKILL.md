---
name: wp-migration-upgrade-review
description: WordPress migration and upgrade review for Codex. Use when reviewing schema updates, version guards, data backfills, dbDelta usage, release safety, and backwards-compatibility risks.
---

# Codex WordPress Migration Review

## Purpose

Use this skill when Codex should review plugin or theme upgrade routines for safety, idempotency, rollout risk, and data integrity.

## Focus Areas

- Versioned upgrade routines
- Schema migrations and `dbDelta()`
- Backfills and batch processing
- Upgrade flags and partial-state handling
- Release and rollback risk

## Workflow

1. Identify activation, upgrade, and backfill entry points.
2. Check version guards and destructive operations first.
3. Review batching, schema safety, and resumability.
4. Load only the needed shared references from `../../claude-skills/wp-migration-upgrade-review/references/`.
5. Report findings with severity, file references, and safe remediation paths.

## References

- `../../claude-skills/wp-migration-upgrade-review/references/versioned-upgrades.md`
- `../../claude-skills/wp-migration-upgrade-review/references/schema-and-backfill-guide.md`

