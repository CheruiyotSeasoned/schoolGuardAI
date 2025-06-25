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

## 📂 Included Files
ml_rtsp_consumer.py – RTSP + YOLO stream processing

fastapi_event_api.py – Ingests ML events

docker-compose.edge.yml – School deployment stack

event_payload_schema.json – Validates payload format

camera_setup_guide.pdf – Hardware setup for any school
📦 License & Usage
SchoolGuard AI is owned and maintained by Brian Cheruiyot.
You may use it for:

Learning or internal prototypes (MIT License)

Paid projects, AI products, or school deployments (commercial license required)

For commercial use, email: schoolguard@briancheruiyot.dev

🚀 Powered AI Platforms
🟢 Akilinova AIOTA (uses SchoolGuard AI internally)

🌍 Want to Collaborate?
If you're building edtech, AI safety tools, or IoT solutions for schools, let's connect.
I'm open to partnerships, custom integrations, and joint deployments.

🧠 Credit
Created with passion by Brian Cheruiyot.
Real-time AI shouldn't be out of reach for the people who need it most.

yaml
Copy
Edit

---

### ✅ What Next?
Let me know your:
1. GitHub username (to link in the README)
2. Preferred email or contact for licensing
3. Optional: Logo to include in the repo

After that, I’ll help you:
- Create the **landing page copy**
- Polish the **product trailer script**
- Add **branding** to your PDF + assets
