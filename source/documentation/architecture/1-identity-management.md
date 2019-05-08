## Identity Management

![Identity Management Solution Architecture](images/identity-management-solution-architecture.png)

The main components shown above are:

1. **Identity Hub**:
The identity hub provides identity federation with different identity providers including the local identity currently provided by NIDA.

2. **Profile Management Service**:
The profile management service holds information on the citizens, non-residents, business representatives
and Government organisations, holding their verified contact information and subscriptions to Governement services.

3. **Employee Identity Management**: The employee and identity management service includes the identity provider, identity federation service and profile and permissions store for Government employees and partners providing citizen services on behalf of Governement.

Supporting services are:

- notifications service to send out profile related messages;
- audit service to track sensitive changes or information access;
- citizen and business identity providers;
- other systems that can query the profile or subscribe to the profile change feed; and
- HR system that provides Government structure information into profile management.
