## REST Architecture (Representational State Transfer)

**REST** is an architectural style for designing distributed systems, particularly web services. It was introduced by Roy Fielding in his 2000 doctoral dissertation. REST emphasizes scalability, simplicity, and performance by leveraging the stateless nature of HTTP.

---

### Key Principles of REST

1. **Client-Server Architecture**:
   - REST separates the client and server concerns.
   - The client handles the user interface (presentation layer) while the server manages the data storage and business logic (data layer).
   - This separation allows them to evolve independently.

2. **Stateless Communication**:
   - Each request from the client to the server must contain all the information needed to understand and process the request (e.g., authentication, session state).
   - The server does not store any session information about the client.

3. **Cacheability**:
   - Responses from the server should indicate whether they are cacheable.
   - Proper use of caching can improve performance and reduce server load.

4. **Uniform Interface**:
   - REST defines a uniform interface between the client and server to simplify and decouple the architecture.
   - This includes standardized HTTP methods (like GET, POST, PUT, DELETE) and resource-based URIs.

5. **Layered System**:
   - The architecture is designed in layers, with each layer providing specific functionality (e.g., security, load balancing).
   - Layers are independent of one another, allowing flexibility and scalability.

6. **Code on Demand (Optional)**:
   - Servers can provide executable code (like JavaScript) to clients for execution, enhancing functionality without requiring new client code.
   - This is optional in REST systems.

7. **Resource-Based**:
   - Resources (e.g., users, products) are the key abstraction in REST.
   - Each resource is uniquely identified by a URI (Uniform Resource Identifier).

---

### Key Concepts in REST

1. **Resources**:
   - Everything in REST is considered a resource (e.g., user data, articles).
   - Resources are accessed using URIs like `/users`, `/products/42`.

2. **HTTP Methods**:
   - RESTful systems use HTTP methods to perform operations on resources:
     - **GET**: Retrieve resource information.
     - **POST**: Create a new resource.
     - **PUT**: Update an existing resource.
     - **PATCH**: Partially update an existing resource.
     - **DELETE**: Remove a resource.

3. **HTTP Status Codes**:
   - REST uses standard HTTP status codes to indicate the success or failure of requests:
     - `200 OK`: Successful request.
     - `201 Created`: New resource created.
     - `204 No Content`: Successful request with no data returned.
     - `400 Bad Request`: Invalid client request.
     - `401 Unauthorized`: Authentication required.
     - `404 Not Found`: Resource not found.
     - `500 Internal Server Error`: Server encountered an error.

4. **Content Negotiation**:
   - REST APIs support multiple formats (e.g., JSON, XML).
   - Clients specify their preferred format via HTTP headers like `Accept`.

5. **Statelessness**:
   - No client context is stored on the server between requests.
   - Any state needed by the client must be sent with each request.

---

### REST API Example

#### Scenario: Managing Users
**Base URL**: `https://api.example.com`

| Action               | HTTP Method | Endpoint            | Description                       |
|----------------------|-------------|---------------------|-----------------------------------|
| Get all users        | GET         | `/users`            | Retrieve a list of all users.    |
| Get a specific user  | GET         | `/users/{id}`       | Retrieve details for a user.     |
| Create a new user    | POST        | `/users`            | Add a new user.                  |
| Update a user        | PUT         | `/users/{id}`       | Update all details of a user.    |
| Partially update     | PATCH       | `/users/{id}`       | Update specific fields of a user.|
| Delete a user        | DELETE      | `/users/{id}`       | Remove a user.                   |

---

### Advantages of REST

1. **Scalability**:
   - Statelessness and layered architecture make scaling easy.
2. **Flexibility**:
   - Clients and servers are loosely coupled.
   - REST APIs can evolve without breaking clients.
3. **Interoperability**:
   - Based on standard HTTP and widely supported formats like JSON and XML.
4. **Simplified Integration**:
   - REST works seamlessly over the web using existing protocols.

---

### Limitations of REST

1. **Overhead**:
   - Statelessness requires clients to send repetitive information in each request.
2. **Lack of Real-Time Communication**:
   - REST is not ideal for real-time applications (e.g., chat apps) that require continuous connections.
3. **Complex Queries**:
   - REST is less efficient for complex queries or operations across multiple resources compared to alternatives like GraphQL.
4. **Loose Standards**:
   - The "uniform interface" is interpreted differently by different developers, leading to inconsistent implementations.

---

## References

- **Fielding, Roy T.**: *Architectural Styles and the Design of Network-based Software Architectures*. Doctoral dissertation, University of California, Irvine, 2000. [https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)
  
- **Tilkov, Stefan**, and **Vinoski, Steve**: "Node.js REST APIs," *Communications of the ACM*, vol. 59, no. 9, pp. 22-24, Sept. 2016. [https://cacm.acm.org/](https://cacm.acm.org/)

- **HTTP/1.1 Documentation**: *RFC 7231: Hypertext Transfer Protocol (HTTP/1.1) Semantics and Content*. IETF, 2014. [https://tools.ietf.org/html/rfc7231](https://tools.ietf.org/html/rfc7231)