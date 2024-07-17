# Telemetry cost optimization

This repository contains techniques for reducing cost of observability data (metrics, logs, traces).

> In fact, according to Charity Majors of Honeycomb, the total cost of observability at an organization today is equivalent to up to 30% of total infrastructure spending. That’s a truly astounding figure, if you think about it. For every dollar spent on the infrastructure that powers applications, 30 cents ends up paying just for the tools and services needed to make sure the apps running on that infrastructure are doing what they’re supposed to.

From https://devops.com/observability-costs-are-too-damn-high/

## Logs

* Deduplication - remove duplicated logs and emit metrics for each occurrence
* Generate metrics from logs

## Traces

* Sampling
  * Head based
  * Tail based
* Generate metrics from traces

## Metrics

* Downsampling - aggregate multiple data points into a single point based on a specific interval
  * Reduces storage requirements
  * Improves query performance
  * Maintains older data at a usable resolution
* Don't collect metrics that are never queried

### Dynamically enable metrics collection

https://github.com/observ-vol-mgt/observ-vol-mgt

## Cross signal techniques

* Remove unnecessary attributes (e.g. UID attributes `k8s.deployment.uid`, `k8s.replicaset.uid` etc.)
* Lower data retention
* Turn off monitoring for not important workloads
* Use cheap, easy to operate in-cluster stores for majority of the data and export only the most important data to expensive SaaS solutions

# OpenTelemetry collector components


* [countconnector](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/connector/countconnector) create counters from logs, traces and metrics

# Companies in this space

* https://www.mezmo.com/ - Mezmo Telemetry Pipeline: Profile your telemetry data to Understand clearly. Make informed choices to Optimize with ease. Take action to Respond rapidly.
* https://edgedelta.com/ - Introducing the world's only platform architected to analyze petabytes with AI
