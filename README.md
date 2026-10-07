# FastStream Microservices System

Asynchronous event-driven microservices architecture built with RabbitMQ message broker.

## 🛠 Tech Stack

- **Python 3.12**
- **FastAPI** — Handling incoming HTTP requests & Producer service
- **FastStream** — Asynchronous message broker integration & stream processing
- **RabbitMQ** — Distributed message broker (Producer / Consumer pattern)
- **Aiogram 3** — Delivering alerts and updates via Telegram bot
- **Docker & Docker Compose** — Broker and service containerization

## Architecture

```text
[ Client / Web ]
       │ (POST /order)
       ▼
[ FastAPI (Producer) ]
       │
       ▼ (FastStream)
[ RabbitMQ Queue ("order") ]
       │
       ▼ (FastStream)
[ Telegram Bot (Consumer) ]
       │
       ▼
[ Telegram User Notification ]
