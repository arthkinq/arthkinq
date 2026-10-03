### artur slanov

3rd-year Software Engineering student at ITMO University, Saint Petersburg.

Looking for a **Go backend internship** (30 h/week). I also have commercial Python backend experience: a Telegram marketplace bot (~300 orders/day) where I moved services out of the monolith and built a microservice (in production, ~60 orders/day).

---

#### go projects

| Project | Description | Stack |
|---|---|---|
| **[order-flow-engine](https://github.com/arthkinq/order-flow-engine)** | Order pipeline: gRPC API → rate limit check → RabbitMQ → worker pool → PostgreSQL. Manual acks and DLQ, order state machine, fail-open when the limiter is down, graceful shutdown. k6 on a local Docker stack: 50 VUs for 50 s, ~250 orders/s, p95 9.5 ms, 0 failed requests. | Go · gRPC · RabbitMQ · PostgreSQL · Prometheus · k6 |
| **[go-kitchen](https://github.com/arthkinq/go-kitchen)** | Food delivery backend: customer API and a closed partner API. Hand-written SQL, transactions and `SELECT ... FOR UPDATE` against overselling under concurrent orders. Versioned SQL migrations, integration tests on a real PostgreSQL in Docker, OpenAPI 3.0 contract, CI on GitHub Actions. | Go · PostgreSQL · pgx · chi · Docker |
| **[gatekeeper](https://github.com/arthkinq/gatekeeper)** | Rate limiting service with a gRPC API. Fixed window counter and sliding window log. Tests with miniredis and testify. Used by order-flow-engine. | Go · gRPC · Redis · Docker |

---

#### stack

```
Go:      PostgreSQL,  Docker, Redis, RabbitMQ, gRPC, Protobuf
Tools:   Git, GitHub Actions, Docker Compose, Linux, SQL, Makefile, Prometheus, k6
```

---

arthurslanov@gmail.com · [telegram](https://t.me/Arthkinq)
