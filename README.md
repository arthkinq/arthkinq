### artur slanov

3rd-year Software Engineering student at ITMO University, Saint Petersburg.

Looking for a **Go Backend / SRE internship** (up to 40 h/week, remote or hybrid).  
In a commercial Telegram marketplace project ([@DodoSeller_Bot](https://t.me/DodoSeller_Bot), ~300 orders/day, peaks up to ~1000), I handled production troubleshooting on a Linux VPS, reduced operational toil (idempotent payments, retries, circuit breaker), and extracted automated Telegram Stars purchasing into a standalone Dockerized service (FastAPI, PostgreSQL, Redis; ~60 orders/day).

---

#### go projects

| Project | Description | Stack |
|---|---|---|
| **[order-flow-engine](https://github.com/arthkinq/order-flow-engine)** | Asynchronous order pipeline: gRPC API → rate-limit check → RabbitMQ → worker pool → PostgreSQL. Manual ACKs, exponential backoff retries before DLQ, order state machine, fail-open (200 ms timeout) when the limiter is down, graceful shutdown. Prometheus metrics & SLO alerts, pre-provisioned Grafana dashboard, structured JSON logs (`slog` with `order_id`), Kubernetes (`kind`) manifests (`Deployment`, `Service`, `ConfigMap`, probes, resource limits), GitHub Actions CI. Load-tested with k6 (50 VUs, p95 9.5 ms, 0 failed requests). | Go · Kubernetes · Prometheus · Grafana · RabbitMQ · PostgreSQL · gRPC · Docker |
| **[go-kitchen](https://github.com/arthkinq/go-kitchen)** | Food delivery backend: customer API and partner restaurant API. Hand-written SQL, transactions and `SELECT ... FOR UPDATE` with deterministic lock ordering against overselling and deadlocks under concurrent orders. Versioned SQL migrations, integration tests on a real PostgreSQL in Docker, OpenAPI 3.0 contract, CI on GitHub Actions. | Go · PostgreSQL · Docker · GitHub Actions · OpenAPI |
| **[gatekeeper](https://github.com/arthkinq/gatekeeper)** | Distributed rate limiting service with a gRPC API. Fixed window counter and sliding window log backed by Redis atomic checks, graceful shutdown, multi-stage Dockerfile. Unit & integration tests (87.2% coverage). Used by order-flow-engine. | Go · Redis · gRPC · Protobuf · Docker |

---

#### stack

```
Languages:       Go (Golang), Python, SQL
Infra & CI/CD:   Kubernetes (kind), Docker, Docker Compose, GitHub Actions, Linux, Git
Observability:   Prometheus (SLI/SLO alerts), Grafana (provisioning as code), JSON logs (log/slog), k6
Data & Network:  PostgreSQL, Redis, RabbitMQ, gRPC/Protobuf, HTTP/REST
```

---

arthurslanov@gmail.com · [telegram](https://t.me/Arthkinq) · [EF SET C2 (81/100)](https://cert.efset.org/MGZSva)
