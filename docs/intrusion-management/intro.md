---
id: intrusion-management
title: Intrusion Management API
tags:
- Intrusion Management API

sidebar_position: 1
---
# Sites Management API

## Description
This API acts whenever an intrusion is detected. It will get the intrusion video clips from the cameras and activate the alarms.
 


## Endpoints

- intrusion - post endpoint to when an intrusion is detected. This endpoints sends a message with rabbit mq to all the cameras requesting the video clips from the camera with a certain ID in a certain timestamp.

- video_clips - post endpoint where the camera sends the video clips that are store in AWS S3.


