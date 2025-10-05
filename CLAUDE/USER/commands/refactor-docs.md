# Validate TODO File Input

Extract the {{project_name}} from $ARGUMENTS (the task description provided by the user). If $ARGUMENTS contains a valid .md filename from docs/3_todos/, proceed with that file.

If $ARGUMENTS is empty or doesn't specify a valid spec file, list available specs in docs/3_todos/ and ask the user to provide one.  
Only accept markdown files that exist in the docs/3_todos/ directory.

# Task Statement

You are refactoring the task-tracking document for the "{{project_name}}" initiative. This initiative always has three companion documents:  
- Specification: docs/1_specs/{{project_name}}-spec.md (authoritative requirements and rationale)  
- Implementation Plan: docs/2_plans/{{project_name}}-spec-plan.md (execution strategy and step breakdown)  
- Task Log: docs/3_tasks/{{project_name}}-spec-todos.md (live working context; you are editing this now)

Mission: reshape the task log so it is the lean, high-signal priming context for agents actively implementing tasks, while moving durable knowledge into the spec and plan. Refactoring the todo document therefore includes updating the plan and spec wherever completed work or new insights belong there.

Follow this workflow:

1. **Orient**  
   - Parse the spec and plan to understand current scope, acceptance criteria, dependencies, and planned phases.  
   - Scan the task log to locate completed tasks, in-progress items, upcoming work, lessons learned, and blockers.  
   - Retain the existing “How to Use This Document” section (including its migration context bullets) verbatim unless the user requests changes; it is mandatory onboarding content.

2. **Distill completed work**  
   - For each completed task/phase, compress verbose notes into concise bullets covering objective, completion date, key outcomes/metrics, and follow-on actions.
   - When collapsing deep dives (e.g., hardware deployment logs), move the durable details into the spec or plan, note exactly where they now live, and leave a pointer in the task log (e.g., “See Spec §8.2 for full deployment notes.”).
   - Use the existing Phase 1–3 summaries as the compression model .
   - Use this as a template for compression of completed phases (2–3 bullets with links to spec/plan sections):

EXAMPLE OF COMPRESSION
## Phase 1: Wyoming Protocol Services Deployment (Completed)
- Wyoming Faster-Whisper, Piper, and OpenWakeWord added to `vars/main_vars.yml`, deployed via Ansible, and validated through Assist pipeline tests.
- Baseline latency/resource metrics captured for comparison with later optimizations.

## Phase 2: Ollama LLM Deployment (Completed)
- GPU-enabled Ollama container deployed with NVIDIA runtime configured, Gemma 2B pulled, and throughput/VRAM baselines recorded.

## Phase 3: Voice Orchestrator Development (Completed)
- Voice orchestrator FastAPI service delivered with numbered entity context, HA service execution, Ollama integration, Prometheus metrics, and unit tests.
- Docker image built and deployed; service definitions stored in Ansible.
EXAMPLE END.

3. **Sharpen active and future tasks**  
   - Ensure every in-progress or upcoming task keeps the minimum execution context (objective, current status, dependencies, open questions).  
   - Group active sections into clear “Completed / Active / Next” or similar subheadings so trimming finished work remains safe.  
   - Incorporate new insights or constraints that affect future tasks without losing traceability.

4. **Maintain structure, traceability, and essential summaries**  
   - Keep the executive/progress summary near the top; even after moving detail out, the log must retain a one-paragraph recap with links back to spec/plan sections.  
   - Every phase should retain a short status blurb (completed or active). Active phases can carry more detail but must stay skimmable.  
   - Preserve or introduce clear sections (e.g., Progress Summary, Active Tasks, Upcoming Tasks, Dependencies, Notes).  
   - Keep checkbox tracking where helpful and reference relevant spec/plan sections so readers can jump to deeper detail.

5. **Protect unfinished work**  
   - Before removing or collapsing any subsection, confirm all child tasks are complete or restated elsewhere in this document.  
   - Outstanding checkboxes, open questions, and known issues must remain in the task log unless the user explicitly marks them obsolete.

6. **Synchronize the document set**  
   - After moving durable knowledge into the spec or plan, update those documents directly and cite the new locations in the task log’s cross-document notes.  
   - Review the spec, plan, and task log together to confirm they tell a coherent, non-contradictory story with information in its optimal home.  
   - Note any remaining gaps or follow-ups required to keep them aligned.

7. **Deliverables**  
   - Revised docs/3_tasks/{{project_name}}-spec-todos.md containing focused, current working context while honoring the preserved scaffolding above.  
   - Corresponding edits to docs/1_specs/{{project_name}}-spec.md and/or docs/2_plans/{{project_name}}-spec-plan.md capturing migrated knowledge.  
   - A brief summary of changes so reviewers can validate before committing.

# Constraints
- Prioritize brevity and clarity; minimize token-heavy narrative.  
- Do not discard information future executors need—relocate it instead.  
- Highlight open questions or decisions awaiting confirmation.  
- Respect existing repository formatting conventions.
