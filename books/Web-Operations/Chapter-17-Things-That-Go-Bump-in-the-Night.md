# Reading notes from Web Operations: Chapter 17 - Things That Go Bump in the Night (and how to sleep through them)

* source: [Web Operations](http://www.amazon.com/Web-Operations-Keeping-Data-Time/dp/1449377440)
* tags: on-call, disaster recovery, high availability

## BCP

Buisness Continuity Plan - simple definition: "two of everything"

Forms of high availablility:

* hot/hot: reads and writes from either location
* hot/warm: reads from either location, writes to one
* hot/cold: reads and writes to one location (failover usually untested so is never used)
* disaster recovery: reads and writes to one location, rebuild in case of emergency

RTO - recovery time objective (how long it takes to get the site up after an outage)
RPO - recovery point objective (how much of the latest data are you willing to loose?)

RTO and RPO are often at odds with one another.

Impact duration - how long an issue affects you
Incident duration - how long the issue lasts

You don't necessarily have to be impacted for the entire duration of the incident. Use failover.

## How many data centers do you need?

How many data centers do you need (assuming a single failure at any given time)?

* 2 - additional complexity, but need 50% extra capacity in each to handle failover
* 3 - much higher complexity than 2, but need 33% extra capcity in each to handle failover
* 4 - slightly higher complexity than 3, but only need 25% extra capacity in each for failover

More locations can lead to better performance because of things like GSLB (Global Server Load Balancing), but consistency of data will be a challange.

You can compromise by favoring consistency for data (ex. 2 locations in hot/warm setup) and favoring performance for application servers (ex. 4 locations).

## Trust Nobody

Use multiple providers (ex. CDNs or DNS), especially if the provider has many customers. Any of those customers could become the target of a DDOS attack and you will experience the residual effects.

## Failover

Make failover a non-event by using your BCP to accomodate every day tasks like maintence and zero downtime deployments.

Make failover a regular part of the job and not a crisis.

Treat failover as risk mitigation instead of disaster recovery.

## Alerts

Document and review alerts often to make sure people do not get fatigued by noise alerts.

Tune alerts and thresholds to the point where you only get the most important ones.

A few alerts a week is a good goal.
