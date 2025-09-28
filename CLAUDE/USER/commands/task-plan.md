Plan the implementation of a task based on specifications from docs/1_specs folder.

# Goal
Take a detailed specification from the docs/1_specs/ folder and create a comprehensive implementation plan that breaks down the work into manageable, sequential tasks.

# Instructions for Claude

## 1) Validate Spec File Input
- If $ARGUMENTS contains a valid .md filename from docs/1_specs/, proceed with that file
- If $ARGUMENTS is empty or doesn't specify a valid spec file, list available specs in docs/1_specs/ and ask the user to provide one
- Only accept markdown files that exist in the docs/1_specs/ directory

## 2) Read and Analyze the Specification
- Read the complete specification file from docs/1_specs/
- Extract all functional requirements, technical specifications, and acceptance criteria
- Identify and catalog all section headers and subsections in the specification
- Map requirements to their specific sections for traceability
- Identify dependencies, prerequisites, and integration points
- Note any risk factors or complexity indicators

## 3) Create Implementation Plan
Create a detailed, step-by-step implementation plan that includes:

### Phase Breakdown
- Break the work into logical phases (e.g., setup, core implementation, testing, integration)
- Sequence phases based on dependencies and logical flow
- Estimate relative effort for each phase

### Task Decomposition
- Break each phase into specific, actionable tasks
- Make tasks small enough to be completed in 1-4 hours each
- Include technical details for each task (files to modify, functions to create, etc.)
- **CRITICAL**: Each task MUST reference the specific section(s) of the specification it implements
- Use format: "Implements [Spec Section X.Y: Title]" or "Addresses requirements from [Section Name]"

### Dependencies and Prerequisites
- Identify what needs to be set up or configured first
- List any external dependencies or integrations required
- Note any architectural decisions that need to be made early

### Testing Strategy
- Plan unit tests, integration tests, and end-to-end tests
- Identify test scenarios and edge cases from acceptance criteria
- Include performance and security testing considerations
- **CRITICAL**: Reference specific acceptance criteria sections from the specification
- Map each test case back to the requirement section it validates

### Risk Mitigation
- Identify potential blockers or complex areas
- Suggest fallback approaches or alternatives
- Plan for unknown unknowns with buffer time

## 4) Output Format
**CRITICAL**: The implementation plan MUST be saved as a markdown file with the following naming convention:
- Take the specification filename and add "-plan" suffix
- Example: "google-calendar-integration-testing-spec.md" becomes "google-calendar-integration-testing-spec-plan.md"
- Save the file in the `docs/2_plans/` folder
- Use the Write tool to create this file

Present the plan in markdown format with:
- Executive summary of the implementation approach
- **Specification Traceability Matrix**: Table mapping each implementation task to specification sections
- Detailed phase-by-phase breakdown with section references
- Task list with clear descriptions, acceptance criteria, and specification section mappings
- Risk assessment and mitigation strategies
- Estimated timeline and effort distribution

### Required Section Reference Format
Every task, phase, and test case MUST include one of these reference formats:
- `[Spec: Section 2.1 - User Authentication]`
- `[Implements: Requirements 3.2.1-3.2.3]`
- `[Addresses: Acceptance Criteria A.1]`
- `[Covers: Non-functional Requirement N.4]`

## 5) Do NOT Create Todo Lists
**IMPORTANT**: Do NOT use the TodoWrite tool or create any todo lists. Only create the implementation plan document as specified above.

# How to use $ARGUMENTS
$ARGUMENTS should contain the filename of a specification document from docs/1_specs/

Examples:
- "google-calendar-integration-testing-spec.md"
- "user-authentication-spec.md"
- "real-time-chat-spec.md"

If no filename is provided or the file doesn't exist, list available specs and prompt the user.

# Expected Outcome
- Comprehensive implementation plan based on the specification
- Clear task breakdown with dependencies and sequencing
- Risk assessment with mitigation strategies
- Actionable next steps for the development team

# Notes
- Always validate that the spec file exists before proceeding
- Focus on practical, implementable tasks rather than high-level concepts
- Consider the existing codebase architecture and patterns
- Include both happy path and error handling in the plan
- **MANDATORY**: Every single task, test case, and implementation item MUST reference its source specification section
- Create a clear audit trail from specification to implementation
- Ensure no specification requirements are missed by maintaining traceability