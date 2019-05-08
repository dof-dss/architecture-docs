## Citizen Portal

![Citizen Portal Solution Architecture](images/citizen-portal-solution-architecture.png)

The portal capability comprises:

- common portal framework and tightly integrated modules (e.g. profile UI);
- specialised external portal that follows implementation guidance, but is implemented as separate
solution hosted on the next-gen hosting environment (web apps cluster/service or container
cluster) enabling more reuse from infrastructure perspective; and
- specialised external portal that follows implementation guidance for portal, but is hosted using IaaS
environment, limiting reuse to be only at virtual machine hosting environment.

Because most of the reuse and best user experience is achieved by tight module integration into UI, the
preference should be building integrated UI modules instead of specialised portals where possible.

As for the tightly integrated modules, the diagram shows some of the UI elements of the other common services owned or provided by DSS – profile, authentication, inbox, notifications etc. At least these common
component UI elements would need to be done in this tightly integrated mode for the benefit of user
experience. Specialised portals are integrated via SSO and common UX guidance, but still the experience
changes when navigating from common portal to any specialised one.
