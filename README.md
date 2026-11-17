# Agentic AI Lab Assignments

**SRN: 02FE23BCI038**  

This repository contains all 14 labs and 28 assignments from the supplied **Agentic AI Systems Lab Guide**, separate solutions for both assignments in each lab, combined solutions, actual console outputs.

## Start here

- [Complete ordered record with every lab's full source and output, followed by the final integrated project](docs/ALL_LABS_AND_PROJECT.md)
- [Assignment requirement map with direct code and output links](docs/ASSIGNMENT_MAP.md)
- [Node graphs and architecture](docs/ARCHITECTURE.md)
- [Course project report in Word](docs/Course_Project_Report.docx)
- [Course project report in Markdown](docs/Course_Project_Report.md)
- [Final integrated project source and complete output](project/PROJECT_COMPLETE.md)
- [GitHub upload instructions](docs/GITHUB_UPLOAD.md)

## Run everything

Use **Python 3.10 or newer**. No pip packages, paid services, API keys, or network access are required.

```bash
python run_all.py
python -m unittest discover -s tests -v
```

Delivered verification: **57/57 program runs**, **25/25 independent requirement tests**, and **19/19 integrated project evaluation cases** passed. Captures were produced with Python 3.12.14. Dates and timestamps in logs may change on rerun. Expected failing feature tests in the Lab 11 deliberate-bug demonstration confirm that the test gate catches the mutation.

To rebuild the readable full-code records after rerunning or editing code:

```bash
python tools/update_records.py
```

To run a single lab or the project:

```bash
python labs/lab_01/reference.py
python labs/lab_01/assignment_1.py
python labs/lab_01/assignment_2.py
python labs/lab_01/combined.py
python project/integrated_project.py
```

## Lab order

| Lab | Topic | Full code and captured outputs |
|---|---|---|
| 01 | Agent vs Chatbot | [Study planner](labs/lab_01/README.md) |
| 02 | Tool-Using Agent | [Campus data assistant](labs/lab_02/README.md) |
| 03 | Skill Creation | [Research summary](labs/lab_03/README.md) |
| 04 | Memory and Retrieval | [Scoped project memory](labs/lab_04/README.md) |
| 05 | MCP-Style Connector | [Capability discovery and boundaries](labs/lab_05/README.md) |
| 06 | OpenCLA and OpenClaw Runtime | [Skills and session controls](labs/lab_06/README.md) |
| 07 | Agentic Node Graph | [Security scan and builder retries](labs/lab_07/README.md) |
| 08 | Parallel Swarm | [Marketing and distributed critique](labs/lab_08/README.md) |
| 09 | Deep Research Agent | [Conflicts and evidence quality](labs/lab_09/README.md) |
| 10 | Cloud Operations Agent | [Incident diagnosis and risk gates](labs/lab_10/README.md) |
| 11 | Agentic SDLC Factory | [Story lineage and mutation detection](labs/lab_11/README.md) |
| 12 | Safety Evaluation and Governance | [Cost controls and re-evaluation](labs/lab_12/README.md) |
| 13 | Engineering Agents | [Electrical and mechanical agents](labs/lab_13/README.md) |
| 14 | Capstone Project Studio | [Skill routing and adversarial tests](labs/lab_14/README.md) |

Every `labs/lab_XX` folder contains `reference.py`, `assignment_1.py`, `assignment_2.py`, `combined.py`, four corresponding files in `outputs/`, and a README embedding all four full programs and outputs in that order.

The project folder contains the final orchestration program, its complete source-and-output record, and machine-readable responses, prompt logs, execution traces, evaluation results, runtime audits, and governance audits. The `.github/workflows/verify.yml` file reruns programs and tests after a GitHub push.

## Scope and attribution

The supplied guide is retained at [docs/reference/Agentic_AI_Lab_Guide.docx](docs/reference/Agentic_AI_Lab_Guide.docx). Original reference programs were extracted from it without edits. Assignment extensions and the final integration are added separately. The report describes the implementation and observed test results; it does not claim a real deployment.

All source records, event data, research findings, engineering readings, approvals, deployments, and external services are classroom simulations. Drafts are never sent. Research figures in Lab 9 are synthetic fixtures, not verified publications. Memory is in-process; JSON outputs are exported evidence rather than a live database. The engineering thresholds are illustrative.

The requested URL works only when the GitHub account or organization owner is `02FE23BCI038`. The ZIP is prepared for upload; it does not create the remote repository.
