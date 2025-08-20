Create a new task in the project's docs/1_specs folder.

# Goal
Transform vague, high-level, or informal task descriptions into detailed technical specifications that developers can immediately implement.

# Instructions for Claude

## 1) Parse the Task Description
- Extract the core objective from $ARGUMENTS (the task description provided by the user)
- Identify any implicit requirements or assumptions
- Recognize the scope and complexity of the requested feature or change

## 2) Invoke Requirements-Spec-Analyst Agent
You MUST use the Task tool to launch the requirements-spec-analyst agent with the following prompt:

```
Analyze the following task description and create comprehensive requirements and specifications:

Task Description: $ARGUMENTS

Please provide:
1. Complete functional and non-functional requirements
2. Detailed acceptance criteria with edge cases
3. Technical specifications including API contracts and data models
4. Implementation guidelines and architecture recommendations
5. Risk assessment and assumptions

Ensure the output is stored as a markdown file in docs/1_specs/ folder as per your configuration.
```

## 3) No Direct Analysis
Do NOT attempt to analyze or break down the requirements yourself. The specialized agent is specifically designed for this task and has the proper context and framework to produce comprehensive specifications.

# How to use $ARGUMENTS
The $ARGUMENTS contains the task description provided by the user. Pass this directly to the requirements-spec-analyst agent without modification.

Examples:
- "Add user authentication with OAuth"
- "Implement real-time chat functionality"
- "Create a dashboard for analytics data"
- "Build a file upload system with validation"

# Expected Outcome
The requirements-spec-analyst agent will:
- Create a comprehensive specification document
- Store it in the docs/1_specs/ folder
- Provide detailed requirements that developers can immediately work from
- Include all necessary technical details and implementation guidance

# Notes
- This command is a direct bridge to the specialized requirements-spec-analyst agent
- Do not attempt to summarize or modify the agent's output
- The agent will handle all formatting, documentation, and storage requirements
