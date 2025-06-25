# 🎓 SchoolGuard AI

> A real-time, multi-tenant backend engine for school surveillance, built for developers, AI teams, and edtech founders.

---

## 🔐 Built by [Brian Cheruiyot](https://github.com/your-profile)

SchoolGuard AI is the backend system that powers real-time surveillance in smart schools — detecting fights, sneaking, bullying, phone use, and more — and triggering alerts across dashboards, SMS, and email.

It’s built to be modular, deployable, and powerful — and it also powers enterprise systems like Akilinova AIOTA.

---

## 🧱 Architecture Overview

| Service            | Tech Stack                     | Role                         |
|--------------------|----------------------------------|-------------------------------|
| **Auth Service**   | Spring Boot + MySQL             | Multi-tenant auth + roles     |
| **ML API**         | FastAPI (Python)                | Receives YOLO/OpenCV events   |
| **Processor**      | NestJS + Kafka + MongoDB        | Processes events in real time |
| **Alert Engine**   | Node.js / Python worker         | Sends notifications           |
| **Dashboard**      | React or Vue (planned)          | View logs + manage users      |

---

## ⚙️ Features

✅ Multi-tenant support  
✅ Real-time ML event ingestion (via FastAPI)  
✅ Kafka event streaming  
✅ Role-based access per school (admins, teachers, security)  
✅ Alerting via SMS, Email, Telegram (custom)  
✅ Modular edge deployment via Docker (Jetson Nano, Pi)  

---

## 🔁 Event Payload Example

```json
{
  "tenant_id": "school_xyz",
  "event_type": "fighting",
  "camera_id": "CAM-7",
  "location": "Hallway A",
  "confidence": 0.92,
  "timestamp": "2025-06-25T12:44:00Z"
}
## How to Run (Dev Mode)
# Step 1: Clone
git clone https://github.com/your-profile/schoolguard-ai.git
cd schoolguard-ai

# Step 2: Setup Docker services
docker-compose -f docker-compose.edge.yml up

# Step 3: Run ML Inference
python ml_rtsp_consumer.py

# Step 4: Run FastAPI Event API
uvicorn fastapi_event_api:app --reload
