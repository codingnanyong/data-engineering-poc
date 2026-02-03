# Data Engineering POC

[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![Docker Compose](https://img.shields.io/badge/Docker%20Compose-Supported-2496ED?logo=docker&logoColor=white)](https://docs.docker.com/compose/)

This repository contains proof-of-concept configurations and guides for data engineering infrastructure components, all deployable with Docker Compose.

## 📋 Overview

This POC provides ready-to-use Docker Compose setups for:

- **Databases**: PostgreSQL, MongoDB, InfluxDB
- **Container Registry**: Docker Private Registry (TLS-enabled)
- **Offline Setup**: Docker installation for restricted/air-gapped environments

## 📁 Directory Structure

| Directory | Description |
| --- | --- |
| [`postgres/`](./postgres/) | PostgreSQL relational database |
| [`mongodb/`](./mongodb/) | MongoDB document database (with TLS) |
| [`influxdb/`](./influxdb/) | InfluxDB 2 time-series database |
| [`registry/`](./registry/) | Docker Private Registry (SSL/TLS) |
| [`docker_install(no enternet)/`](./docker_install(no%20enternet)/) | Docker & Docker Compose offline installation guide |

## 🚀 Quick Start

### Prerequisites

- Docker and Docker Compose installed
- For offline environments: see [Docker Installation Guide](./docker_install(no%20enternet)/README.md)

### Running a Component

Each subdirectory contains its own `docker-compose.yml`. Navigate to the desired component and run:

```bash
cd postgres   # or mongodb, influxdb, registry
docker-compose up -d
```

## 📚 Component Guides

| Component | Port | Documentation |
| --- | --- | --- |
| **PostgreSQL** | 5432 | [postgres/README.md](./postgres/README.md) |
| **MongoDB** | 27017 | [mongodb/README.md](./mongodb/README.md) |
| **InfluxDB** | 8086 | [influxdb/README.md](./influxdb/README.md) |
| **Docker Registry** | 5000 | [registry/README.md](./registry/README.md) |
| **Docker Install (Offline)** | - | [docker_install(no enternet)/README.md](./docker_install(no%20enternet)/README.md) |

## 🔧 Common Notes

- **Network**: Several components expect an external Docker network (e.g. `storage_network`). Create it with:

```bash
docker network create storage_network
```

- **Environment**: Copy `.env.example` to `.env` in each directory and set values before running.
- **Data Persistence**: Volumes are configured for data persistence; paths may need adjustment per deployment.

## 📃 License

Copyright © Changsin Inc. All rights reserved.

## 🤝 Contributing

Contributions are welcome. Feel free to open issues or submit pull requests.
