## 📦 Services Breakdown

- **Order Producer Service (`order-service`)**:
  - Exposes REST API endpoints via **FastAPI**.
  - Handles incoming client requests, payload validation via Pydantic, and publishes event messages to the RabbitMQ exchange.
- **Notification Consumer Service (`bot-service`)**:
  - Listens to RabbitMQ queues using **FastStream**.
  - Consumes order events asynchronously and dispatches real-time Telegram alerts via **Aiogram 3**.
- **Message Broker (`RabbitMQ`)**:
  - Decouples services, handles routing keys, and manages retry/DLQ logic.

## 🚀 How to Run Locally

```bash
# Clone repository with submodules
git clone --recurse-submodules [https://github.com/TkachukStanislav/faststream-microservices-system.git](https://github.com/TkachukStanislav/faststream-microservices-system.git)

# Start the entire infrastructure via Docker Compose
docker compose up -d --build
