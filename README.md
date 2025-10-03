# Glotto

**Glotto** is a modern, scalable backend API platform for a multilingual learning application. It provides all the APIs needed to power a front-end language-learning app, including user authentication, lessons, video streaming, progress tracking, and gamification features.

It is designed with **feature-based Clean Architecture** to keep the code modular, testable, and maintainable. Glotto supports background processing, observability, and load-balanced deployments, making it ready for production at scale.

---

## 🚀 Key Features

- **Feature-Based Clean Architecture**  
  Organizes code by features (Auth, Courses, Videos, Lessons, Subscriptions) instead of types, making it easier to maintain and extend.

- **Background Jobs with Hangfire**  
  Reliable processing for video uploads, transcoding, notifications, and reminders, separate from API request threads.

- **Observability with OpenTelemetry + Prometheus + Grafana**  
  Collects traces, metrics, and logs for API requests, background jobs, and system performance. Enables monitoring of latency, failures, and throughput.

- **Mapster for Object Mapping**  
  Fast and clean DTO ↔ entity mapping for commands, queries, and responses.

- **Scalar API Documentation**  
  Auto-generated, browsable API docs to make the backend easily consumable for front-end developers.

- **Database Support**  
  PostgreSQL or SQL Server for relational data storage, optimized for scalability and multi-language content.

- **Load Balanced Ready**  
  Designed to run behind Nginx or HAProxy for high-traffic scenarios, ensuring API availability and reliability.

---

## 🛠️ Tech Stack

- **Backend Framework:** ASP.NET Core  
- **Database:** PostgreSQL / SQL Server  
- **Background Jobs:** Hangfire  
- **Mapping:** Mapster  
- **Observability:** OpenTelemetry, Prometheus, Grafana  
- **API Documentation:** Scalar  

---

## 🏗️ Architecture Overview

- **API Layer:** Minimal APIs or controllers exposing endpoints.  
- **Application Layer:** Commands, Queries, Validators, and DTOs for each feature.  
- **Domain Layer:** Core entities, value objects, and business rules.  
- **Infrastructure Layer:** EF Core, storage services, Hangfire jobs, external integrations.  

**Features Example:**
- Auth (Register, Login, JWT tokens)  
- Courses & Lessons  
- Video streaming and processing  
- Progress tracking & gamification  
- Notifications and reminders  

---

## ⚡ Getting Started

Follow these steps to run Glotto locally:

1. **Clone the repository:**
```bash
git clone https://github.com/AlrzAmini/glotto.git
