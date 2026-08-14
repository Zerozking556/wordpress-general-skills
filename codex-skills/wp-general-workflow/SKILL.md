---
name: wp-general-workflow
description: General WordPress workflow router for Codex. Use when building, editing, debugging, reviewing, or operating any WordPress site, including Elementor, Astra, Local/XAMPP, themes, plugins, WooCommerce, performance, security, accessibility, and releases.
---

# Codex WordPress General Workflow

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

| Request area | Specialist skill |
|---|---|
| First-pass classification and routing | `wp-site-audit-and-onboarding` |
| Theme, Astra, templates, styling, or builder-heavy structure | `wp-theme-development` |
| Elementor layout, Flexbox, responsive polish, or visual QA | This workflow plus `wp-theme-development`, `wp-accessibility-review`, and `wp-performance-review` as needed |
| Plugin architecture and lifecycle | `wp-plugin-development` |
| Gutenberg blocks and `block.json` | `wp-block-development` |
| WooCommerce and commerce extensions | `wp-woocommerce-dev` |
| ACF, CPTs, taxonomies, and content models | `wp-acf-and-content-modeling` |
| REST routes and permissions | `wp-rest-api-development` |
| Headless WordPress and WPGraphQL | `wp-headless-and-wpgraphql` |
| Admin screens and settings UX | `wp-admin-ui-development` |
| Slow pages, queries, caching, or asset loading | `wp-performance-review` |
| XSS, SQL injection, CSRF, uploads, or auth | `wp-security-review` |
| Keyboard, focus, labels, semantics, and contrast | `wp-accessibility-review` |
| Unit, integration, or end-to-end coverage | `wp-test-strategy` |
| Versioned upgrades, backfills, or schema changes | `wp-migration-upgrade-review` |
| CI/CD, release gates, artifacts, and rollback | `wp-ci-cd-and-release-engineering` |
| WP-CLI, multisite, automation, or operational runbooks | `wp-wpcli-and-ops` |
| Reproducible Playground environments | `wp-playground-development` |
| PHPStan and WordPress static analysis | `wp-phpstan-review` |

Use one specialist for a narrow task and combine only the specialists required by the evidence.

### 4. Builder and visual quality gates

For Elementor/Astra requests, verify:

- One clear H1 per page and a sensible heading hierarchy.
- Flexbox containers rather than legacy sections/columns where the builder supports them.
- Consistent global colors, typography, spacing, card dimensions, image ratios, and object-fit behavior.
- Native button hover and keyboard focus states with readable contrast.
- Local Media Library assets with useful alt text; do not hotlink external images.
- Desktop, tablet, and a narrow mobile viewport such as 390px without horizontal overflow.
- Every menu item and CTA has a real destination or an explicit placeholder.

### 5. WordPress local and operations checks

For Local/XAMPP work, confirm Apache and MySQL state, the exact site URL, the WordPress admin URL, filesystem permissions, PHP errors, and relevant Apache/MySQL logs. Do not change database records or remove files without a verified backup and a scoped target.

## Verification

Choose checks proportional to the change:

- Pages, routes, and internal links return the expected HTTP status.
- WordPress admin and the relevant builder/editor open without a blank screen or new console error.
- Responsive layouts have no overflow at desktop, tablet, and mobile widths.
- Changed code passes the available lint, type, unit, integration, or repository checks.
- Security, accessibility, performance, migration, and rollback risks are either verified or called out as remaining gaps.

## Output

Report:

1. Target and scope.
2. Specialist skills used and why.
3. Changes made, grouped by behavior.
4. Verification evidence and failures.
5. Remaining risks and rollback notes.

## References

Load only the routing and quality references needed for this task:

- `../../claude-skills/wp-general-workflow/references/routing-guide.md`
- `../../claude-skills/wp-general-workflow/references/quality-gates.md`
