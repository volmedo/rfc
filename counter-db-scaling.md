# Counter Service Data Backend Scalability

## Abstract

## Introduction

Counter is an event ingestion service. As such, it reads events published by other services and stores relevant metadata about them in a database. This metadata can then be queried to present the user with helpful graphical representations in the metrics analytics UI.

[[MAYBE ADD GRAPH HERE]]

Counter was implemented long ago with the main goal of being flexible enough to count any kind of events, without a specific use case in mind. Back when the team designed the service, it was decided to use an SQL database as the data backend for the service, mainly because most other services in the company use relational databases and there is a data infrastructure operations team in charge of large SQL on prem database clusters.

## The problem

## Potential solutions

## Proposed path forward
