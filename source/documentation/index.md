# Enterprise Architecture

This document is based on and contains extracts from the architecture description described in [Common Capabilities to Support Northern Ireland Citizen Service Delivery](https://www.finance-ni.gov.uk/publications/architecture-description-common-capabilities-support-northern-ireland-citizen-service-delivery). The aim of this document is to summarise the principles, constraints, capabilities and initiatives described in the architecture description that are needed to deliver the next generation of NICS digital services. The development of the required capabilities is described in terms of a number of initiatives which are grouped into phases.

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

1. [Maintain your service catalogue](documentation/principles/maintain-catalogue.html)
2. [Leverage public cloud capabilities](documentation/principles/public-cloud.html)
3. [Manage IT service documentation and configuration centrally](documentation/principles/doc-configuration.html)
4. [Track and expose usage information](documentation/principles/track-usage.html)
5. [Track service delivery status](documentation/principles/track-service-delivery.html)
6. [Expose APIs and queue messages](documentation/principles/expose-apis.html)
7. [Use centralised identity/federation providers](documentation/principles/identity.html)
8. [Follow UX guidance](documentation/principles/ux-guidance.html)
9. [Follow secure development guidelines](documentation/principles/secure-dev-guidelines.html)
10. [Leverage feature flags](documentation/principles/feature-flags.html)
11. [Ensure multi-tenancy support](documentation/principles/multi-tenancy.html)
12. [Ensure multi-channel citizen support](documentation/principles/multi-channel.html)
13. [Expose functionality for departments as APIs](documentation/principles/functionality-apis.html)
14. [Document for developers extensively](documentation/principles/document-for-developers.html)
15. [Ensure multiple development teams can add new "scenarios"](documentation/principles/new-scenarios.html)

### Architectural Constraints

1. [Employee identity management is Active Directory exposing OpenID Connect and SAML-P endpoints](documentation/constraints/employee-identity.hmtl)
2. [REST based APIs exchanging JSON documents are the message/document exchange approach](documentation/constraints/rest-based-api-json.html)
3. [Citizen identity management is based on OAuth/OpenID Connect](documentation/constraints/citizen-identity.html)
4. [Centralised content management platform is Drupal](documentation/constraints/content-management.html)
5. [DSS manages custom built services](documentation/constraints/custom-build.html)
6. [Solution security should adhere to Government wide standards](documentation/constraints/security-standards.html)
7. [Monitoring/management should leverage a common hybrid solution](documentation/constraints/monitoring.html)

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

1. [Citizen Portal](documentation/capabilities/citizen-portal.html)
2. [Notifications](documentation/capabilities/notifications.html)
3. [Open Data Publishing](documentation/capabilities/open-date.html)
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

- service functionality is exposed to partners (G2G) and to citizens/businesses (G2C) over REST based APIs

### Reusable Services

The following services have been identified specifically for reuse by developers:
- NI External Identity Hub
- another service

### Documentation and Configuration Management

tbd

### CI/CD

tbd

### DevSecOps Pattern

tbd

### Infrastructure Architecture

tbd

### Hosting Model

tbd

## Roadmap

tbd

### Technical Initiatives

A number of initiatives have been created to deliver the required capabilities. These have been logically grouped into four phases:

#### Phase 1

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

#### Phase 2

- Portal Core (basic features)
- Case Management Core (No authentication)
- Identity Hub: Identity Federation and Profile Extensions
- Structured Service Catalogue
- Notification Service
- Feature Flags Service
- Report/Dashboard Platform
- Business Systems exposing APIs
- Inbox/Outbox (NIDA based)

#### Phase 3

- Portal Core (extended features)
- Data Set Sharing
- Case Management Core (extended features)
- Knowledge Base
- Service Delivery Tracking
- Inbox/Outbox (extended features)

#### Phase 4

- Identity Hub (business)
- Content Management Enhancements
- Payments/Invoice Service
- Chatbot Core
- Forms Engine
