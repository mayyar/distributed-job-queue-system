# distributed-job-queue-system

## 🔧 Architecture Diagram

```mermaid
flowchart TD
    A[Client / User] --> B["API Service 
    (FastAPI)"]
    B --> C[(PostgreSQL Job Status DB)]
    B --> D[(Redis Queue)]
    D --> E[Worker Nodes]
    C --> E
    E --> C
    E -->|Update Status| B