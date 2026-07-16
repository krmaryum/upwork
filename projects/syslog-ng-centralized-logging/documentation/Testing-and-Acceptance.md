# Testing and Acceptance Plan

## 1. Purpose

This document defines objective tests for the project deliverables. Final source names, ports, paths, thresholds, and expected results must be approved by the client.

## 2. Test Matrix

| ID | Test | Expected result | Evidence | Status |
|---|---|---|---|---|
| T01 | Validate syslog-ng syntax | No syntax errors | Command output | Not Started |
| T02 | Check service after start/restart | Service active | Service status | Not Started |
| T03 | Check approved TCP listeners | Correct ports listening | `ss` output | Not Started |
| T04 | Check approved UDP listeners | Correct ports listening | `ss` output | Not Started |
| T05 | Send UDP test message | Message stored in correct source/port path | Sanitized log evidence | Not Started |
| T06 | Send TCP test message | Message stored in correct source/port path | Sanitized log evidence | Not Started |
| T07 | Send from second source | Separate source directory created | Directory evidence | Not Started |
| T08 | Send one source to two ports | Separate port paths used | Directory evidence | Not Started |
| T09 | Validate permissions | Approved account access only | Permission output | Not Started |
| T10 | Force test rotation | Active log replaced safely | Rotation evidence | Not Started |
| T11 | Validate compression | Rotated file compressed and readable | Archive evidence | Not Started |
| T12 | Validate retention on test data | Only approved expired test files selected/deleted | Retention evidence | Not Started |
| T13 | Check activity history | Source, port, protocol, and time correct | Query/report | Not Started |
| T14 | Check dashboard | Flow and status panels update | Dashboard evidence | Not Started |
| T15 | Stop test source | Inactivity state/alert appears at threshold | Alert evidence | Not Started |
| T16 | Check disk alert | Warning triggers at test threshold | Alert evidence | Not Started |
| T17 | Validate restart persistence | Service and listeners return | Status evidence | Not Started |
| T18 | Review documentation | Runbook matches final system | Client review | Not Started |

## 3. Acceptance Criteria

The project is complete when:

- Syslog-ng is active and enabled according to the approved design.
- Every approved port is listening on the correct protocol/interface.
- Test messages arrive from every agreed source type.
- Logs are stored by approved port, source, and date structure.
- Rotation and compression work without interrupting collection.
- Retention removes only approved expired data.
- Last-received activity is accurate.
- Dashboard panels show source and port flow.
- Silent-source and disk alerts work.
- Security and permissions meet the approved design.
- Final configuration, runbook, troubleshooting guide, and handover are delivered.

## 4. Defect Handling

| Severity | Meaning | Required action |
|---|---|---|
| Critical | Collection unavailable or unsafe deletion/security issue | Stop acceptance and correct immediately |
| High | Major deliverable does not work | Correct before milestone approval |
| Medium | Partial issue with an available workaround | Record and agree correction date |
| Low | Cosmetic/documentation improvement | Correct before final handover when agreed |

## 5. Sign-off

| Role | Name | Decision | Date |
|---|---|---|---|
| Consultant | Muhammad Khalid Khan | Pending |  |
| Client technical owner |  | Pending |  |
| Client project owner |  | Pending |  |

