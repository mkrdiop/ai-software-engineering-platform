# AI Software Engineering Platform

**Workflow-first · Agent-powered · Evidence-driven**

AI Software Engineering Platform (AISP) is a cloud SaaS engineering workspace designed to coordinate professional software delivery through specialized AI roles, controlled autonomy, human approval gates, and verifiable engineering evidence.

## Product direction

- Audience: individual software professionals and professional engineering teams.
- Deployment: cloud SaaS.
- UX: centralized Engineering Workspace.
- Execution: integrated, isolated Docker environments.
- Operating model: Project Owner, Product Manager, Software Architect, Planner, Developer, Independent Code Reviewer, QA & Test Engineer, Security Auditor, and Delivery Manager.
- Relationship to Enterprise Factory: standalone, with interoperability considered deliberately rather than assumed.

## Core engineering principle

AISP is its own first customer. Its development must follow the same engineering governance, quality gates, traceability, and evidence standards the product intends to provide to its customers.

## Source of truth

- **Notion:** product requirements, architecture, ADRs, API contracts, governance, and durable decisions.
- **Linear:** official backlog, tasks, dependencies, priorities, and milestones. Team: `AiSoftTeam` (key: `AISP`).
- **GitHub:** source code, branches, pull requests, reviews, CI/CD, and execution evidence.

## Engineering governance

Read [ENGINEERING_GOVERNANCE.md](ENGINEERING_GOVERNANCE.md) before contributing. Every change must be traceable to an approved Linear issue and relevant Notion specification. Reviews and test evidence must identify the exact commit SHA they verified.

## Project workspace

- [Linear project](https://linear.app/getpsi/project/ai-software-engineering-platform-4c53ef1c5ac2)
- [Notion project home](https://www.notion.so/41bf741d651181338afaeddea49a8c40)

## Status

The repository is in its foundation stage. Product requirements and detailed architecture remain drafts until reviewed and approved. Do not infer that candidate technology choices are final merely because they appear in planning documents.
