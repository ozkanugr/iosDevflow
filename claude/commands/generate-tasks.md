---
description: Generate feature specification from PRD and break down into implementable tasks
argument-hint: <feature-name>
allowed-tools: Read, Write
model: sonnet
---

# Generate Feature Tasks

Read the PRD at `docs/PRD.md` and create a comprehensive specification with detailed task breakdown for: $ARGUMENTS

## Steps

1. Read and analyze the PRD
2. Extract relevant user stories and requirements for this feature
3. Define detailed acceptance criteria
4. Design technical architecture
5. Identify all implementation steps
6. Order by dependencies
7. Estimate complexity (S/M/L)
8. Create the unified spec and task file

## Document Structure

Create `docs/tasks/$ARGUMENTS.md`:

```markdown
# Feature: [Feature Name]

**Status**: Draft | In Review | Approved | In Progress | Complete
**Priority**: P0 | P1 | P2
**PRD Reference**: Section [X]
**Author**: [Name]
**Created**: [Date]
**Last Updated**: [Date]

---

## 1. Overview

[Brief description of the feature and its purpose]

---

## 2. User Stories

1. As a [user], I want [action] so that [benefit]
2. As a [user], I want [action] so that [benefit]
3. ...

---

## 3. Acceptance Criteria

- [ ] AC1: [Specific, testable criterion]
- [ ] AC2: [Specific, testable criterion]
- [ ] AC3: [Specific, testable criterion]
- ...

---

## 4. Technical Design

### 4.1 Architecture

[How this feature fits into the overall architecture]

### 4.2 Data Models

```[language]
// Model definitions
```

### 4.3 API Endpoints (if applicable)

| Method | Endpoint | Description | Request | Response |
|--------|----------|-------------|---------|----------|
| GET | /api/... | ... | ... | ... |
| POST | /api/... | ... | ... | ... |

### 4.4 State Management

[How state is managed for this feature]

### 4.5 Dependencies

- [ ] [External dependency 1]
- [ ] [Internal prerequisite 1]

---

## 5. UI/UX Design

- **Design Reference**: [Link if available]
- **Key Screens**: [List of screens]
- **User Flow**: [Description of the user journey]

### Wireframe/Mockup Notes

[Key design considerations and constraints]

---

## 6. Edge Cases & Error Handling

### Edge Cases

| Scenario | Expected Behavior |
|----------|-------------------|
| [Edge case 1] | [How to handle] |
| [Edge case 2] | [How to handle] |

### Error Handling

| Error | User Message | Recovery Action |
|-------|--------------|-----------------|
| [Error type] | [User-friendly message] | [Recovery steps] |

---

## 7. Security & Performance

### Security Considerations

- [ ] [Security item 1]
- [ ] [Security item 2]

### Performance Considerations

- [ ] [Performance item 1]
- [ ] [Performance item 2]

---

## 8. Implementation Tasks

### Progress Summary

| Step | Task | Size | Status | Depends On |
|------|------|------|--------|------------|
| 1 | [Task name] | S/M/L | ⬜ | - |
| 2 | [Task name] | S/M/L | ⬜ | Step 1 |
| 3 | [Task name] | S/M/L | ⬜ | Step 2 |
| ... | ... | ... | ... | ... |

**Legend**: ⬜ Not Started | 🔄 In Progress | ✅ Complete | ⏸️ Blocked

### Prerequisites

- [External dependency that must be ready]
- [Internal prerequisite that must be complete]

---

### Step 1: [Task Name]

**Size**: S | M | L
**Depends On**: None
**Acceptance**: [When is this step done?]

#### Subtasks

- [ ] [Subtask 1]
- [ ] [Subtask 2]
- [ ] [Subtask 3]

#### Implementation Notes

[Detailed guidance for implementation]

#### Files to Create/Modify

| File | Action | Description |
|------|--------|-------------|
| `path/to/file.ext` | Create/Modify | [What to do] |

---

### Step 2: [Task Name]

**Size**: S | M | L
**Depends On**: Step 1
**Acceptance**: [When is this step done?]

#### Subtasks

- [ ] [Subtask 1]
- [ ] [Subtask 2]

#### Implementation Notes

[Detailed guidance for implementation]

#### Files to Create/Modify

| File | Action | Description |
|------|--------|-------------|
| `path/to/file.ext` | Create/Modify | [What to do] |

---

### Step N: [Continue as needed...]

---

## 9. Testing Plan

### Unit Tests

| Component | Test Cases | Priority |
|-----------|------------|----------|
| [Component 1] | [Test description] | High/Medium/Low |
| [Component 2] | [Test description] | High/Medium/Low |

### Integration Tests

| Flow | Test Cases | Priority |
|------|------------|----------|
| [Flow 1] | [Test description] | High/Medium/Low |
| [Flow 2] | [Test description] | High/Medium/Low |

### E2E Tests

| Scenario | Test Cases | Priority |
|----------|------------|----------|
| [Scenario 1] | [Test description] | High/Medium/Low |

---

## 10. Rollout Plan

- [ ] Feature flag: `feature_[name]_enabled`
- [ ] Metrics to monitor: [List metrics]
- [ ] Rollback plan: [Describe rollback steps]

---

## 11. Open Questions

- [ ] Question 1?
- [ ] Question 2?

---

## 12. Changes Log

| Date | Author | Changes |
|------|--------|---------|
| [Date] | [Name] | Initial specification and task breakdown |
```

## Task Sizing Guide

| Size | Description | Typical Scope |
|------|-------------|---------------|
| S | Simple | Single file change, straightforward logic |
| M | Medium | Multiple files, moderate complexity |
| L | Large | Significant changes, consider splitting |

## Guidelines

- Each task should be completable in a single session
- Tasks should be independently verifiable
- Include clear acceptance criteria for each step
- Order by dependencies (prerequisites first)
- Split large tasks (L) into smaller steps when possible
- Include enough detail for any developer to implement

## Output

- Comprehensive feature document at `docs/tasks/$ARGUMENTS.md`
- Complete specification with technical design
- Detailed task breakdown with dependencies
- Testing plan with priorities
- Summary of total steps, sizes, and implementation order
- Any blockers or open questions identified
