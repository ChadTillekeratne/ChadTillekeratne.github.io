## What does an Site Reliability Engineer (SRE) do?

An SRE is an engineer who drives reliability for a service. In every company (and every team), the daily responsibilities that an SRE performs can vary. 

In some teams an SRE is a developer that has additional knowledge and focus around reliability, where they code features for reliability (diagnostics, resiliency, etc.).  To the other extreme, an SRE can be an operational role that has a focus on areas of Infrastructure (own data tiers, networking, storage, etc.)

I believe that an SRE sits in between the two extremes.  An SRE is an engineer who understands one-or-more disciplines (databases, networking, debugging, etc.) an uses their knowledge and experience to improve reliability for an area.  This is a rather open statement as the exact _responsibility_ and _accountability_ of the SRE shall compliment the responsibilies and ownerships of the rest of the team.

While this can be confusing, this is also similiar to the "Software Engineer" role.  Within software engineering there are many areas of focus and specialties (frontend, backend, networking, AI, ML, data science, etc.)

### Disciplines and Focus Areas

Some areas that an SRE has ownership or respoinsbility in are (and not limited to):

- Service Level Objectives (SLO and SLA)
- Observability and Alerting
- On Call and Incident Response
- Problem Management and Postmortems
- Capacity Planning
- Performance Management
- Reliability in System Architecture ([Cloud Design Patterns](https://docs.microsoft.com/en-us/azure/architecture/patterns/))
- Dependency Management
- Security Operations (Blue Team)

## Principles

- Reliability is Team Sport
  - Reliability doesn't come from any one role, it's the output of all roles
- [Eliminate Toil](https://sre.google/sre-book/eliminating-toil/), Automate Everything
  - Engineer solutions rather than perform manual actions
- [Embrace Risk](https://sre.google/sre-book/embracing-risk/)
  - An evolving system requires changes, understand how to manage it 
- Manage with Metrics
  - Identify _what matters_ and create objective measures to identify success
- Standardize and Commonize
  - Managing commonality is more scalable than special cases

## Objective and Key Results (OKR)
_What is successful?  How do we measure success?_

Objectives Key Results is a goal setting framework to help understand our desired outcome and how we will measure our success to achieving.

References:
  - https://www.whatmatters.com/get-started/

|Area|Objective|Key Results|Notes
|--|--|--|--|
|Development
||Developer Fungability - Developers are able to work on any project |
|||//TODO: Developer can add a simple feature to a visiting service in {n} hours
|||//TODO: Developers are able to be on-call for services that they don't work often
||Developer an deploy a change to development environment in less than 1 hour
||Development Velocity - Developers have a known and rapid process to get a feature into master
||Release Velocity - Developers are able to rapidly and safely get changes in production
|||Master to Production in less than 5 business days
|Livesite|
||Service availability excedes customer SLAs|
|||Scenario Reliability
|Quality
||Services are secure
