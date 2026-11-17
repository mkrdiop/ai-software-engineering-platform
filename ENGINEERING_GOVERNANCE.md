# Engineering Governance

**Status:** Initial baseline — subject to Project Owner approval and subsequent ADRs.

## 1. Systems of record

| Concern | Authority |
|---|---|
| Product requirements, architecture, ADRs, API contracts, governance | Notion |
| Backlog, task state, dependencies, priorities, milestones | Linear |
| Source code, branches, commits, PRs, review records, CI evidence | GitHub |

Do not duplicate the official backlog in GitHub Issues. Link PRs to Linear issues and the relevant Notion specification.

## 2. Work readiness

- No implementation starts without a defined requirement, scope, and testable acceptance criteria.
- Each implementation task must identify its source specification and dependencies.
- Significant architecture changes require an Architecture Decision Record (ADR).
- A Planner must identify sequencing, dependencies, risks, and readiness before work is delegated.

## 3. Pull requests and review

- Every PR references its Linear issue and applicable specification.
- PR descriptions identify the exact base and head commit SHA at review time.
- Developers cannot approve their own changes.
- Code reviewers must inspect the exact PR head and operate with read-only access to the implementation under review.
- A new commit invalidates review and test evidence associated with the previous head unless an explicit policy establishes that the evidence remains applicable.
- Technical verification and formal acceptance are separate decisions.

## 4. Evidence and auditability

- Build, test, security, and review results are evidence records, not narrative claims.
- Evidence is bound to immutable identifiers: commit SHA, artifact digest, workflow run, and relevant configuration/version.
- Preserve provenance: actor, role, action, timestamp, tool, inputs, outputs, and target version.
- Workflow transitions and approvals must be recorded and attributable.
- External side effects must be idempotent or reconciled after uncertain outcomes.

## 5. Agent authority and human approvals

- The workflow engine owns state transitions and approval policy.
- Agents may propose actions and execute only within granted permissions; they cannot self-approve or unilaterally advance governed states.
- Critical delivery and policy exceptions require the designated human approval.
- A separate ChatGPT session is not proof of a separate human identity. Independent technical analysis is distinct from a human approval requirement.

## 6. Security boundaries

- Enforce least privilege in actual GitHub permissions, connector scopes, tool authorization, and execution infrastructure; role prompts are not security controls.
- Execution environments must be isolated, non-privileged, and restricted by explicit network egress policy.
- Do not expose production credentials or production database access to code sandboxes.
- Scope secrets to the minimum task, repository, and duration; redact secrets from logs and artifacts.
- Treat repository content, issue text, tool output, and external artifacts as untrusted input.

## 7. Delivery management

- Delivery Manager verifies completeness of required evidence and approvals.
- Delivery Manager cannot replace missing tests, security review, architecture acceptance, or human approval with a status update.
- A release is ready only when all policy-required checks are satisfied against the release candidate's exact version.

## 8. Initial repository policy

The default branch is `main`. Configure GitHub branch protection or a ruleset to require pull requests, required CI checks, and at least one eligible approval before merge. Where supported, prevent the pull-request author from satisfying the approval requirement. These settings must be verified in GitHub; documentation alone does not enforce them.

## 9. Change control

Changes to this governance baseline require a PR and an explicit rationale. Changes affecting approval authority, evidence validity, identity, tenancy, or sandbox isolation require an ADR and Project Owner approval.
