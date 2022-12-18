---
id: intrusion-alarms-intro
title: Introduction
tags:
- Intrusion
- Alarms
sidebar_position: 1
---
# Introduction

An alarm instance is composed of two parts that run asynchronously. The Activate Alarm Functionality and the flask server.

## Activate Alarm Functionality
The Activate Alarm Functionality (AAF) consists of a RabbitMQ Consumer with an Alarm ID, a Property ID and an atribute to check if is ativate.
First the AAF sends a request to the Service Registry to get an Alarm ID. Next, send a request to the Site Management API to request his Property ID. Finally, it connects to a RabbitMQ connection as a consumer to receive message from the Intrusion Management API. If the alarm's Property ID match the Property ID of the message, the alarm is activated for 30 seconds.


## Flask Server
The Flask Server has only one endpoint "/health". This endpoint is used to check if the alarm is available and running and to check if the alarm is "ringing" (activate).


# API Documentation

https://documenter.getpostman.com/view/24950294/2s8YzZPKBS
