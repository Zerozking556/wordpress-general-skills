# WordPress Workflow Routing Guide

Use this guide to select the smallest useful specialist set:

| Signal in the request | Start with |
|---|---|
| Unfamiliar repository or inherited site | `wp-site-audit-and-onboarding` |
| Elementor, Astra, layout, responsive, or visual builder | `wp-theme-development` plus the relevant quality skill |
| Plugin, hook, lifecycle, Settings API, or i18n | `wp-plugin-development` |
| Block editor or `block.json` | `wp-block-development` |
| Store, checkout, HPOS, or WooCommerce extension | `wp-woocommerce-dev` |
| ACF, CPT, taxonomy, fields, or content relationships | `wp-acf-and-content-modeling` |
| REST route, permission callback, or schema | `wp-rest-api-development` |
| Headless frontend or WPGraphQL | `wp-headless-and-wpgraphql` |
| Admin menu, settings page, notice, or admin UX | `wp-admin-ui-development` |
| Slow query, cache, asset, cron, or load issue | `wp-performance-review` |
| Auth, upload, XSS, SQLi, CSRF, or secret exposure | `wp-security-review` |
| Keyboard, focus, semantics, labels, or contrast | `wp-accessibility-review` |
| Test coverage or regression planning | `wp-test-strategy` |
| Database/schema upgrade or backfill | `wp-migration-upgrade-review` |
| Pipeline, packaging, deployment, or rollback | `wp-ci-cd-and-release-engineering` |
| WP-CLI, multisite, automation, or operations | `wp-wpcli-and-ops` |
| Playground blueprint or reproducible demo | `wp-playground-development` |
| PHPStan configuration or baseline | `wp-phpstan-review` |

For mixed work, start with onboarding, then route to no more than five focused specialists before making changes.
