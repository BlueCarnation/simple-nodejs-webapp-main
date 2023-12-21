# Part 2: Microservices Architecture

## Q1: Define what is a Microservices architecture and how does it differ from a Monolithic application.
**Microservices Architecture** is a design approach where a single application is composed of many loosely coupled and independently deployable smaller services. Each service in a microservices architecture can be developed, deployed, operated, and scaled independently. These services typically communicate with each other through well-defined APIs and protocols.

In contrast, a **Monolithic Application** is a single-tiered software application in which different components are combined into a single program from a single platform. All components of the application are interconnected and interdependent.

## Q2: Compare Microservices and Monolithic architectures by listing their respective pros and cons.

### Microservices
**Pros**:
1. **Scalability**: Individual components can be scaled as needed.
2. **Flexibility**: Different technologies can be used in different services.
3. **Resilience**: Failure in one service doesn't affect the entire application.
4. **Continuous Deployment**: Enables more frequent updates and deployments.

**Cons**:
1. **Complexity**: More complex to develop, deploy, and maintain.
2. **Network Latency**: Increased communication between services can lead to delays.
3. **Resource Intensive**: Can require more resources and overhead.
4. **Debugging Difficulty**: More difficult to trace issues across multiple services.

### Monolithic
**Pros**:
1. **Simplicity**: Easier to develop, test, deploy, and scale.
2. **Performance**: Typically faster due to shared memory access.
3. **Less Overhead**: Fewer complexities with networking and communication.
4. **Consistency**: Easier to maintain consistency and uniformity.

**Cons**:
1. **Scalability Issues**: Scalability is often limited to the entire application.
2. **Flexibility Limitations**: Tied to one technology stack.
3. **Downtime**: Updates can require the entire application to restart.
4. **Large Code Base**: Can become unwieldy and difficult to manage over time.

## Q3: In a Micoservices architecture, explain how should the application be split and why.
 
In **Microservices Architecture**, an application should be split based on business capabilities or functionalities. Each microservice should encapsulate a specific business function or process. This is often guided by the **Single Responsibility Principle** where each service does one thing and does it well. The split allows for independent development and scaling of each microservice according to its specific demands.

## Q4: Briefly explain the CAP theorem and its relevance to distributed systems and Microservices.
The **CAP Theorem** states that a distributed system can only simultaneously provide two of the following three guarantees: Consistency, Availability, and Partition Tolerance. 

- **Consistency**: Every read receives the most recent write or an error.
- **Availability**: Every request receives a response, without guarantee of it containing the most recent write.
- **Partition Tolerance**: The system continues to operate despite network partitions.

### Relevance to Microservices
In microservices, which inherently involve distributed systems, the CAP theorem underlines the trade-offs when designing and deploying services, especially in terms of data consistency and system availability.

## Q5: What consequences on the architecture ?
The implications of the CAP theorem on architecture involve making strategic decisions about which two of the three properties (Consistency, Availability, Partition Tolerance) to prioritize. This affects the choice of databases, communication protocols, and data replication strategies.

## Q6: Provide an example of how microservices can enhance scalability in a cloud environment.

**Example**: Consider a cybersecurity web application offering services like threat monitoring, vulnerability scanning, and incident response. In a monolithic architecture, a surge in threat monitoring requests (e.g., during a widespread cyber-attack) could strain the entire application, slowing down other functionalities.

However, in a microservices-based architecture, each functionality is a separate service: one microservice for threat monitoring, another for vulnerability scanning, and a third for incident response. 

**Now Why does int enhance scalability in a cloud environment ?**

Imagine a cyber-attack, the threat monitoring service experiences a significant increase in demand. 

In a cloud environment, this specific microservice can be dynamically scaled up, leveraging cloud resources (such as additional compute instances) to handle the increased load. This scaling is independent and does not require scaling of the other services, which may not be experiencing increased demand. Thus, the vulnerability scanning and incident response services continue to operate efficiently without the additional load, maintaining overall system performance and responsiveness.

## Q7: What is statelessness and why is it important in microservices architecture ?
**Statelessness** means the service does not store any state about the client session on the server side. In microservices, statelessness is important as it makes services easier to scale and redeploy. It also ensures that any instance of the service can handle any request, making the system more resilient and load-balancing more effective.

## Q8: What purposes does an API Gateway serve ?
An **API Gateway** acts as a single entry point for all clients. It routes requests to the appropriate microservice, aggregates the responses, and handles cross-cutting concerns like authentication, SSL termination, and rate limiting. This simplifies the client's interaction with the backend and provides a central place for monitoring and security.
