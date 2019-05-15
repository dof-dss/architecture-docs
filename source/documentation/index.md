# Enterprise Architecture

This document is based on and contains extracts from the architecture description contained within [Common Capabilities to Support Northern Ireland Citizen Service Delivery](https://www.finance-ni.gov.uk/publications/architecture-description-common-capabilities-support-northern-ireland-citizen-service-delivery).

The aim of this document is to summarise the **principles**, **constraints**, **capabilities** and **initiatives** that are needed to deliver the next generation of NICS digital services. The development of the required capabilities is described in terms of a number of initiatives which are grouped into phases.

This Enterprise Architecture is considered a living document and will be subject to change as organisational business needs and priorities change over time. Significant changes in technology may also drive changes in this architecture.

**TEST CHANGE**

## Need for Change

### Strategic Context

Our overarching goal is to provide services to the citizens of Northern Ireland that deliver the outcomes associated with the Programme for Government and the Outcomes Delivery Plan.

Three published documents set out the vision for digital transformation and how this will be achieved in a robust and secure way.

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

### Quality Attributes

Digital services must also exhibit the following quality attributes:

- Usability and Accessibility
- Security and Compliance
- Availability and Reliability
- Extensibility
- Manageability, Maintainability and Supportability

### Organisational Benefits

A benefit dependency network (BDN) is a diagram having a specific structure that visualises multiple cause-effect relationships organised into capabilities, changes and benefits. It is usually read from right to left in order to provide a one-page overview of how a business vision and outcomes can be achieved, and to describe the supporting role of technology capabilities. As such a benefits dependency map allows to validate if and how technology capabilities help achieve overall goals set out by an organisation.

The BDN below identifies the following benefits to the NICS:

- Increased use of digital services (e-services);
- Reduced administrative overhead;
- Increased citizen satisfaction with Government services;
- Increased transparency;
- Reduced overall service delivery costs (total cost of ownership);
- Investment decisions based on service usage statistics;
- Reduced time to market; and
- Reduced net effort for new digital services.

![Benefits Dependency Network](images/benefits-dependency-network.png)

## Architecture

### Required Capabilities

A list of required capabilities has been created based on current and predicted future needs and by referencing solutions in use in other countries that are recognised as leaders in this digital service delivery; these are depicted below and described in more detail below that.

![NICS Common Capabilities](images/common-capabilities-2.png)

1. [Citizen Portal](documentation/capabilities/#1-citizen-portal)
2. [Notifications](documentation/capabilities/#2-notifications)
3. [Open Data Publishing](documentation/capabilities/#3-open-data-publishing)
4. [E-participation](documentation/capabilities/#4-e-participation)
5. [Developer Tools](documentation/capabilities/#5-documentation-and-configuration-repository)
6. [Citizen Identity and Federation](documentation/capabilities/#6-citizen-identity-and-federation)
7. [Social Network Management](documentation/capabilities/#7-social-network-management)
8. [API Management](documentation/capabilities/#8-api-management)
9. [Inbox/Outbox (Secure Messaging)](documentation/capabilities/#9-secure-messaging)
10. [Citizen Chatbot](documentation/capabilities/#10-citizen-chatbot-text-and-voice)
11. [Content Management and Knowledge Base](documentation/capabilities/#11-content-management-and-knowledge-base)
12. [Service Delivery History](documentation/capabilities/#12-service-delivery-history)
13. [Mobile Apps](documentation/capabilities/#13-mobile-apps)
14. [Service Desk](documentation/capabilities/#14-service-desk)
15. [Integrating Core Data Sets](documentation/capabilities/#15-integrating-core-data-sets)
16. [Unified Service Catalogue](documentation/capabilities/#16-unified-service-catalogue)
17. [Government Identity and Federation](documentation/capabilities/#17-government-identity-management-and-federation)
18. [Case Management](documentation/capabilities/#18-case-management)
19. [Usage Tracking](documentation/capabilities/#19-usage-tracking)
20. [Payments and Invoices](documentation/capabilities/#20-payments-and-invoices)

The following capabilities are relevant but not currently considered to be a priority:

- Mapping
- Records Management
- Field Service
- Performance Management
- Event Ingestion and Advanced Analytics

### Architecture Pattern

Before defining the services required to implement the common capabilities as identified in the capability
definition section, it is important to define the architectural pattern of how services providing citizen
capabilities should be built. This pattern applies not only to common capabilities and services providing
common functionality, but also to all services providing citizen facing functionality.

To support omni-channel access to functionality exposed by various systems as e-services and to enable
sustained development and evolution of this functionality over time, any service implemented should follow
these principles:

- service functionality exposed to partners (G2G) or citizens and businesses (G2B/G2C) are exposed
over REST based API;

- API(s) is published on API management common capability enabled layer to provide seamless
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

A schematically described pattern is shown below which represents the typical service components in pink
and external components using the service or used by the service in blue. The diagram also identifies APIs and messages that can be versioned by showing V1 and V2 appropriately on interaction lines. It also
illustrates that there are components of the service that can be developed standalone (e.g. specific mobile app providing the service to citizens) and there are components that can be hosted on existing platforms (e.g. portal pages hosted on portal common) to achieve more seamless user experience and to ensure more reuse from implementation and also solution hosting perspective.

![Service Implementation Pattern](images/service-pattern.png)

### Service Map

The overall service map and dependencies of services enabling common capabilities of citizen service delivery is displayed below. The diagram shows only the main interactions of component groups, grouping components based on their responsibility area/type:

- identity and profile management;
- providing citizen interaction (channels);
- API management – providing “glue layer” for external access to functionality and ensuring
decoupling/indirection;
- core service functionality exposed via APIs and providing internal employee user interaction;
- supporting all services for elements like audit and usage capturing; and
- supporting DevSecOps teams managing configuration, making changes and running solution
deployment and tests.

Elements shown with red border are platform elements that support building new types of certain services
(e.g. new workflows in case management or new forms in forms engine, new UI modules in citizen services
portal, new API registrations in API management). Being platform components as per architectural principles
they support both multi-tenancy (to be used by teams in different departments) and extensibility by
multiple development teams.

Elements shown with blue border are ready-made multi-tenant components supporting multiple department teams, but not extensible by other developers.

The diagram also shows how other Government and non-Government systems can participate in the overall
service delivery and reuse common platform, services and overall architectural approach:

- existing web and mobile solutions providing specialised services can leverage citizen identity and
call existing common services or other government systems publishing data and functionality via
API management layer;
- Government systems reusing services can perform G2G calls to other systems exposing their data
and services in a uniform way through API management;
- backend systems can publish their APIs to enable their e-services access the functionality or to
enable other government systems accessing the data/functionality exposed; and
- Government systems can reuse important building block functionality from common capability
services, things like profile management, notification sending, inbox/outbox for secure messaging,
payment/invoice service, data integration and reporting platforms to host their data and reports
(more on reusable services exposed via common services.

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

At present most of the solutions run by departments are hosted by Digital Shared Services (IT Assist) in IaaS environments or procured
as external managed services. Looking into the future and considering potential improvements into
deployment consolidation, especially reuse of platforms, the hosting model should support additional
middle ground options to raise the reuse level and speed of development for custom solutions.

The models of hosting to support solutions providing citizen services with associated evaluation criteria is provided below.

#### IaaS

Model where solution builders have virtual machines allocated to them based on their specification. Solution builders then often deploy their own application stack and solutions on these virtual machines that need to be maintained with time together with application itself.

Suggested use only for legacy applications that do not support other hosting models. Can be used for very sensitive solutions that require maximum separation of solution from other solutions (if similar cannot be achieved in higher level platforms).

#### IaaS+

Model where solution builders get shared container deployment environment that provides advantages in deployment, amount of consolidation possible on the same hardware and maintenance.

Suggested for use in solutions requiring cloud independence (possibility to move from one cloud to another). Avoid using when advanced services are required. Do not use containers for hosting common IT services like RDBMS. Good to host stateless service components, e.g. web sites and APIs.

#### PaaS

Model where solution builders care only about their solution application code and configuration, not the infrastructure and application stack. Good for maintenance, but also for advanced features like declarative scalability, features like built in backups, DR, automated deployment and versioning. Extreme option of the PaaS is serverless platforms, when instead of solution builders deploying full application and still defining sizing of the infrastructure to use, they are deploying application modules without knowledge of infrastructure to run them.

Primary choice for all new custom developed solutions, e.g. APIs, Web sites, batch processing, case management/workflow solutions. Primary choice for application platform components like database management systems, noSQL data stores, queuing mechanisms and API management.

#### SaaS

Model to be used for services that can be implemented using configuration of ready-made platform (no customisation via code allowed). For commodity functionality (e.g. collaboration) this reduces implementation risks and overall costs as commodity SaaS platforms are used by many customers, thus raising overall quality and decreasing the cost due to economy of scale.

Primary choice for services that provide commodity functionality (e.g. surveys, collaboration) and do not
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

- [Implement API management](documentation/initiatives#api-management)
- [Implement documentation and configuration repository and DEVOPS pipeline](documentation/initiatives#documentation-and-configuration-repository-and-devops-pipeline)
- [Create Usage Tracking Service](documentation/initiatives#usage-tracking-service)
- [Implement Audit Service](documentation/initiatives#audit-service)
- [Standardise Employee and System Identity](documentation/initiatives#employee-and-system-identity)
- [Implement External Identity Hub (profile)](documentation/initiatives#identity-hub)
- Infrastructure
  - Hybrid Networking
  - Hybrid System Identity
  - Hybrid Management
  - Hybrid Monitoring

#### Phase 2 initiatives

- [Implement Portal Core (basic features)](documentation/initiatives#portal-core)
- [Implement Case Management Core (no authentication)](documentation/initiatives#case-management-platform)
- [Implement Identity Hub Identity (federation and profile extensions)](documentation/initiatives#identity-hub)
- [Implement Structured Service Catalogue](documentation/initiatives#structured-service-catalogue)
- [Implement Notification Service](documentation/initiatives#notification-service-core)
- [Feature Flags Service](documentation/initiatives#feature-flags-service)
- [Report/Dashboard Platform](documentation/initiatives#reporting-and-dashboard-management)
- [Secure Messaging (NIDA based)](documentation/initiatives#secure-messaging-core)

#### Phase 3 initiatives

- [Portal Core (extended features)](documentation/initiatives#portal-core)
- [Data Set Sharing](documentation/initiatives#g2g-data-sharing-and-open-data-delivery)
- [Case Management Core (extended features)](documentation/initiatives#case-management-platform)
- [Knowledge Base](documentation/initiatives#knowledge-base)
- [Service Delivery Tracking](documentation/initiatives#service-delivery-tracking-history)
- [Secure Messaging (extended features)](documentation/initiatives#secure-messaging-hybrid-delivery)

#### Phase 4 initiatives

- [Identity Hub (business)](documentation/initiatives#identity-hub-business-support)
- [Content Management Enhancements](documentation/initiatives#content-management-enhancements)
- [Payments/Invoice Service](documentation/initiatives#payment-and-invoicing-service)
- [Chatbot Core](documentation/initiatives#chatbot-core)
- [Forms Engine](documentation/initiatives#forms-engine-for-portal-and-mobile)

## Solution Architecture

This section provides detailed logical service architecture for the main services identified as high priority or the ones that are pre-requisites for other services.

- [Identity Management](documentation/architecture#identity-management)
- [API Management](documentation/architecture#api-management)
- [Notification Service](documentation/architecture#notification-service)
- [Service Catalogue](documentation/architecture#service-catalogue)
- [Secure Messaging](documentation/architecture#secure-messaging)
- [Citizen Portal](documentation/architecture#citizen-portal)

## NICS Information & Technical Design Authority

This site and its contents are reviewed and approved by the NICS Information & Technical Design Authority (ITDA). ITDA meets once a quarter. Its memberships comprises senior IT professionals from DSS (Department of Finance) and other NICS departments. Any changes to this architecture will require ITDA approval.

## Providing feedback

The NICS Enterprise Architecture Team is happy to discuss any of the content contained in this document
and openly welcomes any feedback you may have.

You may contact the team at [ea-team@ea.finance-ni.gov.uk](mailto:ea-team@ea.finance-ni.gov.uk).
