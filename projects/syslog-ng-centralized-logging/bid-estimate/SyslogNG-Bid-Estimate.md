# Syslog-ng Project Bid Estimate

## 1. Bid Summary

This estimate covers a production-standard implementation on one RHEL server with up to 25 log sources, up to five approved listening ports, local structured storage, retention automation, source-activity tracking, a graphical dashboard, testing, and documentation.

## 2. Example Work Estimate

| Phase | Work | Hours |
|---|---|---:|
| 1 | Discovery and solution design | 8 |
| 2 | RHEL and syslog-ng installation | 8 |
| 3 | Listeners and routing | 12 |
| 4 | Local storage structure | 8 |
| 5 | Rotation, compression, and cleanup | 8 |
| 6 | Activity-history database | 12 |
| 7 | Graphical monitoring and alerts | 12 |
| 8 | Testing and tuning | 6 |
| 9 | Documentation and handover | 6 |
| **Total** |  | **80** |

## 3. Example Price Calculation

```text
Estimated hours:    80
Example hourly rate: $40
Base labor:          $3,200
Contingency at 10%:  $320
Calculated estimate: $3,520
Rounded bid:         $3,550
```

The hourly rate, hours, and contingency must be edited based on the confirmed client environment and freelancer profile.

## 4. Proposed Milestones

| Milestone | Deliverable | Hours | Acceptance evidence |
|---|---|---:|---|
| M1 | Discovery and approved design | 8 | Design and implementation plan |
| M2 | Installation, listeners, routing, and storage | 28 | Service validation and received test logs |
| M3 | Rotation, retention, and activity history | 20 | Archive test and activity records |
| M4 | Dashboard, alerts, and system testing | 18 | Dashboard and test report |
| M5 | Documentation and handover | 6 | Runbook and knowledge transfer |

## 5. Assumptions

- One supported RHEL server
- Up to 25 log sources
- Up to five listeners
- Client-provided administrative access
- Storage provisioned before implementation
- Approved monitoring and database platforms available
- No high-availability cluster
- No historical log migration
- One handover session

## 6. Possible Exclusions

- Infrastructure or license purchasing
- High availability and disaster recovery
- Custom parsing of proprietary formats
- Changes to every source device
- Historical data migration
- Unspecified SIEM integration
- Ongoing support after final acceptance

## 7. Questions Required Before Final Price

1. Which RHEL version is installed?
2. How many sources will send logs?
3. Which ports and protocols are required?
4. What is the expected daily volume or events per second?
5. What are the active and archive retention periods?
6. Is TCP/TLS required?
7. Which dashboard platform must be used?
8. When should a source be marked inactive?
9. Is high availability required?
10. What documentation and training are expected?

## 8. Proposal Template

> Hello,
>
> I can implement a centralized syslog-ng solution on your Red Hat server that receives logs on the required TCP/UDP ports, separates them by source and listener, applies automated compression and retention, and provides graphical source-activity monitoring.
>
> I propose completing the work in controlled phases: discovery and design, installation, listener and storage configuration, archive lifecycle automation, activity tracking, dashboard implementation, testing, and documentation.
>
> Before finalizing the scope, please confirm the RHEL version, number of sources, ports/protocols, expected log volume, retention period, and preferred monitoring platform.
>
> Regards,  
> Muhammad Khalid Khan

## 9. Important Note

The accompanying Excel workbook is the editable source for the bid calculation. Adjust its highlighted input cells before submitting a price.

