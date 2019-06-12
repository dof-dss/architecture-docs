## Secure Messaging

![Secure Messaging Solution Architecture](/images/secure-messaging-solution-architecture.png)

Service implementation follows the defined architecture pattern separating citizen UI components from
backend components. Functionality to citizen channels and other Government systems that need to interact
with secure messaging is provided via APIs secured using appropriate identity management solution.

Secure Messaging Admin UI is used by Government employees to manage institution inbox (see received
messages) and send messages/documents to citizens.

To notify citizens and Government department employees about documents arriving in their inbox, the solution
depends on the notification service that is being accessed via its APIs. Also, as each profile needs its inbox, solution subscribes to profile changes feed from profile management
