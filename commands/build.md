---
description: Build the project and report any errors
allowed-tools: Read, Bash
---

# Build Project

Build the project and provide a clear report of results.

## Steps

1. Detect the project type and build system
2. Run the appropriate build command
3. Capture and analyze any errors or warnings
4. Report results with:
   - Build status (success/failure)
   - Error details with file locations
   - Suggested fixes for common errors

## Build System Detection

Check for these in order:
1. Package manager configs (package.json, Cargo.toml, etc.)
2. Build tool configs (Makefile, CMakeLists.txt, etc.)
3. IDE project files (.xcodeproj, .sln, etc.)

## Error Reporting

For each error:
- File path and line number
- Error message
- Suggested fix if obvious

## Output

- Clear build status indicator
- List of errors/warnings if any
- Suggestions for fixing issues
