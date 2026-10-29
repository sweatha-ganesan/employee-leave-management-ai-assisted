# Employee Leave Management — User Stories and Acceptance Criteria

The following draft uses only the supplied requirements as its baseline. Functional acceptance criteria are separated from cross-cutting non-functional requirements, and unresolved details are explicitly flagged rather than treated as established business rules.

## 1. User stories and requirement mapping

| ID | Role | User story | Requirement mapping |
|---|---|---|---|
| US-01 | Employee | As an employee, I want to submit a leave request through a standardized workflow and view its current status, so that I can submit requests consistently and track their progress. | Primary: FR-01, FR-03. Business objective: BR-01. |
| US-02 | Manager | As a manager, I want to review submitted leave requests and approve or reject them, so that leave requests can be processed through a consistent workflow. | Primary: FR-02. Business objective: BR-01. |
| US-03 | HR | As an HR user, I want to maintain leave records in a centralized location, so that leave information can be managed centrally and consistently. | Primary: FR-04. Business objective: BR-01. |

Cross-cutting requirements: NFR-01 (security), NFR-02 (availability) and NFR-03 (prompt status updates and communication) apply to the system as a whole. Their applicability to individual actions is indicated in the acceptance criteria below.

## 2. Acceptance criteria

### US-01 — Employee: Submit and track leave requests

| AC ID | Acceptance criterion | Requirement mapping | Basis |
|---|---|---|---|
| E-AC-01 | Given an employee is using the standardized leave workflow, when they submit a leave request with the required information, then the system records the request and makes it available for manager review. | FR-01; supports FR-02 | Supported by the requirements. The required information and validation rules need clarification. |
| E-AC-02 | Given an employee has submitted a leave request, when they access that request's status, then the system displays its current status. | FR-03 | Directly supported. The exact status labels are unspecified. |
| E-AC-03 | Given the status of an employee's leave request changes, when the change is processed, then the updated status is reflected and the change is communicated promptly. | FR-03, NFR-03 | Supported at a high level. The meaning of “promptly” and the communication method need clarification. |

### US-02 — Manager: Review and decide on leave requests

| AC ID | Acceptance criterion | Requirement mapping | Basis |
|---|---|---|---|
| M-AC-01 | Given a leave request has been submitted and is available for review, when the manager opens the request, then the manager can review the submitted request. | FR-02 | Directly supported. The information that must be displayed for review is unspecified. |
| M-AC-02 | Given a submitted leave request is available for review, when the manager chooses to approve or reject it, then the system records the selected decision against that request. | FR-02 | Approval and rejection are supported. Recording the decision against the request is an implementation-level interpretation that should be confirmed. |
| M-AC-03 | Given a manager's decision results in a request-status change, when that change is processed, then the updated status is reflected and communicated promptly. | FR-03, NFR-03 | Supported at a high level. The status transition, communication recipients, channel and timing need clarification. |

### US-03 — HR: Maintain centralized leave records

| AC ID | Acceptance criterion | Requirement mapping | Basis |
|---|---|---|---|
| H-AC-01 | Given an authorized HR user accesses the leave-record function, when they access leave records, then the records are available through a centralized repository. | FR-04 | Directly supported. |
| H-AC-02 | Given an authorized HR user performs a permitted record-maintenance action, when the action is completed successfully, then the maintained information is reflected in the centralized records. | FR-04 | Consistent with the requirement to maintain centralized records. The permitted actions and save/update behaviour need clarification. |

## 3. Cross-cutting acceptance criteria: Non-functional requirements

These criteria apply across the relevant workflows. The supplied requirements establish the expected outcomes, but some details must be agreed before the criteria can be used for definitive acceptance testing.

| AC ID | Acceptance criterion | Requirement mapping | Outstanding clarification |
|---|---|---|---|
| NFR-AC-01 | Access to employee leave information is restricted according to the agreed authorization rules; users without the required permission cannot access protected information. | NFR-01 | Which roles can view, submit, approve, or maintain each category of information? What security controls must be implemented? |
| NFR-AC-02 | The system meets the agreed availability requirements for its intended users. | NFR-02 | What availability target, service hours and planned-maintenance exclusions apply? |
| NFR-AC-03 | A leave-request status change is reflected and communicated within the agreed time through the agreed communication method. | NFR-03 | What does “promptly” mean in measurable terms? Should communication occur in the system or through another channel? Who must receive it? |

Important: NFR-AC-02 and NFR-AC-03 are not fully testable as written until their acceptance thresholds are agreed. No numerical targets or time limits have been assumed.

## 4. Assumptions and details requiring clarification

The table below separates what the baseline establishes from what remains unknown.

| Area | Established by the requirements | Assumption or question requiring clarification |
|---|---|---|
| Leave request submission | Employees can submit requests through a standardized workflow. | What fields are required? What validation rules apply? What happens when information is missing or invalid? |
| Request status | Employees can view the current status of their requests. | Which status values are used? What are the permitted transitions, and at what point is a status considered changed? |
| Manager review | Managers can review submitted requests and approve or reject them. | How is the responsible manager identified? Can more than one manager review a request? Are comments or rejection reasons required? |
| Status communication | Status changes must be reflected and communicated promptly. | What is the agreed time limit, communication channel, and intended recipient for each change? |
| Centralized records | HR can maintain leave records centrally. | Does maintenance include viewing, creating, updating, correcting or archiving records? Are deletion or bulk-import operations permitted? |
| Security | Employee leave information must be appropriately secured. | What are the role-based access permissions and authentication requirements? Are there additional privacy or audit requirements? |
| Availability | The system must provide reliable availability for intended users. | What availability target and operating hours define acceptable reliability? |
| Business outcome | The workflow should reduce avoidable manual effort and improve status visibility. | What current process or baseline will be used for comparison? How will improvement be measured? No target has been supplied. |
| Record history | Centralized record maintenance is required. | Must changes, decision timestamps or previous values be retained? The requirements do not establish an audit-history requirement. |

## 5. Scope control

The following capabilities are not included in these user stories because they are not in the supplied requirements:

- Leave balances, entitlement or eligibility rules.
- Chatbot functionality.
- Leave cancellation, request editing or resubmission.
- Escalation, delegation or multi-level approval workflows.
- Specific notification channels, rejection-reason fields or audit-history features.

These could be considered later only if stakeholders confirm that they belong in scope.

## 6. Traceability summary

| Requirement ID | Covered by | Coverage |
|---|---|---|
| BR-01 | US-01, US-02, US-03 | Business objective supported by the three workflows; measurable success criteria remain to be defined. |
| FR-01 | US-01; E-AC-01 | Employee leave submission |
| FR-02 | US-02; M-AC-01, M-AC-02 | Manager review and approve/reject decision |
| FR-03 | US-01; E-AC-02, E-AC-03; M-AC-03 | Request-status visibility |
| FR-04 | US-03; H-AC-01, H-AC-02 | Centralized leave-record maintenance |
| NFR-01 | NFR-AC-01 | Appropriate access security |
| NFR-02 | NFR-AC-02 | Reliable availability |
| NFR-03 | E-AC-03, M-AC-03, NFR-AC-03 | Prompt status reflection and communication |

BA assessment: This is a traceable first draft of the user stories and acceptance criteria. The main next step is requirements clarification—particularly status definitions, access permissions, HR maintenance operations, and measurable interpretations of “promptly” and “reliable availability.” Those decisions will make the acceptance criteria precise enough for development and UAT without introducing unsupported business rules.
