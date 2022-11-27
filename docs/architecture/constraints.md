---
id: architecture-constraints
title: Architecture Constraints
tags:
- Architecture
- Technical Docs
sidebar_position: 1
---

# Architecture Constraints

Our system is expected to handle a huge amount of clients. These clients may have multiple buildings with multiple cameras and alarms. Our system will need to process all the data being transmitted by those clients to check if there are intruders or not. 

Once the data being transmitted is heavy (video data), our system needs to be very scalable and efficient so it can process all the data being received.

Once we are developing a system that will assist companies with their security, its availability is a critical constraint, i.e., our system should be always available and should be always processing data received from our client's cameras and triggering the necessary alarms when needed. 

It is important for our clients to be able to review the footage of their cameras whenever an intruder is detected, therefore, our system will also need to use an external storage service to store this data and make it available to our clients whenever they request it.