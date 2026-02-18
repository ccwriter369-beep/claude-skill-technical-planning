# technical-planning

A Claude Code skill that enforces rigorous technical planning before implementation. Treats planning as a proof obligation, not overhead — "80% planning, 20% coding."

![Claude Code skill](https://img.shields.io/badge/Claude_Code-skill-blue)

## What it does

Guides Claude through a structured 6-phase planning process before touching any code:

1. **Deep Reading** — three passes (structure → details → implications)
2. **Codebase Exploration** — verify claims against actual code, not docs
3. **Synthesis** — reconcile multiple sources, identify contradictions
4. **Conflict Prediction** — for parallel work, build a file-touch matrix to catch merge conflicts before they happen
5. **Plan Structure** — phases, priorities, specific file paths, verification steps
6. **Verification** — every plan must include automated + manual checks

## Install

```bash
npx skills add technical-planning
```

Or clone manually:

```bash
git clone https://github.com/ccwriter369-beep/claude-skill-technical-planning \
  ~/.claude/skills/technical-planning
```

## Usage

Invoked automatically when:
- Task touches 3+ files
- Multiple valid approaches exist
- Architectural decisions needed
- Requirements are ambiguous
- Refactoring or migration work

Or explicitly:

```
/technical-planning
plan this before implementing
think through the approach first
```

## Decision: Plan or Just Do?

**Plan when ANY apply:**
- Task touches 3+ files
- Multiple valid approaches exist
- Affects system behavior or contracts
- Refactoring or migration

**Just do when ALL apply:**
- Single file, obvious location
- User gave exact instructions
- No design decisions
- Trivial scope (typo, one-liner)

When uncertain — plan.

## Key insight

> "Prod discipline should be treated as a proof obligation, not tribal knowledge."

The plan is evidence you understood. Verification proves the solution works. Together: implementation as theorem, not hope.

## License

MIT
