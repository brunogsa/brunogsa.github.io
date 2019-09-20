---
title: "Introduction to Instana"
metaTitle: "Introduction to Instana"
metaDescription: "An overview of this amazing monitoring tool"

date: "2019-09-13"
author: "Bruno Agostini"
---

## Goal

In this documents I wanna go through what Instana does and how it can help you in a more pragmatic way than its official docs.

## Instana Overview

Instana is a `Performance Monitoring` tool that offers automatic monitoring for your infrastructure and applications.

## Known Companies using it

- None :(

## Popular Alternatives

- Datadog
- NewRelic

Popularity Comparison on StackShare:
![Popularity Comparison on StackShare](http://i.imgur.com/Jgw26Kw.png "Popularity Comparison on StackShare")

## How it works

- You need an configured environment to work with Instana: either on Cloud or On-Premise
- Then, you need to install a [proper agent](https://docs.instana.io/quick_start/agent_setup/) onto every host of your system
- Each agent will have one or more [sensors](https://docs.instana.io/quick_start/agent_sensors/)
- Instana will automatically make the rest for you, once it has administrative permissions

### Agent Options

- For Docker Containers, it's recommended that you use their base image
- It also integrates with Kubernetes
- There're agents for Linux and Windows, but [partial support for MacOS](https://docs.instana.io/quick_start/agent_setup/other/)
- There's an agent for AWS environments as well

## Relevant Sensors and Integrations

- PHP
- Node.js
- Golang
- Python
- Ruby
- Java
- GraphQL
- ElasticSearch
- Grafana
- Redis
- MySQL
- PostgreSQL
- MongoDB
- CockroachDB
- Jenkins
- Consul
- Zookeeper
- Docker
- Kubernetes
- Nginx
- HAProxy
- RabbitMQ
- Kafka
- AWS
- Azure
- Email
- Slack
- Webhooks

Some sensors may require you to install or integrate some package into your application.

## Features

- Automatic Discovery of Zones, Hosts, Clusters, Containers, DBs, APIs, Endpoints, Processes and other services
- Support for defining your own abstraction, throught Application Perspectives
- Performance metrics gathering
- Real-time graph of the interconnections of your discovered infrastructure, services and perspectives
- Tracing and Callstacks
- Capturing of Error Responses and logs of level WARN and ERROR
- Issues and Incidents reporter, powered by AI
- Configurable Alerts
- Release Markers*
- Gathered data is extendable throught its SDK or RESTful API

Data is [generally*](https://docs.instana.io/core_concepts/data_collection/) stored for 7 days, after that retention strategy only retains statistically significant traces and calls.

### Release Markers

Instana has an amazing feature that points in your graphs when other pieces of your system has been released.

![Release Markers](https://i.imgur.com/IzAEQq1.png "Release Markers")

The image above might be saying that a release is impacting the CPU of another Service.

To enable it, engineers must inform instana about the release events, or use the provided Jenkins plugin for a more automatic and out of the box solution.

## Infrastructure Monitoring

> Infrastructure - physical, virtual, cloud, hybrid, containerized - is the underlying layer to provide the relevant resources and services for applications.

Instana shows a 2D map, where each pillar represents an installed agent, inside a particular zone.

![Instana -> Infrastructure -> Map](http://i.imgur.com/IF6ijnz.png "Instana -> Infrastructure -> Map")

The pillar colors represents their health:
- White: healthy
- Yellow: warning level
- Red: error level

You can zoom in or out to adjust the abstraction level you're observing: zone, infrastructure, applications and then processes; or hover, for a feeling of how things are interconnected:

![Infrastructure Map .gif](https://media.giphy.com/media/mFGnOSR3ksmLX8AlKc/giphy.gif "Infrastructure Map .gif")

## Application Monitoring

On Instana docs:

> The term “application” is ambiguous, and different teams may use it to describe distinctly different things. Instead of applications, Instana provides application perspectives, in order to allow teams to capture the type of semantics that are meaningful to them.

### Application Perspectives

It's up to you to define what is an `Application Perspective` for you.  
It can be a domain, a zone, an API or whatever you want.

Generally, Application Perspectives will be a higher abstraction built over `Services`.  
But again, it's up to you to decide what's the best for your case.

As defined by Instana:

> Application perspectives are fundamentally groups of calls, and which calls match depends on tags.
> Every call that matches these conditions is associated to this application, as well as calls to any database or messaging services invoked within the application.

It automatically provides some data, so you can tag things basing on them.

![Creating an Application Perspective](http://i.imgur.com/dVCB6bu.png "Creating an Application Perspective")

After defining what's an application for you, Instana will start gathering:
- Inbound Calls
- Error Rate
- Mean Latency
- Processing Time
- And many other useful info

Below we mapped an entire system as an Application Perspective.

Part of its `Summary`:  
![Instana -> Applications -> Summary](http://i.imgur.com/CyBK8OU.png "Instana -> Applications -> Summary")

Tab `Dependencies`:  
![Instana -> Applications -> Dependencies](http://i.imgur.com/yMuhj8j.png "Instana -> Applications -> Dependencies")

It can be zoomed in as well, so you can observe it in real time:  
![Instana -> Applications -> Dependencies .gif](https://media.giphy.com/media/XB2cgVYjmgEu2NHkMl/giphy.gif "Instana -> Applications -> Dependencies .gif")

You can also see the related infrastructure (clusters, containers, processess etc):  
![Instana -> Infrastructure -> Containers](http://i.imgur.com/Maf1izK.png "Instana -> Infrastructure -> Containers")

And their resources, like CPU, RAM, I/O and so on:  
![Instana -> Infrastructure -> Containers -> ContainerX](http://i.imgur.com/xvdVqKs.png "Instana -> Infrastructure -> Containers -> ContainerX")

The more agents you install, the more info you'll have access to.

### Services

As defined on Instana docs:

> A service can be seen as a logical component that provides a public API to the rest of the system, in which the API is made up of its endpoints.
> 
> Instana will automatically map services based on default rules. These rules examine call and infrastructure data and create a service as soon as it’s recognized. Additionally, teams can add a custom rules.

All visualizations and metrics gathered for Application Perspectives are also available for `Services`.  
Your databases and some APIs will be under this section.

## Website Monitoring

> Instana supports website monitoring by analyzing actual browser request times and route loading times. This allows detailed insights into the web browsing experience of end-users, as well as deep visibility into application call paths.
> 
> The Instana website monitoring solution works by means of a lightweight JavaScript agent which is embedded into the monitored website.

It offers support for both SSR and SPA websites, which can be analyzed through [Page Loads, Page Views and/or Transitions](https://docs.instana.io/products/website_monitoring/faq/#what-is-the-difference-between-page-views-loads-and-transitions).

## Conclusion

Instana is a young tool with great potencial.

It offers lots of insights with minimum integration efforts through beatiful visualizations, covering almost the entire infrastructure e application layers.

It may be specially useful to integrate in legacy systems to have a better view how it's working in a more automatic way.

## Related Links

- https://docs.instana.io
- https://opentracing.io/docs/overview/
- https://www.instana.com/blog/instana-pipeline-feedback/
- https://stackshare.io/instana
