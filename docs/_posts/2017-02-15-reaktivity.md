---
title: Reaktive HttpServer
date: 2017-02-17 10:00:00
authors: [jfallows]
categories: [home]
---

![Reaktivity logo]({{ site.url }}/assets/images/reaktivity.png)

# Reaktive HttpServer

## The Reaktivity Project 

### Introduction

When monolithic applications are decomposed into microservices, the architecture must rely on network protocols to communicate between the distributed components. Therefore, when scaling microservices it is necessary to scale the entire application stack of networking protocols and microservices logic.

The Reaktivity Project uses shared memory streams to directly communicate between each different layer in the application stack, including both the networking protocols and the microservices logic. Parallel execution of each layer in the application stack takes full advantage of the available CPU cores to maximize throughput with predictably low latency.

Recognizing that large systems can have 1000s of CPU cores, this technology can be deployed economically in the cloud to provide affordable real-time solutions.

<!--more-->

### Status Quo

The built-in Java HttpServer bundled since JDK6 provides a simple application stack to support HTTP and HTTPS microservices.

Despite using non-blocking IO, the built-in Java HttpServer in JDK8 still attempts to scale up by allocating a thread per connection. Other implementations of the same application stack scale up more efficiently by using non-blocking IO to handle multiple connections per thread.

However, in both scenarios the entire application stack is executed on the same thread to process an HTTP request. When multiple HTTP requests are being processed in parallel, each thread executes all layers of the application stack, as shown in the diagram below.
