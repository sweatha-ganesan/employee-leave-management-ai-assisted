# AI vs Human Review Summary

## 1. Overview

This hypothetical Business Analyst case study explores how AI can support requirements documentation while keeping human review central to the quality of the output.

AI was used to draft user stories, acceptance criteria, requirement mappings and clarification questions from a supplied requirements baseline. The resulting draft was then reviewed for requirement alignment, clarity, testability, scope control and traceability.

The AI-generated content was treated as a first draft, not as a final or stakeholder-approved specification.

## 2. What AI Contributed

The initial AI draft provided:

- User stories for employees, managers and HR.
- Acceptance criteria in Given–When–Then format.
- Mappings between user stories, acceptance criteria and requirement IDs.
- Initial identification of assumptions and unresolved details.
- Clarification questions relating to request statuses, security, availability and record maintenance.
- A preliminary traceability summary.

This created a structured starting point for human review.

## 3. What Human Review Added

The human review focused on evaluating whether the drafted criteria were supported by the requirements baseline and whether any assumptions had been introduced.

| Review Area | Human Review Finding | Decision |
|---|---|---|
| Requirement alignment | Some criteria were directly supported, while others included additional interpretations. | Retain supported criteria and flag additional behaviour for confirmation. |
| Ambiguous wording | Terms such as “required information” and “promptly” were not sufficiently defined. | Identify clarification questions rather than inventing definitions. |
| Overlapping criteria | E-AC-03 and M-AC-03 both addressed status reflection and communication. | Propose one consolidated functional criterion, AC-STATUS-01. |
| Security | Authorization rules were not defined in the baseline. | Retain the security criterion provisionally and flag permissions for clarification. |
| Availability | No measurable availability target was supplied. | Retain the original availability criterion provisionally without inventing a numerical target. |
| Record maintenance | Permitted HR actions were unspecified. | Refine the wording around agreed maintenance actions and identify open questions. |
| Traceability | Requirement mappings were present in the initial draft. | Preserve requirement IDs and map the consolidated criterion to FR-03 and NFR-03. |
| Scope control | Additional features could easily be assumed based on common leave-management systems. | Keep unrequested features out of scope. |

## 4. Example: Consolidating Overlapping Acceptance Criteria

### Original AI draft

**E-AC-03**

Given the status of an employee's leave request changes, when the change is processed, then the updated status is reflected and the change is communicated promptly.

**M-AC-03**

Given a manager's decision results in a request-status change, when that change is processed, then the updated status is reflected and communicated promptly.

### Human-review decision

Both criteria cover the same general behaviour: reflecting and communicating a leave-request status change. Keeping them separate could duplicate coverage across employee and manager workflows.

### Proposed consolidated criterion

**AC-STATUS-01**

Given a leave-request status changes, when the status change is processed, then the updated status is reflected and the change is communicated through the agreed communication method.

**Requirement mapping:** FR-03 and NFR-03.

The original criteria remain unchanged in the original AI draft document. The consolidated wording appears in the refined acceptance criteria document.

## 5. Example: Identifying an Unsupported Assumption

The baseline requires managers to approve or reject submitted leave requests. The original AI draft additionally states that the system records the selected decision against the request.

Although this behaviour may be reasonable, it is not explicitly stated in FR-02.

**Human-review decision:** Keep the criterion as a proposal subject to confirmation rather than presenting the additional behaviour as an established business requirement.

This illustrates the distinction between a plausible system behaviour and a requirement supported by the baseline.

## 6. Important Clarification Questions Identified

The review identified the following unresolved questions:

- What information must employees provide when submitting leave requests?
- Which request-status values and transitions are permitted?
- Which user roles may access specific leave information?
- Which record-maintenance actions may HR perform?
- Must manager decisions be recorded against individual requests?
- How quickly must status changes be reflected and communicated?
- Which communication method and recipients should apply?
- What availability target and measurement conditions are required?
- How will improvements in processing efficiency and status visibility be measured?

These questions remain open. They were not answered through actual stakeholder interviews.

## 7. What Was Not Changed or Assumed

The review deliberately avoided:

- Inventing mandatory leave fields or status values.
- Assigning numerical availability or response-time targets without a source.
- Treating a specific notification channel as a confirmed requirement.
- Adding leave eligibility, balances or entitlement rules.
- Adding cancellation, editing, escalation or multilevel approval features.
- Claiming stakeholder approval, implementation, UAT completion or measured benefits.

## 8. Outcome of the Review

The result is a structured set of proposed user stories and acceptance criteria with clearer wording, identified gaps, retained traceability and a consolidated functional status-update criterion.

The review also highlights that NFR-AC-02 and NFR-AC-03 require measurable targets before objective acceptance testing can be performed.

The main contribution of human review was not simply rewriting AI output. It was distinguishing supported requirements from assumptions, identifying duplicated coverage, preserving scope and making unresolved decisions visible.

## 9. Limitations and Learning

This is a hypothetical documentation-focused case study. The review was not validated with actual company stakeholders, and no solution was implemented or tested. Business improvements have not been measured.

The key learning is that AI can accelerate the initial drafting of BA documentation, but its output still requires human evaluation against the requirements baseline. Clear traceability, explicit clarification questions and disciplined scope control are necessary before proposed acceptance criteria can be treated as agreed requirements.
