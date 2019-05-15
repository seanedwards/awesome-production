# Building Awesome Production Services

# Architecture

## Surface Area

The full scope of externally accessible surface area.

## State

State storage.

### Relational Databases

#### Migrations

### Columnar/Analytics Databases

#### Migrations

### Document Stores

#### Migrations

### Key/Value Stores

#### Migrations

# Operations

## Packaging

## Deployment

### Stateless Applications

* Canaries
* Rolling deployment
* A/B Deployments

### Orchestrated Deployment

1. Disconnect from inputs
2. Drain in-flight work
3. Flush buffers
4. Reboot
5. Warm-up? Prefill caches?
6. Reconnect to inputs

## Error Handling

### Alerts and Pagers

* Actionable alerts
* Alert Fatigue

### Circuit Breakers

* Graceful failure

## Configuration

## Scale

* "Orders of magnitude" (10x 100x 1000x scale...)

# Observability

## Structured Logging

## Transaction IDs

Transaction IDs are issued when a request first hits your [Surface Area](#surface-area), and are propagated throughout other services, so that logs, errors, and other data can be associated with a specific intent from the end user.

* https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-request-tracing.html
* https://opentracing.io/
* https://www.honeycomb.io/

# Security

## Authentication

## Authorization

## Auditing

