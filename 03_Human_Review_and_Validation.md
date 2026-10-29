# Human Review and Validation

## 1. Purpose of the Review

The initial AI-generated user stories and acceptance criteria were reviewed against the hypothetical requirements baseline to assess requirement alignment, clarity, testability, scope control and traceability.

The review focused on identifying unsupported assumptions, ambiguous wording, overlapping acceptance criteria and details requiring clarification before development or acceptance testing.

**Review approach:** AI-assisted drafting followed by human review and refinement.

## 2. Acceptance Criteria Validation Log

### 2.1 Employee Acceptance Criteria

| AC ID | Review Finding | Human Review Decision | Open Questions |
|---|---|---|---|
| E-AC-01 | The criterion is aligned with leave submission, but “required information” is not defined in the baseline. | Refine the wording to refer to agreed mandatory information. | What fields are mandatory? Should a successful submission confirmation be displayed? When must the request become available for manager review? |
| E-AC-02 | The criterion is aligned with FR-03. However, the valid status values are unspecified. | Retain the criterion with minor wording clarification. | What status values are permitted? Does the status update automatically or require a page refresh? |
| E-AC-03 | The criterion overlaps with M-AC-03 because both address status reflection and communication. | Consolidate the overlapping functional status criteria into one criterion. | What communication method, recipient and expected update time should apply? |

### 2.2 Manager Acceptance Criteria

| AC ID | Review Finding | Human Review Decision | Open Questions |
|---|---|---|---|
| M-AC-01 | The criterion is directly aligned with FR-02, but the information required for manager review is not specified. | Retain the original criterion. | What information must be available to the manager? |
| M-AC-02 | Approval and rejection are supported by FR-02. Recording the selected decision against the request is an additional interpretation. | Retain as a proposed criterion subject to confirmation. | Should the decision be recorded against the request? Are comments or rejection reasons required? |
| M-AC-03 | The criterion overlaps with E-AC-03 on status reflection and communication. | Consolidate the overlapping functional status criteria. | Which status transitions occur after approval or rejection, and how should the change be communicated? |

### 2.3 HR Acceptance Criteria

| AC ID | Review Finding | Human Review Decision | Open Questions |
|---|---|---|---|
| H-AC-01 | The criterion aligns with FR-04. The authorized HR roles and record-access boundaries remain undefined. | Refine the wording to clarify retrieval of records through the centralized repository. | Which HR roles are authorized, and which records may they access? |
| H-AC-02 | The criterion aligns with centralized record maintenance, but permitted maintenance actions are unspecified. | Refine the wording to refer to agreed record-maintenance actions and successfully updated information. | Which actions are permitted? How is successful maintenance confirmed? |

### 2.4 Non-Functional Acceptance Criteria

| AC ID | Review Finding | Human Review Decision | Open Questions |
|---|---|---|---|
| NFR-AC-01 | The criterion reflects the security requirement, but the authorization rules are not defined. | Retain the criterion provisionally. | Which roles and permissions apply to each category of information? |
| NFR-AC-02 | The criterion reflects the availability requirement, but no measurable target is provided. | Retain the original wording provisionally; do not invent an availability target. | What availability target, service hours, exclusions and measurement method apply? |
| NFR-AC-03 | The criterion reflects the requirement for prompt status updates, but the expected time and communication method are undefined. | Retain the criterion provisionally. | What time limit, communication method and recipient should be specified? |

## 3. Refined Acceptance Criteria

The following wording reflects the proposed human-review refinements. These are proposed criteria, not stakeholder-approved requirements.

### Employee Workflow

**E-AC-01 — Leave request submission**

Given an employee is using the standardized leave workflow, when the employee submits a leave request containing the agreed mandatory information, then the system records the request and makes it available for manager review.

**E-AC-02 — View request status**

Given an employee has submitted a leave request, when the employee accesses that request's status, then the system displays the current status of the request.

### Manager Workflow

**M-AC-01 — Review request**

Given a leave request has been submitted and is available for review, when the manager opens the request, then the manager can review the submitted request.

**M-AC-02 — Record manager decision**

Given a submitted leave request is available for review, when the manager approves or rejects the request, then the system records the manager's decision against that request.

*Note: Recording the decision remains subject to confirmation because the baseline specifies approval or rejection but does not explicitly require this recording behaviour.*

### HR Workflow

**H-AC-01 — Retrieve centralized records**

Given an authorized HR user accesses the leave-record function, when the HR user retrieves leave records, then the records are available through the centralized repository.

**H-AC-02 — Maintain centralized records**

Given an authorized HR user performs an agreed record-maintenance action, when the action is completed successfully, then the updated information is reflected in the centralized leave records.

## 4. Consolidation of Overlapping Criteria

The original AI draft contains two criteria covering substantially overlapping status-update behaviour:

- E-AC-03 — Status changes for an employee's leave request.
- M-AC-03 — Status changes resulting from a manager's decision.

Both criteria address reflecting and communicating a request-status change. Keeping them separate could create duplicate coverage of the same cross-workflow behaviour.

**Consolidated criterion: AC-STATUS-01**

Given a leave-request status changes, when the status change is processed, then the updated status is reflected and the change is communicated through the agreed communication method.

**Requirement mapping:** FR-03 and NFR-03.

The consolidation is proposed for the refined set. The original AI draft retains E-AC-03 and M-AC-03 separately for comparison and traceability.

## 5. Review of AI Assumptions and Clarification Questions

The review identified details that must not be treated as confirmed business rules:

- Mandatory leave-request fields and validation rules.
- Permitted request-status values and transitions.
- Authorization rules for employee leave information.
- Permitted HR record-maintenance operations.
- Whether manager decisions must be recorded against requests.
- The communication method, recipients and expected timing for status changes.
- Measurable availability expectations.
- Measurable success indicators for the business objective.

Some points are assumptions introduced by the AI draft; others are gaps in the supplied requirements baseline. They require clarification rather than unsupported decisions.

## 6. Scope Control Review

The review retained the original scope boundaries. The following remain outside scope unless subsequently agreed:

- Leave balances, entitlements and eligibility rules.
- Chatbot development.
- Request cancellation, editing and resubmission.
- Escalation, delegation and multilevel approval.
- Specific notification channels.
- Mandatory rejection reasons and audit-history features.
- Database design and implementation.

No additional features were added solely because they might be common in a leave-management system.

## 7. Traceability Review

The original draft provides mappings between user stories, acceptance criteria and the requirements baseline.

The review retained traceability to the original requirement IDs and identified the consolidated status criterion as covering FR-03 and NFR-03.

BR-01 is supported by the overall proposed workflow, but measurable business success criteria remain undefined.

NFR-AC-02 and NFR-AC-03 require measurable targets before they can support objective acceptance testing.

## 8. Review Outcome

The review found that the AI draft provided a useful first version of the user stories, acceptance criteria, requirement mappings and clarification questions.

Human review was necessary to:

- Identify ambiguous terms and undefined business rules.
- Distinguish requirements supported by the baseline from assumptions requiring confirmation.
- Refine wording for greater clarity.
- Identify and consolidate overlapping status-update criteria.
- Preserve scope boundaries and requirement traceability.
- Flag non-functional criteria that are not yet objectively testable.

## 9. Limitations

This review was conducted for a hypothetical case study. It does not represent actual stakeholder validation, implementation, user acceptance testing or measured process improvement. Proposed refinements remain subject to confirmation by relevant stakeholders in a real project.
