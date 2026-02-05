# iosDevflow — Claude Code Configuration Framework

> A comprehensive, schema-compliant Claude Code project configuration featuring the iosDevflow brainstorming engine, PRD workflow, agents, skills, hooks, and commands — all wired into the official `settings.json` schema.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue.svg)](https://claude.ai/code)

---

## 📁 Directory Structure

```
project-root/
├── CLAUDE.md                                  # Project memory & instructions
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
│   │   ├── brainstorm.md                      # 5-phase brainstorming (Opus)
│   │   ├── researcher.md                      # Technical research (Sonnet)
│   │   ├── reviewer.md                        # Code review (Sonnet)
│   │   └── specialist.md                      # Domain expert template
│   │
│   ├── commands/                              # Slash commands (/command-name)
│   │   ├── _base-command.md                   # Command template
│   │   ├── brainstorm.md                      # /brainstorm [new|resume] [type]
│   │   ├── build.md                           # /build
│   │   ├── create-feature.md                  # /create-feature <n>
│   │   ├── create-prd.md                      # /create-prd [session]
│   │   ├── generate-spec.md                   # /generate-spec <feature>
│   │   ├── generate-tasks.md                  # /generate-tasks <feature>
│   │   └── test.md                            # /test
│   ├── hooks/                                 # Lifecycle scripts (wired in settings.json)
│   │   ├── session-start.sh                   # → SessionStart hook
│   │   ├── post-edit.sh                       # → PostToolUse (Write|Edit) hook
│   │   ├── file-protection.sh                 # → PreToolUse (Write|Edit) hook
│   │   └── statusline.sh                      # → statusLine command
│   │
│   ├── skills/                                # Auto-activated capabilities
│   │   ├── _base-skill/SKILL.md               # Skill template
│   │   ├── brainstorming/                     # 5-phase brainstorming engine
│   │   │   ├── SKILL.md                       # Main methodology
│   │   │   ├── references/
│   │   │   │   ├── question-bank.md           # 100+ curated questions
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
    ├── specs/                                 # Feature specifications
    │   └── template.md
    └── tasks/                                 # Task breakdowns
        └── template.md
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
/brainstorm → /create-prd → /generate-spec → /generate-tasks
```

| Phase | Command | Methodology | Output |
|-------|---------|-------------|--------|
| 1 | `/brainstorm new [type]` | 5W1H + Design Thinking + Lean Canvas + MoSCoW + User Stories | `docs/brainstorm/session-*.md` |
| 2 | `/create-prd` | PRD generation from session or guided discovery | `docs/PRD.md` |
| 3 | `/generate-spec <feature>` | Technical design from PRD | `docs/specs/<feature>.md` |
| 4 | `/generate-tasks <feature>` | Task breakdown from spec | `docs/tasks/<feature>-tasks.md` |

Project types: `mobile-app`, `library`, `backend`, `cli`, `multi-platform`

---

## 🚀 Quick Start

```bash
# 1. Copy everything to your project root
cp -r .claude/ your-project/
cp CLAUDE.md .mcp.json .gitignore your-project/
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

# 7. Try the PRD workflow
# /brainstorm new mobile-app
```

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

*Framework Version: 2.0.0 — Schema-Compatible Edition*
*Compatible with Claude Code*
