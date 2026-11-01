Learning Schedule

Project: Cognis
Document: Learning Schedule
Version: 1.0
Status: Proposed Baseline
Document Type: Academic Operations
Parent Document: "docs/academy/ACADEMIC_SYSTEM.md"

Related Documents:

- "PRD.md"
- "docs/architecture/SYSTEM_ARCHITECTURE.md"
- "docs/autonomous-learning/AUTONOMOUS_LEARNING_SPEC.md"
- "docs/autonomous-learning/COMPETENCY_CURRICULUM.md"
- "docs/academy/FACULTY_PROGRESSION_POLICY.md"
- "docs/academy/ASSESSMENT_POLICY.md"

---

1. Purpose

This document defines how Cognis organizes, schedules, executes, and reports its learning activities.

The learning schedule establishes a structured operational rhythm so that Cognis can conduct research consistently without creating uncontrolled workloads or exceeding its authorized learning scope.

It defines:

1. Daily learning activities.
2. Scheduled and manual learning execution.
3. Founder planning and authorization.
4. Morning learning brief delivery.
5. Daily learning report delivery.
6. Schedule configuration and execution boundaries.
7. Missed schedule and failure handling.
8. Academic and technical scheduling separation.
9. Future scheduling capabilities.

The schedule must support consistent learning while preserving Founder control over academic direction and permanent system changes.

---

2. Scheduling Principles

All learning schedules must follow these principles.

2.1 Structured Consistency

Learning activities should follow a predictable schedule instead of being initiated randomly without a clear objective.

2.2 Founder-Controlled Direction

The Founder defines or authorizes the learning focus, active faculty, and permitted learning scope.

The scheduler must not independently change the primary learning direction.

2.3 Controlled Autonomy

An active recurring schedule may execute within its previously authorized scope.

A new learning objective, expanded scope, or permanent academic change must not be treated as automatically approved merely because a scheduled execution exists.

2.4 Resource Awareness

Scheduling must account for available computing resources, API quotas, execution limits, and workload.

The system must prefer reliable execution over launching more learning jobs than it can handle.

2.5 Traceability

Each scheduled execution must be traceable to its schedule configuration, academic context, execution time, and resulting report.

2.6 No Fabricated Completion

A scheduled task that fails, remains incomplete, or produces insufficient evidence must not be reported as successfully completed.

2.7 Timezone Consistency

All human-facing schedule definitions must use an explicitly configured timezone.

The default timezone for Cognis is:

"Asia/Jakarta"

This corresponds to Western Indonesian Time (WIB, UTC+7).

The timezone must be configurable rather than hardcoded throughout the application.

---

3. Scheduling Architecture

Cognis separates scheduling into three related layers.

3.1 Academic Scheduling

Academic scheduling defines what Cognis is expected to learn.

It includes:

- Active faculty.
- Academic program.
- Course or learning topic.
- Learning objective.
- Expected learning depth.
- Learning sequence.
- Learning session context.

Academic scheduling is governed by "ACADEMIC_SYSTEM.md", "COMPETENCY_CURRICULUM.md", and "FACULTY_PROGRESSION_POLICY.md".

3.2 Technical Execution Scheduling

Technical scheduling determines when and how a learning task is executed.

It includes:

- Scheduled execution time.
- Manual execution requests.
- Job queue handling.
- Execution priority.
- Resource limits.
- Retry handling.
- Execution status.
- Failure records.

Technical scheduling is governed by the system architecture and autonomous learning specification.

3.3 Communication Scheduling

Communication scheduling determines when Cognis delivers information to the Founder.

It includes:

- Daily learning brief.
- Execution status notifications.
- Daily learning report.
- Approval requests.
- Failure notifications.
- Optional periodic summaries.

Communication delivery must reflect actual execution results.

A report must not imply that a learning activity happened when no corresponding execution record exists.

---

4. Default Timezone and Daily Operating Schedule

The default daily operating schedule uses "Asia/Jakarta".

The following times are proposed operational defaults. They must remain configurable.

Time (WIB)| Activity| Purpose
07:00| Morning Checkpoint| Verify the daily learning brief and authorized learning plan
07:00–17:30| Learning Execution Window| Execute approved scheduled and manual learning tasks
18:00| Daily Learning Report| Deliver a summary of the day's actual learning activity
19:00| Founder Planning and Approval| Review learning results and authorize or adjust the next learning focus

These times define the default operating rhythm, not guaranteed completion deadlines.

Actual execution duration depends on workload, model availability, network conditions, research complexity, and available resources.

---

5. Daily Learning Cycle

The daily learning cycle is divided into four stages.

5.1 Stage A: Founder Planning and Authorization

Default time: 19:00 WIB

The Founder reviews the current learning direction and determines the next learning activity.

The planning stage may include:

1. Reviewing the previous learning report.
2. Reviewing unresolved research questions.
3. Selecting or confirming the next learning topic.
4. Confirming the active faculty.
5. Defining the learning objective.
6. Adjusting the permitted research scope.
7. Authorizing the next learning activity.

The Founder may:

- Approve the proposed learning plan.
- Modify its objective or scope.
- Defer the activity.
- Reject the proposal.
- Request additional research.
- Pause the recurring schedule.

An approval applies only to the stated task or recurring scope.

It must not be interpreted as permission to modify system architecture, policies, permanent prompts, or curriculum definitions.

MVP Boundary

The MVP does not require a complete automated Founder approval workflow.

The Founder may authorize a recurring schedule through configuration or initiate a learning task manually.

A future interactive approval interface may be implemented through Telegram or another supported channel.

If a task explicitly requires per-run approval and no approval mechanism is available, the system must not execute it without authorization.

5.2 Stage B: Morning Checkpoint

Default time: 07:00 WIB

At the beginning of the daily learning cycle, Cognis checks whether the expected learning brief and execution plan are available.

The checkpoint must verify:

- Whether an authorized learning plan exists.
- Whether the active faculty is valid.
- Whether the objective is defined.
- Whether the schedule is enabled.
- Whether required configuration is available.
- Whether previous execution failures block the next task.

If a valid brief exists, Cognis may deliver it to the Founder.

If the brief is missing, the system must report the actual reason.

Possible reasons include:

- No learning plan was authorized.
- The previous planning stage was not completed.
- Required configuration is missing.
- The scheduled task failed.
- A required dependency is unavailable.
- The learning job remains queued.

Cognis must not silently generate an unrelated topic to fill the schedule.

The system may request clarification or authorization when required.

5.3 Stage C: Learning Execution

Default window: 07:00–17:30 WIB

During the execution window, Cognis performs authorized learning activities.

The MVP learning pipeline is:

"Scheduler → Research → Source Validation → Evidence Evaluation → Knowledge Storage → Learning Report"

Each stage must preserve the relationship between its input, output, and execution metadata.

Learning execution may include:

- Research planning.
- Information retrieval.
- Source validation.
- Claim and evidence evaluation.
- Knowledge synthesis.
- Persistent research note storage.
- Candidate knowledge recording.
- Learning report preparation.

The system must distinguish completed stages from failed or incomplete stages.

A failure in one learning job must not automatically authorize an unrelated replacement job.

5.4 Stage D: Daily Learning Report

Default time: 18:00 WIB

Cognis prepares and delivers a daily report summarizing the actual learning activity.

The report should include:

1. Learning objective.
2. Active faculty and academic context.
3. Tasks attempted.
4. Research completed.
5. Important findings.
6. Source and evidence quality.
7. Unverified or conflicting information.
8. Knowledge records created or updated.
9. Execution failures or incomplete stages.
10. Remaining questions.
11. Recommended next learning activities.

The report must distinguish between:

- Information successfully researched.
- Information supported by evidence.
- Information that remains uncertain.
- Knowledge records stored.
- Activities that were attempted but not completed.

The report must not claim competency mastery merely because a research job completed successfully.

After the report is delivered, Cognis waits for the next authorized instruction or scheduled activity.

---

6. Learning Session and Learning Job Scheduling

A Learning Session and a Learning Job are different objects.

6.1 Learning Session

A Learning Session represents an academic learning activity.

It defines:

- Learning objective.
- Academic context.
- Faculty.
- Course or topic.
- Expected learning depth.
- Learning sequence.
- Relevant competency references.

A session may contain multiple related activities.

6.2 Learning Job

A Learning Job represents a technical execution unit.

It defines:

- Execution request.
- Input parameters.
- Processing stages.
- Model invocations.
- Source retrieval.
- Evidence evaluation.
- Storage operations.
- Execution result.

One Learning Session may produce multiple Learning Jobs.

A Learning Job may fail without making the academic Learning Session automatically invalid.

Likewise, a completed Learning Job does not automatically mean the academic objective has been achieved.

6.3 Scheduling Relationship

The recommended relationship is:

"Learning Schedule → Learning Session → Learning Job"

The schedule determines when a session should occur.

The session defines why the activity exists.

The job executes the technical work.

This separation must be preserved in future implementation.

---

7. Schedule Types

Cognis supports several schedule types.

7.1 Manual Schedule

A manual schedule is initiated directly by the Founder.

Examples:

- Research a specific economic policy.
- Investigate a business model.
- Analyze a geopolitical development.
- Study a financial concept.
- Evaluate a market-related hypothesis.

Manual tasks should enter the normal execution pipeline.

They must not bypass source validation, evidence evaluation, or recording requirements.

7.2 Recurring Schedule

A recurring schedule executes according to a predefined cadence.

Examples:

- Daily learning session.
- Weekly research review.
- Periodic review of an active learning topic.

A recurring schedule must have an explicitly authorized scope.

It must not automatically expand into unrelated subjects or additional faculties.

7.3 One-Time Scheduled Activity

A one-time scheduled activity executes at a specific date and time.

Examples:

- Research a scheduled economic announcement.
- Review a previously collected dataset.
- Investigate an unresolved research question.

A one-time activity must not repeat automatically unless a retry policy explicitly permits it.

7.4 Retry Execution

A retry is another attempt to execute an existing Learning Job.

A retry must preserve the original job identity or its linked execution history according to the system architecture.

A retry must not create the appearance of a new academic learning session.

---

8. Learning Focus and Faculty Scheduling

The five faculties are parallel knowledge domains:

- FAC-ECO: Faculty of Economics.
- FAC-BUS: Faculty of Business.
- FAC-GEO: Faculty of Geopolitics.
- FAC-FIN: Faculty of Finance.
- FAC-MKT: Faculty of Financial Markets.

They are not sequential intelligence levels.

8.1 Primary Active Faculty

A learning sequence should have one primary active faculty.

The active faculty determines the primary academic direction of scheduled learning.

The Founder controls faculty activation according to "FACULTY_PROGRESSION_POLICY.md".

8.2 Cross-Faculty Research

Cognis may use relevant knowledge from other faculties when necessary.

For example:

- Economics research may reference financial markets.
- Business research may reference finance.
- Geopolitical analysis may reference economics and energy markets.
- Financial analysis may reference business fundamentals.

Cross-faculty references do not automatically activate another faculty.

8.3 Faculty Schedule Changes

The scheduler must not independently change the primary active faculty.

A change in academic focus requires an authorized decision consistent with the faculty progression policy.

8.4 MVP Boundary

During the MVP, the active faculty may be selected through configuration or another explicitly controlled process.

Automatic faculty activation and progression are deferred.

---

9. Workload and Resource Management

Scheduling must account for the technical resources available to Cognis.

9.1 Execution Queue

Learning jobs should be placed in a managed execution queue.

The queue must support:

- Job ordering.
- Execution availability.
- Retry scheduling.
- Duplicate prevention.
- Failure recording.
- Cancellation where supported.

9.2 Concurrency

The MVP should use a conservative default of one active learning job at a time.

This reduces unnecessary resource contention and simplifies debugging.

Concurrency may be increased only after system performance, API limits, and execution reliability have been tested.

9.3 Resource Limits

Each learning job should respect configurable limits for:

- Execution duration.
- Number of research requests.
- Number of sources processed.
- Model invocations.
- API usage.
- Retry attempts.
- Stored output size.

The limits must be recorded in execution metadata when relevant.

9.4 API and Provider Availability

If the configured model provider or research service becomes unavailable, Cognis must record the failure and follow its configured retry policy.

The system must not silently switch to an unapproved provider when doing so could affect cost, data handling, or evaluation consistency.

9.5 Workload Priority

Recommended priority order:

1. Founder-initiated urgent task.
2. Previously authorized scheduled task.
3. Retry of an interrupted authorized task.
4. Non-urgent maintenance or review task.

Priority must not override authorization boundaries.

---

10. Missed Schedules and Execution Failures

A missed schedule must be handled explicitly.

10.1 Missed Execution

A missed schedule may occur because:

- The system was offline.
- The scheduler was unavailable.
- The job queue was blocked.
- Required credentials were unavailable.
- The task exceeded resource limits.
- The required authorization was missing.

The system must record the reason whenever it can determine it.

10.2 Recovery Policy

The recovery policy must distinguish between different task types.

Task Type| Default Recovery Behavior
Daily learning task| Do not create unlimited catch-up jobs
One-time task| Preserve as missed or queued according to its expiration policy
Recurring task| Continue according to the next valid occurrence
Retryable job| Retry within configured limits
Unauthorized task| Remain unexecuted until authorization exists

10.3 No Unbounded Catch-Up

If Cognis is offline for several days, it must not automatically launch every missed daily learning job at once.

The scheduler should preserve the latest valid learning plan and mark older occurrences as missed, skipped, or expired according to policy.

10.4 Failed Learning Stage

If a learning job fails during one pipeline stage:

- Record the failed stage.
- Preserve completed stage outputs where safe.
- Identify the reason for failure.
- Apply the configured retry policy.
- Avoid duplicating previously completed operations.
- Report incomplete results honestly.

A failed job must not be reported as a fully completed learning activity.

---

11. Duplicate Prevention and Schedule Reliability

Scheduled execution must avoid accidental duplication.

11.1 Idempotency

Each scheduled occurrence should have a stable identity or idempotency key.

Reprocessing the same scheduler event must not create multiple independent Learning Jobs for the same occurrence.

11.2 Schedule Configuration Changes

Changes to schedule configuration must be versioned.

Each execution should identify the schedule version that initiated it.

Historical execution records must retain their original configuration reference.

11.3 Scheduler Restart

When the scheduler restarts, it must recover pending work without creating duplicate jobs.

Recovery behavior must follow the execution state and idempotency rules defined in the system architecture.

11.4 Clock Handling

The scheduler must use the configured timezone when determining local execution times.

Persisted timestamps should use a consistent canonical representation, preferably UTC.

Human-facing reports may display timestamps in the configured local timezone.

The system must not depend on the server's local timezone being correctly configured.

---

12. Communication and Notification Policy

Communication must be useful without generating unnecessary notifications.

12.1 Morning Learning Brief

The morning brief should summarize:

- Today's authorized learning objective.
- Primary active faculty.
- Expected research scope.
- Planned activities.
- Relevant constraints.
- Any unresolved authorization or configuration issue.

The brief is a plan, not evidence that the learning activity has already been completed.

12.2 Execution Notifications

Execution notifications should be limited to meaningful events.

Examples:

- Learning job started.
- Learning job completed.
- Learning job failed.
- Approval or configuration is required.
- A significant blocker prevents execution.

Minor internal stage transitions do not need individual notifications unless they are useful for debugging.

12.3 Daily Learning Report

The daily report is the primary summary of the day's learning activity.

It should avoid repeating every technical log entry.

Detailed execution logs should remain available separately.

12.4 Notification Channels

Telegram is a planned communication option.

However, Telegram is not mandatory for the MVP.

The notification layer should remain modular so that future channels can be integrated without changing the core learning pipeline.

Possible future channels include:

- Telegram.
- Web application dashboard.
- Internal notification interface.
- Email.

A delivery failure must not be confused with a learning execution failure.

For example, a successfully completed research job may still have a failed Telegram report delivery.

These events must be recorded separately.

---

13. Schedule Configuration

A schedule configuration should conceptually support the following fields.

Field| Purpose
schedule_id| Unique schedule identifier
schedule_name| Human-readable schedule name
schedule_version| Schedule configuration version
schedule_type| Manual, recurring, or one-time
timezone| Timezone used for execution
recurrence_rule| Recurrence definition, when applicable
scheduled_at| One-time execution timestamp, when applicable
active_faculty_id| Primary active faculty
learning_scope| Authorized learning scope
learning_objective| Intended learning objective
approval_mode| Required authorization behavior
resource_policy| Applicable workload and resource limits
delivery_policy| Brief and report delivery configuration
enabled| Whether the schedule is active
created_at| Schedule creation timestamp
updated_at| Last configuration update

These fields define conceptual requirements.

They do not require the MVP to create a separate database entity for every field if the existing architecture provides a simpler suitable implementation.

13.1 Approval Modes

The schedule should conceptually distinguish two authorization modes.

PREAUTHORIZED_RECURRING

The Founder explicitly enables a recurring schedule within a defined scope.

Each valid occurrence may run without requesting separate approval, provided the execution remains within that scope.

PER_RUN_APPROVAL

Each occurrence requires explicit Founder authorization.

If authorization is unavailable, the task must remain unexecuted.

The MVP may support pre-authorized recurring schedules through configuration.

A complete interactive per-run approval workflow is deferred.

13.2 Schedule Suspension

The Founder must be able to disable or pause a recurring schedule through the supported configuration process.

Disabling a schedule prevents future occurrences from being initiated.

It must not silently delete historical execution records.

---

14. Weekly and Periodic Review

Daily learning reports provide execution-level visibility.

A periodic review serves a different purpose.

A future weekly review may examine:

- Research coverage across the active faculty.
- Repeated unresolved questions.
- Recurring source-quality problems.
- Knowledge organization.
- Learning job reliability.
- API and resource usage.
- Potential improvements to learning scope.
- Recommendations for future learning activities.

Weekly review is optional and disabled by default until explicitly configured.

The review must not automatically trigger faculty progression or permanent system changes.

---

15. Academic and Execution Status Separation

Schedule status, Learning Session status, Learning Job status, and Faculty status must remain separate.

Examples:

- A schedule may be enabled while its next occurrence is waiting.
- A Learning Session may remain active while one of its jobs fails.
- A Learning Job may be completed while the academic objective remains only partially demonstrated.
- A Faculty may remain active even when no job is currently running.

The system must not infer one status from another without an explicit rule.

The canonical Learning Job states defined in "SYSTEM_ARCHITECTURE.md" remain:

- QUEUED
- RUNNING
- COMPLETED
- FAILED
- CANCELLED

Schedule lifecycle and academic lifecycle states must not replace these technical job states.

---

16. MVP Implementation Requirements

The MVP must provide a reliable minimum scheduling mechanism.

16.1 Required

The MVP must support:

1. Manual learning task initiation.
2. Scheduled learning task initiation.
3. Explicit timezone configuration.
4. A controlled execution queue.
5. A configurable active learning scope.
6. Duplicate execution prevention.
7. Basic schedule enablement and suspension.
8. Execution status tracking.
9. Failure and retry handling.
10. Daily learning report generation.
11. Preservation of execution metadata.

16.2 Deferred

The following capabilities are not required for MVP:

- Full Telegram integration.
- Interactive daily approval workflow.
- Advanced calendar integration.
- Automatic faculty progression.
- Automatic curriculum progression.
- Dynamic self-generated recurring schedules.
- Unrestricted multi-job concurrency.
- Automatic expansion of learning scope.
- Complex multi-user scheduling and delegation.
- Fully automated weekly academic review.
- Automatic permanent system improvement.

16.3 MVP Priority

Implementation priority should be:

P0: Scheduling Reliability

- Manual and scheduled execution.
- Timezone correctness.
- Queue handling.
- Duplicate prevention.
- Failure tracking.

P1: Reporting

- Daily report generation.
- Report metadata.
- Execution and report delivery status separation.

P2: Operational Expansion

- Telegram.
- Interactive approval.
- Weekly reviews.
- Advanced schedule management.

---

17. Security and Operational Boundaries

The scheduler must not be treated as a trusted authorization mechanism by itself.

A valid schedule does not authorize the system to:

- Access unrelated resources.
- Ignore source validation.
- Bypass evidence evaluation.
- Modify permanent system policies.
- Change the active faculty without authorization.
- Modify curriculum definitions without approval.
- Train or fine-tune models without approval.
- Execute arbitrary instructions found in retrieved content.

Scheduled tasks must use the same security and validation controls as manually initiated tasks.

Schedule configuration and authorization records must be protected from untrusted input.

---

18. Acceptance Criteria

The learning scheduling mechanism is considered acceptable for MVP when:

1. Manual learning tasks can be initiated successfully.
2. Authorized recurring or one-time tasks can be scheduled.
3. Execution uses the configured timezone.
4. The scheduler does not create duplicate jobs for the same occurrence.
5. A system restart does not produce uncontrolled duplicate execution.
6. Failed jobs and missed occurrences are recorded.
7. A missed schedule does not create unbounded catch-up workloads.
8. The active learning scope is respected.
9. The scheduler does not automatically activate another faculty.
10. The morning brief reflects an authorized learning plan.
11. The daily report reflects actual execution records.
12. Report delivery failure is distinguishable from learning execution failure.
13. Learning Job status remains separate from Learning Session and Faculty status.
14. Resource and execution limits are respected.
15. Permanent system changes remain outside ordinary scheduled execution.

---

19. Governance and Change Control

This document is the authoritative reference for Cognis learning schedule principles.

Any implementation or proposed change must:

1. Preserve Founder control over academic direction.
2. Respect the active faculty configuration.
3. Preserve authorization boundaries.
4. Maintain execution traceability.
5. Avoid duplicate or uncontrolled learning jobs.
6. Distinguish academic sessions from technical execution.
7. Respect the MVP scope.
8. Remain consistent with the autonomous learning specification and system architecture.

Changes to default schedule times, approval behavior, or recurring learning scope must be documented and versioned.

A schedule modification must not silently change historical execution records.

---

20. Final Policy Statement

Cognis must learn consistently without losing control over what it learns, why it learns, and when it is authorized to execute.

The daily schedule provides a predictable rhythm:

- 19:00 WIB for Founder planning and authorization.
- 07:00 WIB for the morning learning checkpoint.
- 07:00–17:30 WIB for controlled learning execution.
- 18:00 WIB for the daily learning report.

These are configurable operating defaults, not guarantees of execution success.

The scheduler is responsible for organizing and initiating authorized work. It is not responsible for inventing academic direction, claiming mastery, or approving permanent changes.

The governing principle is: a predictable learning process, controlled execution, transparent reporting, and Founder authority over academic direction.