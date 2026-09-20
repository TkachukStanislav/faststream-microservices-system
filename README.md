# FastStream Microservices System

Асинхронна мікросервісна система через брокер повідомлень RabbitMQ.

## 🛠 Стек технологій
* **Python 3.12**
* **FastAPI** — прийом HTTP-запитів
* **FastStream** — асинхронна робота з чергами повідомлень
* **RabbitMQ** — брокер повідомлень (Producer / Consumer патерн)
* **Aiogram 3** — надсилання сповіщень через Telegram-бота
* **Docker & Docker Compose** — контейнеризація брокера

---

## Архітектура

```text
[ Client / Web ]
       │  (POST /order)
       ▼
[ FastAPI (Producer) ]
       │
       ▼  (FastStream)
[ RabbitMQ Queue ("order") ]
       │
       ▼  (FastStream)
[ Telegram Bot (Consumer) ]
       │
       ▼
[ Telegram User Notification ]
