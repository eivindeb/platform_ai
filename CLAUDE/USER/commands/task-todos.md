Create concrete tasks/todos based on implementation plans from docs/2_plans/ folder.

# Goal
Take a detailed implementation plan from the docs/2_plans/ folder and create actionable todos that can be tracked and executed step-by-step.

# Instructions for Claude

## 1) Validate Plan File Input
- If $ARGUMENTS contains a valid .md filename from docs/2_plans/, proceed with that file
- If $ARGUMENTS is empty or doesn't specify a valid plan file, list available plans in docs/2_plans/ and ask the user to provide one
- Only accept markdown files that exist in the docs/2_plans/ directory

## 2) Read and Analyze the Implementation Plan
- Read the complete implementation plan file from docs/2_plans/
- Extract all phases, tasks, and deliverables from the plan
- Identify the sequence and dependencies between tasks
- Note any specific acceptance criteria or validation requirements
- Extract timeline estimates and priority levels

## 3) Create Concrete Todo List
Use the TodoWrite tool to create a comprehensive todo list that includes:

### Task Extraction
- Convert each task from the implementation plan into a concrete todo item
- Break down complex tasks into smaller, actionable subtasks if needed
- Maintain the original task structure and phase organization
- Preserve all specification references from the original plan

### Todo Format
**CRITICAL**: Each todo MUST include:
- Clear, actionable description derived from the plan task
- **MANDATORY**: Reference to the specific implementation plan section (e.g., "Phase 2.1.1", "Task 3.2.4")
- Reference to the original specification section (preserved from plan)
- Any specific deliverables or acceptance criteria
- Dependencies on other todos (noted in description)

**Required Reference Format for Todos**:
- Plan Reference: `[Plan: Phase X.Y.Z - Task Name]` or `[Implementation: Section X.Y]`
- Spec Reference: `[Spec: Section A.B - Requirement Name]`
- Example: "Set up Jest Testing Framework [Plan: Task 1.1.1] [Spec: Section 14 - Implementation Guidelines]"

### Status Management
- All todos start with status "pending"
- Maintain logical ordering based on the implementation plan phases
- Group related todos by phase when possible

## 4) Output File Creation
**CRITICAL**: Also create a markdown file documenting the todos with the following naming convention:
- Take the plan filename and replace "-plan" with "-todos"
- Example: "google-calendar-integration-testing-spec-plan.md" becomes "google-calendar-integration-testing-spec-todos.md"
- Save the file in the `docs/3_tasks/` folder
- Use the Write tool to create this file

The markdown file should include:
- Link back to the original implementation plan
- Link back to the original specification (if referenced in plan)
- Complete list of all todos with their descriptions
- Phase organization and dependencies
- Progress tracking section

## 5) Todo Management Guidelines
- **FIRST**: Use TodoWrite to create all todos from the plan
- **THEN**: Create the markdown documentation file
- **MANDATORY**: Every single todo MUST reference its implementation plan section
- Ensure todos are actionable and specific
- Maintain traceability to both plan sections AND original specification sections
- Include any testing or validation requirements as separate todos

### Traceability Requirements
**CRITICAL**: Each todo must provide a complete audit trail:
1. **Plan Section Reference**: Which specific task/phase in the implementation plan
2. **Spec Section Reference**: Which original specification requirement (if available)
3. **Deliverables**: What concrete outcome is expected
4. **Acceptance Criteria**: How to validate completion

Example todo description format:
"Configure Jest with TypeScript support and coverage thresholds [Plan: Task 1.1.1] [Spec: Section 14 - Implementation Guidelines] - Deliverable: jest.config.js with 80% coverage requirements"

# How to use $ARGUMENTS
$ARGUMENTS should contain the filename of an implementation plan from docs/2_plans/

Examples:
- "google-calendar-integration-testing-spec-plan.md"
- "user-authentication-spec-plan.md"
- "real-time-chat-implementation-plan.md"

If no filename is provided or the file doesn't exist, list available plans and prompt the user.

# Expected Outcome
- Complete todo list created via TodoWrite tool with all implementation tasks
- Markdown documentation file in docs/3_tasks/ folder
- Clear task progression from plan to executable todos
- Maintained traceability to original specifications
- Ready-to-execute implementation roadmap

# Notes
- Always validate that the plan file exists before proceeding
- Focus on creating actionable, specific todos that can be completed
- Maintain the logical sequence from the implementation plan
- **MANDATORY**: Every todo MUST reference its implementation plan section for complete traceability
- Preserve all specification references for dual traceability (plan + spec)
- Include both implementation and validation/testing todos
- Start all todos with "pending" status for proper workflow management
- Use consistent reference format: `[Plan: Section] [Spec: Section]` for all todos