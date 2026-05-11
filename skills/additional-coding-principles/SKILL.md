---
name: additional-coding-principles
description: Additional behavioral guidelines that extend andrej-karpathy-skills. Use when writing, reviewing, or refactoring code to handle ambiguity, conflicts, context management, test intent, convention-matching, and failure visibility.
license: MIT
---

# Additional Coding Principles

These extend `andrej-karpathy-skills:karpathy-guidelines`. Both skills should be applied together when coding.

**Bias:** caution over speed on non-trivial work; use judgment on trivial tasks.

## Use code, not the model, when code suffices

If a task is deterministic — parsing, transforming, routing, retries, sorting, validation — write code. Don't invoke the model for work that code does better and more reliably. Regex over LLM-call when regex fits.

## Be deliberate with context

When a thread gets long or wanders, propose a summary and reset rather than continuing in a state you can't describe back. Surface when you're about to do something context-expensive (large file reads, broad searches, long agent runs).

## Surface conflicts, don't average them

If two patterns contradict, pick one — favor the more recent or more tested — explain why, and flag the other for cleanup. Don't blend conflicting patterns into a third thing that satisfies neither.

## Read before you write

Before adding code, read exports, immediate callers, and shared utilities. "Looks orthogonal" is dangerous. If you can't explain why existing code is structured the way it is, ask before changing it.

## Tests verify intent, not just behavior

Tests must encode *why* behavior matters, not just *what* it does. A test that still passes after the business logic changes is a test that isn't really testing the business logic.

## Checkpoint after significant steps

After each significant step, restate what's verified, what's pending, and any open uncertainty. Skip for trivial work. Don't continue from a state you can't describe back to the user.

## Match the codebase's conventions

Conformance beats personal taste inside a codebase. If a convention is genuinely harmful, surface it explicitly — don't fork silently.

## Fail loud

"Completed" is wrong if anything was skipped silently. "Tests pass" is wrong if any were skipped. Default to surfacing uncertainty rather than hiding it.
