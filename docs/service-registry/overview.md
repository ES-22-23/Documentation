---
id: service-registry-overview
title: Overview
tags:
- Micro-Service
- Technical Docs
sidebar_position: 1
---

The **Service Registry** allows the micro-services to register themselves and to check the status of the remaining ones. Using the Service Registry is also possible to obtain more details about the micro-services running in our system. Besides storing information about each one of the registered services like their addresses and their IDs, our Service Registry has a set of features that are important for our system:

* [Micro-Services Status](./micro-services-status.md)
* [Unique Id attribution](./id-allocation.md)
* [Smart ID allocation](./id-allocation.md)

## Problem statement

In our system, we are using the Elastic Load Balancer from AWS, which, in addition to distributing the load equally across the different service instances in our system, also plays the role of a Discovery Router insofar as our services are deployed in containers managed by ECS automatically “register” themselves with the ELB, making their address known and allowing other services to contact them using the Load Balancer DNS together with a port associated with a particular service.

However, for cameras and alarms the discovery service built into the ELB is not enough, as in this case we not only need to know where to send traffic, but also to know details about the cameras and alarms. We need to know how many cameras there are, we need to associate them with a unique ID, whether they are connected or not (the same applies to alarms). Thus, it is necessary to think of another solution that solves this problem.

### Goals

- Get a list of cameras that are available for registration;
- Check the status of cameras and alarms - know if they are online or offline;
- Be able to communicate with specific cameras and alarms;
- Assign a unique ID to cameras and alarms (UUID);

### Non-goals

- Create a state in the cameras - make sure that the same ID is always associated with the same process. This is out of *Scope* because we are dealing with cameras that are actually virtual processes and that have different conditions in each deployment.

## Proposed solution

To solve the problem, we are going to create a new micro-service that will act as a Client-Side Service Discovery - i.e., it will only provide information about the IP of a camera or alarm, not dealing with the forwarding logic or Load Balancing. This system will provide Self-Registration, i.e., cameras and alarms must ask to register for service discovery.

# Alternative solutions

Use a ready-made Service Discovery like Eureka or Consul. We won't do that as these services contain unnecessary complexity for our use case.

# Implementation and rollout plan

The project will be implemented using Spring Boot and a MySQL database.