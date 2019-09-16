---
title: "Introduction to Instana"
metaTitle: "TODO"
metaDescription: "TODO"

date: "2019-09-13"
author: "Bruno Agostini"
---

> Automatic Application and Infrastructure Monitoring

Category: Performance Monitoring

## Known Companies using it

- None :(

## Popular Alternatives

- Datadog
- NewRelic

Popularity Comparison:
![Popularity Comparison](http://i.imgur.com/Jgw26Kw.png "Popularity Comparison")

## How it works

- You need an configured environment to work with Instana: either on Cloud or On-Premise
- Then, you need to install a [proper agent](https://docs.instana.io/quick_start/agent_setup/) onto every host of your system
- Each agent will have one or more [sensors](https://docs.instana.io/quick_start/agent_sensors/)
- Instana will automatically make the rest for you, so ensure it has administrative permissions

### Agent Options

- For Docker Containers, you must use an Instana Image as a base (`FROM instana/agent`)
- It also integrates with Kubernetes
- There're agents for Linux and Windows, and partial support for MacOS
- There's a special agent for AWS environments

## Relevant Sensors (Integrations)

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

Some sensors may require you to install and integrate it into your application or service.

## Infrastructure Monitoring

> Infrastructure - physical, virtual, cloud, hybrid, containerized - is the underlying layer to provide the relevant resources and services for applications.

Instana shows a 2D map, where each pillar represents an installed agent, inside a particular zone.

Infrastructure Map on Instana:
![Infrastructure Map on Instana](http://i.imgur.com/SMIn3nE.png "Infrastructure Map on Instana")

The pillar colors represents their health:
- White: healthy
- Yellow: warning level
- Red: error level

You can zoom in or out to adjust the abstraction level you're observing: infrastructure, applications, processes etc.

Zommed in Map:
![Zommed in Map](http://i.imgur.com/Ce38akC.png "Zommed in Map")

Zoomed in on Process Level:
![Zoomed in on Process Level](http://i.imgur.com/Jc6Mb9P.png "Zoomed in on Process Level")

## Application Monitoring

> Instana introduces the next generation of APM with its application hierarchy of services, endpoints, and application perspectives across them. Our main goal is to simplify the monitoring of your business’ service quality.

### Application Perspectives

> The term “application” is ambiguous, and different teams may use it to describe distinctly different things. Instead of applications, Instana provides application perspectives, in order to allow teams to capture the type of semantics that are meaningful to them.

It's up to you to define what is an application (perspective) for you.  
It can be a domain, a zone or whatever you want.

Generally, Application Perspectives will be a higher abstraction built over Services.  
But again, it's up to you to decide what works better.

An entire system as an Application Perspective, tab Dependencies:
![An entire system as an Application Perspective, tab Dependencies](http://i.imgur.com/Cuf284B.png "An entire system as an Application Perspective, tab Dependencies")

Application Perspectives can be zoomed in as well:
![Application Perspectives can be zoomed in as well](http://i.imgur.com/A09CBF0.png "Application Perspectives can be zoomed in as well")

> Application perspectives are fundamentally groups of calls, and which calls match depends on tags.

> Every call that matches these conditions is associated to this application, as well as calls to any database or messaging services invoked within the application.

Creating an Application Perspective:
![Creating an Application Perspective](http://i.imgur.com/vMqLmHm.png "Creating an Application Perspective")

### Services

> A service can be seen as a logical component that provides a public API to the rest of the system, in which the API is made up of its endpoints. 

> Instana will automatically map services based on default rules. These rules examine call and infrastructure data and create a service as soon as it’s recognized. Additionally, teams can add a custom rules.

## Website Monitoring

> Website monitoring, often called End-User Monitoring (EUM) or Real-User Monitoring (RUM), is an important tool to understand digital user experience.

> Instana supports website monitoring by analyzing actual browser request times and route loading times. This allows detailed insights into the web browsing experience of end-users, as well as deep visibility into application call paths. The Instana website monitoring solution works by means of a lightweight JavaScript agent which is embedded into the monitored website.

It offers support for SSR and SPA websites, which can be analyzed through [Page Loads, Page Views and/or Transitions](https://docs.instana.io/products/website_monitoring/faq/#what-is-the-difference-between-page-views-loads-and-transitions).

## Conclusion

Instana is a young tool with great potencial.

It offers lots of insights with minimum integration efforts using beatiful visualizations, covering your infrastructure, APIs and websites.
