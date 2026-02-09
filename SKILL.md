---
name: technical-planning
description: |
  Rigorous technical planning before implementation. Use PROACTIVELY when: (1) task touches 3+ files, (2) architectural decisions needed, (3) requirements are ambiguous, (4) changes affect system behavior, (5) user enters plan mode, (6) task involves refactoring or migration. NOT for: single-file fixes, trivial changes, user gave exact instructions. Core principle: "80% planning, 20% coding" - treat planning as proof obligation, not overhead.
---

# Technical Planning

Planning is a proof obligation, not overhead. Time spent understanding deeply saves multiples in implementation.

## Decision: Plan or Just Do?

**Plan when ANY apply:**
- Task touches 3+ files
- Multiple valid approaches exist
- Architectural/design decisions needed
- Requirements are ambiguous
- Affects system behavior or contracts
- Refactoring or migration

**Just do when ALL apply:**
- Single file, obvious location
- User gave exact instructions
- No design decisions
- Trivial scope (typo, one-liner)

When uncertain, plan.

## Phase 1: Deep Reading

**Never skim. Multiple passes are normal.**

| Pass | Focus |
|------|-------|
| First | Structure - what sections, what purpose |
| Second | Details - numbers, paths, specific claims |
| Third | Implications - constraints, what's NOT said |

```
[ ] Read full document (not just headers)
[ ] Note claims needing verification
[ ] Identify files/paths mentioned
[ ] Mark contradictions to assumptions
[ ] Re-read complex sections
```

## Phase 2: Codebase Exploration

**Verify claims against code. Assumptions are liabilities.**

1. **Find entry points** - Where does execution start?
2. **Trace the path** - Follow code flow
3. **Check both modes** - Dev vs prod, test vs runtime
4. **Verify claims** - Does code match docs?

### Common Traps
- Analyzing dev entrypoint, concluding "no auth" (prod has it)
- Reading stale docs
- Assuming files exist without checking
- Trusting comments over implementation

## Phase 3: Synthesis

Multiple sources > one source repeated.

Gather from: requirements, audits, code, tests, CI, ADRs.

1. List claims from each source
2. Note contradictions
3. Verify disputed claims against code
4. Identify gaps
5. Prioritize by impact

## Phase 4: Plan Structure

See `references/plan-template.md` for full template.

**Essential sections:**
- Context Summary (concise)
- Gap Analysis (exists vs needed)
- Phases with priorities
- Files to modify (specific paths)
- Verification steps

**Priority tiers:**
- MVP-Critical: Required for system to be "real"
- Phase-2: Important but not blocking
- Backlog: Future

## Phase 5: Verification

Every plan MUST include verification.

```markdown
## Verification

### Automated
- [ ] `pytest tests/` passes
- [ ] CI pipeline green

### Manual
- [ ] Command: [specific command]
- [ ] Expected: [specific result]

### Invariants
- [ ] [Condition] remains true
```

## Anti-Patterns

| Pattern | Problem |
|---------|---------|
| Shallow reading | Missing details in paragraphs |
| Single-source trust | Believing docs without verifying code |
| Assumption stacking | Building on unverified assumptions |
| Missing verification | No "how to prove this works" |
| Scope creep | Adding nice-to-haves to MVP |

## Key Insight

> "Prod discipline should be treated as a proof obligation, not tribal knowledge."

The plan is evidence you understood. Verification proves the solution works. Together: implementation as theorem, not hope.
