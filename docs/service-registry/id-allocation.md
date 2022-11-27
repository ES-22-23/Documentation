---
id: service-registry-id-attribution
title: Unique Id Attribution
tags:
- Micro-Service
- Technical Docs
sidebar_position: 3
---

Besides allowing services to register themselves in our system the Service Registry also attributes dinamically an Id to each service that is being registered in our system. The Ids that are attributed are selected from a pole of Ids set in the Spring application configuration. With the integration between the Service Registry and the Configuration Service we can easily change the configuration to add or remove more Ids to the pole.
