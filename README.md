# Edge-AI Demand Forecasting & Business Analytics Platform

This project implements a complete end-to-end Edge-AI system designed for retail chains that want real-time, store-level forecasting with centralized analytics and enterprise-grade MLOps.

The platform demonstrates how AI models can be trained in the cloud, deployed to thousands of edge devices, monitored continuously, and used to generate live business insights.

Key Capabilities
1. AI at the Edge (Edge Device Runtime)

Each store runs a lightweight LSTM forecasting model locally on an edge device.

Features:

Real-time inference (no internet required)

Local model lifecycle management

Auto-update when a new version is published

Sensor ingestion (simulated footfall, sales, weather)

Forecast API running directly on the device

Telemetry reporting back to the cloud

2. Cloud Model Registry (Central Model Hub)

A dedicated Flask-based registry server stores and distributes all model versions.

Edge devices poll the registry for the latest model

Cloud MLOps pipelines push new models automatically

Tracks metadata like version, store, timestamp

Allows multi-store A/B deployments

3. Automated MLOps Pipeline

A full CI/CD workflow for packaging and deploying ML models:

Package trained .pt model + metadata

Compute integrity hashes

Upload to registry

Edge devices automatically fetch, verify, and load the update

Version-controlled rollouts

This is exactly how large retail/IoT companies manage ML updates at scale.

4. Cloud Telemetry & Business Analytics

Every edge device sends telemetry back to the cloud (errors, inference stats, model version, device health).

Cloud analytics API provides:

Store-level forecasting summaries

Model performance monitoring

Aggregated KPI dashboards

Usage logs for compliance

Root-cause diagnostics

5. End-to-End Demo Workflow

The project includes a complete runnable demo:

Train model -> generate lstm_v1.pt

Package model

Deploy to registry

Edge device fetches new model

Sensor simulator generates real-time data

Forecasts run live on the device

Telemetry flows back to the cloud

Analytics API exposes aggregated business metrics

Everything is runnable with simple commands.
