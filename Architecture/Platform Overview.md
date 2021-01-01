## Purpose
Creating and operating a service has similiar requirements, functions, and capabilities no matter the industry or implementation.  The table below is meant to summarize those functions.  

The table is not ground-breaking, nor authorative for all functions, rather a starting point for understanding the composition of a service and operations. I've found this exercise value for:
- **New Employee Onboarding** - Joining a group can be intimidating, you go from knowing your past group to jumping into a new area.  It can be hard to see the forest from the trees.  This table is meant to be the top of the funnel that allows individuals to dive deeper.
- **Setting a North Star** - Technology is always evolving, as services mature and grow, it's important to understand where we are today and where we want to be in the future.  Adding additional columns to understand the areas for change can be helpful to understand where we're going.

## Service Functionality Table
|Category|Area|Sub Sub-Area|Sample|Description
|--|--|--|--|--|
|Documentation|
||Repository|
||Service Catalog
|Compliance Requirements|
||Security Requirements|
||Privacy Requirements|
||Process Requirements||ISO 9001
||Business Continuity and Data Recovery
||SLA
||OLAs/Dependency SLAs
|User to Service
||Service Discovery||DNS
||Protocol||HTTPS
||Traffic Management, Delivery, Load-Balancing|CDN
|||Gateway|
||DDoS Protection|Layer 4
||| Layer 7
||Rate Limitting and Throttling| Per Client IP
|||Per Tenant
||Authentication||OAUTH (Google, Twitter)
||Authorization||JWT Claims
||Service Code Framework|Service Code|C# .NET 5.0
|Experimentation
||Segmentation
||//TODO:
|Configuration 
||Application 
|Livesite and Operations|||
||Service Telemetry|Telemetry Library
|||Distributed Tracing
|||Telemetry Services - Events
|||Telemetry Services - Metrics
|||Dashboards
|||Reliability Reporting
||Monitoring and Alerting|Tool
||Troubleshooting and Debugging|Process Memory Dump (on-demand)
|||Process Crash Dump
|||Live Debugging
|||Profiling (system aggregate)
|||Profiling (per request)
|Build and Release |||
||Build|System
|||Release Drop
|||Deployment|System
|||Rollback
|||Change Freeze||Calendar of freeze windows and/or how this is technically implemented
|Environments|
||//TODO:
||Feature Release|Feature Flags|
||Secret Management|Certificates - Storage
|||Certificates - Usage Reference|
|||Certificates - Generation|
|||Certificate - Inventory|
|||Certificates - Update|
|||Keys/Strings - Storage
|||Keys/Strings - Usage Reference|
|||Keys/Strings - Generation|
|||Keys/Strings- Inventory|
|||Keys/Strings - Update|
|Data Tiers|||
||Persistant Storage System|
||Backup
||Restoration/Recovery Plan
|Platform / Infrastructure|||
||Isolation and Secure Access|||Management networks, secure workstations, etc.
||Identity|Authentication
|||JIT
||Operating System||CentOS 8
||Compute Hosting Platform||Kubernetes (Azure Kubernetes Services)
||Remote Access|System (RDP/SSH)
||OS Patching
||Component Patching
||Antivirus/Malware
||Vunerbility
||Integrity Monitoring / Operations Audit
|Code Quality|||
||Unit Testing
||Fuzz Testing
||Vulnerbility Testing
||Chaos, Fault, and Resiliency Testing||
|Performance Testing|
||Scale Targets
||Load Testing|||Gradual step up traffic
||Performance Testing|||How
||Stress Testing|||Purposefully overload
|CoGs Management
|Developer Experience
| Source Code| Repository
||Local Build and Run
||Calling downstream dependencies
||Upstream service invocation
|Service-to-Service
||Protocol
||Service Discovery
||Authentication
||Authorization
||Resiliency (retries, circuit breaker, etc.)
|Incident Management
||Tooling
||Customer Outage Dashboard
||Customer Support|Ticket System|Zen Desk|
|||Social Analysis||For a public service, analyzing social media sentiment can be helpful to understand issues that monitoring might have missed
||Customer Forums