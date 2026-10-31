Cognis AI

Product Requirements Document (PRD)

Project Name: Cognis AI
Repository: "cognis"
Document Version: 1.0
Status: Initial Specification
Product Category: AI Research and Autonomous Learning System

---

1. Product Overview

Cognis AI is a domain-specialized artificial intelligence system designed to conduct research, develop domain competencies, evaluate its own capabilities, and improve through a controlled autonomous learning process.

Cognis is not intended to be just a conversational AI or a document retrieval system.

Its primary purpose is to develop reliable analytical capabilities across interconnected domains, maintain an organized knowledge base, conduct evidence-based research, and demonstrate measurable improvements through independent evaluations.

The system will use existing AI models through provider integrations during its initial development. Its architecture must remain flexible enough to support different models and future fine-tuning initiatives.

The long-term objective is to develop an increasingly capable, specialized intelligence system through the Autonomous Learning System (ALS).

2. Product Vision

Build an AI system that continuously develops specialized knowledge and analytical competence through research, structured learning, evaluation, and controlled improvement.

Cognis should eventually be capable of:

- Understanding complex economic and business problems.
- Analyzing financial and market conditions.
- Connecting geopolitical developments with economic consequences.
- Conducting independent research using credible sources.
- Identifying conflicting evidence and uncertainty.
- Producing structured analytical reports.
- Recognizing its own competency gaps.
- Designing learning activities to address those gaps.
- Demonstrating measurable improvements over time.

The system must prioritize actual reasoning and task performance over the appearance of intelligence.

3. Target Users

Primary User

The initial primary user is the system owner, who supervises Cognis, provides research directions, reviews learning reports, and approves permanent changes.

Future Users

The architecture should allow additional authorized users to interact with Cognis through controlled access.

Future user-facing capabilities may include:

- Research assistance.
- Economic and business analysis.
- Financial education.
- Market research.
- Structured learning.
- Access to approved research outputs.

Multi-user capabilities must not compromise user privacy, data isolation, or administrative control.

4. Core Knowledge Domains

Cognis will initially concentrate on five interconnected domains.

4.1 Economics

Competencies include:

- Microeconomics.
- Macroeconomics.
- Monetary economics.
- Fiscal policy.
- International trade.
- Economic history.
- Economic schools of thought.
- Central banking and monetary systems.
- Economic indicators.
- Economic crises and business cycles.

4.2 Business

Competencies include:

- Business models.
- Market research.
- Competitive analysis.
- Strategy development.
- Operations management.
- Entrepreneurship.
- Unit economics.
- Pricing and profitability.
- Supply chains.
- Business risk management.

4.3 Geopolitics

Competencies include:

- International relations.
- Geopolitical strategy.
- International conflicts.
- Resource competition.
- Trade relations.
- Energy security.
- Political economy.
- Strategic alliances.
- Regional and global power dynamics.

4.4 Finance

Competencies include:

- Financial statements.
- Corporate finance.
- Capital allocation.
- Investment principles.
- Banking systems.
- Financial markets and institutions.
- Risk management.
- Portfolio theory.
- Financial instruments.
- Financial history.

4.5 Financial Markets

Competencies include:

- Market structure.
- Price discovery.
- Market participants.
- Liquidity.
- Trading psychology.
- Technical analysis.
- Fundamental analysis.
- Market microstructure.
- Volatility.
- Risk and position management.
- Derivatives and leverage.

These domains must not operate as isolated knowledge categories.

Cognis should progressively develop cross-domain reasoning, including relationships such as:

- Geopolitical conflict and energy prices.
- Monetary policy and currency movements.
- Interest rates and capital allocation.
- Supply chains and business profitability.
- Liquidity conditions and financial market behavior.

5. Product Architecture at the Product Level

Cognis is organized around six primary functional capabilities.

5.1 Intelligence Layer

Responsible for interacting with AI models and coordinating tasks that require reasoning, analysis, extraction, and communication.

Responsibilities:

- Model selection.
- Model provider integration.
- Task-specific model routing.
- Response generation.
- Reasoning workflows.
- Structured output generation.

Cognis must not depend on one permanent AI provider.

5.2 Research Engine

Responsible for gathering, assessing, and organizing external information.

Responsibilities:

- Research discovery.
- Source retrieval.
- Source credibility assessment.
- Evidence extraction.
- Cross-source comparison.
- Citation management.
- Research summarization.
- Identification of conflicting information.

Research outputs must distinguish facts, interpretations, assumptions, hypotheses, predictions, and uncertainty.

5.3 Knowledge and Memory System

Responsible for organizing information obtained from research and interactions.

Knowledge must be separated into distinct categories:

1. General knowledge: relatively stable concepts and principles.
2. Contextual knowledge: information related to specific users, projects, or research tasks.
3. Time-sensitive knowledge: information that requires current verification.
4. Evaluated knowledge: information that has passed defined validation procedures.

Storing information must not automatically make it authoritative or verified.

5.4 Autonomous Learning System (ALS)

Responsible for managing the system's learning lifecycle.

The ALS must:

- Identify competency gaps.
- Set learning objectives.
- Select learning resources.
- Conduct research.
- Create learning outputs.
- Run competency evaluations.
- Identify weaknesses.
- Generate improvement proposals.
- Request approval for permanent changes.
- Apply approved changes.
- Measure post-change performance.
- Support rollback when improvements fail.

The ALS is a central product capability, not an optional background feature.

5.5 Competency Engine and Evaluation System

Responsible for defining, measuring, and tracking Cognis's actual capabilities.

Responsibilities:

- Competency definitions.
- Learning objectives.
- Difficulty levels.
- Assessment generation.
- Evaluation rubrics.
- Benchmark execution.
- Performance history.
- Weakness identification.
- Competency progression.

Competency must be measured through demonstrated task performance, not merely accumulated documents or self-assessed confidence.

5.6 User Interaction Layer

The initial interaction channel is Telegram.

Responsibilities:

- Receive user instructions.
- Start research tasks.
- Deliver research outputs.
- Request daily learning briefs.
- Send daily learning reports.
- Present improvement proposals.
- Receive approval or rejection.
- Communicate task status and failures.

The internal business logic must remain independent of Telegram so additional interfaces can be added later.

6. Core User Workflows

6.1 Research Workflow

1. User submits a research question.
2. Cognis interprets the objective and scope.
3. Cognis identifies necessary research sources.
4. Research Engine gathers relevant evidence.
5. Cognis evaluates source quality.
6. Intelligence Layer analyzes the findings.
7. Cognis generates a structured report.
8. User receives the result through Telegram.
9. Research materials are stored with appropriate provenance and access controls.

The system must communicate when evidence is insufficient or conflicting.

6.2 Autonomous Learning Workflow

1. ALS checks the active competency curriculum.
2. ALS identifies learning priorities.
3. ALS creates a learning objective.
4. Research Engine gathers relevant materials.
5. Cognis studies and organizes the information.
6. Evaluation System tests the acquired competency.
7. ALS records the result.
8. ALS identifies remaining weaknesses.
9. ALS proposes the next learning activity or system improvement.
10. Permanent changes enter the human approval process.

6.3 Daily Learning Workflow

The initial intended schedule uses Asia/Jakarta time and must be configurable.

07:00 WIB: Daily Brief Request

If the user has not submitted a daily brief, Cognis sends a Telegram message requesting the day's research or learning direction.

During the Day: Learning Execution

Cognis processes approved learning activities using background jobs, checkpoints, resource budgets, and controlled retry behavior.

18:00 WIB: Daily Learning Report

Cognis delivers a structured report containing:

- Learning objectives.
- Topics studied.
- Sources reviewed.
- Important findings.
- New concepts.
- Competency evaluations.
- Identified weaknesses.
- Proposed next steps.
- Changes requiring approval.

The report must separate newly acquired information from verified competency improvements.

Human Review

The user can review the report and approve, reject, or request revisions to proposed permanent changes.

A report being delivered does not automatically authorize its proposed changes.

7. MVP Scope

The MVP must establish the smallest usable foundation for Cognis without prematurely implementing the entire long-term vision.

7.1 MVP Features

A. Core Application

- Basic application structure.
- Configuration management.
- Environment-based secret handling.
- Modular service organization.
- Error handling and structured logging.

B. AI Model Integration

- At least one working AI provider integration.
- Replaceable provider interface.
- Configurable model selection.
- API error handling.
- Request timeout handling.
- Usage and cost tracking where available.

C. Telegram Interface

- Telegram bot connection.
- Authorized user access.
- Basic command handling.
- Research request submission.
- Result delivery.
- Task status notifications.

D. Research Engine

- Research task creation.
- Source retrieval through approved integrations.
- Source metadata preservation.
- Research summarization.
- Citation tracking.
- Structured reports.

E. Knowledge Management

- Persistent knowledge storage.
- Basic categorization.
- Source provenance.
- Knowledge status and review state.
- Search and retrieval.

F. Autonomous Learning Foundation

- Competency curriculum storage.
- Learning objective creation.
- Learning task execution.
- Learning result recording.
- Basic competency evaluation.
- Improvement proposal generation.

G. Human Approval

- Proposal creation.
- Proposal review.
- Explicit approval and rejection.
- Approval history.
- Controlled application of approved changes.

H. Operational Reliability

- Asynchronous job processing.
- Persistent job state.
- Checkpoint and recovery support.
- Bounded retries.
- API and resource budgets.
- Basic monitoring.

7.2 MVP Exclusions

The following are not required for the first MVP:

- Training a foundation model from scratch.
- Large-scale pretraining.
- Fully autonomous model-weight modification.
- Unrestricted autonomous code execution.
- Unrestricted web scraping.
- Autonomous financial transactions.
- Broker or exchange trading execution.
- Public multi-tenant SaaS launch.
- Complex graphical dashboards.
- Multi-agent orchestration without a demonstrated requirement.

These may be considered in later development phases after the core system has demonstrated reliability and measurable value.

8. Functional Requirements

ID| Requirement| Priority
FR-01| Cognis must accept research requests through Telegram.| Must
FR-02| Cognis must integrate with at least one AI provider.| Must
FR-03| AI providers must be replaceable through a defined interface.| Must
FR-04| Research outputs must preserve source references.| Must
FR-05| Research outputs must distinguish evidence from interpretation.| Must
FR-06| Cognis must store research results persistently.| Must
FR-07| Cognis must maintain an organized competency curriculum.| Must
FR-08| ALS must create and track learning objectives.| Must
FR-09| Cognis must evaluate learning results against defined criteria.| Must
FR-10| Cognis must record evaluation history.| Must
FR-11| ALS must identify competency gaps.| Must
FR-12| ALS must generate improvement proposals.| Must
FR-13| Permanent changes must require explicit authorization.| Must
FR-14| The system must maintain an auditable approval history.| Must
FR-15| Long-running jobs must support asynchronous processing.| Must
FR-16| Jobs must support checkpointing and recovery.| Must
FR-17| The system must enforce access controls.| Must
FR-18| The system must track resource consumption where available.| Must
FR-19| Cognis must support configurable daily learning schedules.| Should
FR-20| Cognis should support multiple model providers.| Should
FR-21| Cognis should support cross-domain analysis.| Should
FR-22| Cognis should support competency progression reports.| Should

9. Non-Functional Requirements

9.1 Reliability

- Long-running tasks must not depend on one uninterrupted API request.
- Failed jobs must preserve enough state for diagnosis and recovery.
- Retries must be bounded.
- Duplicate task execution must be controlled.
- Critical changes must be auditable.

9.2 Security

- Secrets must never be exposed in frontend code or committed to Git.
- Only authorized users may access protected functionality.
- AI-generated instructions must not bypass security controls.
- Tool execution must follow explicit permissions.
- Approval controls must be enforced independently of model-generated claims.

9.3 Performance

- Simple interactions should avoid unnecessary background jobs.
- Long research activities should run asynchronously.
- Resource-intensive operations must have configurable limits.
- Model calls should be selected according to task requirements and cost.

9.4 Maintainability

- Components must have clearly defined responsibilities.
- Provider integrations must be replaceable.
- Important business logic must be testable independently.
- Documentation must reflect actual system behavior.

9.5 Scalability

The initial deployment may use modest infrastructure.

However, the architecture should allow future migration to larger infrastructure without requiring a complete application rewrite.

10. Intelligence Quality Requirements

Cognis must not claim to be improving merely because it processes more documents.

Its intelligence development must be measured using a consistent evaluation framework.

The system should be evaluated across:

- Factual accuracy.
- Source reliability.
- Reasoning quality.
- Causal analysis.
- Quantitative reasoning.
- Critical thinking.
- Cross-domain understanding.
- Uncertainty calibration.
- Research completeness.
- Task execution quality.

Each competency must have measurable evaluation criteria.

Benchmark changes must be versioned and documented.

Historical results must remain available so improvements and regressions can be compared fairly.

11. Governance and Approval Requirements

Cognis must operate under human-supervised autonomy.

The system may independently perform permitted research and learning tasks.

However, it must not independently redefine its permanent operating rules.

The approval process must include:

1. Proposed change.
2. Reason for the change.
3. Evidence supporting the proposal.
4. Expected benefit.
5. Potential risks.
6. Implementation scope.
7. Evaluation plan.
8. Rollback plan.
9. Human decision.
10. Final implementation status.

A rejected proposal must not be silently applied.

An approved proposal must still pass implementation and post-change verification.

12. Initial Success Metrics

Success must be measured through observable system behavior.

Product Metrics

- Successful completion rate of research jobs.
- Research report delivery success rate.
- Average API cost per completed task.
- Task failure and recovery rate.
- Citation completeness.
- Approval workflow correctness.

Intelligence Metrics

- Accuracy on fixed benchmark cases.
- Reasoning rubric scores.
- Source evaluation quality.
- Performance on unseen evaluation cases.
- Cross-domain reasoning performance.
- Calibration of uncertainty.
- Regression frequency after approved changes.

Learning Metrics

- Number of competency gaps identified.
- Percentage of learning objectives evaluated.
- Measured improvement between comparable benchmark versions.
- Number of proposals accepted or rejected.
- Percentage of approved changes successfully verified.
- Frequency and severity of regressions.

No numerical performance target should be invented before baseline measurements exist.

Targets must be defined after the initial benchmark and operational baseline are established.

13. Development Phases

Phase 1: Specification and Foundation

Objectives:

- Complete product and architecture specifications.
- Establish repository instructions.
- Define ALS behavior.
- Define competency curriculum.
- Define evaluation framework.
- Define governance and security requirements.

Exit criteria:

- Core specifications are documented.
- Major architecture decisions are recorded.
- Requirements are internally consistent.
- Unresolved decisions are explicitly listed.

Phase 2: Core Infrastructure

Objectives:

- Establish application foundation.
- Implement configuration and secret handling.
- Implement database integration.
- Implement job processing.
- Establish logging and basic monitoring.

Exit criteria:

- Application starts reliably.
- Persistent data operations work.
- Background jobs can be created and recovered.
- Basic tests pass.

Phase 3: AI and Research Engine

Objectives:

- Integrate AI provider.
- Build provider abstraction.
- Implement research workflows.
- Preserve source metadata.
- Generate structured research reports.

Exit criteria:

- Research tasks can complete end-to-end.
- Sources can be traced.
- Failures are handled and reported correctly.

Phase 4: ALS and Competency Engine

Objectives:

- Implement competency curriculum storage.
- Implement learning objectives.
- Implement learning task workflows.
- Implement evaluation and historical tracking.
- Implement improvement proposals.

Exit criteria:

- ALS completes a learning cycle.
- Evaluations produce structured results.
- Weaknesses can be identified.
- Improvement proposals can be generated.

Phase 5: Telegram and Human Governance

Objectives:

- Implement Telegram interaction.
- Implement daily brief workflow.
- Implement daily learning reports.
- Implement approval and rejection.
- Record governance history.

Exit criteria:

- User can interact with Cognis through Telegram.
- Approval controls work correctly.
- Unauthorized changes are blocked.
- Scheduled workflows can recover from failures.

Phase 6: Reliability and Controlled Evolution

Objectives:

- Improve performance and operational reliability.
- Expand independent benchmarks.
- Test rollback procedures.
- Evaluate model alternatives.
- Prepare future fine-tuning capabilities.

Exit criteria:

- Core workflows pass defined tests.
- Benchmark results are reproducible.
- Approved changes are verifiable.
- Regression and recovery procedures work.

14. Key Product Constraints

The project must account for:

- Limited initial infrastructure.
- API cost constraints.
- Rate limits and provider availability.
- Long-running research workloads.
- Limited compute resources.
- Data provenance requirements.
- Security and authorization.
- Human review capacity.

Architecture choices must reflect these constraints rather than assume unlimited compute, budget, or API access.

15. Open Decisions

The following decisions must be evaluated and documented before their implementation becomes permanent:

1. Final database technology.
2. Final AI provider strategy.
3. Research and search provider selection.
4. Vector search requirements and implementation.
5. Background job infrastructure.
6. Authentication and user authorization model.
7. Hosting and deployment architecture.
8. Data retention and backup policies.
9. Future fine-tuning strategy.
10. Long-term multi-user product model.

Do not silently convert these open decisions into permanent architectural commitments.

16. Definition of MVP Completion

The Cognis MVP is considered functionally complete when:

- A user can submit a research request through Telegram.
- Cognis can conduct a research workflow using an integrated model.
- Research results contain traceable sources.
- Results can be stored and retrieved.
- ALS can execute a defined learning cycle.
- Competency evaluations can be recorded.
- ALS can generate improvement proposals.
- The user can approve or reject proposals.
- Permanent changes are blocked without authorization.
- Long-running tasks can recover from failures.
- Relevant tests and security checks pass.
- Operational limitations are documented.

A working chatbot alone does not qualify as a completed Cognis MVP.

---

End of Document