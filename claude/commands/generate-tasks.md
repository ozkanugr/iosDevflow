---
description: Break down feature spec into implementable tasks
argument-hint: <feature-name>
allowed-tools: Read, Write
model: sonnet
---

# Generate Task Breakdown

Read the specification at `docs/specs/$ARGUMENTS.md` and create a detailed task breakdown.

## Steps

1. Read and analyze the feature specification
2. Identify all implementation steps
3. Order by dependencies
4. Estimate complexity (S/M/L)
5. Create task file

## Task Structure

Create `docs/tasks/$ARGUMENTS-tasks.md`:

```markdown
# Tasks: [Feature Name]

**Feature Spec**: `docs/specs/$ARGUMENTS.md`
**Status**: Not Started | In Progress | Complete
**Total Steps**: X

## Progress Summary
- [ ] Step 1: [Name] (Size)
- [ ] Step 2: [Name] (Size)
- ...

## Dependencies
- [External dependency that must be ready]
- [Internal prerequisite]

---

## Step 1: [Task Name]
**Size**: S | M | L
**Depends On**: None | Step X
**Acceptance**: [When is this step done?]

### Subtasks
- [ ] [Subtask 1]
- [ ] [Subtask 2]
- [ ] [Subtask 3]

### Implementation Notes
[Guidance for implementation]

### Files to Create/Modify
- `path/to/file.ext` - [What to do]

---

## Step 2: [Task Name]
**Size**: S | M | L
**Depends On**: Step 1
**Acceptance**: [When is this step done?]

### Subtasks
- [ ] [Subtask 1]
- [ ] [Subtask 2]

### Implementation Notes
[Guidance for implementation]

---

## Testing Tasks

### Unit Tests
- [ ] Test [component 1]
- [ ] Test [component 2]

### Integration Tests
- [ ] Test [flow 1]
- [ ] Test [flow 2]

---

## Changes Log
| Date | Step | Changes |
|------|------|---------|
| [Date] | - | Initial task breakdown |
```

## Task Sizing Guide

| Size | Description | Typical Scope |
|------|-------------|---------------|
| S | Simple | Single file change, straightforward |
| M | Medium | Multiple files, some complexity |
| L | Large | Significant changes, consider splitting |

## Guidelines

- Each task should be completable in a single session
- Tasks should be independently verifiable
- Include clear acceptance criteria
- Order by dependencies (prerequisites first)
- Split large tasks into smaller steps

## Output

- Task breakdown at `docs/tasks/$ARGUMENTS-tasks.md`
- Summary of total steps and sizes
- Suggested order of implementation
- Any dependencies or blockers identified
