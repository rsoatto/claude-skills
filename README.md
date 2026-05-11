# rsoatto-skills

Personal Claude Code plugin: extra coding principles plus a meta-skill that bundles them with [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills).

## Skills

- **`additional-coding-principles`** — guidelines that extend karpathy's: write code (not LLM calls) for deterministic work, manage context deliberately, surface conflicts, read before writing, test intent, checkpoint, match conventions, fail loud.
- **`coding-principles`** — meta-skill. Invoke `/coding-principles` (or via the Skill tool) and Claude will load both `karpathy-guidelines` and `additional-coding-principles` in one shot.

## Install (per server)

```bash
# In Claude Code:
/plugin marketplace add rsoatto/claude-skills
/plugin install rsoatto-skills@rsoatto-skills
/reload-plugins
```

The meta-skill depends on `andrej-karpathy-skills` being installed alongside it. Install that first:

```bash
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin install andrej-karpathy-skills@karpathy-skills
```

## Update

```bash
# Pull marketplace changes
/plugin marketplace update rsoatto-skills
/reload-plugins
```

Or manually:

```bash
git -C ~/.claude/plugins/marketplaces/rsoatto-skills pull
rm -rf ~/.claude/plugins/cache/rsoatto-skills
cp -r ~/.claude/plugins/marketplaces/rsoatto-skills ~/.claude/plugins/cache/rsoatto-skills
# then /reload-plugins
```

## Develop locally

```bash
git clone <this-repo> ~/claude-skills
# edit skills/*/SKILL.md
git commit && git push
# on each server: /plugin marketplace update rsoatto-skills
```
