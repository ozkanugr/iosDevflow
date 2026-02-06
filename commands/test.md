---
description: Run tests and report results
argument-hint: <optional-test-pattern>
allowed-tools: Read, Bash
---

# Run Tests

Execute tests and provide a comprehensive report.

## Steps

1. Detect the test framework in use
2. Run tests (all or matching `$ARGUMENTS` pattern)
3. Capture test output
4. Parse and report results:
   - Total tests run
   - Passed/failed/skipped counts
   - Details of any failures

## Test Framework Detection

Look for:
1. Test configuration files
2. Test directories (tests/, __tests__/, *Tests/)
3. Test runner commands in package configs

## Failure Reporting

For each failure:
- Test name and file location
- Expected vs actual values
- Stack trace or relevant context
- Suggested investigation steps

## Output

```
Tests: X passed, Y failed, Z skipped
Time: Ns

[If failures:]
FAILURES:
1. [Test name]
   Location: [file:line]
   Error: [message]

[Summary of what might be wrong]
```
