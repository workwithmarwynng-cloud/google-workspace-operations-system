# Operations Tracker Field Definitions

## Purpose

This document defines the core fields used in the central operations tracker.

The field model is designed to support request intake, task management, prioritization, workflow tracking, document production, quality control, exception management, and operational reporting.

The objective is to ensure that operational information is structured consistently rather than being distributed across email threads, chat messages, documents, and disconnected spreadsheets.

## Field Definition Framework

Each field should have a clear operational purpose, an expected data format, and defined relationships with other fields.

The tracker should distinguish between:

- Information provided during intake
- Information generated during workflow execution
- Information used for decision making
- Information used for quality control
- Information used for reporting
- Information used for final closure

## Core Fields

### Request ID

**Purpose:** Provides a unique identifier for each operational request.

**Data Type:** Text

**Example:** REQ-2026-001

**Source:** System-generated

**Used For:**

- Request tracking
- Document naming
- Workflow references
- Automation
- Auditability
- Reporting

The Request ID should remain unchanged throughout the request lifecycle.

### Request Date

**Purpose:** Records when the request entered the operational system.

**Data Type:** Date

**Source:** Intake process

**Used For:**

- Aging analysis
- Processing-time measurement
- Reporting
- Deadline management

### Requester

**Purpose:** Identifies the person or function that submitted the request.

**Data Type:** Text

**Source:** Intake

**Used For:**

- Communication
- Ownership clarification
- Reporting
- Follow-up

### Request Type

**Purpose:** Classifies the operational request.

**Data Type:** Controlled category

**Examples:**

- Administrative Request
- Client Request
- Document Request
- Research Request
- Operations Request
- Reporting Request
- Internal Support

Controlled categories should be used where possible to maintain consistent reporting.

### Description

**Purpose:** Provides a concise description of the request and required outcome.

**Data Type:** Long text

**Source:** Intake

**Used For:**

- Task understanding
- Assignment
- Execution
- AI-assisted processing
- Quality control

Descriptions should be sufficiently clear for an assigned owner to understand the requested outcome without relying entirely on informal conversation.

### Priority

**Purpose:** Indicates the operational urgency or importance of the request.

**Data Type:** Controlled category

**Example Values:**

- Low
- Normal
- High
- Critical

Priority should be based on business impact, deadline requirements, dependencies, and urgency rather than subjective preference alone.

### Owner

**Purpose:** Identifies the person responsible for moving the request through execution.

**Data Type:** Text

**Source:** Assignment process

**Used For:**

- Accountability
- Workload visibility
- Escalation
- Status reporting

Every active request should have a clearly identifiable owner unless it is intentionally awaiting assignment.

### Status

**Purpose:** Represents the current workflow state of the request.

**Data Type:** Controlled category

**Example Values:**

- New
- Assigned
- In Progress
- Waiting
- Blocked
- In Review
- Revision Required
- Approved
- Completed
- Archived

Status should represent the actual workflow state rather than simply indicating that work has started.

### Deadline

**Purpose:** Defines the required completion date for the request.

**Data Type:** Date

**Source:** Intake or operational planning

**Used For:**

- Scheduling
- Prioritization
- Overdue identification
- Executive reporting
- Escalation

Deadline information should be reviewed when priorities or business requirements change.

### Deliverable

**Purpose:** Identifies the expected output of the request.

**Data Type:** Text

**Examples:**

- Report
- Presentation
- Client document
- Research summary
- Spreadsheet
- Process document

The deliverable field connects the operational request to its expected outcome.

### Review Status

**Purpose:** Tracks whether the required quality review has occurred.

**Data Type:** Controlled category

**Example Values:**

- Not Required
- Pending Review
- In Review
- Revision Required
- Approved

Review Status should remain separate from workflow Status because a request can be operationally complete while still awaiting quality approval.

### Final File

**Purpose:** Stores the reference to the approved final deliverable.

**Data Type:** File reference or URL

**Source:** Google Drive or designated document repository

**Used For:**

- Final deliverable access
- Traceability
- Handoff
- Record keeping

The final file should point to the approved version rather than an intermediate draft.

### Completion Date

**Purpose:** Records when the request was formally completed.

**Data Type:** Date

**Source:** Workflow completion

**Used For:**

- Processing-time analysis
- Reporting
- Historical records
- Performance analysis

Completion should only be recorded when the defined completion criteria have been satisfied.

### Exception Status

**Purpose:** Identifies whether the request has encountered an issue requiring attention.

**Data Type:** Controlled category

**Example Values:**

- None
- Awaiting Information
- Blocked
- Data Issue
- Review Issue
- Deadline Risk
- Escalation Required

Exception Status allows operational problems to be surfaced without changing the underlying request history.

### Notes

**Purpose:** Stores relevant operational context that does not belong in the structured fields.

**Data Type:** Long text

**Used For:**

- Exceptions
- Context
- Follow-up information
- Special instructions
- Operational observations

Notes should supplement structured data rather than replace it.

## Field Relationships

The fields operate as an interconnected data model rather than as independent columns.

The primary relationships are:

**Request ID → Request Record**

The Request ID identifies the complete operational record.

**Request Type + Description → Work Definition**

These fields establish what is being requested and what outcome is expected.

**Priority + Deadline → Urgency**

These fields help determine how quickly the request should be addressed.

**Owner + Status → Accountability**

These fields establish who is responsible and where the work currently stands.

**Deliverable + Final File → Output**

These fields connect the request to its expected and completed output.

**Status + Review Status → Workflow and Quality State**

These fields distinguish operational progress from quality approval.

**Exception Status → Operational Risk**

This field identifies issues that may prevent normal workflow progression.

**Completion Date → Closure**

This field establishes when the request officially reached completion.

## Controlled Fields

Where practical, fields such as Request Type, Priority, Status, Review Status, and Exception Status should use controlled values.

Controlled fields improve:

- Consistency
- Filtering
- Reporting
- Automation
- Data validation
- Trend analysis

Free-text values should be avoided when the information can be represented reliably through a predefined category.

## Validation Rules

The tracker should apply basic validation rules to protect data integrity.

Examples include:

- Request ID must be unique.
- Request Date must contain a valid date.
- Priority must use an approved priority value.
- Status must use an approved workflow state.
- Review Status must use an approved review state.
- Completion Date should not precede Request Date.
- Completed requests should have appropriate completion information.
- Final File should reference the approved deliverable when a deliverable is required.
- Active requests should have an owner or an explicit assignment exception.
- Exception Status should be updated when a material blocker or operational issue is identified.

## Reporting Fields

The core fields also support operational reporting.

Potential reporting views include:

- Open requests
- Requests by priority
- Requests by owner
- Requests approaching deadline
- Overdue requests
- Requests in review
- Requests requiring revision
- Blocked requests
- Completed requests
- Requests by type
- Average processing time
- Exception frequency

These views allow management to focus on operational conditions rather than manually reviewing every individual request.

## Automation-Relevant Fields

Several fields can serve as triggers or inputs for future automation.

Examples:

**Status**

Can trigger workflow actions when a request moves between states.

**Priority**

Can influence task ordering or escalation rules.

**Deadline**

Can support upcoming-deadline and overdue detection.

**Review Status**

Can trigger review or approval workflows.

**Final File**

Can support completion checks.

**Exception Status**

Can trigger escalation or follow-up actions.

**Owner**

Can support assignment notifications and workload reporting.

## Data Integrity Principle

The operations tracker should function as a controlled operational data source.

Information should be entered once where practical and reused throughout the workflow.

This reduces:

- Duplicate data entry
- Conflicting versions
- Missing information
- Manual reconciliation
- Reporting inconsistencies

The tracker should provide the operational state of the request while linked documents and files provide the detailed working or final content.

## Archive Model

Completed requests should remain available for historical reference while being separated from active operational work.

An archive structure can preserve:

- Request ID
- Original request information
- Workflow history
- Final deliverable
- Completion date
- Relevant exception information
- Final notes

Archiving should preserve traceability without allowing completed records to clutter active work queues.

## Design Objective

The field model is designed to create a structured operational data layer that supports the entire workflow.

The objective is not simply to create a spreadsheet with more columns.

The objective is to create a reliable operational record that connects:

**Request → Ownership → Priority → Workflow State → Deliverable → Quality Control → Completion → Reporting**

This structure provides the foundation for future automation, operational dashboards, AI-assisted processing, and executive visibility.


