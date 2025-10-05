# Validate TODO File Input

Extract the {{project_name}} from $ARGUMENTS (the task description provided by the user). If $ARGUMENTS contains a valid .md filename from docs/3_todos/, proceed with that file

If $ARGUMENTS is empty or doesn't specify a valid spec file, list available specs in docs/3_todos/ and ask the user to provide one
Only accept markdown files that exist in the docs/3_todos/ directory

# Task Statement 
You are refactoring the task-tracking document for the "{{project_name}}" initiative. This initiative always has three companion documents:
- Specification: docs/1_specs/{{project_name}}-spec.md (authoritative requirements and rationale)
- Implementation Plan: docs/2_plans/{{project_name}}-spec-plan.md (execution strategy and step breakdown)
- Task Log: docs/3_tasks/{{project_name}}-spec-todos.md (live working context; you are editing this now)

Mission: reshape the task log so it is the lean, high-signal priming context for agents actively implementing tasks, while moving durable knowledge into the spec and plan. Refactoring the todo document therefore includes updating the plan and spec wherever completed work or new insights belong there.

Follow this workflow:
1. Orient
   - Parse the spec and plan to understand current scope, acceptance criteria, dependencies, and planned phases.
   - Scan the task log to locate completed tasks, in-progress items, upcoming work, lessons learned, and blockers.

2. Distill completed work
   - For each completed task/phase, collapse verbose progress notes into concise bullet(s) that capture the final outcome, key metrics, and any follow-on actions.
   - Migrate design decisions, requirement changes, metrics, troubleshooting knowledge, and other durable insights into the appropriate sections of the spec or plan. Update those documents directly and annotate the task log so readers know where to look.

3. Sharpen active and future tasks
   - Ensure every in-progress or upcoming task retains the minimum context needed for execution (objective, current status, dependencies, open questions).
   - Incorporate newly learned insights or constraints that affect future tasks.
   - Remove stale blockers or obsolete commentary; replace them with actionable next steps or validation gates.

4. Maintain structure and traceability
   - Preserve or introduce clear sections (e.g., Progress Summary, Active Tasks, Upcoming Tasks, Dependencies, Notes).
   - Keep checkbox tracking where helpful.
   - Reference relevant spec/plan sections so readers can jump to deeper detail.

5. Synchronize the document set
   - After editing, review the spec, plan, and task log together to confirm they tell a coherent, non-contradictory story, with each piece of information living in its optimal home.
   - Note any remaining gaps or follow-ups required to keep them aligned.

6. Deliverables
   - Revised docs/3_tasks/{{project_name}}-spec-todos.md containing focused, current working context.
   - Corresponding edits to docs/1_specs/{{project_name}}-spec.md and/or docs/2_plans/{{project_name}}-spec-plan.md that capture migrated knowledge.
   - A brief summary of changes so reviewers can validate before committing.

# Constraints:
- Prioritize brevity and clarity; minimize token-heavy narrative.
- Do not discard information future executors need—relocate it instead.
- Highlight open questions or decisions awaiting confirmation.
- Respect existing repository formatting conventions.
