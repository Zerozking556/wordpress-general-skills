# Claude WordPress Skills

<p align="center">
  <img src="public/Claude%20Skills%20for%20Wordpress.jpg" alt="Claude WordPress Skills" width="100%" />
</p>

<p align="center">
  <a href="https://claude.ai/code">
    <img src="https://img.shields.io/badge/Claude%20Code-Ready-1f6feb?style=for-the-badge" alt="Claude Code Ready" />
  </a>
  <img src="https://img.shields.io/badge/WordPress-6%20review%20domains-21759b?style=for-the-badge&logo=wordpress&logoColor=white" alt="WordPress review domains" />
  <img src="https://img.shields.io/badge/Commands-12%20slash%20commands-2da44e?style=for-the-badge" alt="12 slash commands" />
  <img src="https://img.shields.io/badge/Focus-Code%20review%20and%20triage-8250df?style=for-the-badge" alt="Code review and triage" />
</p>

Professional WordPress skills for [Claude Code](https://claude.ai/code), built for code review, fast triage, and modern WordPress development workflows across performance, security, plugins, blocks, themes, and WooCommerce.

## Why This Pack

- Structured review workflows for real WordPress codebases
- Quick triage commands for fast audits before deeper review
- Specialized guidance for Gutenberg, block themes, and WooCommerce
- Cross-skill handoffs when a finding belongs in another domain
- Line-numbered, severity-based review output with fix guidance

## Available Skills

| Skill | Focus | Status |
|-------|-------|--------|
| **wp-performance-review** | Performance bottlenecks, query patterns, caching, cron, asset loading | ✅ |
| **wp-security-review** | XSS, SQL injection, CSRF, auth checks, file upload risks | ✅ |
| **wp-plugin-development** | Plugin structure, lifecycle hooks, Settings API, i18n, WordPress.org standards | ✅ |
| **wp-block-development** | `block.json`, React/JSX editor patterns, render callbacks, Interactivity API | ✅ |
| **wp-theme-development** | `theme.json`, templates, template parts, style variations, FSE patterns | ✅ |
| **wp-woocommerce-dev** | HPOS, CRUD APIs, payment gateway patterns, cart fragments, template overrides | ✅ |

## Installation

Pick the install path that matches how you use Claude Code.

### Which Option Should You Use?

- **Use Option 1** if you want the skills available inside one project for yourself or your team
- **Use Option 2** if you want the skills available across your machine
- **Use Option 3** if you only want one skill and are fine updating it manually

### Option 1: Add to Your Project (Recommended)

Best for shared projects, client work, and teams.

```bash
# In your project root
git submodule add https://github.com/jorgerosal/wordpress-skills.git .claude/plugins/wordpress
git commit -m "Add WordPress Claude skills"
```

To update later:

```bash
git submodule update --remote .claude/plugins/wordpress
git add .claude/plugins/wordpress
git commit -m "Update WordPress Claude skills"
```

### Option 2: Install for Your User Account

Best for solo usage across multiple projects.

```bash
git clone https://github.com/jorgerosal/wordpress-skills.git ~/.claude/plugins/wordpress
```

To update later:

```bash
cd ~/.claude/plugins/wordpress
git pull
```

### Option 3: Install One Skill Manually

Best if you only want a single skill and do not need the full pack.

```bash
# Copy just the performance review skill
cp -r skills/wp-performance-review ~/.claude/skills/
```

If you use this option, updates are manual. Re-copy the skill when the source changes.

### Verify the Install

After installing:

1. Restart Claude Code if needed
2. Open a WordPress project
3. Run a command such as:

```bash
/wp-perf-review
```

## Slash Commands

Each skill includes a full review command and a faster triage command.

| Command | Use Case |
|---------|----------|
| `/wp-perf-review [path]` | Full performance review with grouped findings and fix guidance |
| `/wp-perf [path]` | Fast performance scan for critical patterns |
| `/wp-sec-review [path]` | Full security review for exploitable patterns |
| `/wp-sec [path]` | Fast security scan for common high-risk issues |
| `/wp-plugin-review [path]` | Full plugin architecture and standards review |
| `/wp-plugin [path]` | Fast plugin structure and standards scan |
| `/wp-block-review [path]` | Full Gutenberg block review across PHP and JS/JSX |
| `/wp-block [path]` | Fast block API and `block.json` scan |
| `/wp-theme-review [path]` | Full block or classic theme review |
| `/wp-theme [path]` | Fast theme structure and FSE scan |
| `/wp-woo-review [path]` | Full WooCommerce extension review |
| `/wp-woo [path]` | Fast WooCommerce compatibility and risk scan |

### Quick Examples

```bash
# Review the current project for performance issues
/wp-perf-review

# Run a fast security scan on a plugin
/wp-sec wp-content/plugins/my-plugin

# Review a custom block package
/wp-block-review wp-content/plugins/my-blocks

# Review a block theme
/wp-theme-review wp-content/themes/my-theme

# Check a WooCommerce extension before release
/wp-woo-review wp-content/plugins/my-woo-extension
```

When installed from the marketplace, commands are namespaced:

```bash
/wordpress-skills:wp-perf-review [path]
/wordpress-skills:wp-perf [path]
```

## Natural Language Usage

You can also invoke the skills without slash commands. Ask naturally, for example:

```text
Review this plugin for performance issues
Audit this theme for security problems
Help me debug this block.json setup
Check this WooCommerce extension for HPOS issues
Review this theme before launch
Find slow queries in this plugin
```

Claude will match the request to the most relevant skill and follow that review workflow.

### Trigger Phrases

| Skill | Common Triggers |
|-------|------------------|
| `wp-performance-review` | "performance review", "slow WordPress", "slow queries", "high-traffic", "timeout", "out of memory" |
| `wp-security-review` | "security audit", "XSS", "SQL injection", "CSRF", "nonce verification", "capability check" |
| `wp-plugin-development` | "plugin review", "plugin architecture", "activation hook", "Settings API", "Plugin Check" |
| `wp-block-development` | "block review", "Gutenberg", "block.json", "InnerBlocks", "Interactivity API", "dynamic block" |
| `wp-theme-development` | "theme review", "block theme", "theme.json", "FSE", "template parts", "style variations" |
| `wp-woocommerce-dev` | "WooCommerce review", "HPOS", "payment gateway", "cart fragments", "Action Scheduler" |

## What Each Skill Covers

All six skills produce structured findings with severity labels (`Critical`, `Warning`, `Info`), file references, and concrete recommendations.

### `wp-performance-review`

- Database query anti-patterns
- Expensive hooks and page-load writes
- Object cache and transient usage
- AJAX, HTTP, and polling bottlenecks
- Template-level N+1 patterns
- Asset loading and cron issues

### `wp-security-review`

- XSS and output escaping issues
- SQL injection risks
- CSRF and nonce validation gaps
- Capability and authorization mistakes
- File upload handling risks
- Dangerous functions and sensitive data exposure

### `wp-plugin-development`

- Plugin headers and structure
- Activation, deactivation, and uninstall flows
- CPT and taxonomy registration
- Settings API usage
- Hook design and priority issues
- Internationalization and WordPress.org readiness

### `wp-block-development`

- `block.json` schema validation
- `edit` and `save` function patterns
- Render callbacks and dynamic blocks
- Attribute handling and deprecations
- Interactivity API usage
- Build setup and source/build review

### `wp-theme-development`

- `theme.json` validation
- Template hierarchy and required files
- Template parts and block markup
- Global styles and spacing systems
- Style variations and patterns
- Classic-to-block migration guidance

### `wp-woocommerce-dev`

- HPOS compatibility
- WooCommerce CRUD usage
- Payment gateway safety patterns
- Cart fragments and performance concerns
- Action Scheduler usage
- Template override quality and hook preservation

## Requirements

- [Claude Code](https://claude.ai/code) CLI
- A local or project-based Claude skills setup

No additional dependencies are required.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for setup, structure, and submission guidance.

Common contribution paths:

- Improve or modernize existing guidance
- Add missing edge cases and anti-patterns
- Expand examples and reference docs
- Propose or implement new WordPress skills

## License

MIT License. See [LICENSE](LICENSE) for details.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for release history.

---

These skills reflect practical WordPress engineering patterns and tradeoffs. They are not affiliated with or endorsed by WordPress, WooCommerce, or any hosting platform.
