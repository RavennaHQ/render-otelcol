# OpenTelemetry Collector and Prometheus Render Blueprints

This repository contains Render blueprint files for hosting an OpenTelemetry (OTEL) Collector and Prometheus. These blueprints facilitate the deployment and configuration of these services on the Render platform.

## Repository Structure

- `otelcol/`
  - `Dockerfile`: Dockerfile for building the OTEL Collector image.
  - `otel-collector-config.yaml`: Configuration file for the OTEL Collector.
- `prometheus/`
  - `autometrics-rules.yml`: Prometheus rules for autometrics.
  - `Dockerfile`: Dockerfile for building the Prometheus image.
  - `prometheus.yml`: Configuration file for Prometheus.
- `render.yaml`: Render blueprint file for deploying the services.
- `README.md`: This file.

## Services

### OpenTelemetry Collector

The OTEL Collector is configured using the [`otel-collector-config.yaml`](otelcol/otel-collector-config.yaml) file. It includes receivers, processors, extensions, and exporters to handle telemetry data.

### Prometheus

Prometheus is configured using the [`prometheus.yml`](prometheus/prometheus.yml) file. It includes global settings, rule files, and scrape configurations.

## Deployment

The deployment is managed using the [`render.yaml`](render.yaml) file, which defines the services, their configurations, and environment variables for the Render platform.

## Usage

1. **Build and Deploy OTEL Collector**:
   - The OTEL Collector Docker image is built using the [`otelcol/Dockerfile`](otelcol/Dockerfile).
   - The configuration is added from the [`otel-collector-config.yaml`](otelcol/otel-collector-config.yaml) file.

2. **Build and Deploy Prometheus**:
   - The Prometheus Docker image is built using the [`prometheus/Dockerfile`](prometheus/Dockerfile).
   - The configuration is added from the [`prometheus.yml`](prometheus/prometheus.yml) file.

3. **Render Deployment**:
   - The services are defined in the [`render.yaml`](render.yaml) file, specifying the Dockerfile paths, context, and commands for running the containers.

## Environment Variables

- `PORT`: Set to `9090` for Prometheus to ensure it listens on the correct port as specified in the [`prometheus.yml`](prometheus/prometheus.yml) file.

## Additional Information

For more details on configuring and using Render blueprints, refer to the [Render documentation](https://render.com/docs).
