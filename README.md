# architecture-docs

## Summary

This repository contains unofficial documentation of the Rucio architecture.
Its primary goal is to provide a minimal and focused understanding of the system (building blocks, communication between components and systems, relevant cross-cutting concepts, etc.). It is intended as a lightweight reference to support personal comprehension and quick lookup, rather than as a comprehensive or authoritative source.

## References

- [What is Rucio?](https://rucio.github.io/documentation/started/what_is_rucio)
- [Rucio daemons](https://rucio.github.io/documentation/started/main_components/daemons)
- [Rucio Project Structure](https://rucio.github.io/documentation/developer/project_structure)
- [arc42 overview](https://arc42.org/overview)

## arc42 chapters

TODO(mgajek-cern): Eventually setup Jekyll based project or use other static site generator tool 

### 1. Introduction and Goals

See [What is Rucio?](https://rucio.github.io/documentation/started/what_is_rucio)

### 2. Constraints

[Overview of constraints influencing the architecture can be found here](./2-constraints/architecture-constraints.md)

### 3. Context & Scope

![Context View](./diagrams/Context%20View.png)

| Name | Type | Description |
| --- | --- | --- |
| Rucio | Internal System | Scientific data management framework providing declarative policy-based data organization, transfer, and lifecycle management across distributed heterogeneous storage infrastructure |
| Workflow Management Systems | External System | Job and task orchestration platforms that coordinate with Rucio for data availability, requesting datasets at specific locations and registering job outputs for lifecycle management |
| Authentication Systems | External System | Identity and access management services providing user authentication and authorization through various protocols and credential mechanisms |
| Storage Systems | External System | Heterogeneous storage backends including traditional filesystems, object storage, tape archives, and cloud storage accessed through standardized protocols |
| Monitoring Systems | External System | Analytics and observability platforms that collect, process, and visualize system performance metrics, usage statistics, and operational health data |
| Logging Systems | External System | Centralized logging infrastructure that aggregates, stores, and provides search capabilities for system events, audit trails, and troubleshooting information |
| Database Systems | External System | Transactional relational database management systems that serve as the persistence layer for catalog metadata, system state, and configuration data |
| Transfer Systems | External System | Data movement services and protocols that handle the physical transfer of files between storage endpoints with reliability, scheduling, and error handling capabilities |

---

[Stakeholder details are provided here](./3-scope-and-context/stakeholders.md)

### 4. Solution strategy

TODO(mgajek-cern): Add links if existing

### 5. Building Block views

#### Lvl 1

![Building Block Lvl 1 View](./diagrams/Building%20Block%20Lvl%201%20View.png)

**Workflow Pattern:**

1. *User/Client* → *REST API*: "Create replication rule: 3 copies on different continents"
2. *REST API* → *Database*: Records the rule as a database entry
3. *Daemons* → *Database*: Query for pending rules/tasks
4. *Daemons* → *Storage/Transfer systems*: Execute the actual data operations
5. *Daemons* → *Database*: Update completion status

#### Lvl 2

![Building Block Lvl 2 View](./diagrams/Building%20Block%20Lvl%202%20View.png)

See also: [Rucio Project Structure](https://rucio.github.io/documentation/developer/project_structure)

### 6. Runtime view

TODO(mgajek-cern): Add links if existing

### 7. Deployment view

TODO(mgajek-cern): Add links if existing

### 8. Crosscutting concepts

Refer to [Accounting and quota](https://rucio.github.io/documentation/started/concepts/accounting_and_quota) and subsequent sections.

### 9. Architectural decisions

TODO(mgajek-cern): Dedicated folder with .md content and add links if existing

### 10. Quality requirements

[Overview of quality requirements can be found here](./10-quality-requirements/quality-requirements.md)

### 11. Risks & technical debt

TODO(mgajek-cern): Add links if existing

### 12. Glossary

TODO(mgajek-cern): Add links if existing

