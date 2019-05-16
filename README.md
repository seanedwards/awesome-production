---
---
# Building Awesome Production Services

# Architecture

## Planning

Weeks of programming can save you hours of planning.

Measure twice cut once.

## Surface Area

The full scope of externally accessible surface area.

## State

State storage. 

### Relational Databases

#### Scaling Write Performance

#### Scaling Read Performance

#### Migrations

### Columnar/Analytics Databases

#### Scaling Write Performance

#### Scaling Read Performance

#### Migrations

### Document Stores

#### Scaling Write Performance

#### Scaling Read Performance

#### Migrations

### Key/Value Stores

#### Scaling Write Performance

#### Scaling Read Performance

#### Migrations

## Documentation

# Operations

## Dependency Management

* Licensing
* Vulnerability scanning

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

## Transaction Tracing

Transaction IDs are issued when a request first hits your [Surface Area](#surface-area), and are propagated throughout other services, so that logs, errors, and other data can be associated with a specific intent from the end user.

* https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-request-tracing.html
* https://opentracing.io/
* https://www.honeycomb.io/

# Security

## Authentication

## Authorization

## Auditing

