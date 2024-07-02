# Counter Service Data Backend Scalability

## Author

## Abstract

## Introduction

Counter is an event ingestion service. As such, it reads events published by other services and stores relevant metadata about them in a database. This metadata can then be queried to present the user with helpful graphical representations in the metrics analytics UI.

[[MAYBE ADD GRAPH HERE]]

Counter was implemented long ago with the main goal of being flexible enough to count any kind of events, without a specific use case in mind. Back when the team designed the service, it was decided to use an SQL database as the data backend for the service, mainly because most other services in the company use relational databases and there is a data infrastructure operations team in charge of large SQL on prem database clusters.

## The problem

The team that designed Counter was disbanded and the service has been running in production for some time now without supervision or maintenance. Without clear ownership, no new features have been added and the original logic has not been adapted to new requirements.

The most pressing issue with Counter is that the service has maxed out the single table it uses to store event metadata to the point that the file where the data lives is about to reach the maximum size supported by the underlying filesystem (16 TiB). This situation impacts several stakeholders, both internal and external, in different ways:

- Customers are affected due to missing data points and increased latency, with some queries taking unreasonable time to complete.

- Internally, the service is also posing a range of operational issues for the data infrastructure team, who struggle to keep its database up.

- It is difficult for the engineering team now owning the service to maintain it adequately or implement new features because of the delicate situation. Given the rate of events being ingested and the poor performance of the database, even deploying new versions causes spikes in queued messages, with a high risk of aggravating the issue and causing downtime.

- Because of this, Product cannot add or change features, hindering the company’s capacity to deliver value to customers.

Given the impact on customers and the operational implications, measures to solve the issue, or at least mitigate its effects, need to be implemented quickly.

## Potential solutions

## Proposed path forward
