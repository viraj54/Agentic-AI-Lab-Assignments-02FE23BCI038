# Campus Agent Hub Course Project Report

Agentic AI Systems Lab Assignments

SRN 02FE23BCI038
Prepared 15 November 2026

## Project overview

Campus Agent Hub is an offline agentic application that routes campus requests to study planning, event analysis, research summaries, project memory, help-desk triage, operations diagnosis, engineering monitoring, and release review. It integrates the combined implementations from all fourteen labs in the supplied guide.

The completed package includes all 28 assignment solutions, a combined version for every lab, full source-and-output records, and the final integrated application. All 57 program runs completed successfully. The independent requirement suite passed 25 checks, and the integrated project passed 19 evaluation cases.

### Submission identity

Requested repository URL
https://github.com/02FE23BCI038/Agentic-AI-Lab-Assignments

This is the intended repository address. The owner portion of a GitHub URL is the actual account or organization username. The prepared archive does not establish that this remote repository exists or that files have been uploaded.

### Implementation scope

The application uses rule-based classroom agents and Python standard-library tools. No external LLM, cloud cluster, identity service, email service, or production endpoint is contacted. Teaching fixtures and simulated approvals are identified throughout the source and records.

## Architecture and agent workflow

CampusAgentHub receives a structured request, validates it, applies the adversarial-input control, and selects a handler from a fixed registry. Each accepted request executes one bounded handler call and records a response with its route and request ID. Specialist handlers compose the actual combined lab implementations.

| Stage | Responsibility and observable result |
|---|---|
| Intake | Check user identity field, payload structure, and instruction manipulation before invoking tools. |
| Route | Select one of eight handlers from the request kind. Unknown kinds are rejected. |
| Act and observe | Run tools and reusable skills; inspect returned data and preserve tool traces. |
| Review | Apply domain safety, node-graph, test, budget, or approval controls as appropriate. |
| Remember | Maintain topic-scoped project memory, help-desk history, and per-user runtime state. |
| Respond and record | Return structured output; export prompt logs, execution traces, audits, and evaluations. |

### Tools and reusable skills

The program uses more than three tools: FAQ search, ticket creation, ticket status lookup, CSV reading, category filtering, calculation, notification drafting, capability discovery, database queries, and sensor classification. Reusable skills include help-desk triage, password-reset guidance, research summarization, and runtime note summarization.

### Memory and context

Lab 4 provides exact-topic long-term project memory with a writer permission boundary and staleness warnings. Lab 6 scopes runtime memory and admission counts per user. Lab 14 records session and ticket history. These stores live in process; exported JSON is execution evidence and is not automatically reloaded as persistent memory.

### Node graph

Request intake branches to the selected specialist and returns to response logging. The release specialist follows requirement, planner, builder, security scan, tester, reviewer, and simulated human-gate nodes. Builder execution permits one retry. A failed scan or failed tests block the release path; production approval remains a separate governance requirement.

## Integration of Labs 1 through 7

| Lab | Assignment implementation | Contribution to the project |
|---|---|---|
| 01 | Two feedback rounds; explicit detection of Wednesday and Friday conflicts. | Study handler revises one plan object and reports conflicts before finalization. |
| 02 | Low-turnout notification draft; CSV to category filter to average chain. | Events handler computes a technical-event average of 7 and drafts a notice. |
| 03 | Evidence-supported selection between claims; unsupported article handling. | Research handler returns an accuracy claim and marks missing evidence without fabrication. |
| 04 | Database and hosting isolation; 30-day retention warning. | Memory handler retrieves exactly one topic and warns for a 60-day-old decision. |
| 05 | Manifest-discovered list_files; safe mock path boundary. | Events handler discovers resources and reads signups through the connector. |
| 06 | Three tasks per user session; escalation after two same-skill errors. | Research uses a registered skill; the final demo exercises rate and failure controls. |
| 07 | Security scan between builder and tester; one builder retry. | Release handler stops on a scan failure and escalates after two build failures. |

### Standalone assignment variants

Each lab contains reference.py, assignment_1.py, assignment_2.py, and combined.py. The assignment scripts retain the original definitions and add the requested extension. A1 and A2 enable the relevant behavior; both are enabled in the combined script. Each program can be executed directly without importing a sibling file.

### Records and evidence

The README in each numbered lab folder embeds all four full programs and their captured outputs. Individual output text files support quick inspection. The ordered master record places Labs 1 through 14 first and appends the final integrated project source and complete output at the end.

## Integration of Labs 8 through 14

| Lab | Assignment implementation | Contribution to the project |
|---|---|---|
| 08 | Fifth marketing role; distributed role-attributed critique. | Events handler executes roles concurrently and resolves spending within one budget cap. |
| 09 | S4 contradiction; disclosed source-quality weighting. | Research handler retains conflicting evidence and identifies the synthesis preference. |
| 10 | Pool-exhaustion scenario; safe warning remediation. | Operations handler diagnoses a down-level pool incident and simulates a local pod restart. |
| 11 | Second story and distinct lineage; deliberate inverted-filter bug. | Release handler processes two stories side by side and blocks the mutant through independent tests. |
| 12 | Fail-closed cost controls; re-evaluation after five proposals. | Release proposals require valid cost and approval; sixth proposal is blocked until evaluation. |
| 13 | Electrical load forecasting; three-warning mechanical trend. | Maintenance handler gates ALARM recommendations and escalates persistent warnings to inspection. |
| 14 | Password guidance skill; expanded adversarial evaluation. | Help-desk handler routes between skills and rejects empty or manipulating requests. |

### Implementation choices

Lab 11 uses a second CSV-export story. The assignment offers PDF as an example rather than a mandatory format; the second story is independently attributed through design, code, tests, review, documentation, and release lineage. The integrated project processes the two story pipelines in a thread pool.

The standalone Lab 9 quality assignment includes S4 so conflicting claims can be weighted even without running Assignment 1. The sources and numerical findings are synthetic teaching records. The comparison treats methodological differences as plausible explanations, not proven causes.

The Lab 13 extension makes a single mechanical warning a monitoring recommendation and three increasing warnings an inspection recommendation. This makes the requested trend escalation visible; ALARM readings continue to require human review.

## Demonstration and observed behavior

The project demonstration exercises every specialist handler and exports structured responses. The original and extended lab captures provide more detailed traces for each assignment, including expected rejection paths.

| Request or scenario | Observed result |
|---|---|
| Study plan | Tuesday changes to 20:00–22:00; Friday becomes 20:00–21:00. The plan object is preserved. |
| Technical event signups | Validated filtered counts produce an average of 7; the notification remains an unsent draft. |
| Event swarm | Distinct roles object to spending. A campus room at 15000 plus marketing at 5000 fits the 30000 cap. |
| Research summary | The evidence-supported accuracy claim is selected; absent evidence remains not stated in source. |
| Scoped memory | Database answer contains PostgreSQL only; hosting answer warns of the 60-day-old decision. |
| Help desk | Wi-Fi uses FAQ triage; forgotten password uses guidance; unknown issues create a local ticket. |
| Operations | Pool exhaustion is classified as down. Rollback is proposed for approval; a warning restart affects a mock pod only. |
| Maintenance | Electrical ALARM requests human review; three rising mechanical warnings recommend inspection. |
| Release | One builder retry succeeds. Passing stories produce a governed proposal that still awaits human approval. |

### Runtime and governance demonstrations

A fourth runtime task is rejected after three admitted tasks for one user. Two failed contact lookups are recorded; the third same-skill attempt escalates rather than running again. A distinct user retains a separate allowance.

Missing or invalid costs are rejected. Over-budget proposals need a separate finance approval flag. Five valid proposals are accepted for review after evaluation; the sixth is blocked. A new evaluation reopens the proposal gate. None of these demonstrations writes to production.

## Evaluation and verification results

| Verification layer | Observed result | Evidence file |
|---|---|---|
| Programs | 57 of 57 successful exits | execution_results.json |
| Requirement checks | 25 of 25 passing tests | tests/test_output.txt |
| Integrated evaluation | 19 of 19 passing cases | project/outputs/evaluation.json |

Program execution success is distinct from behavioral verification. The requirement suite tests boundaries and expected outcomes independently, while the integrated evaluation checks routed end-to-end results. All outputs were captured from actual execution with Python 3.12.14.

### Integrated evaluation coverage

| Cases | Expected behavior verified |
|---|---|
| FAQ and password routing | Correct skill resolution for both supported issue types. |
| Unknown and empty issues | Create a ticket for an unknown valid issue; reject empty text. |
| Instruction manipulation and unknown route | Reject both before specialist execution. |
| Study and event requests | Preserve plan identity and return the expected filtered average and draft. |
| Research and two memory topics | Mark missing evidence, disclose conflict, preserve scope, and warn for old memory. |
| Pool incident and warning restart | Different severity and bounded low-risk simulation; rollback remains gated. |
| Maintenance | Electrical ALARM never automatically executes the recommended action. |
| Security and mutation checks | Security failure and independently detected filter bug block release. |
| Missing cost, over-budget cost, valid proposal | Reject invalid proposals; valid proposal still awaits human approval. |

### Deliberate failure evidence

Lab 11 intentionally inverts a filter in the coding agent without changing the instructor testing agent. Failing feature-test lines are expected in that mutant run. The demonstration passes because those failures correctly prevent release; the normal implementation passes the same tests.

## Safety controls and practical limits

The implemented controls include least-privilege mock connectors, exact-topic retrieval, validated nonempty tool subsets, per-user admission limits, audit-based escalation, bounded builder retries, a security node, independent tests, cost validation, periodic evaluation, and human-review requirements for production changes and ALARM recommendations.

### Limitations

Language understanding is deterministic and rule-based. Keyword matching can miss paraphrases; the adversarial detector recognizes selected patterns rather than providing a comprehensive injection defense. Research extraction uses a small lexical heuristic. These choices make the architecture inspectable but do not establish production-grade accuracy.

The campus datasets, research sources, incidents, deployments, financial approvals, sensor logs, and human checkpoints are simulated. The two event sources are separate fixtures and are not joined as one authoritative dataset. Engineering thresholds and linear load forecasts are illustrative and are not certified safety assessments.

Project topics share one classroom memory namespace, while runtime state is per user. Real multi-tenant use needs authentication, authorization, secret redaction, durable tenant-scoped storage, and concurrency-safe ticket IDs. JSON output is exported evidence. It does not make in-memory state persistent across restarts.

### Next steps

First, introduce durable authenticated storage and typed input validation across tools. Next, replace the mock connector and keyword FAQ lookup with audited integrations and source-grounded retrieval. Then expand held-out evaluations, injection tests, data-quality checks, and engineering validation before considering any real deployment.

## Reproduction and submission

Extract the archive, open a terminal at the repository root, and run python run_all.py followed by python -m unittest discover -s tests -v. No third-party packages or API keys are required. Run python tools/update_records.py to refresh embedded code-and-output records after rerunning.

Upload the extracted repository contents to Agentic-AI-Lab-Assignments. A detailed browser and Git workflow is supplied in docs/GITHUB_UPLOAD.md. Review docs/ASSIGNMENT_MAP.md for direct links to all 28 solutions and outputs, and docs/ALL_LABS_AND_PROJECT.md for the complete ordered submission.

Source attribution: original reference programs and assignment wording come from the user-supplied Agentic_AI_Lab_Guide.docx, retained under docs/reference. Assignment extensions, project orchestration, verification, and submission records are added in this package.
