# Java
### Jackson
Jackson is a popular Java library used for converting Java objects to and from JSON.
It’s the default JSON processor in Spring Boot.

When the microservice receives or returns data via REST APIs, Jackson automatically converts:
	•	Incoming JSON (from requests) into Java objects => deserialization
	•	Outgoing Java objects (responses) into JSON => serialization

### ObjectMapper
ObjectMapper is the core class from the Jackson library that enables actual conversion between Java objects and JSON.

Purpose of ObjectMapper:
	1.	Serialize Java objects to JSON:
String json = objectMapper.writeValueAsString(myObject);

This is useful when sending JSON responses from your service.

	2.	Deserialize JSON to Java objects:
MyObject obj = objectMapper.readValue(jsonString, MyObject.class);

This is useful when processing incoming API requests or reading data from MongoDB or external APIs.


### Serialization & Deserialization
### Mapstruct
### Entity vs DTO
### 100% Object Oriented or not
### Memory areas
### Garbage collection
### String, StringBuffer, StringBuilder
### Stream vs ParallelStream
### Functional programming
### Concurrent Modification Exception
### ShallowCopy vs DeepCopy

# RESTful API
### HTTPs methods
### Rest API Security Design principles

# Spring
### End to End Architecture or Flow
### Spring Security
### Spring Profiles
### Spring Bean

# Maven

# MongoDB

# Docker

# Kubernetes
### Your application stores order data in MongoDB Cloud (eg. Atlas). Should you deploy it as a Deployment or StatefulSet? Why?
Since, MongoDB is not hosted inside Kubernetes, your application should be deployed as a `Deployment`. <br>
The app interacts with MongoDB as an external managed service, not within your cluster. <br>
The application: <br>
	- Does not store state between requests. <br>
	- Sends data to or queries data from MongoDB Cloud. <br>
MongoDB’s persistence and state are managed outside Kubernetes and is handled by the cloud provider. <br>
Therefore, your application is still stateless, and a Deployment is the right choice. <br>

### Your application stores order data in MongoDB hosted inside Kubernetes cluster. Should you deploy it as a Deployment or StatefulSet? Why?
You should deploy your application (Java + Spring Boot) as a Deployment, and MongoDB as a StatefulSet. <br>

# Architecture
### Stateful vs Stateless applications
`State` meaning `user/session data`.

Stateless application: <br>
**1. Definition:**
- The app `does NOT remember any user/session data` between requests.
- Each request is `independent` and contains all info needed to process it.

**2. Behavior:**
- The app reads/writes state only from an `external source` like MongoDB, and does not rely on in-memory session data.

> Example: Your Spring Boot app receives an order request with all necessary data. It saves the order directly in MongoDB and doesn’t keep anything about that user’s order in memory between requests.

**3. Pros:**
- Easier to scale (any server can handle any request).
- More resilient (stateless servers can restart without losing session info).

**4. Cons:**
- Every request must include all necessary info.
- May involve more database calls.

Stateful application: <br>
**1. Definition:**
- The app `remembers the user/session data` between requests.
- It stores some state `in memory` or somewhere local (not only in the database).

**2. Behavior:**
- Each user/session is “tied” to some server or instance because it holds specific info about the session.

> Example: Imagine your Spring Boot app stores the user’s current shopping cart `in memory` on the server during the session (not just in MongoDB). If the user sends multiple requests, the app remembers the cart state.

**3. Pros:**
- Easy to implement session logic.
- Faster access to user session data (in-memory).

**4. Cons:**
- Scaling is harder because user state is on a particular server (need sticky sessions or session replication).
- If the server crashes, session data is lost.

### SOLID principles
### Idempotent
### ACID properties
### Jwt
### Zero Trust Architecture
