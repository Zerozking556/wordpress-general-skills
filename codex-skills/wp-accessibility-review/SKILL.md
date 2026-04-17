---
name: wp-accessibility-review
description: WordPress accessibility review for Codex. Use when reviewing semantic HTML, keyboard access, focus behavior, form labels, ARIA usage, and accessible interaction patterns in themes, blocks, plugins, and admin screens.
---

# Codex WordPress Accessibility Review

## Purpose

Use this skill when Codex should review WordPress UI implementation for accessibility issues in structure, interaction, and assistive-technology support.

## Focus Areas

- Semantic markup
- Keyboard accessibility
- Focus management
- Forms and labels
- Modals, tabs, accordions, and admin interactions

## Workflow

1. Identify whether the surface is frontend, block output, or admin UI.
2. Check structural semantics and keyboard access first.
3. Review focus behavior, forms, and ARIA usage.
4. Load only the needed shared references from `../../claude-skills/wp-accessibility-review/references/`.
5. Report findings with severity, file references, and practical fixes.

## References

- `../../claude-skills/wp-accessibility-review/references/semantic-and-form-patterns.md`
- `../../claude-skills/wp-accessibility-review/references/interactive-a11y-patterns.md`

