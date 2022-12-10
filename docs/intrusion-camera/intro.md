---
id: intrusion-cameras-intro
title: Introduction
tags:
- Intrusion
- Cameras
sidebar_position: 1
---
# Introduction

A camera instance is composed of two partsthat run asynchronously. The Camera and the flask server.

## Camera
The Camera starts a RabbitMQ connection with the humand detection model to send it's video to detect if an intrusion ocurred. Then starts a RabbitMQ connection to the Intrusion Management API. When a message is received the camera reads the timestamp value from it and sends a POST request to the intrusion API with a cut of the video 3 minutes before and after that timestamp. 


## Flask Server
The Flask Server has only one endpoint "/health". This endpoint is used to check if the camera is available and running.
