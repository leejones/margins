# Notes from Watching "Paasta - Platform for Services at Yelp"

* source: https://vimeo.com/121183491 (starts about 9:45)
* speaker: Evan Krall
* tags: PaaS, service oriented architecture, migration

## Paasta

Internal PaaS - build/deploy/connect/monitor services

Opinionated glue for open-source software.

## Motivation

* moving to Service Oriented Architecture
* many servers
* many developers
* many services
* many data centers

## Design goals

### Operations

* interoperate with existing systems
* fault tolerance
* machine mobility
* efficient use of resources
* no SPOFs


### Service authors

* easy setup
* easy deployment
* isolation
* control over what you care about
* pleasant interface

## Declarative control (instead of imperative)

* Describe the end goal, not the path to get there.
* Helps achieve fault tolerance.

> Deploy 12abcd34 to prod"

vs.

> Commit 12abcd34 should be running in prod

Gas pedal vs cruise control.

## Components

### Docker

Every service runs in containers.

* Isolation from other services
* Consistency across dev, ci, production
* Isolation from host

### Git

* source for services
* used for control of Paasta
* declare what you want with a git commit
* service configuration

### Jenkins

* builds Docker images
* pushes to Docker registry
* marks image for deployment

### Marathon

* managing services
* like ASG for Mesos
* supervision
* fault tolerance
* efficient resource allocation

They don't expose the marathon API. Everything is controlled declaratively through git.

> I don't care which boxes run which services - let a computer figure it out.

### Smartstack

Service registration and discovery.

Zookeeper + HAProxy (locally) connecting a service to its service dependencies.

## Process

1. git push to repo
2. jenkins builds docker image, runs tests
3. jenkins push image to docker registry
4. jenkins tags image in git repo
5. marathon tells servers to run container
6. marathon + sensu monitor deployment progress
