# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
Platform AI is a documentation repository tracking AI use cases across Vipps MobilePay departments. The project focuses on identifying efficiency improvements for teams without dedicated developers.

## Architecture & Management
This is a documentation-centric project with no build system or dependencies:
- **use-cases.md**: Main tracking document with dual-structure (overview table + detailed sections)
- **README.md**: Basic project introduction with team information
- **Git workflow**: Standard workflow with main branch and feature branches
- **use-case-validator agent**: Maintains document consistency

## Use Case Management
All use cases follow a dual-structure approach that **must remain synchronized**:

1. **Overview table**: Quick status tracking (Use Case, Team/Segment, Priority, Status, Date)
2. **Detailed sections**: Full template with Team/Segment, Main Contact, Problem, AI Solution, Impact, Priority, Status, Date Identified, Notes

**Critical**: Use the use-case-validator agent after any modifications to ensure synchronization.

## Project Conventions
- **Status Lifecycle**: Identified → In Review → Approved → In Progress → Completed
- **Priority Levels**: High/Medium/Low/TBD
- **Team Coverage**: 17+ departments (Tech Services, Legal, Risk & Compliance, Finance, Accounting, Marketing, HR, Brand, Procurement, etc.)
- **Template Compliance**: All new use cases must follow the established format

## Available Claude Agents

### use-case-validator
**When to use**: After adding, modifying, or removing use cases
**Purpose**: Validates that overview table and detailed sections are synchronized
- Checks every table entry has corresponding detailed section
- Validates field consistency (name, team, priority, status, date)
- Provides specific error reports for quick fixes

## Configuration
- Claude permissions: WebFetch access to `docs.anthropic.com`