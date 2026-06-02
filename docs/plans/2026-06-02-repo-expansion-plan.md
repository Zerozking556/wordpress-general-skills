# WordPress Skills Expansion Plan

> **Repo:** `jorgerosal/wordpress-skills`
> **Date:** 2026-06-02
> **Purpose:** Compare the current pack against adjacent WordPress agent-skill repos and identify the highest-value expansion paths.

## Current Repo Snapshot

Validated on 2026-06-02:

- Repo validator: **pass** (`python3 scripts/validate_repo.py`)
- Git remote: `https://github.com/jorgerosal/wordpress-skills.git`
- Current pack strength: **17 WordPress review domains** with Claude and Codex coverage
- Current positioning: **AI-assisted WordPress code review, fast triage, and modern development workflows**

Current core domains already covered well:

- Performance
- Security
- Plugin development
- ACF / content modeling
- Headless / WPGraphQL
- Block development
- Theme development
- WooCommerce development
- REST API development
- Admin UI development
- Migration / upgrade review
- Accessibility review
- Test strategy
- CI/CD and release engineering
- WP-CLI and ops
- Playground
- PHPStan

## External Landscape Reviewed

Comparable repos reviewed during this pass:

1. `elvismdev/claude-wordpress-skills`
   - Narrower set focused on core code-review skills
   - Lower domain breadth than this repo

2. `respira-press/agent-skills-wordpress`
   - Expands into **site onboarding**, **technical debt audits**, **WooCommerce health checks**, **mobile experience**, **SEO/AEO**, **image optimization**, **internal linking**, and **page-builder migrations**
   - Much broader operational/content surface, less tightly centered on code review

3. `10up/localwp-agent-tools`
   - Focuses on **LocalWP + MCP tooling** and live project context instead of a pure skill-pack library

4. `Automattic/claude-woocommerce-toolkit`
   - Strong specialization around **WooCommerce plugin development**, **finalization**, **upgrade safety**, **rollback safety**, and **traceability analysis**

5. `levantoan/DevVN-WordPress-Skills`
   - Broad WordPress agent-skills positioning across development and operations

## Strategic Read

This repo is already ahead on **code-review breadth**.

The biggest gap is not “more of the same review domains.” The gap is **adjacent high-value workflows** that connect review to action:

- onboarding a WordPress codebase or site quickly
- auditing technical debt at the site/platform level
- migrating legacy builder-heavy sites toward modern WordPress stacks
- handling release/finalization scenarios for WooCommerce more deeply
- supporting enterprise-style WordPress stacks such as Bedrock/composer/multisite/VIP

## Recommended Positioning

Do **not** turn this repo into a generic “do everything in WordPress” pack.

Recommended positioning to preserve:

> **Review-first WordPress skills for Claude and Codex, with carefully selected adjacent workflows that help teams go from triage to safe implementation.**

That means expansions should stay close to:

- review
- migration risk
- modernization
- release safety
- operational safety

Avoid leading with content-marketing automation features unless they clearly support engineering or review workflows.

## Highest-Value Gaps

### Tier 1 — Add next

#### 1) `wp-site-audit-and-onboarding`

Why it matters:

- A strong entry point for new repositories and inherited WordPress projects
- Complements every existing review skill
- Helps the agent decide whether to route into plugin, theme, ACF, WooCommerce, performance, or migration review

Scope:

- detect stack shape: plugin, theme, headless, WooCommerce, multisite, Bedrock, builder-heavy, custom tables
- inventory key plugins and architectural hotspots
- classify risk areas and recommend follow-up skills
- output a prioritized review path

Likely commands:

- `/wp-onboard-review [path]`
- `/wp-onboard [path]`

#### 2) `wp-technical-debt-review`

Why it matters:

- Close to the repo’s review-first identity
- Differentiates from feature-oriented skill packs
- Useful for agencies inheriting client sites and legacy codebases

Scope:

- dead integrations
- orphaned hooks / shortcodes / templates
- outdated patterns
- duplicated logic
- options/transients bloat indicators
- deprecated builder leftovers
- risky custom tables / cron / migrations

Likely commands:

- `/wp-debt-review [path]`
- `/wp-debt [path]`

#### 3) `wp-builder-migration-review`

Why it matters:

- Competitor repos are investing heavily in migration workflows
- High practical value for agencies moving from Elementor/Divi/WPBakery toward blocks or modern themes
- Fits this repo if framed as **migration review and modernization planning**, not auto-conversion magic

Scope:

- detect builder lock-in patterns
- estimate migration risk by source builder
- flag shortcode dependency and dynamic-data coupling
- recommend target architecture: block theme, custom blocks, ACF blocks, hybrid
- produce phased migration recommendations

Start with review/planning only. If successful, later split into source-specific skills:

- Elementor
- Divi
- WPBakery
- Beaver Builder

Likely commands:

- `/wp-builder-review [path]`
- `/wp-builder [path]`

### Tier 2 — Strong follow-ups

#### 4) `wp-woocommerce-upgrade-safety`

Why it matters:

- Automattic’s toolkit shows real demand here
- Narrower and more decision-useful than expanding the generic WooCommerce skill endlessly

Scope:

- upgrade path safety
- payment gateway continuity
- HPOS compatibility during upgrades
- rollback readiness
- webhook compatibility
- changelog / deprecation / version-gate review

Likely commands:

- `/wp-woo-upgrade-review [path]`
- `/wp-woo-upgrade [path]`

#### 5) `wp-enterprise-platform-review`

Why it matters:

- Current pack is light on Bedrock/composer/VIP-style project conventions
- Useful for higher-maturity teams without diluting the repo into non-engineering topics

Scope:

- Bedrock layout
- composer-managed plugins/themes
- environment config safety
- deployment/build assumptions
- multisite constraints
- object-cache / edge-cache / platform-specific gotchas

Likely commands:

- `/wp-platform-review [path]`
- `/wp-platform [path]`

### Tier 3 — Optional, only if positioning broadens

#### 6) SEO / content-ops skills
Examples:

- SEO/AEO review
- image optimization
- internal linking
- content portability

These are real demand areas, but they should come later unless the repo intentionally expands from engineering review into broader site operations and content workflows.

## Recommended Rollout Order

### Phase 1

1. `wp-site-audit-and-onboarding`
2. `wp-technical-debt-review`

Reason:

- highest leverage across the entire existing pack
- minimal brand drift
- easiest to route into current skills

### Phase 2

3. `wp-builder-migration-review`
4. `wp-woocommerce-upgrade-safety`

Reason:

- strong market pull
- practical agency value
- pairs well with existing migration and WooCommerce coverage

### Phase 3

5. `wp-enterprise-platform-review`

Reason:

- useful, but narrower audience
- best after the audit/debt/migration story is established

## Implementation Notes

For each new domain, keep the repo’s existing pattern:

1. Claude skill under `claude-skills/`
2. Matching Codex wrapper under `codex-skills/`
3. Two Claude slash commands under `commands/`
4. README updates
5. CHANGELOG updates
6. Optional search-oriented docs guide page when the workflow has strong standalone search intent

## Suggested Acceptance Criteria For New Skills

Each new skill should include:

- clear “when to use” and “when not to use” sections
- quick triage search patterns
- deeper structured review workflow
- explicit cross-skill handoffs
- output format with severity definitions
- realistic WordPress examples
- at least 2–4 supporting reference docs for Claude skills

## Immediate Next Move

Recommended next implementation target:

**Build `wp-site-audit-and-onboarding` first.**

Why this first:

- best top-of-funnel skill for the repo
- improves first-use experience
- creates a natural dispatcher into the existing 17-domain pack
- offers strong differentiation without abandoning the repo’s review-first identity
