# 🔄 MongoDB Round-Robin Sharding with Docker Compose

![MongoDB](https://img.shields.io/badge/MongoDB-7.0-green)
![Docker](https://img.shields.io/badge/Docker-24.0-blue)
![High Availability](https://img.shields.io/badge/HA-3--node-orange)

## 📌 Overview
Distributes each shard's components across multiple EC2 instances for maximum fault tolerance.

```mermaid
graph LR
    subgraph EC2-1
        A[Shard1-Primary] --> B[Shard2-Secondary]
        B --> C[Shard3-Arbiter]
    end
    subgraph EC2-2
        D[Shard2-Primary] --> E[Shard3-Secondary]
        E --> F[Shard1-Arbiter]
    end
    subgraph EC2-3
        G[Shard3-Primary] --> H[Shard1-Secondary]
        H --> I[Shard2-Arbiter]
    end
