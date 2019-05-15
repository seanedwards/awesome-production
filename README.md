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

## Error Handling

### Circuit Breakers

## Configuration

## Scale

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

