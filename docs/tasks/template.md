# Feature: [Feature Name]

**Status**: Draft | In Review | Approved | In Progress | Complete
**Priority**: P0 | P1 | P2
**PRD Reference**: Section [X]
**Author**: [Name]
**Created**: [Date]
**Last Updated**: [Date]

---

## 1. Overview

[Brief description of the feature and its purpose - 2-3 sentences]

---

## 2. User Stories

1. As a [user type], I want [action] so that [benefit]
2. As a [user type], I want [action] so that [benefit]
3. As a [user type], I want [action] so that [benefit]

---

## 3. Acceptance Criteria

- [ ] AC1: [Specific, testable criterion]
- [ ] AC2: [Specific, testable criterion]
- [ ] AC3: [Specific, testable criterion]

---

## 4. Technical Design

### 4.1 Architecture

[How this feature fits into the overall architecture]

```
[Component diagram or data flow]
```

### 4.2 Data Models

```[language]
// Define data structures
interface FeatureModel {
  id: string;
  // ... properties
}
```

### 4.3 API Endpoints (if applicable)

| Method | Endpoint | Description | Request | Response |
|--------|----------|-------------|---------|----------|
| GET | `/api/v1/...` | ... | - | `{ ... }` |
| POST | `/api/v1/...` | ... | `{ ... }` | `{ ... }` |

### 4.4 State Management

[How state is managed for this feature]

### 4.5 Dependencies

- [ ] [Internal dependency - module/feature]
- [ ] [External dependency - API/service]

---

## 5. UI/UX Design

- **Design Reference**: [Figma/Design Link if available]
- **Key Screens**: [List of screens]
- **User Flow**: [Description of the user journey]

### User Flow Diagram

```
[Start] → [Step 1] → [Step 2] → [Decision]
                                   ↓
                          [Yes] → [Step 3] → [End]
                          [No]  → [Step 4] → [End]
```

---

## 6. Edge Cases & Error Handling

### Edge Cases

| Scenario | Expected Behavior |
|----------|-------------------|
| [Edge case 1] | [How to handle] |
| [Edge case 2] | [How to handle] |

### Error Handling

| Error Condition | User Message | Technical Handling |
|-----------------|--------------|-------------------|
| [Error 1] | [User-friendly message] | [Log, retry, etc.] |
| [Error 2] | [User-friendly message] | [Log, retry, etc.] |

---

## 7. Security & Performance

### Security Considerations

- [ ] [Security item - e.g., input validation]
- [ ] [Security item - e.g., authorization checks]

### Performance Considerations

- [ ] [Performance item - e.g., lazy loading]
- [ ] [Performance item - e.g., caching]

---

## 8. Implementation Tasks

### Progress Summary

| Step | Task | Size | Status | Depends On |
|------|------|------|--------|------------|
| 1 | [Task name] | S/M/L | ⬜ | - |
| 2 | [Task name] | S/M/L | ⬜ | Step 1 |
| 3 | [Task name] | S/M/L | ⬜ | Step 2 |

**Legend**: ⬜ Not Started | 🔄 In Progress | ✅ Complete | ⏸️ Blocked

### Prerequisites

- [ ] [Prerequisite 1 - e.g., API endpoint available]
- [ ] [Prerequisite 2 - e.g., design approved]

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

### E2E Tests

| Scenario | Test Cases | Priority |
|----------|------------|----------|
| [Scenario 1] | [Test description] | High/Medium/Low |

### Manual Testing

- [ ] [Manual verification 1]
- [ ] [Manual verification 2]

---

## 10. Rollout Plan

- [ ] Feature flag: `feature_[name]_enabled`
- [ ] Metrics to monitor: [List metrics]
- [ ] Rollback plan: [Describe rollback steps]

---

## 11. Open Questions

- [ ] [Question needing answer]
- [ ] [Question needing answer]

---

## 12. Changes Log

| Date | Author | Changes |
|------|--------|---------|
| [Date] | [Name] | Initial specification and task breakdown |

---

## Task Sizing Guide

| Size | Description | Typical Scope |
|------|-------------|---------------|
| S | Simple | Single file change, straightforward logic |
| M | Medium | Multiple files, moderate complexity |
| L | Large | Significant changes, consider splitting |
