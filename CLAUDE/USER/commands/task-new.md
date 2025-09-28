Create a new task in the project's docs/1_specs folder.

# Goal
Transform vague, high-level, or informal task descriptions into detailed technical specifications that developers can immediately implement.

# Instructions for Claude

## 1) Parse the Task Description
- Extract the core objective from $ARGUMENTS (the task description provided by the user)
- Identify any implicit requirements or assumptions
- Recognize the scope and complexity of the requested feature or change

## 2) Analyze and Create Specifications
Analyze the task description and create comprehensive requirements and specifications:

Task Description: $ARGUMENTS

Please provide:
1. Complete functional and non-functional requirements
2. Detailed acceptance criteria with edge cases
3. Technical specifications including API contracts and data models
4. Implementation guidelines and architecture recommendations
5. Risk assessment and assumptions

Store the output as a markdown file in docs/1_specs/ folder.

# How to use $ARGUMENTS
The $ARGUMENTS contains the task description provided by the user. Use this to create comprehensive specifications.

Examples:
- "Add user authentication with OAuth"
- "Implement real-time chat functionality"
- "Create a dashboard for analytics data"
- "Build a file upload system with validation"

# Expected Outcome
This command will:
- Create a comprehensive specification document
- Store it in the docs/1_specs/ folder
- Provide detailed requirements that developers can immediately work from
- Include all necessary technical details and implementation guidance

# Notes
- This command creates detailed specifications for development tasks
- Ensure all technical requirements are captured comprehensively
- Follow established documentation formatting and storage requirements
