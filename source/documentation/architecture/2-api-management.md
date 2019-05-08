## API Management

![API Management Solution Architecture](images/api-management-solution-architecture.png)

API management is the "glue" component that is not externally visible (except to developers), yet it is very important to ensure sustainable service evolution over time. It enables redirection of APIs to new systems, enables versioning and API revisions.

API Management and Service Catalogue are linked where APIs defined on the API Management layer get listed in the Service Catalogue for consumption by other systems and services.

Core components of the API management capability are:

1. **API Management Portal/API**: Used to manage the API definitions, products and subscriptions,
configure various policies to be enforced;

2. **API Management Gateway**: Receives all external calls and forwards them as per
defined policies to relevant backend services; and

3. **API Management Developer Portal**: Used by developers to learn about approaches of using APIs,
learning API definitions and even testing calls to backend APIs.

Usage tracking is an important dependency of API management that enables all incoming calls to be traced
to enable both insights into service popularity, but also debugging any error situations/conditions.
