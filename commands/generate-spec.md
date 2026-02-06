---
description: Generate feature specification from PRD
argument-hint: <feature-name>
allowed-tools: Read, Write
model: sonnet
---

# Generate Feature Specification

Read the PRD at `docs/PRD.md` and create a detailed specification for: $ARGUMENTS

## Steps

1. Read and analyze the PRD
2. Extract relevant user stories and requirements for this feature
3. Define detailed acceptance criteria
4. Design technical architecture
5. Create the spec file

## Specification Structure

Create `docs/specs/$ARGUMENTS.md`:

```markdown
# Feature Specification: [Feature Name]

**Status**: Draft | In Review | Approved | In Progress | Complete
**Priority**: P0 | P1 | P2
**PRD Reference**: Section [X]
**Author**: [Name]
**Last Updated**: [Date]

## Overview
[Brief description of the feature]

## User Stories
1. As a [user], I want [action] so that [benefit]
2. ...

## Acceptance Criteria
- [ ] AC1: [Specific, testable criterion]
- [ ] AC2: ...

## Technical Design

### Architecture
[How this feature fits into the overall architecture]

### Data Models
```[language]
// Model definitions
```

### API Endpoints (if applicable)
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/... | ... |

### State Management
[How state is managed for this feature]

### Dependencies
- [ ] [Dependency 1]
- [ ] [Dependency 2]

## UI/UX Design
- Design reference: [Link if available]
- Key screens: [List]
- User flow: [Description]

## Edge Cases
1. [Edge case]: [How to handle]
2. ...

## Error Handling
| Error | User Message | Recovery |
|-------|--------------|----------|
| [Error] | [Message] | [Action] |

## Testing Plan
- Unit tests for [components]
- Integration tests for [flows]
- E2E tests for [scenarios]

## Security Considerations
- [Security item 1]
- [Security item 2]

## Performance Considerations
- [Performance item 1]
- [Performance item 2]

## Rollout Plan
- [ ] Feature flag: `feature_[name]_enabled`
- [ ] Metrics to monitor

## Open Questions
- [ ] Question 1?
```

## Output

- Feature specification at `docs/specs/$ARGUMENTS.md`
- Summary of key design decisions
- Suggested task breakdown
