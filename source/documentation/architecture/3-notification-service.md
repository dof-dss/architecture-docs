## Notification Service

![Notification Service Solution Architecture](/images/notification-service-solution-architecture.png)

The Notification Service follows the service implementation pattern defined previously where each service has:

- one or more citizen user interface components implemented on relevant platform;
- exposed APIs available to both citizens and government systems (leveraging appropriate identity
solutions);
- backend components implementing the functionality that interact/integrate with other external
services required; and
- backend administrative UI that enables management of templates for notifications by government
employees and that allows notifications to be sent out to groups of users manually.

Given that citizen, business representative and even Government organisation contact information is managed
within the profile management solution, this service depends on rich profile management to get the preferences of notification delivery and validated delivery addresses from profile management.
