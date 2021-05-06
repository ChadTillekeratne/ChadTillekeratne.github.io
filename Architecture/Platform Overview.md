## Purpose
Creating and operating a service has similiar requirements, functions, and capabilities no matter the industry or implementation.  The table below is meant to summarize those functions.  

The table is not ground-breaking, nor authorative for all functions, rather a starting point for understanding the composition of a service and operations. I've found this exercise value for:
- **New Employee Onboarding** - Joining a group can be intimidating, you go from knowing your past group to jumping into a new area.  It can be hard to see the forest from the trees.  This table is meant to be the top of the funnel that allows individuals to dive deeper.
- **Setting a North Star** - Technology is always evolving, as services mature and grow, it's important to understand where we are today and where we want to be in the future.  Adding additional columns to understand the areas for change can be helpful to understand where we're going.

It is okay to not have a story for each functionality/capability, however it is important for the team to have a consistent understanding.

## OKR
_What is successful?  How do we measure success?_

Objectives Key Results is a goal setting framework to help understand our desired outcome and how we will measure our success to achieving.

References:
  - https://www.whatmatters.com/get-started/

|Area|Objective|Key Results|Notes
|--|--|--|--|
|Development
||Developer Fungability - Developers are able to work on any project |
||Developer an deploy a change to development environment in less than 1 hour
||Development Velocity - Developers have a known and rapid process to get a feature into master
||Release Velocity - Developers are able to rapidly and safely get changes in production
|||Master to Production in less than 5 business days
|Livesite|
||Service availability excedes customer SLAs|
|||Scenario Reliability
|Quality
||Services are secure

## Service Functionality Table
|Category|Area|Sub Sub-Area|Sample|Description
|--|--|--|--|--|
|Documentation|
||Repository||GitHub Enterprise, Azure DevOps
||Service Catalog|||List of Services with metadata
||Service Architecture, Components, Flows
||Standards, Processes, Procedures
||Acronym Glossary
|Project / Work Management
||Tasks/Bugs/etc. ||Jira, Azure DevOps, Trello, Monday
||Roadmap / Gantt Views|
||Brainstorm
|Architecture
||Architecture Process Standards||TOGAF
||API Guidelines
||Architecture Design Documentaton
||Architecture Approval
|Compliance Requirements|
||Security Requirements|
||Privacy Requirements|
||Process Requirements||ISO 9001
||Business Continuity and Data Recovery
||SLA
||OLAs/Dependency SLAs
|User-to-Service
||Customer Allowlist to Service||Published CIDR Range, Published DNS Host names
||Service Discovery||DNS
||Protocol||HTTPS
||Traffic Management, Delivery, Load-Balancing|CDN
|||Gateway|
||DDoS Protection|Layer 4
||| Layer 7
||Rate Limitting and Throttling| Per Client IP
|||Per Tenant
|||Per Functionality
||Authentication||OAUTH (Google, Twitter)
||Authorization||JWT Claims
||Service Code Framework|Service Code|C# .NET 5.0
|Experimentation
||Segmentation
||//TODO:
|Livesite and Operations|||
||Observability
|||Telemetry Library
|||Distributed Tracing
|||Events
|||Metrics
|||Metrics - Long Term Retention
|||Dashboards||Grafana, Azure Dashboard
|||Reliability Reporting
||Monitoring and Alerting|Tool
||Troubleshooting and Debugging|Process Memory Dump (on-demand)
|||Process Crash Dump
|||Live Debugging
|||Profiling (system aggregate)
|||Profiling (per request)
|Build and Release |||
||Build|System
|||Code Sign
|||Integrity Validation (Vulnerbility Scan)
|||Release Drop||
||Deployment|System|ADO Pipeline to ARM
|||Rings||Dogfood, Canary Deployment, etc.
|||Rollback
||Change Freeze||Calendar of freeze windows and/or how this is technically implemented
||Feature Release|Feature Flags|
|Configuration Management
||Service Library/Patterns
||Application String
|Secret Management|Certificates - Storage
||Certificates|Usage Reference|
|||Generation|
|||Inventory|
|||Update / Rotation|
|||Expiration Monitoring
||Keys/Strings|Storage
|||Usage Reference|
|||Generation|
|||Inventory|
|||Update / Rotation|
|||Expiration Monitoring
|Data Tiers|||
||Persistant Storage System|
||Backup
||Restoration/Recovery Plan
|Platform / Infrastructure|||
||Isolation and Secure Access|||Management networks, secure workstations, etc.
||Identity
|||Authentication
|||Authorization
|||Just-in-Time Access (JIT)
||Operating System||CentOS 8
|||OS Patching
|||OS Configuration Management
||Compute Hosting Platform||Kubernetes (Azure Kubernetes Services)
||Remote Management Access|System (RDP/SSH)
||Component Patching (Dependencies)
||Antivirus/Malware
||Vunerbility Monitoring
||Integrity Monitoring, Operations Audit
||Integrity Remediation
|Code Quality|||
||Unit Testing
||Fuzz Testing
||Vulnerbility Testing
||Chaos, Fault, and Resiliency Testing||
|Performance Testing|
||Scale Targets|||
|||Peak Demand
|||Scaling Pattern
||Load Testing|||Gradual step up traffic
||Performance Testing|||
||Stress Testing|||Purposefully overload
|Cost Management (CoGs)
||Reporting
||Alerting
|Security Governance and Operations
||Security Incident Management
||Penetration Testing
||Risks/Exceptions Register|||Protected list of all known exceptions for not meeting a requirement
|Source Code
||Repository|
|||Tool|GitHub, Azure DevOps
|||Repository Strategy|Monorepo, Repo per service
|||Branching Strategy|main/master branch, release branches, release tags
|||Dependency Management (shared libraries/components)
||Local Build and Run
||Calling downstream dependencies
||Upstream service invocation
|Service-to-Service
||Protocol||HTTP, gRPC
||Service Discovery||DNS
||Authentication||Client Cert, OAUTH
||Authorization
||Resiliency (retries, circuit breaker, etc.)||Polly
|Environments
||//TODO: Local Development Machine, Dev, PPE, Prod
|Incident Management
||Tooling||Service Now, Pager Duty
|||Paging
||Troubleshooting Guides 
||Automated Remediation Responses
||Customer Outage Reporting
|||Dashboard
|||Pro-active Alerts (SMS, Email, etc.)
||On-Call Rotation
||Customer Support|Ticket System|Zen Desk|
|||Social Analysis||For a public service, analyzing social media sentiment can be helpful to understand issues that monitoring might have missed (or upstream dependencies)
||Customer Forums

## Processes
- Incident Management
  - Privacy Incident Management
  - Security Incident Management
- Documentation Management
- Security Operations

## KPIs
|Category|Metric|Target|Calculation|Notes
|--|--|--|--|--|
|Livesite||
||SLA Compliance|99.9%|
||Reliability|99.9%
||Response Time|{Dependent on API}
||Call Rate|Vanity
|Incident Management
||MTTN (time to notification)
||MTTE (time to engagement)
||time to status update
||MTBF (time between failures)

## Software Development Lifecycle (SDLC)

Process is an art and a science.  A _good_ process allows for a well-known and quality output.  A _bad_ process adds to un-needed work adding time, complexity, and killing morale. The balance between a _good_ and _bad_ process is a continual improvement for all stakeholders.

All stakeholders shall understand _what_ their role is to deliver a service.  This is not to say that a stakeholder can't do more, but is the based understanding.  To help set the expectations, we will use the roles: RACI (responsible, accountable, consulted, informed)

### Strategy for Process
- Compliance - Internal and external compliance requirements may dictate some steps the must be completed. Understand the _why_ for each step.
- Automate - Do steps require a human? Can they be automated?
- Fungability - A process step shall rely on roles, not key individuals.

### Process Overview
- Plan
  - PM Spec
    - Functional/non-function requirements
    - Scope / out-of-scope
    - KPIs
    - Scale Requirements
    - ...
- Design
  - Architecture Design Document
    - Component Architecture
    - Build-To Scale
  - Technical Spec
    - API Contracts
    - Observability
      - Metrics, Logs, Audit, Alerting
  - Design Reviews
    - Security
    - Privacy
    - Technical Design (reliability, performance)
- Develop
  - Code Review
  - Security Testing (Automated)
    - Vulnerbility
    - Fuzz Testing
  - Performance Testing
    - Scale Metrics
  - ...
- Release
  - Security Review
  - Privacy Review
- Operate
  - Observability/Monitoring
  - Troubleshooting Guides
  - Incident Review
- Decomission
