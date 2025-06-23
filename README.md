# SWITCH - Street WITCHer API

The **SWITCH API** gives mobility and logistics companies access to powerful forecasting, optimization, and simulation tools — available via simple, RESTful endpoints.

It powers both the **SWITCH AI Agent** and external applications via secure, authenticated API calls. You can plug directly into SWITCH's AI models to forecast demand, rebalance your fleet, solve routing problems, and track ingestion workflows.

---

## 🔑 Authentication

All endpoints require authentication via **Bearer token**.

1. Use the `/auth/login` endpoint to obtain your access token.
2. Pass the token in the `Authorization` header of each request:

Authorization: Bearer <your_token_here>

To manage your credentials, visit `/auth/api-keys`.

---

## 📊 Key Capabilities

Here’s what you can do with the API:

- **Forecast demand** across spatial zones and time ranges
- **Analyze fleet imbalance** and identify oversupplied/undersupplied areas
- **Get rebalancing suggestions** (e.g. pick-ups, drop-offs, battery swaps)
- **Run routing optimization** for your ops teams
- **Ingest operational data** from your system (JSON or CSV)
- **Monitor ingestion + forecasting pipeline health**

---

## 📘 Main Endpoints

### 🧠 Forecasting
- `POST /forecast/`  
  Get predicted demand with default parameters.

- `POST /forecast/{forecast_type}`  
  Use a specific forecast model (`demand`, `unsatisfied-demand`, etc.).

### 📦 Operations
- `POST /operations/imbalance`  
  Returns demand-supply mismatches across zones.

- `POST /operations/rebalance`  
  Suggests rebalancing actions, optionally considering battery thresholds.

- `POST /operations/routing`  
  Solves routing problems based on vehicles, tasks, and constraints.

### ⏺ Ingestion
- `POST /ingestion/ingest`  
  Ingest structured JSON payloads.

- `POST /ingestion/ingest/bulk`  
  Ingest batch data from CSV or JSON files.

### 🩺 Monitoring
- `GET /monitoring/`  
  Overview of system processes (ingestion, forecasting).

- `GET /monitoring/ingestion`  
  Check ingestion status and progress.

- `GET /monitoring/forecast`  
  View forecast job status and metadata.

---

## 🧭 Forecast Models

The following forecast types are currently supported:

- `demand`: standard expected demand forecast by zone/time
- `unsatisfied-demand`: estimated missed demand based on availability constraints

All forecasts return time series across user-defined geographic zones.

---

## 🧩 How This API Fits In

SWITCH developed this API to serve as a plug-in intelligence layer across fleet management platforms. It is:

- Modular and **tool-agnostic**
- Secure and **production-ready**
- Designed to scale from a few vehicles to tens of thousands

You can integrate it into:
- In-house mobility dashboards
- Partner fleet management tools
- External agentic AI interfaces (chat, voice, API)

---

## 🛠 Docs & Tools

- API Docs: [https://api.getswitch.io/redoc](https://api.getswitch.io/redoc)
- Live base URL: `https://api.getswitch.io`
- OpenAPI spec (download): [openapi.json](https://api.getswitch.io/openapi.json)

---

## 📮 Contact & Support

Want to test it? Need access?

- 📩 [https://getswitch.io/contacts/](https://getswitch.io/contacts/)

---

© SWITCH SRL – All rights reserved.
