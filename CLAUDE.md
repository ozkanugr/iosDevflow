# Project: [PROJECT_NAME]

## Quick Reference

- **Platform**: [Platform - e.g., Web, iOS, Android, Backend, Multi-Platform]
- **Language**: [Primary Language - e.g., TypeScript, Swift, Kotlin, Python, Rust]
- **Framework**: [UI/App Framework - e.g., React, SwiftUI, Jetpack Compose]
- **Architecture**: [Architecture Pattern - e.g., MVVM, MVC, Clean Architecture]
- **Package Manager**: [Package Manager - e.g., npm, CocoaPods, Cargo]
- **Test Framework**: [Test Framework - e.g., Vitest, XCTest, pytest]

## Project Structure

```
[PROJECT_NAME]/
├── src/                    # Source code
│   ├── features/           # Feature modules
│   │   └── [feature]/
│   │       ├── components/ # UI components
│   │       ├── hooks/      # Custom hooks/logic
│   │       └── types/      # Type definitions
│   ├── core/               # Shared utilities
│   │   ├── api/            # API client
│   │   ├── utils/          # Helpers
│   │   └── types/          # Shared types
│   └── app/                # App entry point
├── tests/                  # Test files
├── docs/                   # Documentation
│   ├── PRD.md              # Product requirements
│   ├── ARCHITECTURE.md     # Architecture decisions
│   ├── brainstorm/         # Brainstorming sessions
│   ├── specs/              # Feature specifications
│   └── tasks/              # Task breakdowns
└── .claude/                # Claude Code configuration
    ├── settings.json       # Team settings (in git)
    ├── settings.local.json # Personal overrides (gitignored)
    ├── agents/             # Subagent definitions
    ├── commands/           # Slash commands (/command-name)
    ├── hooks/              # Lifecycle hook scripts
    ├── skills/             # Auto-activated capabilities
    ├── output-styles/      # Response formatting
    └── plans/              # Stored plan files
```

## Coding Standards

### General

- Follow language-specific style guides
- Use meaningful, descriptive names
- Keep functions focused (single responsibility)
- Write self-documenting code
- Add comments for complex logic only

### Patterns

- [Pattern 1]: [Brief description]
- [Pattern 2]: [Brief description]
- [Pattern 3]: [Brief description]

### Error Handling

- Use typed errors where possible
- Handle errors at appropriate levels
- Provide meaningful error messages
- Log errors for debugging

## Testing Requirements

- Unit tests for business logic
- Integration tests for API interactions
- E2E tests for critical user flows
- Target 80% coverage for core modules

## DO NOT

- Commit secrets or API keys
- Use deprecated APIs
- Create monolithic components
- Skip error handling
- Ignore linter warnings
- Edit lock files directly

## Planning Workflow

When starting new features, use the PRD workflow:

1. **Brainstorm**: `/brainstorm new [project-type]` — 5-phase structured ideation
2. **Create PRD**: `/create-prd` — Generate formal product requirements
3. **Generate Spec**: `/generate-spec <feature>` — Detailed feature specification
4. **Generate Tasks**: `/generate-tasks <feature>` — Implementation task breakdown
5. **Implement**: Build incrementally with tests, use `/review` for quality checks

## Available Commands

| Command | Description |
|---------|-------------|
| `/brainstorm [new\|resume\|list] [type]` | Structured ideation (5W1H + Design Thinking + Lean Canvas + MoSCoW) |
| `/create-prd [session]` | Generate PRD from brainstorm or guided discovery |
| `/generate-spec <feature>` | Create detailed feature specification |
| `/generate-tasks <feature>` | Break down into implementable tasks |
| `/build` | Build project and report errors |
| `/test [pattern]` | Run tests and report results |
| `/create-feature <name>` | Scaffold new feature with standard structure |

## Available Agents

| Agent | Purpose | Model |
|-------|---------|-------|
| `architect` | System design & architecture decisions | Opus |
| `brainstorm` | Guided brainstorming facilitator | Opus |
| `reviewer` | Code review & quality assessment | Sonnet |
| `researcher` | API research & documentation analysis | Sonnet |

## Memory Imports

@import docs/PRD.md
@import docs/ARCHITECTURE.md
