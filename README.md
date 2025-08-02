
---

## 🎯 Kafka in This Project

Apache Kafka acts as the **central event streaming backbone** enabling:

- **Asynchronous Communication** between services (decoupled systems)
- **Event-Driven Architecture**: e.g., Order Created → Inventory Updated → Payment Processed
- **Durability** and **scalability** of messages
- **High throughput** for real-time event processing

Kafka setup variations:

| Phase | Kafka Mode      | Broker Setup  | Notes                      |
|-------|------------------|----------------|-----------------------------|
| 1     | No Kafka         | –              | Simple monolith             |
| 2     | Dev Mode         | 1 broker       | Dockerized single instance  |
| 3     | KRaft (Prod Sim) | Kafka cluster  | Zookeeper-free architecture |

Kafka Concepts Used:

- **Producer**: Services that publish events (e.g., `OrderService`)
- **Consumer**: Services that subscribe to topics (e.g., `InventoryService`)
- **Topics**: Channels for message flow (e.g., `order-created`, `inventory-updated`)
- **Partitions**: Enable parallel processing for scalability
- **Offsets**: Track message consumption per consumer group

---

## 📁 Project Phases

### 1️⃣ Without Microservices
- Single service managing all logic
- Synchronous calls only

### 2️⃣ Microservices + Single Kafka Broker
- Services: `Order`, `Inventory`, `Payment`, etc.
- Events: `order-created`, `payment-processed`, `stock-reserved`
- Kafka via Docker Compose for local use

### 3️⃣ Microservices + Kafka Cluster (KRaft)
- Services scale independently
- Kafka cluster with multi-broker setup
- Ideal for simulating real-world production

---

## 🛠 Technologies

- **Apache Kafka** (KRaft mode)
- **Node.js** – Microservices
- **KafkaJS** – Kafka client for Node
- **Docker Compose** – Service orchestration
- **Kafka Topics** – Message channels per event type

---

## 🚀 Quick Start (for Phase 2)

```bash
cd 2-microservices-single-kafka-server/
docker-compose up --build
