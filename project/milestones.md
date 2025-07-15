# Project Milestones

---

## M1 – End-to-End Auto Ingestion Prototype (2 sprints)

**Features to Deliver:**
- TDengine cluster setup (3-node HA configuration)
- Fluentd cluster deployment with autoscaling
- Kafka → Fluentd input via Kafka plugin
- Fluentd output:
  - To TDengine via fluent-plugin-tdengine
- Sample event in protobuf format
- Kafka Connect MQTT connector setup to simulate device data flow
- Initial schema design for raw TDengine tables (events, metrics)

---

## M2 – Event Logging Implementation (2 sprints)

**Features to Deliver:**
- Revise the Kafka connector to support the event-schema
- End-to-end ingestion flow from Kafka → Fluentd → TDengine
- Event tables:
  - TRS-OPTIM-CLOUD-EVENTS-EQUIP
  - TRS-OPTIM-CLOUD-EVENTS-WAN
  - TRS-OPTIM-CLOUD-EVENTS-ACS
  - TRS-OPTIM-CLOUD-EVENTS-INTERFACE
  - TRS-OPTIM-CLOUD-EVENTS-SERVICE
  - TRS-OPTIM-CLOUD-EVENTS-WIFI
  - TRS-OPTIM-CLOUD-EVENTS-MESH
  - TRS-OPTIM-CLOUD-EVENTS-RADIO
  - TRS-OPTIM-CLOUD-EVENTS-VAP
  - TRS-OPTIM-CLOUD-EVENTS-DEVICE
- Optim event query REST API service implementation
- Event retrieval support for:
  - TRS-OPTIM-CLOUD-EVENTS-DEVICE
  - TRS-OPTIM-CLOUD-EVENTS-EQUIP
  - TRS-OPTIM-CLOUD-EVENTS-WAN
- Filter support
- Event attributes selection
- Paginated resultset support
- MongoDB cluster setup for update events
- Fluentd output:
  - To MongoDB via fluent-plugin-mongo

---

## M3 – Metrics Event Support Implementation (1 sprint)

**Features to Deliver:**
- Implement `wan_metrics_stable` in TDengine
- Visual validation using Grafana (basic dashboard)
- Optim event query REST API service implementation
- Event retrieval support for:
  - TRS-OPTIM-CLOUD-EVENTS-ACS
  - TRS-OPTIM-CLOUD-EVENTS-INTERFACE
  - TRS-OPTIM-CLOUD-EVENTS-SERVICE
  - TRS-OPTIM-CLOUD-EVENTS-WIFI

---

## M4 – Update Event and Lifecycle Schema (1 sprint)

**Features to Deliver:**
- MongoDB cluster
- Support UPDATE event types (stored in MongoDB)
- Lifecycle overwrite semantics: keep only latest record
- Fluentd → MongoDB pipeline (fluent-plugin-mongo)
- Optim update query API (REST)
- TTL/Retention handling and tooling for MongoDB collections
- Optim event query REST API service implementation
- Event retrieval support for:
  - TRS-OPTIM-CLOUD-EVENTS-MESH
  - TRS-OPTIM-CLOUD-EVENTS-RADIO
  - TRS-OPTIM-CLOUD-EVENTS-VAP

---

## M5 – Event/Metrics/Update Scalability Testing (1 sprint)

**Features to Deliver:**
- TDengine auto ingestion scalability
- TDengine scale-up
- Fluentd auto scaling
- Indexing tuning and query performance optimization

---

## M6 – Final Integration, Monitoring, and Documentation (1–2 sprints)

**Features to Deliver:**
- Full-system validation and performance testing (1M+ subtables)
- Load testing with Locust or custom event generator
- System-level monitoring (Fluentd, TDengine, MongoDB)
- Grafana dashboard templates for event/metrics visualization
- Documentation: API specs, schema registry format, Fluentd config examples