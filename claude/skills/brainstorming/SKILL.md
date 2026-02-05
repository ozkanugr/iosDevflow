---
name: brainstorming
description: AI-guided comprehensive brainstorming engine combining 5W1H analysis, Design Thinking, Lean Canvas, MoSCoW prioritization, and User Story generation for software development projects.
model: opus
---

# Brainstorming Engine

Transform ideas into actionable, well-documented development plans through a structured, AI-guided brainstorming process.

## Overview

The brainstorming engine follows a **5-phase hybrid methodology**. Each phase builds on the previous, creating a comprehensive project foundation that feeds directly into PRD creation.

---

## Phase 1: 5W1H Discovery

Ask structured questions to understand the project scope. **Never skip questions.** Each question category must be explored thoroughly.

### WHO - Stakeholders & Users
- Who is the primary end user?
- Who are secondary users?
- Who are the project stakeholders?
- Who maintains the codebase?
- What team size and skill level?

### WHAT - Product Definition
- What does the application do at its core?
- What problem does it solve?
- What platforms does it target?
- What existing solutions compete with it?
- What differentiates this solution?
- What data does it handle?
- What third-party integrations are needed?

### WHEN - Timeline & Phases
- When is the target release?
- When are milestone deadlines?
- What is the MVP scope vs full scope?
- What phased rollout strategy applies?

### WHERE - Distribution & Environment
- Where will the app be distributed?
- Where does backend infrastructure live?
- Where is data stored?
- What deployment environments exist?

### WHY - Purpose & Value
- Why does this project need to exist?
- Why would users choose this over alternatives?
- Why is this the right time to build it?
- What business metrics define success?

### HOW - Technical Approach
- How should the architecture be structured?
- How will the team collaborate on the codebase?
- How will testing be approached?
- How will CI/CD be configured?
- How will performance/security requirements be met?

---

## Phase 2: Design Thinking

After 5W1H discovery, apply Design Thinking methodology:

### Empathize
- Create user personas from WHO answers
- Map user pain points
- Identify emotional triggers and motivations
- Document user journey (current state)

### Define
- Synthesize problem statement
- Create "How Might We" questions
- Define success metrics
- Establish constraints and assumptions

### Ideate
- Generate feature ideas (quantity over quality)
- Cross-reference with WHAT answers
- Explore unconventional approaches
- Group related ideas into themes

### Prototype (Conceptual)
- Define screen flow / navigation map
- Sketch core interaction patterns
- Identify key UI components
- Define data flow between screens

### Test (Validation)
- Define testable hypotheses
- Create validation criteria
- Plan user testing approach
- Define feedback collection methods

---

## Phase 3: Lean Canvas

Generate a Lean Canvas from the brainstorming output:

```
┌─────────────────┬─────────────────┬─────────────────┐
│    PROBLEM       │   SOLUTION       │  KEY METRICS     │
│                  │                  │                  │
│ Top 3 problems   │ Top 3 features   │ Key activities   │
│ from discovery   │ addressing them  │ to measure       │
├─────────────────┤                  ├─────────────────┤
│  EXISTING ALT.   │                  │  COST STRUCTURE  │
│                  │                  │                  │
│ Current solutions│                  │ Development costs│
├─────────────────┼─────────────────┼─────────────────┤
│  UNIQUE VALUE    │  UNFAIR          │  REVENUE         │
│  PROPOSITION     │  ADVANTAGE       │  STREAMS         │
│                  │                  │                  │
│ Single, clear    │ What can't be    │ How does it      │
│ message          │ easily copied    │ generate value   │
├─────────────────┼─────────────────┼─────────────────┤
│  CUSTOMER        │  CHANNELS        │                  │
│  SEGMENTS        │                  │                  │
│                  │ Distribution     │                  │
│ Target users     │ channels         │                  │
└─────────────────┴─────────────────┴─────────────────┘
```

---

## Phase 4: MoSCoW Prioritization

Classify all identified features:

### Must Have (M)
- Core features without which the product has no value
- Regulatory/compliance requirements
- Security fundamentals

### Should Have (S)
- Important features that add significant value
- Features most users would expect
- Performance optimizations

### Could Have (C)
- Nice-to-have features
- Quality-of-life improvements
- Advanced customization options

### Won't Have (W) - This Release
- Features deferred to future releases
- Ideas that need more validation
- Features dependent on unbuilt infrastructure

---

## Phase 5: User Story Generation

Generate structured user stories from prioritized features:

### Story Format
```
As a [persona from Phase 2],
I want to [action from prioritized features],
So that [value from Phase 3].

Acceptance Criteria:
- [ ] Given [precondition], when [action], then [result]
- [ ] Given [precondition], when [action], then [result]

Priority: [Must/Should/Could]
Estimate: [S/M/L/XL]
Sprint: [Suggested sprint number]
```

### Story Map Structure
```
User Activities  →  [Activity 1]  →  [Activity 2]  →  [Activity 3]
                        │                 │                 │
User Tasks       →  [Task 1.1]     [Task 2.1]       [Task 3.1]
                     [Task 1.2]     [Task 2.2]       [Task 3.2]
                        │                 │                 │
User Stories     →  [Story 1.1.1]  [Story 2.1.1]    [Story 3.1.1]
                     [Story 1.1.2]  [Story 2.1.2]    [Story 3.1.2]
```

---

## Session Management

### Starting a Session
1. Create session file: `docs/brainstorm/session-{timestamp}.md`
2. Record session metadata (date, participants, project context)
3. Begin Phase 1 questioning
4. Progress through phases sequentially

### Resuming a Session
1. Read the latest session file from `docs/brainstorm/`
2. Identify the last completed phase
3. Continue from the next phase
4. Maintain context from previous answers

### Session Output Format

```markdown
# Brainstorming Session: {Project Name}

**Date:** {timestamp}
**Participants:** {team members}
**Status:** {phase-1|phase-2|phase-3|phase-4|phase-5|complete}

## Phase 1: 5W1H Discovery
### WHO
{answers}
### WHAT
{answers}
### WHEN
{answers}
### WHERE
{answers}
### WHY
{answers}
### HOW
{answers}

## Phase 2: Design Thinking
### Personas
{persona definitions}
### Problem Statement
{synthesized problem}
### Feature Ideas
{ideation results}
### Navigation Map
{screen flow}

## Phase 3: Lean Canvas
{canvas content}

## Phase 4: MoSCoW Prioritization
### Must Have
{features}
### Should Have
{features}
### Could Have
{features}
### Won't Have
{features}

## Phase 5: User Stories
{generated stories}

## Next Steps
- [ ] Generate PRD document (/create-prd)
- [ ] Generate feature specifications (/generate-spec)
- [ ] Create task breakdown (/generate-tasks)
```

---

## Questioning Strategy

### Rules for Asking Questions
1. **Never skip questions** - Every 5W1H category must be explored
2. **Ask one question at a time** - Allow thorough answers
3. **Probe deeper** - Follow up on vague answers with specific sub-questions
4. **Offer options** - When the user is unsure, provide 2-4 concrete options with explanations
5. **Validate understanding** - Summarize answers back before moving to the next category
6. **Respect scope** - If a category doesn't apply, acknowledge it and move on
7. **Record everything** - Every answer goes into the session document

### Question Depth by Project Type
- **Mobile App:** Heavy emphasis on WHO (users), WHAT (features), WHERE (distribution)
- **Library/Package:** Heavy emphasis on WHAT (API surface), HOW (integration), WHY (vs alternatives)
- **Backend/Server:** Heavy emphasis on WHERE (infrastructure), HOW (scalability), WHAT (endpoints)
- **Multi-Platform:** Heavy emphasis on WHERE (platforms), HOW (code sharing), WHAT (platform-specific features)
- **CLI Tool:** Heavy emphasis on WHAT (commands), HOW (installation), WHO (developer users)

---

## Integration with PRD Workflow

Brainstorming output feeds directly into:

| Brainstorm Phase | PRD Section | Purpose |
|------------------|-------------|---------|
| Phase 1 (5W1H) | Problem Statement, Target Users | Foundation |
| Phase 2 (Design Thinking) | Success Metrics, User Personas | Validation |
| Phase 3 (Lean Canvas) | Executive Summary, Business Model | Strategy |
| Phase 4 (MoSCoW) | Core Features, Out of Scope | Prioritization |
| Phase 5 (User Stories) | Feature Specifications, Tasks | Implementation |

---

## References

For detailed methodology guides:
- `references/question-bank.md` - 100+ curated questions by project type
- `references/design-thinking.md` - Design Thinking deep dive
- `references/lean-canvas.md` - Lean Canvas guide

For session templates:
- `templates/universal.md` - Domain-agnostic template
- `templates/mobile-app.md` - Mobile application template
- `templates/library.md` - Library/Package template
- `templates/backend.md` - Backend/Server template
