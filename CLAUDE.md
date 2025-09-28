# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository hosts custom commands and resources to improve the functioning of Claude Code. It provides a spec-driven development workflow system and specialized Claude Code commands for project management and analysis.

## Custom Commands Available

### Spec-Driven Development Workflow
- `/task-new [task description]` - Create detailed technical specifications from vague task descriptions in `docs/1_specs/`
- `/task-plan [spec-filename]` - Generate comprehensive implementation plans from specifications in `docs/2_plans/`
- `/task-todos [plan-filename]` - Create actionable todo lists from implementation plans in `docs/3_tasks/`

### Analysis Commands
- `/analyze [focus-area]` - Comprehensive codebase analysis including architecture, risks, and runbook
- `/ria [focus-area]` - Generate Security and Privacy Risk Identification Assessment document
- `/gpt5 [message]` - Send messages to GPT-5 via MCP server

## Workflow Architecture

The repository implements a structured 3-phase development approach:

1. **Specification Phase** (`docs/1_specs/`)
   - Transform informal requirements into detailed technical specifications
   - Include functional/non-functional requirements, acceptance criteria, technical specs

2. **Planning Phase** (`docs/2_plans/`)
   - Convert specifications into implementation plans with task breakdown
   - Maintain traceability to original specification sections
   - Include risk assessment and testing strategies

3. **Execution Phase** (`docs/3_tasks/`)
   - Generate concrete todo lists from implementation plans
   - Preserve dual traceability (plan section + spec section references)
   - Enable systematic execution tracking

## Directory Structure

```
.claude/agents/          # Custom agent definitions
CLAUDE/USER/commands/    # Custom command definitions
docs/                    # Generated during spec-driven workflow
├── 1_specs/            # Technical specifications
├── 2_plans/            # Implementation plans
└── 3_tasks/            # Todo lists and task tracking
```

## Key Features

### Traceability System
All commands maintain complete audit trails:
- Todo items reference implementation plan sections: `[Plan: Section X.Y]`
- Implementation tasks reference specification sections: `[Spec: Section A.B]`
- Enables tracking from requirements to implementation

### Custom Agent
- `use-case-validator` - Validates synchronization between overview tables and detailed sections in use-cases.md files

### Spec-Driven Development Guidelines
- Create comprehensive specifications before implementation
- Break complex projects into phases with clear dependencies
- Maintain documentation alignment throughout development
- Test after each phase completion

## Development Notes

- This is a documentation and command repository - no build tools or dependencies required
- Commands are defined as markdown files in `CLAUDE/USER/commands/`
- The spec-driven workflow creates its own folder structure as needed
- All generated documentation follows consistent naming conventions with proper suffixes (-plan, -todos)