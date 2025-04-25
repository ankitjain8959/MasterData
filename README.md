# Java
- Jackson
Jackson is a popular Java library used for converting Java objects to and from JSON.
It’s the default JSON processor in Spring Boot.

When the microservice receives or returns data via REST APIs, Jackson automatically converts:
	•	Incoming JSON (from requests) into Java objects => deserialization
	•	Outgoing Java objects (responses) into JSON => serialization

- ObjectMapper
ObjectMapper is the core class from the Jackson library that enables actual conversion between Java objects and JSON.

Purpose of ObjectMapper:
	1.	Serialize Java objects to JSON:
String json = objectMapper.writeValueAsString(myObject);

This is useful when sending JSON responses from your service.

	2.	Deserialize JSON to Java objects:
MyObject obj = objectMapper.readValue(jsonString, MyObject.class);

This is useful when processing incoming API requests or reading data from MongoDB or external APIs.



- Serialization & Deserialization
- Jackson, ObjectMapper
- Mapstruct
- Entity vs DTO
- 100% Object Oriented or not
- Memory areas
- Garbage collection
- String, StringBuffer, StringBuilder
- Stream vs ParallelStream
- Functional programming
- Concurrent Modification Exception
- ShallowCopy vs DeepCopy

# RESTful API
- HTTPs methods
- Rest API Security Design principles

# Spring
- End to End Architecture or Flow
- Spring Security
- Spring Profiles
- Spring Bean
  
# Architecture
- SOLID principles
- Idempotent
- ACID properties
- Jwt
- Zero Trust Architecture

# Maven

# MongoDB

# Docker

# Kubernetes
