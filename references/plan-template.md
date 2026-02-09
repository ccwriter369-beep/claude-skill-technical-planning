# Plan Template

Copy and adapt this structure for implementation plans.

---

# [Project/Feature]: Implementation Plan

## Context Summary

### What We Learned

**From [Source 1]:**
- Key finding 1
- Key finding 2

**From [Source 2]:**
- Key finding 1
- Key finding 2

**From Codebase Exploration:**
- What exists
- What's missing
- Contradictions found

---

## Gap Analysis

### What's Already Solid

| Area | Status | Evidence |
|------|--------|----------|
| Area 1 | ✅ Good | [specific file/test] |
| Area 2 | ✅ Good | [specific file/test] |

### What Needs Work

| Area | Gap | Priority |
|------|-----|----------|
| Area 1 | [specific gap] | **MVP-Critical** |
| Area 2 | [specific gap] | **Phase-2** |
| Area 3 | [specific gap] | **Backlog** |

---

## Remediation Plan

### Phase 1: [Name] (MVP-Critical)

**Goal**: [One sentence]

#### 1.1 [Task Name]

**Problem**: [Specific problem]

**Fix**: [Specific solution]

**Files to modify**:
- `path/to/file.py` - [what changes]
- `path/to/other.py` - [what changes]

**Implementation**:
```python
# Key code snippet or approach
```

#### 1.2 [Task Name]

[Same structure]

---

### Phase 2: [Name]

**Goal**: [One sentence]

[Tasks with same structure]

---

## Priority Order

| Phase | Effort | Impact | Do When |
|-------|--------|--------|---------|
| 1.1 | 2 hours | High | Before release |
| 1.2 | 4 hours | High | Before release |
| 2.1 | 1 day | Medium | Next sprint |

---

## Verification

### Phase 1 Verification

**Automated**:
- [ ] `pytest tests/` passes
- [ ] CI checks pass
- [ ] [Specific test file] covers changes

**Manual**:
- [ ] Start service: `[command]`
- [ ] Test endpoint: `[curl command]`
- [ ] Verify behavior: [expected result]

**Invariants**:
- [ ] [Existing behavior X] unchanged
- [ ] [Contract Y] still holds

### Phase 2 Verification

[Same structure]

---

## Files Modified

List of all files touched by this plan:

```
path/to/file1.py       # Phase 1.1
path/to/file2.py       # Phase 1.2
path/to/file3.md       # Phase 2.1
```

---

## Key Decisions Made

| Decision | Rationale | Alternatives Considered |
|----------|-----------|------------------------|
| [Choice] | [Why] | [What else was possible] |

---

## Open Questions

- [ ] [Question needing user input]
- [ ] [Question needing more research]
