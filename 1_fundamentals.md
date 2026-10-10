# Backend from First Principles 

## 1. Backend Roadmap

1.  HTTP Protocol
2.  Routing
3.  Serialization & Deserialization
4.  Authentication & Authorisation
5.  Validation & Transformation
6.  Middlewares
7.  Request Context
8.  Handlers or Controllers
9.  CRUD Deep Dive
10. REST Best Practices
11. Databases
12. Business Logic Layer (BLL)
13. Caching
14. Transactional Emails
15. Task Queuing & Scheduling
16. Elastic Search
17. Configuration Management
18. Error Handling
19. Logging, Monitoring & Observability
20. Graceful Shutdown
21. Security
22. Scaling & Performance
23. Concurrency & Parallelism
24. Object Storage & Large Files
25. Real-Time Systems
26. Testing & Code Quality
27. 12 Factor App Principles
28. OpenAPI Standard
29. Webhooks
30. DevOps for Backend Engineers

**Learning order:** Start with HTTP, routing, APIs, validation,
application layers, databases, and security. Learn testing, logging,
configuration, and deployment during implementation. Defer advanced
distributed systems topics until later.

## 2. Backend Request Lifecycle

``` text
Browser / Client
      |
      v
DNS lookup (domain -> IP address)
      |
      v
Cloud/network security rules
      |
      v
Nginx / Reverse proxy
      |
      v
Backend application
      |
      v
Database or external services (if needed)
      |
      v
HTTP response to client
```

-   **DNS:** Resolves a domain name to an IP address.
-   **Security groups/firewalls:** Allow or deny network traffic.
-   **Nginx:** Can act as a reverse proxy and forward requests to the
    application.
-   **Backend application:** Validates requests, applies business logic,
    and may access databases or other services.
-   **Load balancer:** In deployments with multiple instances,
    distributes traffic across healthy targets.

This is a simplified flow; real deployments vary.

## 3. Why Do We Need a Backend?

Frontend code runs in the user's browser. Backend code runs on a server
and provides a controlled place to process requests, enforce rules,
protect secrets, and manage shared data.

### Security and secrets

Frontend code is visible to users, so private API keys and database
credentials must not be stored there. The backend can keep secrets
server-side and enforce authorization.

### External APIs and CORS

Browsers enforce the same-origin policy. Cross-origin browser requests
may require permission through **Cross-Origin Resource Sharing (CORS)**
headers. Server-to-server requests are not subject to browser CORS
enforcement, but still require proper authentication and authorization.

### Database access

A backend provides a controlled interface to databases, enabling input
validation, access control, transactions, and persistent storage without
exposing database credentials to clients.

### Computing and resources

Server-side processing can handle work that needs controlled resources
or shared execution. The best location for processing depends on
performance, cost, privacy, and application requirements.

## Key Takeaway

The frontend handles the user-facing experience. The backend applies
business rules, protects secrets, manages data, communicates with
services, and returns responses.
