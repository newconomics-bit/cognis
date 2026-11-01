Assessment Policy

Project: Cognis
Document: Assessment Policy
Version: 1.0
Status: Proposed Baseline
Document Type: Academic Governance
Parent Document: "docs/academy/ACADEMIC_SYSTEM.md"
Related Documents:

- "PRD.md"
- "docs/architecture/SYSTEM_ARCHITECTURE.md"
- "docs/autonomous-learning/AUTONOMOUS_LEARNING_SPEC.md"
- "docs/autonomous-learning/COMPETENCY_CURRICULUM.md"
- "docs/academy/FACULTY_PROGRESSION_POLICY.md"

---

1. Purpose

This document defines how Cognis evaluates the quality of research outputs, learning activities, analytical work, and demonstrated competencies.

The purpose of assessment is to determine whether an output is accurate, logically valid, adequately supported by evidence, and appropriate for its intended learning objective.

Assessment must help Cognis identify:

1. What has been demonstrated successfully.
2. What remains incomplete or incorrect.
3. Whether the reasoning process is valid.
4. Whether conclusions are supported by reliable evidence.
5. Which weaknesses require further investigation or learning.
6. What information can reasonably be used in future capability evaluation.

Assessment must not become a mechanism for generating artificial confidence or claiming mastery without sufficient evidence.

A successful assessment is not merely a high score. It is a traceable evaluation whose criteria, evidence, reasoning, limitations, and conclusions can be inspected.

---

2. Policy Principles

All assessment activities must follow these principles.

2.1 Evidence-Based Evaluation

Every material assessment conclusion must be supported by observable evidence.

The evaluator must not assign a high score simply because an answer sounds convincing, uses technical terminology, or reaches the expected conclusion.

2.2 Reasoning Matters

Cognis must evaluate the reasoning behind an answer, not only its final result.

A correct answer reached through invalid reasoning, unsupported assumptions, or accidental guessing must not be treated as equivalent to a well-supported answer.

2.3 Explicit Uncertainty

When available evidence is insufficient, conflicting, or incomplete, the assessment must communicate uncertainty.

The evaluator must not manufacture certainty to produce a complete-looking report.

2.4 Contextual Evaluation

Assessment criteria must reflect the actual learning objective, subject domain, task difficulty, and expected analytical depth.

A basic economics explanation should not be evaluated using the same expectations as an advanced macroeconomic policy analysis.

2.5 Traceability

Assessment results must be connected to the task, relevant curriculum version, evaluation criteria, evidence, and evaluator configuration.

2.6 No Automatic Mastery Claims

A single successful task does not establish long-term competency.

Competency development requires repeated, relevant, and sufficiently diverse evidence over time.

2.7 Controlled Academic Decisions

Assessment results may inform future academic decisions, but they must not independently trigger permanent curriculum changes, automatic faculty progression, or capability modification in the MVP.

---

3. Assessment Architecture

Cognis distinguishes four related but separate concepts.

Concept| Purpose| MVP Status
Research Evidence Evaluation| Evaluate whether claims are adequately supported by sources and evidence| Included
Task-Level Performance Assessment| Evaluate the quality of a specific learning output or analytical task| Limited and controlled
Competency Assessment| Estimate demonstrated competency across multiple relevant tasks| Deferred
Benchmark Evaluation| Measure system performance against controlled test cases| Basic testing may be performed; full benchmark governance is deferred

These concepts must not be merged into one generic score.

3.1 Research Evidence Evaluation

Research Evidence Evaluation determines whether information acquired during a learning job is credible and whether individual claims are adequately supported.

It examines:

- Source credibility.
- Source relevance.
- Source independence.
- Evidence quality.
- Claim-to-evidence relationships.
- Conflicting information.
- Information limitations.
- Unverified claims.

This evaluation belongs to the MVP learning pipeline.

It does not measure whether Cognis has mastered a subject.

3.2 Task-Level Performance Assessment

Task-Level Performance Assessment evaluates one specific output against a predefined learning objective.

Examples include:

- Explaining an economic concept.
- Interpreting a financial indicator.
- Comparing two business models.
- Analyzing a geopolitical development.
- Evaluating a market hypothesis.
- Identifying weaknesses in a research argument.

The assessment must focus on the task that was actually assigned.

A task-level result must not automatically become a permanent competency rating.

3.3 Competency Assessment

Competency Assessment evaluates the development of a specific competency using multiple relevant observations.

For example, evaluating critical thinking requires more than one correct answer. It may require evidence that Cognis can:

- Identify assumptions.
- Examine alternative explanations.
- Recognize logical weaknesses.
- Compare competing arguments.
- Revise conclusions when new evidence appears.

A competency assessment must account for evidence across different tasks and contexts.

Automatic competency aggregation and proficiency updates are outside the MVP scope.

3.4 Benchmark Evaluation

Benchmark Evaluation measures system behavior against predefined test cases.

Benchmark results are intended to measure consistency, accuracy, reasoning quality, and regression after system changes.

Benchmark testing must be separated from ordinary learning outputs to reduce the risk of treating familiar or memorized answers as proof of general capability.

---

4. Separation of Learning Depth, Task Scores, and Competency Proficiency

Cognis must keep three measurement concepts separate.

4.1 Curriculum Learning Depth

The competency curriculum defines four qualitative learning depth categories:

Learning Depth| Description
Foundation| Basic concepts, definitions, terminology, and fundamental relationships
Applied| Applying concepts to practical situations and straightforward problems
Analytical| Examining relationships, comparing explanations, interpreting evidence, and evaluating complex problems
Strategic| Integrating multiple domains, evaluating long-term consequences, and developing high-level decisions or frameworks

These categories describe the complexity and intended depth of a learning objective.

They do not represent a numerical score or a confirmed level of mastery.

A task assigned to Strategic depth does not automatically mean Cognis has achieved Strategic competence.

4.2 Task-Level Assessment Rubric

A provisional 0–4 rubric may be used to evaluate individual assessment criteria.

Each score applies only to the criterion and task being evaluated.

The rubric is defined in Section 7.

A task-level score must not be interpreted as an overall intelligence, capability, or competency rating.

4.3 Competency Proficiency

A long-term competency proficiency scale requires its own validated definitions, evidence aggregation rules, and measurement standards.

An earlier 0–5 proficiency concept is not an active measurement standard in this version of the curriculum.

Therefore:

- The 0–5 scale must not be used operationally in the MVP.
- Task-level scores must not be converted into proficiency scores.
- Curriculum depth categories must not be converted into proficiency scores.
- Competency proficiency must not be inferred from the number of completed learning sessions.
- Any future proficiency scale must be formally defined and approved before implementation.

This separation prevents misleading academic conclusions.

---

5. MVP Assessment Scope

The MVP focuses on establishing reliable research and evidence handling.

5.1 Included

The MVP must support:

1. Evaluating sources used during research.
2. Evaluating whether claims are supported by available evidence.
3. Recording conflicts and information limitations.
4. Preserving claim-to-source traceability.
5. Producing learning reports that distinguish supported, partially supported, and unverified information.
6. Recording relevant task, model, prompt, and evaluation metadata.
7. Allowing manual inspection of selected outputs by the Founder.

5.2 Limited or Deferred

The following capabilities are not required for MVP implementation:

- Automated competency proficiency calculation.
- Automatic competency score aggregation.
- Automatic faculty readiness calculation.
- Automatic faculty progression.
- Permanent learning ability updates based on a single assessment.
- Automatic curriculum modification.
- Automatic benchmark generation and governance.
- Model fine-tuning based on assessment results.
- Automatic modification of system policies or architecture.

The assessment policy defines the conceptual requirements for these future capabilities, but their existence in this document does not authorize their implementation.

---

6. Assessment Design

Every formal assessment should begin with a clearly defined evaluation target.

An assessment must identify:

1. What is being evaluated.
2. Why the evaluation is necessary.
3. Which learning objective is relevant.
4. Which competency references are relevant, when applicable.
5. Which curriculum version applies.
6. Which learning depth is expected.
7. Which assessment criteria will be used.
8. What evidence is required.
9. What limitations may affect the result.

6.1 Learning Objective

The learning objective must describe an observable capability or expected output.

Weak objective:

«Understand financial markets.»

Better objective:

«Explain how changes in interest-rate expectations can influence bond yields, currency movements, and equity valuations, including the assumptions and limitations of the explanation.»

The second objective provides a clearer basis for evaluation.

6.2 Assessment Task

The task must be specific enough for the evaluator to identify whether the objective has been achieved.

Task instructions should avoid ambiguity about:

- Expected output.
- Relevant context.
- Available data.
- Required reasoning.
- Expected analytical depth.
- Source or evidence requirements.

6.3 Competency References

An assessment may reference one or more competency IDs from "COMPETENCY_CURRICULUM.md".

The references identify which competencies the task is intended to exercise.

A competency reference does not mean the assessment has measured the entire competency.

6.4 Curriculum Version

Assessment records should preserve the curriculum version used when the task was created.

This is necessary because competency definitions and learning objectives may change over time.

Historical assessment results must not silently inherit new definitions from a later curriculum version.

---

7. Task-Level Assessment Rubric

Cognis may use a 0–4 rubric for individual assessment criteria.

The rubric is provisional and intended for structured internal evaluation.

Score| Interpretation| Description
0| No Valid Evidence| The response is incorrect, irrelevant, fundamentally unsupported, or provides no assessable evidence for the criterion
1| Weak| The response demonstrates major gaps, serious reasoning errors, or substantial unsupported claims
2| Developing| The response contains some valid elements but has important gaps, incomplete reasoning, or insufficient evidence
3| Adequate| The response satisfies the objective with mostly valid reasoning and only limited weaknesses
4| Strong| The response demonstrates accurate, coherent, well-supported reasoning and appropriately recognizes relevant limitations

7.1 Not Assessed

A criterion may be marked "NOT_ASSESSED" when there is insufficient information to evaluate it.

"NOT_ASSESSED" is not equivalent to score 0.

Score 0 means the criterion was evaluated and no valid evidence was demonstrated.

7.2 Score Interpretation

Scores must be interpreted at the criterion level.

For example:

Criterion| Score
Factual Accuracy| 4
Reasoning Validity| 2
Evidence Traceability| 3
Uncertainty Recognition| 2

This indicates that the response may contain accurate information but still have weaknesses in reasoning and uncertainty handling.

The evaluator must explain the scores rather than presenting numbers without justification.

7.3 No Universal Passing Threshold

The MVP must not apply a universal total score or percentage threshold to determine mastery.

In particular:

- A score of 3 is not an automatic competency pass.
- A score of 4 in one criterion does not establish overall mastery.
- A percentage such as 80/100 is not a universal faculty progression requirement.
- Scores from different tasks must not be averaged without a formally defined aggregation method.

Any future pass threshold must be justified by validated assessment design and approved governance rules.

---

8. Assessment Dimensions

Assessment criteria must be selected according to the objective and task.

Not every task requires every dimension.

8.1 Factual Accuracy

Evaluates whether factual statements are correct and consistent with reliable evidence.

Questions:

- Are important facts accurate?
- Are dates, figures, units, and definitions correct?
- Are claims presented in the right context?
- Are outdated or incomplete facts treated appropriately?

8.2 Reasoning Validity

Evaluates whether conclusions follow logically from the stated premises and evidence.

Questions:

- Are assumptions identified?
- Are logical steps consistent?
- Are causal claims adequately supported?
- Are correlations improperly presented as causation?
- Are alternative explanations considered when relevant?

8.3 Evidence and Source Traceability

Evaluates whether important claims can be traced to appropriate evidence.

Questions:

- Are important claims supported by identifiable sources?
- Are sources relevant to the claims?
- Is source independence considered?
- Are contradictory sources handled transparently?
- Are unsupported statements clearly marked?

8.4 Application and Problem Solving

Evaluates whether the knowledge can be applied to the intended situation.

Questions:

- Is the concept applied correctly?
- Does the analysis reflect the actual problem?
- Are relevant contextual conditions considered?
- Does the proposed solution address the problem?

8.5 Quantitative and Data Handling

Used when the task involves numerical information.

Questions:

- Are calculations correct?
- Are units and measurement periods consistent?
- Are statistical interpretations appropriate?
- Are data limitations acknowledged?
- Are numerical conclusions reproducible?

8.6 Uncertainty and Limitations

Evaluates whether the response recognizes incomplete information and the limits of its conclusions.

Questions:

- Is uncertainty communicated accurately?
- Are assumptions distinguished from facts?
- Are missing data identified?
- Are alternative outcomes considered?
- Does the conclusion exceed what the available evidence supports?

8.7 Analytical Communication

Evaluates whether the reasoning and conclusions are communicated clearly.

Questions:

- Is the structure understandable?
- Are important distinctions preserved?
- Are conclusions connected to supporting reasoning?
- Are technical terms used correctly?
- Is the explanation appropriate for the intended audience?

---

9. Assessment Procedure

A controlled assessment should follow this sequence.

Step 1: Define the Assessment

Identify the learning objective, expected depth, task, relevant competency references, and evaluation criteria.

Step 2: Establish Evaluation Context

Provide the evaluator with the task instructions, relevant data, permitted sources, and necessary context.

The evaluator must not be given irrelevant information that may distort the assessment.

Step 3: Evaluate the Output

Evaluate each applicable criterion independently.

The evaluator must distinguish:

- Verified facts.
- Reasoning.
- Assumptions.
- Inferences.
- Unsupported claims.
- Missing information.

Step 4: Record Supporting Evidence

Each significant evaluation judgment must include supporting excerpts, source references, calculations, or other observable evidence.

The evaluator must not use its own confidence as evidence.

Step 5: Record Weaknesses

Identify errors, missing reasoning, unsupported conclusions, and limitations.

Weakness descriptions should be specific and actionable.

Step 6: Produce the Assessment Result

Produce a structured result containing criterion-level scores where applicable, explanations, evidence references, uncertainty, and an overall qualitative interpretation.

Step 7: Human Review When Required

Send the assessment for Founder review when the result has material consequences, contains unresolved disputes, or cannot be evaluated reliably.

Step 8: Preserve the Record

Store the assessment result with sufficient metadata to reproduce or inspect the evaluation later.

Assessment results must not silently modify curriculum definitions or permanent system configurations.

---

10. Evaluation Integrity

10.1 Correct Answer Versus Correct Reasoning

A response must not receive a strong reasoning score merely because its final answer matches the expected result.

The evaluator must inspect how the conclusion was obtained.

For example, an economic forecast may happen to be correct while relying on an invalid causal assumption.

The factual result and reasoning quality must therefore be evaluated separately.

10.2 Unsupported Confidence

Confidence statements such as "I am 95% certain" do not establish correctness.

The evaluator must identify the evidence and reasoning supporting its judgment.

10.3 Fabricated Evidence

The evaluator must not invent:

- Source references.
- Quotations.
- Data points.
- Calculations.
- Research findings.
- Benchmark results.
- Assessment observations.

When supporting evidence is unavailable, the result must state that limitation.

10.4 Contradictory Evidence

When evidence conflicts, the evaluator must not selectively present only the evidence supporting its preferred conclusion.

It must describe:

- Which claims conflict.
- Which sources support each position.
- Differences in methodology or context.
- Whether the conflict can be reasonably resolved.
- What remains uncertain.

10.5 Evaluation Reproducibility

Where practical, assessment records must retain the task, criteria, relevant input, evaluator identity, model version, prompt configuration, and supporting evidence.

This allows later review of how an assessment result was produced.

---

11. Evaluator Requirements

The evaluator is responsible for applying the assessment criteria consistently and transparently.

11.1 Role Separation

Where practical, the model that produces an answer and the model or evaluation process that assesses it should have distinct evaluation roles.

The evaluator should receive:

- The original task.
- The expected objective.
- The response being evaluated.
- The assessment rubric.
- Relevant supporting evidence.

The evaluator must not simply repeat or endorse the original model's conclusions.

11.2 Independence Limitations

Using a separate prompt or evaluation role does not guarantee independent judgment.

Using the same model provider does not establish independent verification.

Using different models also does not automatically eliminate shared blind spots or systematic errors.

Cognis must describe the actual evaluation arrangement instead of claiming independence that has not been demonstrated.

11.3 Evaluation Explanation

For each assessed criterion, the evaluator should provide:

- Assigned score or "NOT_ASSESSED".
- Reason for the result.
- Supporting evidence.
- Identified weaknesses.
- Relevant uncertainty.

11.4 Evaluator Limitations

The evaluator must be allowed to return an inconclusive result.

It must not be forced to assign a score when the task, rubric, or available evidence is insufficient.

---

12. Human Review and Founder Oversight

The Founder retains authority over permanent academic and system governance decisions.

Human review is particularly important when:

- Assessment results are contradictory.
- Evidence is insufficient for a reliable judgment.
- The evaluation contains a potentially serious factual error.
- A proposed change may affect curriculum or academic policy.
- A result may influence future faculty activation decisions.
- A high-impact benchmark shows unexpected regression.

Founder review may result in:

1. Accepting the assessment result.
2. Rejecting the assessment result.
3. Requesting additional evidence.
4. Requesting a new evaluation.
5. Revising the assessment criteria.
6. Marking the result as inconclusive.
7. Invalidating the assessment.

Human review must preserve the original assessment record.

A reviewed assessment must not overwrite its previous version without an audit trail.

During the MVP, Founder review may be conducted manually. A complete approval workflow is not required.

---

13. Assessment Outcomes and Status

Assessment workflow status must be separated from assessment conclusions.

13.1 Assessment Status

The following status definitions are proposed:

Status| Meaning
DRAFT| Assessment definition is being prepared
IN_REVIEW| Evaluation is being performed
EVALUATED| An evaluation result has been produced
HUMAN_REVIEW_REQUIRED| Human inspection is required before the result is treated as reviewed
REVIEWED| Human review has been completed
INVALIDATED| The assessment result has been declared invalid

These are assessment lifecycle states.

They must not be confused with Learning Job, Learning Session, or Faculty statuses.

13.2 Assessment Conclusion

An assessment may use a qualitative conclusion appropriate to its objective.

Suggested categories:

Conclusion| Meaning
STRONG| The available evidence demonstrates strong fulfillment of the objective
ADEQUATE| The objective is fulfilled with limited weaknesses
LIMITED| Some relevant capability is demonstrated, but important weaknesses remain
INSUFFICIENT| The available output does not adequately demonstrate the objective
INCONCLUSIVE| The available information is insufficient for a reliable conclusion

The conclusion is a task-level interpretation.

It does not establish long-term competency proficiency or authorize faculty progression.

---

14. Benchmark Assessment

Benchmark evaluation is intended to measure system performance across controlled test cases.

A benchmark may evaluate:

- Factual accuracy.
- Reasoning validity.
- Source handling.
- Evidence traceability.
- Quantitative correctness.
- Uncertainty recognition.
- Analytical consistency.
- Domain-specific task performance.

14.1 Benchmark Design

A benchmark should define:

1. Test case ID.
2. Test case version.
3. Evaluation objective.
4. Input and expected evaluation criteria.
5. Applicable competency references.
6. Scoring rubric.
7. Required evidence.
8. Known limitations.
9. Evaluation procedure.

14.2 Benchmark Integrity

Benchmark cases must not be silently modified to make system performance appear better.

Changes to benchmark definitions must be versioned.

When a benchmark result is compared across system versions, the comparison must account for changes in:

- Model version.
- Prompt configuration.
- Retrieval configuration.
- Available evidence.
- Evaluation criteria.
- Test case version.

14.3 Data Leakage

Benchmark cases should be separated from ordinary learning material when practical.

Repeated exposure to a test case must not be treated as proof of generalization.

Where possible, future evaluations should include new or held-out cases to test whether Cognis can apply knowledge beyond familiar examples.

14.4 MVP Boundary

The MVP may use basic controlled tests during development and verification.

A comprehensive benchmark management system, automatic benchmark generation, and long-term capability scoring remain deferred.

---

15. Assessment Records

Assessment records should preserve enough information to inspect and reproduce the evaluation.

A future structured assessment record should support the following fields.

Field| Purpose
assessment_id| Unique assessment identifier
assessment_version| Version of the assessment record
session_id| Related academic learning session, when applicable
learning_job_id| Related technical learning job, when applicable
task_id| Identifier of the evaluated task
task_definition| Original task and evaluation objective
competency_refs| Related competency IDs
curriculum_version| Curriculum version used
learning_depth| Expected learning depth
rubric_version| Version of the assessment rubric
criterion_results| Scores and explanations for individual criteria
evidence_refs| References to supporting evidence
conclusion| Qualitative task-level conclusion
uncertainty| Known limitations and unresolved issues
evaluator_model| Evaluator model identity and version
evaluator_prompt_version| Evaluation prompt version
evaluation_metadata| Relevant configuration and execution metadata
status| Assessment lifecycle status
reviewed_by| Human reviewer, when applicable
reviewed_at| Review timestamp, when applicable
created_at| Record creation timestamp
updated_at| Last record update timestamp

These are conceptual record requirements, not a mandatory database schema for MVP implementation.

The actual implementation must follow the system architecture and avoid duplicating data already stored in related entities.

---

16. Assessment History and Versioning

Assessment records must be historically traceable.

When an assessment is repeated or revised:

- Preserve the original result.
- Create a new version or linked assessment record.
- Record why the reassessment occurred.
- Identify any changed task or rubric definitions.
- Preserve the evaluator configuration.
- Keep human review decisions traceable.

Historical results must not be silently recalculated using new rubrics.

If a previous result is invalidated, the reason must be recorded.

Invalidation does not mean the original event never happened. It means the result is no longer considered valid for its intended use.

---

17. Assessment and Learning Improvement

Assessment findings may identify weaknesses that should influence future learning.

Examples include:

- Repeated misunderstanding of an economic concept.
- Inconsistent interpretation of statistical evidence.
- Weak causal reasoning.
- Poor source verification.
- Incorrect quantitative analysis.
- Inadequate uncertainty handling.

During the MVP, these findings may be included in learning reports or recorded as research and improvement recommendations where supported by the implementation.

They must not automatically trigger:

- Permanent competency score changes.
- Curriculum restructuring.
- Faculty progression.
- System prompt modification.
- Model fine-tuning.
- Permanent architecture or policy changes.

Future Autonomous Learning System capabilities may use validated assessment evidence to propose improvements.

Any permanent change must follow the governance process defined by the applicable future ALS specification, including Founder approval, controlled implementation, testing, and rollback where necessary.

---

18. Security and Assessment Integrity

Assessment inputs and retrieved material must be treated as untrusted data.

Instructions embedded in research sources, benchmark cases, or evaluated responses must not override Cognis system policies.

The evaluator must distinguish task content from trusted system instructions.

Assessment records must also follow the project's data protection and access-control policies.

Sensitive or unnecessary personal information must not be collected as assessment evidence.

Assessment history must not be modified by untrusted source content or by the output being evaluated.

---

19. Implementation Roadmap

Assessment capabilities are introduced progressively.

Phase 1: MVP

Focus:

- Research source evaluation.
- Claim and evidence evaluation.
- Evidence traceability.
- Structured learning reports.
- Basic task-level output inspection where needed.
- Recording relevant evaluation metadata.

Explicit exclusions:

- Automatic competency proficiency calculation.
- Automatic faculty readiness scoring.
- Automatic academic progression.
- Permanent self-improvement based on assessment results.

Phase 2: Structured Task Assessment

Potential capabilities:

- Formal task definitions.
- Versioned assessment rubrics.
- Structured criterion-level evaluation.
- Human review interface.
- Assessment history and comparison.

Implementation requires an approved scope and a validated assessment process.

Phase 3: Competency Evidence Management

Potential capabilities:

- Collecting relevant evidence across multiple tasks.
- Identifying recurring strengths and weaknesses.
- Measuring evidence coverage and diversity.
- Evaluating consistency across different contexts.
- Proposing competency-level observations.

A proficiency scale and aggregation methodology must be formally defined before automated competency measurement is activated.

Phase 4: Governed Capability Improvement

Potential capabilities:

- Benchmark-driven weakness detection.
- Improvement proposals based on assessment history.
- Founder approval.
- Controlled curriculum or system changes.
- Regression testing.
- Rollback after failed changes.

This phase belongs to the future governed ALS roadmap, not the MVP.

---

20. Acceptance Criteria

This policy is considered correctly implemented at the MVP level when:

1. Research claims can be linked to identifiable supporting evidence.
2. Source quality and claim support are evaluated as separate concerns.
3. Unsupported or uncertain claims are not presented as verified facts.
4. Important conflicting evidence is preserved and communicated.
5. Learning reports distinguish evidence quality from competency mastery.
6. Evaluation metadata is recorded where required by the architecture.
7. Task-level scores, when used, are not treated as permanent competency ratings.
8. Learning depth categories are not confused with mastery scores.
9. The system does not automatically calculate or update competency proficiency.
10. The system does not automatically promote faculties based on assessment results.
11. Assessment conclusions can be inspected and reviewed.
12. Historical assessment results remain traceable after revisions.

---

21. Governance and Change Control

This document is the authoritative reference for Cognis assessment principles and boundaries.

Any implementation or proposed change must:

1. Preserve the separation between research evidence evaluation and competency assessment.
2. Preserve the distinction between learning depth and task-level scores.
3. Avoid unsupported claims of mastery.
4. Maintain traceability of evaluation evidence.
5. Respect MVP scope and autonomy boundaries.
6. Be consistent with the competency curriculum and faculty progression policy.
7. Receive appropriate Founder approval when it changes permanent academic governance.

Conflicts between assessment rules and other documents must be reported rather than silently resolved through implementation.

Changes to this policy must be versioned and documented.

---

22. Final Policy Statement

Cognis must evaluate what it can demonstrate, not what it claims to know.

Research evidence, task performance, competency development, and benchmark performance are separate forms of evaluation.

A successful research result does not prove mastery. A high task score does not establish permanent capability. A completed learning session does not demonstrate competency by itself.

During the MVP, Cognis must prioritize reliable evidence evaluation, transparent learning reports, and traceable execution.

More advanced assessment and competency measurement may be introduced only after the system has accumulated sufficient evidence and the measurement methodology has been formally defined.

The governing principle is simple: no capability claim without evidence, no mastery claim without repeated demonstration, and no permanent academic change without controlled approval.