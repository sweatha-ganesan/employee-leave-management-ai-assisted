# Consolidated Acceptance Criteria

## 1. Purpose

This document presents the proposed refined acceptance criteria for the hypothetical Employee Leave Management case study.

The criteria were drafted with AI assistance and reviewed for clarity, requirement alignment, scope control, testability and traceability. They remain proposed criteria because no actual stakeholder validation has taken place.

## 2. Employee Workflow

### E-AC-01 — Submit a Leave Request

**Given** an employee is using the standardized leave workflow,

**When** the employee submits a leave request containing the agreed mandatory information,

**Then** the system records the request and makes it available for manager review.

**Requirement mapping:** FR-01; supports FR-02.

**Open questions:** What information is mandatory? Should the employee receive a submission confirmation? When must the request become available for manager review?

### E-AC-02 — View Request Status

**Given** an employee has submitted a leave request,

**When** the employee accesses that request's status,

**Then** the system displays the current status of the request.

**Requirement mapping:** FR-03.

**Open questions:** Which status values are permitted? Does the status update automatically, or is a refresh required?

## 3. Manager Workflow

### M-AC-01 — Review a Leave Request

**Given** a leave request has been submitted and is available for review,

**When** the manager opens the request,

**Then** the manager can review the submitted request.

**Requirement mapping:** FR-02.

**Open question:** What information must be displayed for the manager's review?

### M-AC-02 — Record the Manager's Decision

**Given** a submitted leave request is available for review,

**When** the manager approves or rejects the request,

**Then** the system records the manager's decision against that request.

**Requirement mapping:** FR-02.

**Open question:** Confirm whether recording the decision against the request is a required business behaviour.

## 4. HR Workflow

### H-AC-01 — Retrieve Centralized Leave Records

**Given** an authorized HR user accesses the leave-record function,

**When** the HR user retrieves leave records,

**Then** the records are available through the centralized repository.

**Requirement mapping:** FR-04.

**Open question:** Which HR roles are authorized to access which records?

### H-AC-02 — Maintain Centralized Leave Records

**Given** an authorized HR user performs an agreed record-maintenance action,

**When** the action is completed successfully,

**Then** the updated information is reflected in the centralized leave records.

**Requirement mapping:** FR-04.

**Open questions:** Which record-maintenance actions are permitted? How is successful maintenance confirmed?

## 5. Consolidated Status-Update Criterion

### AC-STATUS-01 — Reflect and Communicate Status Changes

**Given** a leave-request status changes,

**When** the status change is processed,

**Then** the updated status is reflected and the change is communicated through the agreed communication method.

**Requirement mapping:** FR-03 and NFR-03.

This criterion consolidates the overlapping status-update behaviour originally covered by E-AC-03 and M-AC-03. The original AI draft retains both original criteria for comparison.

**Open questions:** What communication method should be used? Who should receive the communication? What timing is expected for the status update and communication?

## 6. Non-Functional Acceptance Criteria

### NFR-AC-01 — Access Security

Access to employee leave information is restricted according to the agreed authorization rules; users without the required permission cannot access protected information.

**Requirement mapping:** NFR-01.

**Open questions:** Which roles and permissions apply to each category of information? What security controls are required?

### NFR-AC-02 — Availability

The system meets the agreed availability requirements for its intended users.

**Requirement mapping:** NFR-02.

**Open questions:** What availability target, service hours, planned-maintenance exclusions and measurement method apply?

### NFR-AC-03 — Timely Status Communication

A leave-request status change is reflected and communicated within the agreed time through the agreed communication method.

**Requirement mapping:** NFR-03.

**Open questions:** What time limit, communication method and recipient should be specified?

**Testability note:** NFR-AC-02 and NFR-AC-03 are not fully objectively testable until measurable targets and relevant conditions are agreed.

## 7. Traceability Summary

| Requirement | Proposed acceptance criteria | Coverage |
|---|---|---|
| BR-01 | Overall workflow criteria | Supports the business objective; measurable success indicators remain undefined. |
| FR-01 | E-AC-01 | Employee leave-request submission. |
| FR-02 | E-AC-01, M-AC-01, M-AC-02 | Request availability for review, manager review and decision. |
| FR-03 | E-AC-02, AC-STATUS-01 | Request-status visibility and status changes. |
| FR-04 | H-AC-01, H-AC-02 | Centralized leave-record retrieval and maintenance. |
| NFR-01 | NFR-AC-01 | Access security. |
| NFR-02 | NFR-AC-02 | Availability. |
| NFR-03 | AC-STATUS-01, NFR-AC-03 | Status reflection and communication. |

## 8. Outstanding Decisions Before Acceptance Testing

The following must be clarified before the proposed criteria can be treated as definitive:

- Mandatory leave-request information and validation rules.
- Valid request-status values and permitted transitions.
- Manager review information and decision-recording behaviour.
- Authorized roles and access permissions.
- Permitted HR record-maintenance actions.
- Status-update timing, communication method and recipients.
- Measurable availability targets and measurement conditions.
- Measurable success indicators for BR-01.

## 9. Limitations

These acceptance criteria are proposed for a hypothetical documentation-focused case study. They have not been approved by actual stakeholders, implemented or used in user acceptance testing. Open questions are explicitly retained rather than resolved through unsupported assumptions.
