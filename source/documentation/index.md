# Enterprise Architecture

This document is based on and contains extracts from the architecture description contained within [Common Capabilities to Support Northern Ireland Citizen Service Delivery](https://www.finance-ni.gov.uk/publications/architecture-description-common-capabilities-support-northern-ireland-citizen-service-delivery). The aim of this document is to summarise the principles, constraints, capabilities and initiatives that are needed to deliver the next generation of NICS digital services. The development of the required capabilities is described in terms of a number of initiatives which are grouped into phases.

## Need for Change

### Strategic Context

Our overarching goal is to provide services to the citizens of Northern Ireland that deliver the
outcomes associated with the Programme for Government and the Outcomes Delivery Plan.

Three published documents set out the vision for digital transformation and how this will be
achieved in a robust and secure way.

- [Making Lives Better - A Strategy for Digital Transformation of Public Services 2017-2021]()
- [Nothern Ireland Civil Service ICT Strategy 2017-2021]()
- [Cyber Security - A Strategic Framework for Action 2017-2021]()

### Key Personas

It is vital that we consider all those involved in or impacted by the development of digital services. The key personas involved in end-to-end service delivery and their future needs are defined below:

- Citizen
- Business representative
- Government employee
- Government executive
- Non-resident
- Internal developers
- External third-party developers

While some of these are obvious, i.e. the consumer and provider of the service, it is perhaps less obvious that we should consider the needs of the teams building digital services for Government.

### Ethical Principles

It is important that all citizens benefit from the transformation of service delivery regardless of the preferred way they access or interact with Government services. The following ethical principles should be considered and followed when constructing new services.

- Fairness
- Inclusion
- Transparency
- Accountability

### Architectural Principles

Architectural Principles are long-lasting and rarely changing statements and guidelines that govern the design, implmentation and operation of solutions. They are derived from the specific needs and priorities of the stakeholders and provide a decision-making framework for the architecture.

1. [Maintain your service catalogue](documentation/principles/#ap1-maintain-your-service-catalogue)
2. [Leverage public cloud capabilities](documentation/principles/#ap2-leverage-public-cloud-capabilities)
3. [Manage IT service documentation and configuration centrally](documentation/principles/#ap3-manage-it-service-documentation-and-configuration-centrally)
4. [Track and expose usage information](documentation/principles/#ap4-track-and-expose-usage-information)
5. [Track service delivery status](documentation/principles/#ap5-track-service-delivery-status)
6. [Expose APIs and queue messages](documentation/principles/#ap6-expose-apis-and-queue-messages)
7. [Use centralised identity/federation providers](documentation/principles/#ap7-use-centralised-identity-federation-providers)
8. [Follow UX guidance](documentation/principles/#ap8-follow-ux-guidance)
9. [Follow secure development guidelines](documentation/principles/#ap9-use-centralised-identity-federation-providers)
10. [Leverage feature flags](documentation/principles/#ap10-leverage-feature-flags)
11. [Provide multi-tenancy support](documentation/principles/#ap11-provide-multi-tenancy-support)
12. [Provide multi-channel citizen support](documentation/principles/#ap12-provide-multi-channel-support-for-citizens)
13. [Expose functionality for departments as APIs](documentation/principles/#ap13-expose-functionality-for-departments-as-apis)
14. [Document for developers extensively](documentation/principles/#ap14-document-extensively-for-developers)
15. [Ensure multiple development teams can add new "scenarios"](documentation/principles/#ap15-ensure-multi-development-teams-can-add-new-scenarios)

### Architectural Constraints

Architectural Constraints are derived from specific mandatory requirements from a number of stakeholders and must be strongly adhered to; there is no option for interpretation or non-compliance.

1. [Employee identity management is Active Directory exposing OpenID Connect and SAML-P endpoints](documentation/constraints/#ac1-employee-identity-management-source-is-active-directory-exposing-openid-connect-and-saml-p-endpoints)
2. [REST based APIs exchanging JSON documents are the message/document exchange approach](documentation/constraints/#ac2-rest-based-apis-exchanging-json-documents-are-the-message-and-document-exchange-approach)
3. [Citizen identity management is based on OAuth/OpenID Connect](documentation/constraints/#ac3-citizen-identity-management-is-based-on-oauth-and-openid-connect)
4. [Centralised content management platform is Drupal](documentation/constraints/#ac4-centralised-content-management-platform-is-drupal)
5. [DSS manages custom built services](documentation/constraints/#ac5-dss-manages-custom-built-services)
6. [Solution security should adhere to Government wide standards](documentation/constraints/#ac6-solution-security-must-adhere-to-government-security-standards)
7. [Monitoring/management should leverage a common hybrid solution](documentation/constraints/#ac6-solution-security-must-adhere-to-government-security-standards)

### Quality attributes

Digital services must also exhibit the following quality attributes:

- Usability and Accessibility
- Security and Compliance
- Availability and Reliability
- Extensibility
- Manageability, Maintainability and Supportability

## Architecture

### Required Capabilities

A list of required capabilities has been created based on current and predicted future needs and by referencing solutions in use in other countries that are recognised as leaders in this digital service delivery; these are depicted below and described in more detail below that.

![NICS Common Capabilities](images/common-capabilities-2.png)

1. [Citizen Portal](documentation/capabilities/#1-citizen-portal)
2. [Notifications](documentation/capabilities/#2-notifications)
3. [Open Data Publishing](documentation/capabilities/#3-open-data-publishing)
4. [E-participation](documentation/capabilities/e-participation.html)
5. [Developer Tools](documentation/capabilities/developer-tools.html)
6. [Citizen Identity and Federation](documentation/capabilities/citizen-identity-federation.html)
7. [Social Network Management](documentation/capabilities/social-network.html)
8. [API Management](documentation/capabilities/api-management.html)
9. [Inbox/Outbox (Secure Messaging)](documentation/capabilities/inbox-outbox.html)
10. [Citizen Chatbot](documentation/capabilities/chatbot.html)
11. [Content Management and Knowledge Base](documentation/capabilities/content-management.html)
12. [Service Delivery History](documentation/capabilities/service-delivery.html)
13. [Mobile Apps](documentation/capabilities/mobile-apps.html)
14. [Service Desk](documentation/capabilities/service-desk.html)
15. [Integrating Core Data Sets](documentation/capabilities/integrating-core-data-sets.html)
16. [Unified Service Catalogue](documentation/capabilities/service-catalogue.html)
17. [Government Identity and Federation](documentation/capabilities/government-identity-federation.html)
18. [Case Management](documentation/capabilities/case-management.html)
19. [Usage Tracking](documentation/capabilities/usage-tracking.html)
20. [Payments and Invoices](documentation/capabilities/payments-and-invoices.html)

The following capabilities are relevant but not currently considered to be a priority:

- Mapping
- Records Management
- Field Service
- Performance Management
- Event Ingestion and Advanced Analytics

### Architecture Pattern

To support omni-channel access to functionality exposed by various systems and digital services and to enable sustained development and evolution of this functionality over time, any service implemented should follow these principles:

- service functionality exposed to partners (G2G) or citizens and businesses (G2B/G2C) are exposed
over REST based API;

- APIs is published on API management common capability enabled layer to provide seamless
versioning, enforce common security approach for sustained evolution of functionality over time;

- there can be multiple frontends leveraging the service API to provide end-user functionality, e.g.
access to it via portal/mobile or access from another service or system;

- exchange of asynchronous messages (preferred over direct calls) is implemented via message
queue-based solution leveraging versioned messages;

- UI exposed by government employees can be more tightly coupled to the service implementation
to enable reuse for COTS products and drive more reuse of ready-made platforms (does not have
to access functionality over APIs exposed API management);

- citizen and business access to service is secured using Citizen (and business) Identity Hub,
government employee and system access to service functionality is secured using Government
Employee Identity Management and Federation solution.

### Service Map

![Common Capability Service Map](images/service-map.png)

### Reusable Services

The following services have been identified specifically for reuse by developers:

- NI External identity hub
- NI employee identity management
- Profile management
- Notifications management
- Secure messaging
- Service delivery tracking
- Service catalogue
- Report management
- Payment and invoice management
- Content management
- Knowledge base
- API management
- Forms engine
- Case management
- Service desk
- Telemetry/usage tracking and usage insights
- Audit service
- Data integration
- Social network engagement
- Survey/polls
- Feature flags
- Configuration management services
- SIEM
- Monitoring/management

### Documentation and Configuration Management

To support sustained development and enhancement of services over time, maintaining documentation
and configuration well, is critical.

Suggested changes in documentation and configuration management include:

- migration of government teams to use centralised documentation and configuration management;

- enabling contributions and reuse of code across the teams, including even public contributions to
documentation or code;

- ensuring external procurement of services for development of IT solutions related to citizen service
(and broadly – even internal services) require documentation and configuration to be managed as
part of the centralised solution.

The minimal set of documentation required for a service includes:

- Business case and technical approach (document/section answering why? question for the service
to be introduced);

- Context (personas and scenarios to be supported by the service – what?);

- Architectural design (identification of service components to be introduced, their internal and
external dependencies, examples of control flow through these components to showcase the
scenarios supported) and Component high level design (how?);

- Deployment guide (information on how to deploy the solution, what are the configuration
parameters and deployment pre-requisites);

- Administration guide (information on operational tasks to follow when running the service in
production).

### CI/CD

Continuous Integration / Continuous Delivery is the process to:

- drive more automation;

- speedier adjustment to changes; and

- earlier detection of integration issues and, if done right, less regression bugs.

To speed up implementation of the solutions in Government and to ensure changes to existing solutions do not introduce regression issues, CI/CD is an important practice to be adopted. Depending on implementation technology leveraged for service implementation this also means the use of automated deployment into dev/test environments and (after necessary validation) automatic deployments of new versions in production as well.

### DevSecOps Pattern

The overall approach showing integrated technical capabilities and process flow to enable documentation
and configuration management, CI/CD pipeline, service improvement through insights into service usage,
monitoring of the environment and managing issues through unified DevSecOps teams is illustrated in
below. This also references security specific products that should be part of the environment to ensure
security related insights on top of gathered usage and IT environment event data. The figure below shows feature flags service to illustrate the suggested way on how feature releases would be planned for gradual release into production.

![DevSecOps Pattern](images/dev-sec-ops.png)

### Infrastructure Architecture

The infrastructure approach must be able to support more agile provisioning and changes in infrastructure environments. To achieve this, and focus effort more on developing/enhancing not running the infrastructure for the services, the suggested approach is to:

- focus on use of higher-level base services to host solutions;

- use IT infrastructure agility and advanced offerings offered through public cloud providers; and

- involve infrastructure planning into service planning and implementation process through
integrated DevSecOps practices.

The infrastructure pattern to support future citizen services platform and the services themselves is
illustrated below.

![Infrastructure Pattern](images/infrastructure-pattern.png)


### Hosting Model

At present most of the solutions run by departments are hosted by DSS in IaaS environments or procured
as external managed service. Looking into the future and considering potential improvements into
deployment consolidation, especially reuse of platforms, the hosting model should support additional
middle ground options to raise the reuse level and speed of development for custom solutions, enable
better hosting.

The models of hosting to support for solutions providing citizen services with evaluation criteria of when to pick one over another is provided below.

#### IaaS

Model where solution builders have virtual machines allocated to them based on their
specification. Solution builders then often deploy their own application stack and solutions on these virtual machines that need to be maintained with time together with application itself.

Suggested use only for legacy applications that do not support other hosting models.
Can be used for very sensitive solutions that require maximum separation of solution from
other solutions (if similar cannot be achieved in higher level platforms).

#### IaaS+

Model where solution builders get shared container deployment environment that provides advantages in deployment, amount of consolidation possible on the same hardware and maintenance.

Suggested for use in solutions requiring cloud independence (possibility to move from one
cloud to another). Avoid using when advanced services are required. Do not use containers for hosting common IT services like RDBMS. Good to host stateless service components, e.g. web sites and APIs.

#### PaaS

Model where solution builders care only about their solution application code and configuration, not the infrastructure and application stack. Good for maintenance, but also for advanced features like declarative scalability, features like built in backups, DR, automated deployment and versioning.
Extreme option of the PaaS is serverless platforms when instead of solution builders deploying full application and still defining sizing of the infrastructure to use, they are deploying application modules without knowledge of infrastructure to run them.

Primary choice for all new custom developed solutions, e.g. APIs, Web sites, batch processing, case management/workflow solutions. Primary choice for application platform components like database management systems, noSQL data stores, queuing mechanisms, API management.

#### SaaS

Model to be used for services that can be implemented using configuration of readymade platform (no customisation via code allowed). For commodity functionality (e.g. collaboration) this reduces implementation risks and overall costs as commodity SaaS platforms are used by many customers, thus
raising overall quality and decreasing the cost due to economy of scale.

Primary choice for services that provide commodity functionality, e.g., surveys, collaboration, and do not
require Northern Ireland specific customisation that goes beyond what configuration offers.
Should not be used for getting custom tailored services as benefits of lower price and reduced implementation risks disappear.

## Roadmap

The roadmap section is based on analysis of gaps of common capabilities vs the ones envisioned and based
on understanding of processes and organisation changes to be made. Initiatives have been proposed with
a draft plan based on dependencies, impact of the initiative and its estimated size/complexity.

### Technical Initiatives

A number of initiatives have been created to deliver the required capabilities; the relative priority of each these is shown below. The roadmap consists of:

- technical initiatives;

- organisational initiatives; and

- process initiatives.

The technical initiatives only are described here.

![Infrastructure Pattern](images/initiative-priorities.png)

These have been logically grouped into four phases:

#### Phase 1 initiatives

- API Management
- Usage Tracking
- Dev/Config Environment
- Audit Service
- Standard Employee and System Identity
- Identity Hub Profile
- Infrastructure
  - Hybrid Networking
  - Hybrid System Identity
  - Hybrid Management
  - Hybrid Monitoring

#### Phase 2 initiatives

- Portal Core (basic features)
- Case Management Core (No authentication)
- Identity Hub: Identity Federation and Profile Extensions
- Structured Service Catalogue
- Notification Service
- Feature Flags Service
- Report/Dashboard Platform
- Business Systems exposing APIs
- Inbox/Outbox (NIDA based)

#### Phase 3 initiatives

- Portal Core (extended features)
- Data Set Sharing
- Case Management Core (extended features)
- Knowledge Base
- Service Delivery Tracking
- Inbox/Outbox (extended features)

#### Phase 4 initiatives

- Identity Hub (business)
- Content Management Enhancements
- Payments/Invoice Service
- Chatbot Core
- Forms Engine
