## AP11 - Provide multi-tenancy support

**Rationale**

Platforms are systems that are used by multiple user groups, e.g., different department teams, each providing a specific scenario while reusing horizontal functionality. Given different teams from
different departments are using those solutions, platforms need to ensure proper segregation for clarity but also data security purposes. E.g., case management platform supporting many case management
solutions should support different teams working with them and not interfering with each other, and not seeing each other’s data.

**Implication**

Platform testing should include test cases showing how multiple separate teams can use the platform
without interfering.
