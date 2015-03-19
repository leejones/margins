# Reading notes from "Using Services to Break Down Monoliths"

* source: http://engineeringblog.yelp.com/2015/03/using-services-to-break-down-monoliths.html
* tags: soa, services, monoliths

## Major themes

## approach

* confronted the realities of distributed systems
* created a set of [basic priciples](https://github.com/Yelp/service-principles) when writing/operating services
* commited to blameless postmortems when things (inevitably) go wrong
* chose HTTP + JSON b/c of familiarity with related tooling, caching, load balancing
* used [Swagger](http://swagger.io/) to define the service interfaces

## testing

* tried running cannonical testing instances for each service, but this proved to be difficult/buggy
* instead created Docker containers for each service (including databases) to use for testing

## the stack

* chose a standard framework, database access library, metrics library, and logging library
* isolated each service's dependencies

## discovery

* created [PaaSTA](https://vimeo.com/121183491#t=9m51s) (an internal PaaS) for building, deploying, monitoring, and interconnecting apps
* using [SmartStack](http://nerds.airbnb.com/smartstack-service-discovery-cloud/) and [ZooKeeper](http://zookeeper.apache.org/)

