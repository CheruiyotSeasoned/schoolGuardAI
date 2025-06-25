# 🎓 SchoolGuard AI

> A real-time, multi-tenant backend engine for school surveillance, built for developers, AI teams, and edtech founders.

---

## 🔐 Built by [Brian Cheruiyot](https://github.com/your-profile)

SchoolGuard AI is the backend system that powers real-time surveillance in smart schools — detecting fights, sneaking, bullying, phone use, and more — and triggering alerts across dashboards, SMS, and email.

It’s built to be modular, deployable, and powerful — and it also powers enterprise systems like Akilinova AIOTA.

---

## 🧱 Architecture Overview

| Service          | Tech Stack               | Role                          |
| ---------------- | ------------------------ | ----------------------------- |
| **Auth Service** | Spring Boot + MySQL      | Multi-tenant auth + roles     |
| **ML API**       | FastAPI (Python)         | Receives YOLO/OpenCV events   |
| **Processor**    | NestJS + Kafka + MongoDB | Processes events in real time |
| **Alert Engine** | Node.js / Python worker  | Sends notifications           |
| **Dashboard**    | React or Vue (planned)   | View logs + manage users      |

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
```

---

## 🧠 Overview

**Project:** SchoolGuard AI
**Author:** Brian Cheruiyot
**Purpose:** Provide a multi-tenant, real-time backend for AI-based school surveillance systems that integrates ML event detection, alerting, and role-based access for schools of all sizes.

This system is designed to power larger platforms like **Akilinova AIOTA**, while also standing alone as a plug-and-play backend solution.

---

## 🧱 Architecture Breakdown

### 🔹 1. System Stack & Microservices

| Service          | Tech Stack                      | Purpose                                 |
| ---------------- | ------------------------------- | --------------------------------------- |
| Auth Service     | Spring Boot + MySQL             | Manages users, roles, school tenants    |
| ML API           | FastAPI + Python                | Receives ML detections (YOLO, OpenCV)   |
| Event Processor  | NestJS + Kafka + MongoDB        | Processes events in real-time           |
| Alert Dispatcher | Node.js / Python / Kafka Worker | Sends out SMS, email alerts, webhooks   |
| School Dashboard | React / Vue (planned)           | View logs, stream alerts, manage access |

---

### 🔹 2. Multi-Tenancy Strategy

* Each school is a **tenant** with a unique `tenant_id`
* Role-based users belong to tenants: admins, teachers, security
* All services support tenant isolation:

  * Kafka messages include `tenant_id`
  * MongoDB collections are indexed by tenant
  * Auth token encodes tenant scope

---

### 🔹 3. Event Flow Architecture

```
Camera Feed (RTSP)
   ⬇
ML Model (YOLO/OpenCV)
   ⬇
FastAPI Event Poster (/event)
   ⬇
Kafka Producer ➜ Topic: ml_events
   ⬇
NestJS Kafka Consumer
   ⬇
MongoDB (tenant-aware)
   ⬇
Notification Engine ➜ SMS, Email, Dashboard
```

---

### 🔹 4. Deployment Roadmap

#### ✅ Phase 1: Edge Setup (Per School)

* Raspberry Pi or Jetson Nano with YOLO
* Connects to RTSP/DVR feed
* Sends ML events to central FastAPI

#### ✅ Phase 2: Core Backend Services

* Kafka broker cluster
* FastAPI event poster
* NestJS + MongoDB consumer
* Spring Boot for roles + tokens

#### ✅ Phase 3: Notification & Monitoring

* Alert workers for SMS/email/Telegram
* Role-based access dashboards
* Logging, audit trails per school

#### ✅ Phase 4: Scale & Region Support

* Region-based multi-tenant partitions
* Docker Swarm / K8s deployment
* SSO/LDAP school-wide integrations (planned)

---

### 🔹 5. Visual Architecture Diagram *(provided in PDF)*

* FastAPI ML Event Gateway
* Kafka → NestJS Real-Time Consumer
* MongoDB (tenant-partitioned collections)
* SchoolGuard Dashboard (role-based views)
* Optional: Firebase/Telegram alerts

---

### 🔹 6. Included Code Assets

| File                        | Description                        |
| --------------------------- | ---------------------------------- |
| `ml_rtsp_consumer.py`       | RTSP video reader + YOLO inference |
| `fastapi_event_api.py`      | ML → Kafka gateway                 |
| `docker-compose.edge.yml`   | School edge deployment (Pi/Nano)   |
| `event_payload_schema.json` | JSON schema for backend            |
| `camera_setup_guide.pdf`    | Step-by-step CCTV integration PDF  |

---

### 🔹 7. Optional Commercial Licensing

**SchoolGuard AI** is owned and maintained by Brian Cheruiyot.
It can be licensed by:

* AI startups building their own platforms
* NGOs/government pilots
* Institutions using it alongside Akilinova AIOTA

**Akilinova AIOTA** may use SchoolGuard AI internally, but the core engine is independent and may also be shared externally under a personal license.

---

Let me know when you're ready for:

* GitHub repo + README
* Voiceover script + product trailer
* Landing page copy (schoolguard.ai or similar)
