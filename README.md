# iosDevflow — Claude Code Configuration Framework

> A comprehensive, schema-compliant Claude Code project configuration featuring the **dynamic multi-mode brainstorming engine** (14 modes), PRD workflow, agents, skills, hooks, and commands — all wired into the official `settings.json` schema.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue.svg)](https://claude.ai/code)

---

## 🧠 Dynamic Multi-Mode Brainstorming

The brainstorming engine supports **14 combinable modes** with **intelligent auto-detection**:

```bash
# Auto-detect modes based on description (RECOMMENDED)
/brainstorm A fitness tracking app for runners
/brainstorm Healthcare appointment booking system        # Auto-detects: high-risk modes
/brainstorm New social platform to compete with Instagram # Auto-detects: competitive modes

# Or specify modes explicitly
/brainstorm full A fitness tracking app for runners
/brainstorm quick A new settings page
/brainstorm 5w1h,swot,competitor,moscow An AI writing assistant
/brainstorm validate A healthcare data system
```

### Auto-Detection

When no modes specified, the system analyzes your description and selects appropriate modes:

| Detected Signal | Auto-Added Modes |
|-----------------|------------------|
| Healthcare, Finance, Legal | `risk`, `assumption`, `reverse` |
| Startup, SaaS, Business | `lean-canvas`, `jtbd` |
| Competitor, Market | `competitor`, `swot` |
| Innovative, Creative | `starburst`, `scamper` |
| Simple feature | `quick` preset |
| Complex platform | `full` + extended modes |

### Available Modes

| Core Modes | Extended Modes |
|------------|----------------|
| `5w1h` - WHO, WHAT, WHEN, WHERE, WHY, HOW | `reverse` - Failure mode analysis |
| `design-thinking` - User-centered design | `starburst` - Question explosion |
| `lean-canvas` - Business model | `scamper` - Innovation technique |
| `moscow` - Feature prioritization | `swot` - Strategic analysis |
| `user-stories` - Implementation specs | `competitor` - Competitive analysis |
| | `jtbd` - Jobs-to-be-Done |
| | `risk` - Risk assessment |
| | `assumption` - Assumption validation |
| | `six-hats` - Multi-perspective thinking |

### Presets

| Preset | Expands To | Best For |
|--------|------------|----------|
| `full` | 5w1h → design-thinking → lean-canvas → moscow → user-stories | New projects |
| `quick` | 5w1h → moscow | Quick features |
| `validate` | reverse → swot → risk → assumption | Risk assessment |
| `ideate` | starburst → scamper → six-hats | Creative exploration |
| `business` | lean-canvas → swot → competitor → jtbd | Business model |

---

## 📁 Directory Structure

```
project-root/
├── CLAUDE.md                                  # Project memory & instructions
├── brainstorm-and-prd.md                      # Multi-mode brainstorming documentation
├── .mcp.json                                  # MCP server definitions
├── .gitignore                                 # Git ignores (includes .claude/settings.local.json)
│
├── .claude/
│   ├── settings.json                          # ✅ Team settings (schema-compliant, in git)
│   ├── settings.local.json                    # 🔒 Personal overrides (gitignored)
│   │
│   ├── agents/                                # Subagent definitions
│   │   ├── _base-agent.md                     # Universal agent template
│   │   ├── architect.md                       # System design (Opus)
│   │   ├── brainstorm.md                      # Multi-mode brainstorming (Opus)
│   │   ├── researcher.md                      # Technical research (Sonnet)
│   │   ├── reviewer.md                        # Code review (Sonnet)
│   │   └── specialist.md                      # Domain expert template
│   │
│   ├── commands/                              # Slash commands (/command-name)
│   │   ├── _base-command.md                   # Command template
│   │   ├── brainstorm.md                      # /brainstorm <modes> <app details>
│   │   ├── build.md                           # /build
│   │   ├── create-architecture.md             # /create-architecture [prd]
│   │   ├── create-feature.md                  # /create-feature <n>
│   │   ├── create-prd.md                      # /create-prd [session]
│   │   ├── generate-tasks.md                  # /generate-tasks <feature> (spec + tasks)
│   │   └── test.md                            # /test
│   │
│   ├── hooks/                                 # Lifecycle scripts (wired in settings.json)
│   │   ├── session-start.sh                   # → SessionStart hook
│   │   ├── post-edit.sh                       # → PostToolUse (Write|Edit) hook
│   │   ├── file-protection.sh                 # → PreToolUse (Write|Edit) hook
│   │   └── statusline.sh                      # → statusLine command
│   │
│   ├── skills/                                # Auto-activated capabilities
│   │   ├── _base-skill/SKILL.md               # Skill template
│   │   ├── brainstorming/                     # Multi-mode brainstorming engine
│   │   │   ├── SKILL.md                       # 14 modes methodology
│   │   │   ├── references/
│   │   │   │   ├── question-bank.md           # 200+ curated questions
│   │   │   │   ├── design-thinking.md         # Design Thinking guide
│   │   │   │   └── lean-canvas.md             # Lean Canvas guide
│   │   │   └── templates/
│   │   │       ├── universal.md               # Domain-agnostic
│   │   │       ├── mobile-app.md              # Mobile applications
│   │   │       ├── library.md                 # Libraries/packages
│   │   │       └── backend.md                 # Backend/server
│   │   ├── testing/SKILL.md                   # Testing patterns
│   │   └── components/SKILL.md                # Component building
│   │
│   ├── output-styles/
│   │   └── mentor.md                          # Teaching-focused response style
│   │
│   └── plans/                                 # Stored plan files
│
└── docs/                                      # Project documentation
    ├── PRD.md                                 # Product Requirements Document
    ├── ARCHITECTURE.md                        # Architecture decisions
    ├── brainstorm/                            # Brainstorming sessions
    └── tasks/                                 # Feature specs + task breakdowns
        └── template.md                        # Unified spec + tasks template
```

---

## ⚙️ What the Schema Integration Adds

Your original iosDevflow templates are now fully wired into the Claude Code settings system:

| Original Component | Schema Integration |
|---|---|
| `hooks/session-start.sh` | → `settings.json` → `hooks.SessionStart` |
| `hooks/file-protection.sh` | → `settings.json` → `hooks.PreToolUse` (matcher: `Write\|Edit`) |
| `hooks/post-edit.sh` | → `settings.json` → `hooks.PostToolUse` (matcher: `Write\|Edit`) |
| `output-styles/mentor.md` | → `settings.json` → `"outputStyle": "Mentor"` |
| Agent tool access | → `settings.json` → `permissions.allow/ask/deny` |
| MCP servers | → `.mcp.json` + `settings.json` → `enabledMcpjsonServers` |
| Secrets protection | → `settings.json` → `permissions.deny` (`.env`, `.key`, `.pem`, etc.) |
| Lock file protection | → `settings.json` → `permissions.deny` (lock files) |
| Build output protection | → `settings.json` → `permissions.deny` (dist/, build/, etc.) |

**New capabilities added:**
- Full audit logging across 10 lifecycle events (SessionStart → PreCompact)
- Sandbox isolation for bash commands
- `settings.local.json` for personal model/env overrides
- Status line showing branch, project type, changes, time
- Company announcements with PRD workflow hints
- Setup hook to auto-chmod hook scripts
- Git attribution configuration

---

## 🔐 Settings Hierarchy (Precedence: High → Low)

| Scope | File | Shared? |
|-------|------|---------|
| **Enterprise Managed** | `/etc/claude-code/managed-settings.json` | IT-deployed |
| **CLI Arguments** | `claude --model ...` | Per-session |
| **Local Project** | `.claude/settings.local.json` | ❌ Gitignored |
| **Shared Project** | `.claude/settings.json` | ✅ In git |
| **User Global** | `~/.claude/settings.json` | Personal |

---

## 🪝 Hooks Wiring Map

| Hook Script | settings.json Event | Matcher | Purpose |
|---|---|---|---|
| `session-start.sh` | `SessionStart` | — | Environment detection, git status |
| `file-protection.sh` | `PreToolUse` | `Write\|Edit` | Block edits to secrets, lock files, binaries |
| `post-edit.sh` | `PostToolUse` | `Write\|Edit` | Auto-lint by file extension |
| `statusline.sh` | `statusLine` | — | Branch, project type, changes, time |
| *(inline)* | `PostToolUseFailure` | — | Error logging |
| *(inline)* | `UserPromptSubmit` | — | Audit logging |
| *(inline)* | `SubagentStart/Stop` | — | Audit logging |
| *(inline)* | `PreCompact` | — | Audit logging |
| *(inline)* | `Setup` | — | Auto-chmod hooks |

---

## 📝 PRD Workflow

```
/brainstorm → /create-prd → /create-architecture → /generate-tasks
                   │                 │                    │
                   │                 │                    └── Feature spec + implementation tasks
                   │                 └── Auto-updates CLAUDE.md
                   └── Auto-updates CLAUDE.md
```

### Brainstorm Command

```bash
/brainstorm [mode(s)] <application details>
```

Modes are **optional** - if not specified, they are auto-detected from your description.

**Examples:**
```bash
# Auto-detection (recommended)
/brainstorm A task management mobile app
/brainstorm Healthcare patient portal with appointments
/brainstorm Innovative social app for local communities

# Explicit modes
/brainstorm full A task management mobile app
/brainstorm 5w1h,lean-canvas,moscow A SaaS analytics platform
/brainstorm quick A user profile settings feature
/brainstorm validate,competitor A fintech payment solution
```

### Session Management

```bash
/brainstorm resume          # Continue latest session
/brainstorm list            # Show all sessions
/brainstorm add <modes>     # Add modes to current session
```

### Workflow Phases

| Phase | Command | Output |
|-------|---------|--------|
| 1 | `/brainstorm <modes> <app>` | `docs/brainstorm/session-*.md` |
| 2 | `/create-prd` | `docs/PRD.md` + updates `CLAUDE.md` |
| 3 | `/create-architecture` | `docs/ARCHITECTURE.md` + updates `CLAUDE.md` |
| 4 | `/generate-tasks <feature>` | `docs/tasks/<feature>.md` (spec + tasks) |

### Mode Selection Guide

| Scenario | Recommended |
|----------|-------------|
| Brand new product | `full` preset |
| Quick feature scoping | `quick` preset |
| High-risk/regulated domain | `5w1h,validate` |
| Competitive market | `business` preset |
| Creative exploration | `ideate` preset |
| Before major investment | `5w1h,assumption,risk,competitor` |

---

## 🚀 Quick Start

```bash
# 1. Copy everything to your project root
cp -r .claude/ your-project/
cp CLAUDE.md .mcp.json .gitignore brainstorm-and-prd.md your-project/
cp -r docs/ your-project/

# 2. Make hooks executable
chmod +x your-project/.claude/hooks/*.sh

# 3. Customize CLAUDE.md with your project details
#    Replace [PROJECT_NAME], [Platform], [Language], etc.

# 4. Customize settings.json permissions for your stack
#    Uncomment platform-specific build tools in permissions.allow

# 5. Create personal overrides (already gitignored)
#    Edit .claude/settings.local.json with your model preference

# 6. Start working
cd your-project
claude  # or launch Claude Code

# 7. Try the brainstorming workflow
# /brainstorm full A fitness tracking app for runners
```

---

## 📖 Brainstorming Modes Reference

### Core Modes

| Mode | Description | Questions |
|------|-------------|-----------|
| `5w1h` | Comprehensive WHO, WHAT, WHEN, WHERE, WHY, HOW discovery | ~50 |
| `design-thinking` | Empathize → Define → Ideate → Prototype → Test | ~25 |
| `lean-canvas` | One-page business model canvas | ~25 |
| `moscow` | Must/Should/Could/Won't prioritization | ~25 |
| `user-stories` | Story generation with acceptance criteria | ~15 |

### Extended Modes

| Mode | Description | Questions |
|------|-------------|-----------|
| `reverse` | "What could make this fail?" - inverted problem solving | ~15 |
| `starburst` | Question-explosion (generate 60+ questions) | ~60 |
| `scamper` | Substitute, Combine, Adapt, Modify, Put to use, Eliminate, Reverse | ~35 |
| `swot` | Strengths, Weaknesses, Opportunities, Threats | ~20 |
| `competitor` | Competitive landscape and differentiation | ~20 |
| `jtbd` | Jobs-to-be-Done framework | ~30 |
| `risk` | Risk identification and assessment | ~25 |
| `assumption` | Surface and validate hidden assumptions | ~25 |
| `six-hats` | Six Thinking Hats multi-perspective analysis | ~30 |

---

## 📚 References

- [Official Settings Docs](https://code.claude.com/docs/en/settings)
- [JSON Schema](https://json.schemastore.org/claude-code-settings.json)
- [Hooks Documentation](https://code.claude.com/docs/en/hooks)
- [MCP Configuration](https://code.claude.com/docs/en/mcp)
- [Permission System](https://code.claude.com/docs/en/iam)
- [Sandboxing Guide](https://code.claude.com/docs/en/sandboxing)
- [Memory Management](https://code.claude.com/docs/en/memory)
- [Output Styles](https://code.claude.com/docs/en/output-styles)

---

## 📄 Key Files

| File | Purpose |
|------|---------|
| `brainstorm-and-prd.md` | Complete brainstorming system documentation |
| `.claude/commands/brainstorm.md` | Command definition with all 14 modes |
| `.claude/commands/generate-tasks.md` | Unified spec + tasks generation |
| `.claude/skills/brainstorming/SKILL.md` | Full methodology reference |
| `.claude/skills/brainstorming/references/question-bank.md` | 200+ questions for all modes |

---

*Framework Version: 2.1.0 — Multi-Mode Brainstorming Edition*
*Compatible with Claude Code*
