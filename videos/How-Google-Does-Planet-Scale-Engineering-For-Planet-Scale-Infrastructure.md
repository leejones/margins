## How Google Does Planet-Scale Engineering for Planet-Scale Infrastructure

* source: https://www.youtube.com/watch?v=H4vMcD7zKM0
* speaker: Melissa Binde
* tags: SRE, on-call, DevOps

Developers are rewarded for features. Operators are rewarded for uptime. New features (change) typically decreases uptime. The two incentives are opposed and each group will work against or around the other in order to achieve their goal.

Developers report to product managers. SREs report to production.

The SRE framework is a set of clear rules that removes the need for negotionation and power struggles between developers and operations.

An SRE is expected to spend 50% of their time on project work. Non-project work is on-call, tickets, meetings (reactive stuff). Project work is proactive (reducing latency by switching data stores, tooling, automation). If an SRE spends less than 50% of their time on project work, then there is something wrong with the service(s) they suport and/or the way they are supporting them (not automating tasks or fixing problems etc.).

SREs at all experience levels go through periodic training for on-call. It's game day scenarios.

When on-call, the SRE has the authority to make the decision and the VP will have their back. If they need to shut down the site then that's what they do.

On-call focuses on restoring service first, then troubleshoot later.

Blameless postmortems are critical to learning.

Alerts should be novel situations, not routine (boring) scenarios. Fix common issues or automate the response.

See also [notes on High Scalability](http://highscalability.com/blog/2016/7/18/how-does-google-do-planet-scale-engineering-for-a-planet-sca.html) from the talk.
