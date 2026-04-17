# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a WordPress skill pack for Claude Code covering six domains:

- Performance reviews
- Security reviews
- Plugin architecture reviews
- Block development reviews
- Theme development reviews
- WooCommerce development reviews

The skills are designed for WordPress 6.x+ codebases and provide structured review workflows, quick triage commands, reference docs, and cross-skill handoffs when a finding belongs in another specialty.

## Repository Structure

```
skills/                        # Skill definitions
  wp-performance-review/
    SKILL.md                   # Main skill file with YAML frontmatter
    references/                # Supporting documentation
  wp-security-review/
    SKILL.md
    references/
  wp-plugin-development/
    SKILL.md
    references/
  wp-block-development/
    SKILL.md
    references/
  wp-theme-development/
    SKILL.md
    references/
  wp-woocommerce-dev/
    SKILL.md
    references/

commands/                      # Slash command definitions
  wp-perf-review.md            # Full performance review command
  wp-perf.md                   # Quick performance triage command
  wp-sec-review.md             # Full security review command
  wp-sec.md                    # Quick security triage command
  wp-plugin-review.md          # Full plugin architecture review command
  wp-plugin.md                 # Quick plugin architecture scan
  wp-block-review.md           # Full block development review command
  wp-block.md                  # Quick block development scan
  wp-theme-review.md           # Full theme development review command
  wp-theme.md                  # Quick theme development scan
  wp-woo-review.md             # Full WooCommerce development review command
  wp-woo.md                    # Quick WooCommerce scan

README.md                      # Public documentation and installation guidance
CHANGELOG.md                   # Release history
CONTRIBUTING.md                # Contribution guidance
```

## Adding New Skills

1. Create directory: `skills/wp-your-skill/`
2. Create `SKILL.md` with YAML frontmatter:
   ```yaml
   ---
   name: skill-name
   description: Trigger phrases and when to use. Max 1024 chars.
   ---
   ```
3. Add references in `skills/wp-your-skill/references/` if needed
4. Add slash commands in `commands/` if the skill needs explicit invocation
5. Update `README.md` skill and command tables
6. Update `CHANGELOG.md`

## Adding Slash Commands

Create a markdown file in `commands/` with:
```yaml
---
description: What the command does
argument-hint: [optional-args]
---
```

## Code Standards

PHP examples must follow WordPress PHP Coding Standards:
- Spaces inside parentheses: `function_name( $arg )`
- Use `array()` not `[]`
- Yoda conditions: `if ( true === $value )`
- Snake_case for variables/functions
- Prefix custom functions: `prefix_function_name()`

Use consistent severity labels in skill content:
- **CRITICAL**: Vulnerability, broken behavior, review blocker, or high-risk production issue
- **WARNING**: Significant correctness, maintainability, compatibility, or performance concern
- **INFO**: Lower-risk improvement, modernization, or follow-up opportunity

Each individual skill may further interpret severity in its own domain, but these global meanings should stay stable across the whole pack.

## Testing Changes

```bash
# Review the changed skill and command together
sed -n '1,120p' skills/wp-your-skill/SKILL.md
sed -n '1,80p' commands/wp-your-command.md

# If you test by copying a single skill locally
cp -r skills/wp-your-skill ~/.claude/skills/
```

## Versioning

When releasing, keep versioned metadata and docs in sync wherever they exist for the distribution method you are using. At minimum:

- Update `CHANGELOG.md`
- Update any plugin or marketplace manifest files checked into the repo
- Make sure `README.md` reflects newly added skills or commands
