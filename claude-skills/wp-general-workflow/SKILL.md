---
name: wp-general-workflow
description: General WordPress workflow router for Claude Code. Use when building, editing, debugging, reviewing, or operating any WordPress site, including Elementor, Astra, Local/XAMPP, themes, plugins, WooCommerce, performance, security, accessibility, and releases.
---

# WordPress General Workflow

## Purpose

Use this skill as the front door for WordPress work that spans more than one specialty. Classify the request, inspect the real project or site, route to the smallest useful set of specialist WordPress skills, make scoped changes, and verify the result.

This skill coordinates the specialist skills in this repository; it does not replace their deeper reference guidance.

## Operating Rules

1. Identify the target before changing anything: repository, Local/XAMPP site, staging site, production site, or a specific WordPress page.
2. Separate build, edit, diagnose, review, migration, and release work so the verification matches the risk.
3. Preserve unrelated user changes and never expose credentials, database dumps, backups, or local environment files.
4. Back up before database, media, plugin, theme, migration, or destructive content changes.
5. For Elementor/Astra work, prefer native widgets, Flexbox containers, global settings, the Media Library, and responsive controls. Use custom PHP, HTML, CSS, or JavaScript only when the request explicitly needs it.
6. Use the specialist skill names below rather than inventing duplicate review rules.

## Workflow

### 1. Classify the request

- **Build or edit:** page layout, Elementor, Astra, theme, block, plugin, content, or WooCommerce.
- **Diagnose:** blank page, Elementor loading, broken links, Local/XAMPP, Apache/MySQL, 404/500 errors, console errors, or editor failures.
- **Review:** onboarding, code quality, security, performance, accessibility, tests, or release readiness.
- **Data and APIs:** ACF, custom post types, REST, WPGraphQL, migrations, search-replace, or schema changes.
- **Operate and ship:** WP-CLI, backups, CI/CD, packaging, Playground repros, PHPStan, or deployment.

### 2. Discover the environment

Record only what is needed to act safely:

- WordPress root or site URL and whether it is Local/XAMPP, staging, or production.
- Active theme, builder, plugins, WordPress/PHP versions, and relevant logs.
- Pages, templates, files, or routes in scope.
- Existing backups, test commands, and rollback options.

Do not assume that a local URL, admin session, database, or filesystem path is available. Verify it first.

### 3. Route to specialist skills

Use the matching specialist skill for theme, plugin, block, WooCommerce, ACF, REST, WPGraphQL, admin UI, performance, security, accessibility, testing, migration, CI/CD, WP-CLI, Playground, or PHPStan work. For Elementor/Astra visual tasks, combine this workflow with `wp-theme-development` and only the quality skills required by the evidence.

Use one specialist for a narrow task and combine only the specialists required by the evidence.

### 4. Builder and visual quality gates

For Elementor/Astra requests, verify one clear H1, Flexbox containers, consistent global design settings, equal image ratios, native hover/focus states, local Media Library assets with alt text, and no overflow at desktop, tablet, or 390px mobile widths.

### 5. WordPress local and operations checks

For Local/XAMPP work, confirm Apache and MySQL state, the exact site URL, the WordPress admin URL, filesystem permissions, PHP errors, and relevant Apache/MySQL logs. Do not change database records or remove files without a verified backup and a scoped target.

## Verification

- Pages, routes, and internal links return the expected HTTP status.
- WordPress admin and the relevant builder/editor open without a blank screen or new console error.
- Responsive layouts have no overflow at desktop, tablet, and mobile widths.
- Changed code passes the available lint, type, unit, integration, or repository checks.
- Remaining security, accessibility, performance, migration, and rollback gaps are called out.

## Output

Report the target, scope, skills used, changes, verification evidence, failures, remaining risks, and rollback notes.

## References

Load only the routing and quality references needed for this task:

- `references/routing-guide.md`
- `references/quality-gates.md`
