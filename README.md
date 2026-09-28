# 🌍 SAHAS

## AI-Driven Spatiotemporal Decision Support System for Proactive Habitation Relocation

> **SAHAS — Spatial Analytics and Hazard Assessment System**
> An AI-powered, GIS-driven decision support platform designed to help disaster management authorities identify high-risk habitations, evaluate safer relocation sites, simulate evacuation logistics, and support proactive relocation decisions.

---

## 📌 Overview

India's disaster management framework often operates on a reactive paradigm, where interventions are initiated after a disaster has already impacted vulnerable communities.

**SAHAS** is an enterprise-grade, closed-loop command architecture designed for the **Ministry of Home Affairs (MHA)** and **State Disaster Management Authorities (SDMAs)**.

By combining **spatiotemporal machine learning, GIS, spatial databases, predictive analytics, and capacity modeling**, SAHAS enables authorities to move from reactive disaster response toward **proactive, data-driven habitation relocation**.

The platform continuously evaluates:

* 🌋 Hazard intensity and progression
* 🗺️ Geospatial vulnerability
* 👥 Population exposure
* 🏠 Infrastructure capacity
* 🚑 Healthcare accessibility
* 💧 Water availability
* 🛣️ Road network capacity
* 📊 Destination carrying capacity
* 🚨 Evacuation and relocation feasibility

SAHAS does not automatically issue public mandates. Instead, it provides **AI-generated intelligence and simulation results** to authorized officials, who verify and approve relocation decisions before deployment.

---

# 🚀 Key Features & Novelty

## 1. 🔴 Dynamic Red Zone Mapping

SAHAS combines environmental, geographical, and meteorological data to continuously evaluate hazard conditions.

The **XGBoost-based risk engine** processes features such as:

* Terrain slope
* Soil characteristics
* Elevation
* Weather conditions
* Hydrological indicators
* Population exposure
* Infrastructure vulnerability

The resulting risk scores are spatially projected onto the map to dynamically identify and update **high-risk Red Zones**.

---

## 2. 🏕️ MCDA-Based Site Suitability & Carrying Capacity

Identifying a safe location alone is insufficient.

SAHAS evaluates whether a potential relocation site can actually support the incoming population.

The **Multi-Criteria Decision Analysis (MCDA)** engine evaluates factors including:

* 🏠 Shelter capacity
* 🛣️ Road network bandwidth
* 💧 Water availability
* 🏥 Healthcare proximity
* 👥 Population load
* 🏫 Essential infrastructure
* 📍 Geographic accessibility

A weighted suitability index is generated for each candidate destination.

This helps prevent **secondary crises caused by overcrowding, insufficient resources, or inadequate infrastructure**.

---

## 3. 📊 Vulnerability Prioritization Matrix (VPM)

SAHAS combines:

**Hazard Risk × Population Exposure × Community Vulnerability**

to prioritize affected habitations.

Habitations are categorized into relocation pipelines such as:

| Priority       | Relocation Window                               |
| -------------- | ----------------------------------------------- |
| 🔴 Immediate   | Critical and rapidly deteriorating risk         |
| 🟠 Short-Term  | Significant risk requiring planned intervention |
| 🟡 Medium-Term | Emerging risk requiring continued monitoring    |

This enables authorities to allocate resources according to both **hazard severity and community vulnerability**.

---

## 4. 🧬 Digital Twin — Shadow Simulation

Before publishing relocation orders, authorities can simulate the proposed operation digitally.

The **Shadow Simulation** models:

* Population movement
* Route congestion
* Road capacity
* Shelter occupancy
* Resource consumption
* Arrival rates
* Destination saturation

Officials can therefore test:

> **"What happens if we relocate this population to this destination?"**

before executing the actual operation.

This allows potential bottlenecks and capacity failures to be identified during the planning stage.

---

## 5. 📡 Zero-Trust Edge Resilience

Disaster scenarios can involve network outages and unreliable connectivity.

SAHAS therefore uses an **offline-first Progressive Web App (PWA)** architecture for field operations.

The field interface can maintain access to:

* Cached maps
* Relocation information
* Previously synchronized data
* Emergency instructions

through service-worker-based offline caching.

This ensures critical information remains accessible even when network connectivity becomes unreliable.

---

# 🛠️ Technology Stack

## 🤖 AI & Data Science

* **Python**
* **FastAPI**
* **XGBoost**
* **Scikit-Learn**
* Predictive Risk Modeling
* Feature Engineering
* Spatiotemporal Risk Analysis

---

## 🗺️ Geospatial & Database

* **PostgreSQL**
* **PostGIS**
* **Leaflet**
* **OpenStreetMap**
* Spatial Intersection
* Geospatial Querying
* Dynamic Risk Polygon Generation

---

## ⚡ Frontend & Edge Delivery

* **React.js**
* **React PWA**
* **Progressive Web App Architecture**
* **Service Workers**
* **Leaflet**
* **OpenStreetMap**

---

## 🔌 External Integrations

* **ISRO Bhuvan** — Topography and elevation data
* **IMD** — Meteorological data and forecasts
* **WebSockets** — Real-time alert and data streaming

---

## ⚡ Supporting Infrastructure

* **Redis** — Low-latency caching and live occupancy data
* **REST APIs**
* **WebSockets**
* **RBAC**
* Offline-first data synchronization

---

# ⚙️ System Architecture

```text
                    ┌───────────────────────────┐
                    │      DATA SOURCES         │
                    │                           │
                    │ ISRO Bhuvan │ IMD │ GIS   │
                    │ Demographic │ Weather     │
                    │ Hydrological│ Topography  │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
                    ┌───────────────────────────┐
                    │      DATA INGESTION       │
                    │                           │
                    │ Normalization             │
                    │ Validation                 │
                    │ Feature Engineering       │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
                    ┌───────────────────────────┐
                    │       ML RISK ENGINE      │
                    │                           │
                    │ XGBoost + Scikit-Learn   │
                    │ Hazard Prediction         │
                    │ Vulnerability Analysis    │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
                    ┌───────────────────────────┐
                    │      SPATIAL ENGINE       │
                    │                           │
                    │ PostgreSQL + PostGIS      │
                    │ ST_Intersects             │
                    │ Risk Polygon Generation   │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
              ┌────────────────────────────────────────┐
              │       DECISION SUPPORT ENGINE          │
              │                                        │
              │ MCDA Site Suitability                  │
              │ Carrying Capacity                      │
              │ Vulnerability Prioritization           │
              │ Relocation Routing                     │
              └────────────────────┬───────────────────┘
                                   │
                                   ▼
                    ┌───────────────────────────┐
                    │     SHADOW SIMULATION     │
                    │                           │
                    │ Crowd Flow                │
                    │ Route Congestion          │
                    │ Shelter Occupancy         │
                    │ Resource Consumption      │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
                    ┌───────────────────────────┐
                    │      MHA / SDMA C2        │
                    │       DASHBOARD           │
                    │                           │
                    │ Verify → Simulate → Sign  │
                    │ → Approve → Broadcast     │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
                    ┌───────────────────────────┐
                    │      FIELD INTERFACE      │
                    │                           │
                    │ React PWA                 │
                    │ Offline Maps              │
                    │ Relocation Instructions   │
                    └───────────────────────────┘
```

---

# 🔄 Architecture Workflow

### 1. Data Ingestion

SAHAS aggregates fragmented datasets including:

* Topographical data
* Meteorological data
* Hydrological data
* Demographic information
* Infrastructure data
* Road network information

The incoming data is normalized and prepared for downstream processing.

---

### 2. ML Risk Engine

The risk engine evaluates hyper-local features such as:

* Slope gradient
* Soil characteristics
* Elevation
* Weather conditions
* Population exposure
* Infrastructure vulnerability

The ML model produces a localized **risk probability / risk score**.

---

### 3. Spatial Overlay

The generated risk information is converted into spatial polygons.

PostGIS spatial operations such as:

```sql
ST_Intersects()
```

are used to determine which habitations and geographic areas fall within identified risk zones.

This produces dynamically updated **Red Zones**.

---

### 4. Vulnerability Prioritization

The system combines hazard severity with population and infrastructure vulnerability.

Affected habitations are assigned to:

```text
Immediate
     ↓
Short-Term
     ↓
Medium-Term
```

relocation pipelines.

---

### 5. MCDA Site Evaluation

Candidate relocation sites are evaluated using multiple weighted criteria.

Conceptually:

```text
Site Suitability Score
        =
Weighted Safety
+ Infrastructure Capacity
+ Accessibility
+ Resource Availability
+ Healthcare Access
```

The system compares available capacity against the expected incoming population.

---

### 6. Shadow Simulation

Before an official relocation order is issued, authorities can simulate:

```text
Population
     ↓
Evacuation Routes
     ↓
Traffic / Bottlenecks
     ↓
Shelter Capacity
     ↓
Resource Consumption
     ↓
Destination Occupancy
```

This allows authorities to identify potential failures before field deployment.

---

### 7. Command & Control Execution

The resulting intelligence is displayed through the secure **MHA / SDMA Command Dashboard**.

Authorized officials can:

1. Review AI-generated intelligence
2. Inspect affected areas
3. Evaluate relocation sites
4. Run simulations
5. Review capacity
6. Verify the proposed action
7. Cryptographically sign the decision
8. Broadcast the approved relocation information

---

# 🔐 MHA Compliance & Security

SAHAS follows a **human-in-the-loop decision architecture**.

The system generates intelligence and recommendations, but does not independently issue public relocation mandates.

### Role-Based Access Control

Access is restricted according to authorized roles.

```text
Government Authority
        │
        ▼
Authentication
        │
        ▼
Role-Based Access Control
        │
        ├── Monitor
        ├── Analyze
        ├── Simulate
        └── Approve / Sign
```

### Human Authorization Layer

All AI-generated:

* Red Zones
* Vulnerability classifications
* Site suitability results
* Relocation proposals

must be reviewed and authorized by designated personnel before field deployment.

---

# 🧠 Core Intelligence Pipeline

SAHAS follows a closed-loop decision architecture:

```text
SENSE
  ↓
ANALYZE
  ↓
PREDICT
  ↓
MAP
  ↓
PRIORITIZE
  ↓
SIMULATE
  ↓
VERIFY
  ↓
AUTHORIZE
  ↓
DEPLOY
  ↓
MONITOR
```

This transforms raw disaster data into actionable operational intelligence.

---

# 📐 Spatial Intelligence

SAHAS uses **PostGIS** to perform spatial operations across hazard and habitation datasets.

Example:

```sql
SELECT habitation_id
FROM habitations
WHERE ST_Intersects(
    habitation_geometry,
    hazard_polygon
);
```

This allows the system to determine which habitations intersect with dynamically generated hazard zones.

---

# 📊 Decision Intelligence

SAHAS combines multiple dimensions instead of relying on a single hazard score.

```text
Hazard Risk
     +
Population Exposure
     +
Infrastructure Vulnerability
     +
Destination Capacity
     +
Resource Availability
     +
Accessibility
     ↓
Relocation Intelligence
```

The result is a decision-support layer designed to provide authorities with a more comprehensive operational picture.

---

# 🌐 Offline-First Field Architecture

The field application is designed as a Progressive Web App.

```text
              ┌───────────────────┐
              │   Online Mode     │
              │                   │
              │ API + WebSocket   │
              └─────────┬─────────┘
                        │
                  Synchronization
                        │
                        ▼
              ┌───────────────────┐
              │  Local Cache      │
              │                   │
              │ Maps              │
              │ Alerts            │
              │ Instructions      │
              │ Last Known Data   │
              └─────────┬─────────┘
                        │
                  Network Failure
                        │
                        ▼
              ┌───────────────────┐
              │   Offline Mode    │
              │                   │
              │ Critical Maps     │
              │ Cached Data       │
              │ Instructions      │
              └───────────────────┘
```

This architecture is intended to preserve access to previously synchronized critical information during connectivity disruptions.

---

# 💻 Local Installation & Setup

## Prerequisites

Make sure the following are installed:

* Node.js `v18+`
* Python `3.10+`
* PostgreSQL
* PostGIS extension

---

## 1. Clone the Repository

```bash
git clone https://github.com/your-org/sahas.git
cd sahas
```

---

## 2. Backend Setup

Navigate to the backend:

```bash
cd backend
```

Create a Python virtual environment:

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI server:

```bash
uvicorn main:app --reload
```

The backend will be available locally through the configured FastAPI server.

---

## 3. Frontend Setup

Open another terminal:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm start
```

---

# 📁 Project Structure

```text
SAHAS/
│
├── backend/
│   ├── main.py
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── ml/
│   ├── gis/
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── hooks/
│   └── public/
│
├── data/
│   ├── spatial/
│   ├── demographic/
│   └── environmental/
│
├── models/
│   └── risk_model/
│
├── docs/
│
└── README.md
```

---

# 🎯 Problem → Solution

| Disaster Management Challenge          | SAHAS Capability                    |
| -------------------------------------- | ----------------------------------- |
| Reactive intervention                  | Predictive risk intelligence        |
| Fragmented data                        | Unified data ingestion              |
| Static hazard boundaries               | Dynamic Red Zone mapping            |
| Unknown relocation capacity            | MCDA carrying-capacity analysis     |
| Population vulnerability overlooked    | Vulnerability Prioritization Matrix |
| Evacuation bottlenecks discovered late | Digital Twin Shadow Simulation      |
| Network failure during disasters       | Offline-first PWA                   |
| AI decisions without accountability    | Human-in-the-loop authorization     |
| Resource overload at safe zones        | Capacity and occupancy modeling     |

---

# 🌱 Expected Impact

SAHAS is designed to help disaster management authorities:

* Identify vulnerable habitations earlier
* Visualize evolving hazard zones
* Prioritize communities based on risk and vulnerability
* Identify feasible relocation destinations
* Evaluate destination carrying capacity
* Detect evacuation bottlenecks before deployment
* Simulate relocation scenarios
* Reduce secondary crises caused by overcrowding
* Maintain critical field information during connectivity failures
* Support transparent, human-authorized disaster decisions

---

# 🔮 Future Scope

Potential extensions include:

* Satellite-based real-time change detection
* Advanced multimodal disaster intelligence
* IoT-based environmental telemetry
* Reinforcement-learning-based evacuation optimization
* Advanced crowd-flow simulation
* Digital twins for district-scale infrastructure
* Multilingual voice-based emergency interfaces
* Automated resource-demand forecasting
* Integration with additional government geospatial datasets
* Federated learning across disaster management jurisdictions

---

# 👥 Core Team

| Team Member                 |
| --------------------------- |
| **Katkuri Harshitha Reddy** |
| **Sahas Reddy Billa**       |
| **Charishma**               |
| **Manish Reddy**            |
| **Rajaneesh**               |
| **Devaashish**              |

---

# 🏆 Smart India Hackathon 2026

**Developed for the Smart India Hackathon 2026**

### Ministry of Home Affairs Track

**Problem Statement:** SIH26191

---

## 📜 Project Philosophy

> **Predict the risk. Map the threat. Simulate the response. Relocate with evidence.**

SAHAS aims to bridge the gap between **disaster prediction, spatial intelligence, relocation planning, and operational decision-making** through a unified AI and GIS-driven command architecture.

---

## ⭐ SAHAS

### **From Reactive Response to Proactive Relocation.**

---
