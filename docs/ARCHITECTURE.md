# Campus Agent Hub node graphs

## Request routing

The bounded router validates a request, applies the Lab 14 manipulation detector, selects a registered handler, and records the result. The handlers cover study, events, research, memory, helpdesk, operations, maintenance, and release. The Python registry is the executable routing contract.

```mermaid
flowchart TD
  A[Request intake] --> B{Valid request}
  B -->|No| X[Rejection response]
  B -->|Yes| C{Manipulation detected}
  C -->|Yes| X
  C -->|No| D[Registered specialist]
  D --> E[Tools and reusable skills]
  E --> F[Domain controls]
  F --> G[Response and audit]
  X --> G
```

## Release control graph

The graph permits exactly one builder retry. Security failure stops downstream testing. Story tests are derived independently from acceptance criteria. The factory's release artifact is a local simulation; production authorization is represented separately by the governance proposal and is never automatically executed.

```mermaid
flowchart TD
  A[Requirements and plan] --> B[Build attempt]
  B --> C{Build passed}
  C -->|No| D{Retry available}
  D -->|Yes| B
  D -->|No| H[Human escalation]
  C -->|Yes| E{Security scan passed}
  E -->|No| H
  E -->|Yes| F[Tests and review]
  F --> G{Tests passed}
  G -->|No| H
  G -->|Yes| I{Cost and evaluation valid}
  I -->|No| J[Reject proposal]
  I -->|Yes| K[Await human approval]
```

Each graph node in Lab 7 declares its owner, success criterion, and failure behavior. The inserted security node also has a separate input/output contract. See `labs/lab_07/combined.py` and `project/integrated_project.py` for the runnable definitions.
