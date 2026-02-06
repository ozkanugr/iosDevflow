---
description: Create a new feature with standard structure
argument-hint: <FeatureName>
allowed-tools: Read, Write, Edit
---

# Create Feature: $ARGUMENTS

Scaffold a new feature following project conventions.

## Steps

1. Read existing features to understand project patterns
2. Create feature directory structure
3. Generate base files:
   - Main component/view
   - ViewModel/Controller (if applicable)
   - Model types
   - Tests
4. Update any routing/navigation configuration
5. Add feature to relevant indexes/exports

## Directory Structure

```
Features/
└── $ARGUMENTS/
    ├── Views/
    │   └── ${ARGUMENTS}View.[ext]
    ├── ViewModels/
    │   └── ${ARGUMENTS}ViewModel.[ext]
    ├── Models/
    │   └── ${ARGUMENTS}Model.[ext]
    └── Tests/
        └── ${ARGUMENTS}Tests.[ext]
```

## Guidelines

- Follow existing naming conventions in the project
- Use the project's established architectural pattern
- Include proper documentation headers
- Add basic unit test scaffolding
- Follow the project's import organization

## Output

- Created file listing
- Brief description of each file's purpose
- Suggested next steps for implementation
