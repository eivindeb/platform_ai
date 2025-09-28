# Platform AI - Claude Code Custom Commands

This repository provides custom commands and resources to improve the functioning of Claude Code. It implements a spec-driven development workflow system and specialized Claude Code commands for project management and analysis.

## Origin and Modifications

This repository is based on an upstream from the Vipps organization, with the following modifications:

1. **Stripped Vipps-specific files** - All files related to Vipps have been removed to create a clean, generic foundation
2. **Windows compatibility** - Custom commands have been renamed from `task:*` pattern to `task-*` pattern for Windows filesystem compatibility

## Custom Commands Available

### Spec-Driven Development Workflow
- `/task-new [task description]` - Create detailed technical specifications from vague task descriptions in `docs/1_specs/`
- `/task-plan [spec-filename]` - Generate comprehensive implementation plans from specifications in `docs/2_plans/`
- `/task-todos [plan-filename]` - Create actionable todo lists from implementation plans in `docs/3_tasks/`

### Analysis Commands
- `/analyze [focus-area]` - Comprehensive codebase analysis including architecture, risks, and runbook
- `/ria [focus-area]` - Generate Security and Privacy Risk Identification Assessment document
- `/gpt5 [message]` - Send messages to GPT-5 via MCP server

## Getting Started

See [CLAUDE.md](./CLAUDE.md) for detailed documentation on the repository purpose, workflow architecture, and usage guidelines.

## Directory Structure

```
.claude/agents/          # Custom agent definitions
CLAUDE/USER/commands/    # Custom command definitions
docs/                    # Generated during spec-driven workflow
├── 1_specs/            # Technical specifications
├── 2_plans/            # Implementation plans
└── 3_tasks/            # Todo lists and task tracking
```