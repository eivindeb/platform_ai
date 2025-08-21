
# Security and Privacy Risk Identification

|                                 |                  |
|---|---|
| **Service Owner(s)**            | AI Platform team |
| **Risk Owner**                  | Sven Malvik |
| **Service Data Classification** | `INTERNAL`       |
| **Last Reviewed**               | 21/08/25         |

## Service description

Platform AI is a comprehensive documentation and workflow repository for AI initiatives across Vipps MobilePay departments, including use case tracking for AI initiatives, Claude Code configurations, and project guidance.

The repository contains:
- Use case tracking documentation (use-cases.md) with dual-structure format (overview table + detailed sections)
- Project documentation (README.md)
- Claude Code configuration and project guidance (CLAUDE.md)
- Custom Claude Code prompts and workflows (CLAUDE/USER/commands/)
- Security and privacy risk identification (ria.md)

The repository is hosted on GitHub and contains only documentation - no executable code, APIs, or runtime services. All content is stored as markdown files in version control.

Access is controlled through standard GitHub repository permissions. The repository tracks AI use case information across 17+ departments including HR, Legal, Finance, Accounting, Marketing, Brand, Procurement, and others.

## Data dictionary

| Data                        | Classification | Comments                                                                                                    |
|---|---|---|
| Use Case Information        | `INTERNAL`     | Details about AI initiatives, problems, solutions, and impact across departments. Contains business strategy information. |
| Department Names            | `INTERNAL`     | Names and structure of Vipps MobilePay departments (HR, Legal, Finance, etc.). Organizational information. |
| Contact Names               | `INTERNAL`     | Names of main contacts for use cases. Employee identification information.                                  |
| Process Descriptions        | `INTERNAL`     | Detailed descriptions of current inefficiencies and manual processes. Business operations information.       |
| AI Solution Details         | `CONFIDENTIAL` | Proposed AI implementations, technologies, and approaches. Could reveal strategic AI capabilities and plans. |
| Priority Classifications    | `INTERNAL`     | Business priority levels (High/Medium/Low/TBD) indicating strategic importance of initiatives.              |
| Status Information          | `INTERNAL`     | Current status of use cases through lifecycle (Identified → In Review → Approved → In Progress → Completed). |
| Impact Assessments          | `INTERNAL`     | Expected efficiency improvements and business impact. Could reveal operational weaknesses and improvement targets. |
| Claude Code Configurations  | `INTERNAL`     | Custom prompts, workflows, and AI assistant configurations. Could contain proprietary prompt engineering.    |
| Risk Assessment Data        | `INTERNAL`     | Security and privacy risk scenarios, controls, and mitigation strategies. Security-sensitive information.    |

## Risk scenarios / Impact Analysis

| Risk scenario                          | Risk Driver                                                                                                                                                                                                 | Impact - What may happen if we don't implement the controls?                                                                                          | Security Controls                                                                 |
|---|---|---|---|
| Sensitive use case information exposure | Repository contains details about internal processes, departments, and potential AI implementations that could reveal business operations to unauthorized parties | Internal processes and strategic AI initiatives could be exposed to competitors or unauthorized individuals | GitHub repository access controls, periodic review of content sensitivity |
| Documentation inconsistency            | Manual maintenance of dual-structure format in use-cases.md could lead to synchronization issues and inaccurate tracking | Inaccurate use case status tracking, potential missed opportunities, confusion about project priorities | use-case-validator agent, regular documentation audits |
| Use case stagnation                    | Identified use cases may remain in "Identified" status without clear progression criteria or ownership | Efficiency opportunities not realized, departments continue manual processes, reduced ROI on AI initiatives | Defined approval workflow, regular status reviews, clear ownership assignment |
| Unauthorized modifications             | Without proper review processes, inappropriate or inaccurate use case information could be committed | Misleading information about departmental needs, incorrect prioritization, potential compliance issues | GitHub branch protection, pull request reviews, defined contributor roles |

[//]: # (Do not delete; used for stats: e68412b4-5dc8-4af6-aef3-67034c73e2c6)
