# Operations Tracker

## Purpose 

The Operations Tracker is the central operational record for requests moving through the Google Workspace Operations System.

Its purpose is to provide a single, structured view of active work, ownership, priority, deadlines, workflow status, review status, and completion.

The tracker functions as the operational source of truth for the workflow.

## Core Record

Each request should have one primary operational record.

Example:

| Field | Example |
|---|---|
| Request ID | REQ-2026-001 |
| Request Date | 2026-09-05 |
| Requester | Operations |
| Request Type | Executive Support |
| Description | Prepare executive brief |
| Priority | High |
| Owner | Operations Associate |
| Status | In Progress |
| Deadline | 2026-09-08 |
| Deliverable | Executive Brief |
| Review Status | Not Started |
| Final File | Drive link |
| Completion Date | |
| Exception Status | None |
| Notes | |

## Request ID

The Request ID provides a unique reference for the operational record.

Example:

```text
REQ-2026-001



The same identifier can be referenced across:

Operations tracking
Google Drive folders
Documents
Quality control
Reporting
Related communications

This creates a consistent connection between operational data and associated outputs.

Request Date

The Request Date records when the request entered the system.

This field supports:

Workflow history
Aging analysis
Completion-time measurement
Reporting
Operational trend analysis
Requester

The Requester identifies the person, team, or function that initiated the request.

This provides context and helps establish the origin of the work.

Request Type

Request Type categorizes the work.

Example categories:

Administrative
Executive Support
Operations
Customer-related
Documentation
Research
Reporting
Project Support

The category structure should reflect the organization's actual operating requirements.

Description

The Description field provides a concise explanation of what needs to be done.

A useful description should make the requested outcome understandable without requiring the operator to search through multiple sources.

Priority

Priority represents the relative urgency or business importance of the request.

Example values:

Priority	Meaning
Critical	Immediate business impact or executive urgency
High	Significant business requirement
Normal	Standard operational request
Low	Non-urgent work

Priority should be reviewable when business circumstances change.

Owner

The Owner identifies the person responsible for progressing the work.

Every active request should have clear ownership unless it is intentionally awaiting assignment.

Status

Status represents the current workflow state.

Example values:

New
Needs Information
Ready
Assigned
In Progress
Pending Review
Revision Required
Complete
Blocked
Archived

The status field should represent the actual state of the work rather than simply indicating whether someone is working on it.

Deadline

The Deadline records when the requested work is expected to be completed.

It supports:

Prioritization
Workload planning
Deadline monitoring
Overdue identification
Executive reporting
Deliverable

The Deliverable field identifies the expected output.

Examples include:

Executive brief
Report
SOP
Proposal
Research summary
Client document
Internal memo

The deliverable should correspond to the original request.

Review Status

Review Status tracks the quality-control stage.

Example values:

Not Started
In Review
Revision Required
Approved
Not Required

Separating review status from workflow status allows the system to distinguish between execution and quality control.

Final File

The Final File field can contain the location of the approved deliverable.

For example:

Google Drive → Operations → REQ-2026-001 → Final

Where appropriate, this can be represented by a Drive link.

Completion Date

The Completion Date records when the request reached its completed state.

This allows the organization to measure operational performance over time.

Exception Status

Exception Status identifies whether the request requires special attention.

Example values:

None
Missing Information
Blocked
Overdue
Duplicate Review
Approval Delay
Technical Issue
Escalation Required

The purpose is to make exceptions visible rather than burying them in notes or communications.

Notes

Notes provide space for relevant operational context that does not fit into structured fields.

Notes should not become a substitute for structured data.

Important recurring information should be represented as dedicated fields when possible.

Field Relationships

The fields should work together as a connected record.

Example:

Request ID
    ↓
Request
    ↓
Priority + Deadline
    ↓
Owner
    ↓
Status
    ↓
Deliverable
    ↓
Review Status
    ↓
Final File
    ↓
Completion Date

This creates a traceable relationship between the original request and the completed output.

Status and Review Logic

Workflow status and review status should remain logically distinct.

For example:

Status = In Progress
Review Status = Not Started

means work is still being completed.

Whereas:

Status = Pending Review
Review Status = In Review

means execution has reached the quality-control stage.

After approval:

Status = Complete
Review Status = Approved

This separation provides greater operational clarity.

Data Validation

Structured fields should use validation where appropriate.

Examples include:

Dropdown values for status
Dropdown values for priority
Valid date fields
Controlled request types
Required owner fields
Standardized review states

Validation reduces inconsistent data entry.

Automation Fields

Some fields may be updated automatically.

Potential examples include:

Request ID
Request Date
Status timestamps
Completion Date
Review notifications
Overdue indicators

Automated fields should be clearly distinguished from fields that operators are expected to maintain manually.

Reporting Fields

The tracker should contain enough structured information to support operational reporting.

Possible reporting dimensions include:

Requests by status
Requests by priority
Requests by owner
Requests by request type
Overdue requests
Blocked requests
Completion volume
Completion time
Revision rate

This allows the operational tracker to serve both workflow and reporting purposes.

Data Integrity

The tracker should maintain consistent records.

Important controls include:

Unique Request IDs
Controlled status values
Standardized priority values
Clear ownership
Required fields
Duplicate detection
Defined completion rules

The goal is to prevent the tracker from becoming another source of fragmented or unreliable information.

Archive Model

Completed records may eventually be moved or filtered into an archive state.

Example:

Active Operations
       ↓
Complete
       ↓
Archive

Archived records can remain available for historical reporting, reference, and process analysis.

Design Objective

The Operations Tracker should provide a reliable answer to the following questions:

What work exists?
Who requested it?
Who owns it?
How important is it?
When is it due?
What is its current status?
Does it require review?
Is there an exception?
Where is the final deliverable?
When was it completed?

A well-designed tracker turns operational activity into structured information that can support both execution and management.
