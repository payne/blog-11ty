---
title: "Using DTOs in Spring Boot MVC applications"
date: "2020-12-13"
template: "post"
draft: false
slug: "/posts/DTOjavaSpring"
tags:
  - "spring-boot"
  - "java"
category: "Java"
layout: layouts/post.njk
description: "Using Data Transfer Objects in Spring MVC is a good tradition?"
---

Many spring boot applications use Spring MVC to provide RESTful APIs or create a GUI for a web browser.
These applications frequently use DTO (data transfer objects) in the controller layer instead of using JPA `@Entity` classes everywhere.

Is this [cargo cult programming](https://en.wikipedia.org/wiki/Cargo_cult_programming) or a good idea?  My opinion is that it's a good idea, except for very tiny applications.   

I'm in favor of:
1. [Thymeleaf](https://www.thymeleaf.org/) and `@Controller` layer share DTOs
1. These DTOs should be simple as possible...
1. DTOs are passed from the `@Controller` layer to/from the `@Service` layer.
1. The `@Service` layer uses the DTOs to build `@Entity` objects for use with the JPA `@Repository` objects.  Lazy loading in JPA is sweet.
`@Service` classes loop through the `@Entity` objects to build the DTOs.  This way the logic around pagination and lazy loading is isolated
to the `@Service` classes.



## References

1. Popular static analysis tool, SonarQube has a rule: [Persistent entities should not be used as arguments of "@RequestMapping" methods](https://rules.sonarsource.com/java/tag/spring/RSPEC-4684) failure to follow this rule results in a critical finding.
1. [How evil are Data Transfer Objects (DTOs)?](https://www.adam-bien.com/roller/abien/entry/how_evil_are_actually_data) is a post from 2009 (pre spring boot, but not spring).  It talks about how DTOs are a common solution to a common problem and that DTOs are not perfect.
1. StackOverflow has a nice discussion of [How to use DTOs in the Controller, Service and Repository pattern](https://stackoverflow.com/questions/61303236/how-to-use-dtos-in-the-controller-service-and-repository-pattern) 

There are many reasons 
[Andreas](https://stackoverflow.com/users/5221149/andreas)'s answer is great.  It acknowledges that in small projects people sometime use `@Entity` classes in the MVC layer and the importance of not doing that as projects get larger.

I'll 
quote 
[Andreas](https://stackoverflow.com/users/5221149/andreas)'s 
answer below, in the rest of this post, (because it's a great answer):

In today programming with Spring MVC and interactive UIs, there are really 4 layers to a web application:

* UI Layer (Web Browser, JavaScript)

* MVC Controller, i.e. Spring components annotated with @Controller

* Service Layer, i.e. Spring components annotated with @Service

* Data Access Layer, i.e. Spring components annotated with @Repository

Every time one of these layers interact with the underlying layer, they need to send/receive data, which generally are POJOs, to transfer the data between layers. These POJOs are DTOs, aka Data Transfer Objects.

Only DTOs should be used between layers, and they are not necessarily the same, e.g. the Service Layer may apply business logic to DTOs received from the Data Access Layer, so the DTOs of the Service Layer API is different from the Data Access Layer API. Similarly, the Controller may rearrange the data to prepare it for presentation (grouping, summaries, ...), so the data sent to the web browser is different from the data received from the Service Layer.

With full abstraction, the Data Access Layer's API should not reflect the technology of the Data Access, i.e. whether it is using JDBC, JPA, NoSQL, a web service, or some other means of storing/retrieving the data. This means that Entity classes shouldn't make it outside the Data Access Layer.

Most projects don't need that level of abstraction, so it is common for a DTO to be an Entity class, and to flow all the way from the Data Access Layer to the Controller, where it is used either by a View, or is send to the web browser, encoded as JSON.

It depends on the size and complexity of the project. The bigger the project, the more important it becomes to make each layer as abstract/standalone as possible.

