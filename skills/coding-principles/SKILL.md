---
name: coding-principles
description: Meta-skill that bundles karpathy-guidelines and additional-coding-principles. Invoke this when you want both principle sets loaded together for a coding task, review, or refactor.
license: MIT
---

# Coding Principles (Meta)

This skill bundles two principle sets into a single invocation. When this skill is run, you must invoke both target skills via the Skill tool, then apply all loaded guidelines to the task at hand.

## Required actions

Invoke each of the following skills exactly once (in either order):

1. `andrej-karpathy-skills:karpathy-guidelines`
2. `rsoatto-skills:additional-coding-principles`

After both are loaded, proceed with the user's task while honoring every principle from both skills together. Treat the two skills as one combined ruleset: where they overlap, follow either; where they differ, follow both.

## When to use

- The user invokes `/coding-principles` explicitly.
- The user asks for a "full principles" pass on code.
- You're about to do non-trivial coding work and want both rulesets in context up front rather than relying on auto-trigger.

## What this skill does *not* do

It does not redefine or paraphrase the underlying principles. The two source skills are the source of truth — if they change, this skill's behavior changes with them automatically.
