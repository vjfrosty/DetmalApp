# Dental Disease Detection – System Architecture (Monolith)

## Monolithic Architecture Overview

### All-in-One Diagram
```mermaid
%% Single Docker container, all-in-one stack
graph TD
  Dentist --> Browser
  Browser --> WebApp[Web App (React + Flask)]
  WebApp --> Auth[JWT + MFA Auth]
  WebApp --> ModelAPI[ML Prediction (U‑Net / YOLO)]
  WebApp --> LocalDB[Postgres DB]
  WebApp --> FileStore[Local/MinIO Storage]
  WebApp --> Logs[Audit Logs]
  WebApp --> ModelManager[Model Hotloader + Retrainer]
```

<ExplainAfter>
This architecture simplifies deployment and cost. Everything runs within a single container or tightly coupled docker-compose setup. Web server (Flask/React) handles UI, auth, inference, and image storage via internal modules. Ideal for VPS deployments.
</ExplainAfter>
