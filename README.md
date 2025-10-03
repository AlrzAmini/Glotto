# Glotto

**Glotto** is a modern, scalable backend API platform for a multilingual learning application. It powers a front-end language-learning app with APIs for user authentication, lessons, video streaming, progress tracking, and gamification features.

Built with **feature-based Clean Architecture**, Glotto ensures modular, testable, and maintainable code. It supports background processing, observability, and load-balanced deployments, making it production-ready for high-scale environments.

---

## 🚀 Key Features

- **Feature-Based Clean Architecture**  
  Organizes code by features (e.g., Auth, Courses, Videos, Lessons, Subscriptions) for better maintainability and extensibility.

- **Background Jobs with Hangfire**  
  Handles video uploads, transcoding, notifications, and reminders reliably, decoupled from API request threads.

- **Observability with OpenTelemetry + Prometheus + Grafana**  
  Collects traces, metrics, and logs for API requests, background jobs, and system performance, enabling monitoring of latency, failures, and throughput.

- **Mapster for Object Mapping**  
  Provides fast, clean DTO ↔ entity mapping for commands, queries, and responses.

- **Scalar API Documentation**  
  Auto-generated, interactive API documentation for seamless integration with front-end developers.

- **Database Support**  
  Supports PostgreSQL or SQL Server for scalable relational data storage, optimized for multilingual content.

- **Load-Balanced Ready**  
  Designed to run behind Nginx or HAProxy for high-traffic scenarios, ensuring API availability and reliability.

---

## 🛠️ Tech Stack

- **Backend Framework:** ASP.NET Core  
- **Database:** PostgreSQL / SQL Server  
- **Background Jobs:** Hangfire  
- **Object Mapping:** Mapster  
- **Observability:** OpenTelemetry, Prometheus, Grafana  
- **API Documentation:** Scalar  

---

## 🏗️ Architecture Overview

- **API Layer:** Exposes endpoints using Minimal APIs or controllers.  
- **Application Layer:** Manages commands, queries, validators, and DTOs for each feature.  
- **Domain Layer:** Defines core entities, value objects, and business rules.  
- **Infrastructure Layer:** Integrates EF Core, storage services, Hangfire jobs, and external APIs.  

**Feature Examples:**
- Authentication (Register, Login, JWT tokens)  
- Courses & Lessons  
- Video streaming and processing  
- Progress tracking & gamification  
- Notifications and reminders  

---

## 📋 Prerequisites

Before running Glotto locally, ensure you have the following installed:
- [.NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)  
- [PostgreSQL](https://www.postgresql.org/download/) 
- [Git](https://git-scm.com/downloads)  
- (Optional) [Docker](https://www.docker.com/get-started) for containerized deployments  
- (Optional) [Hangfire Dashboard](https://www.hangfire.io/) for monitoring background jobs  
- (Optional) [Prometheus](https://prometheus.io/download/) and [Grafana](https://grafana.com/grafana/download) for observability  

---

## ⚡ Getting Started

Follow these steps to set up and run Glotto locally:

1. **Clone the repository**  
   ```bash
   git clone https://github.com/AlrzAmini/glotto.git
   cd glotto
   ```

2. **Configure the database connection**  
   Update the connection string in `src/Glotto.Api/appsettings.json`:  
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Host=localhost;Database=GlottoDb;Username=your_username;Password=your_password"
     }
   }
   ```

3. **Apply EF Core migrations to initialize the database**  
   Ensure you have the EF Core CLI tools installed (`dotnet tool install --global dotnet-ef`), then run:  
   ```bash
   dotnet ef database update --project src/Glotto.Infrastructure
   ```

4. **Start the backend API**  
   ```bash
   dotnet run --project src/Glotto.Api
   ```

5. **Access the API**  
   - The API will be available at `https://localhost:5001` (or the port specified in `appsettings.json`).  
   - View the Scalar API documentation at `https://localhost:5001/api-docs`.

---

## 🐳 Running with Docker

To run Glotto in a containerized environment:

1. Build the Docker image:  
   ```bash
   docker build -t glotto-api .
   ```

2. Run the container:  
   ```bash
   docker run -p 5001:80 -e ConnectionStrings__DefaultConnection="your_connection_string" glotto-api
   ```

---

## 🧪 Running Tests

Glotto includes unit and integration tests to ensure code quality. Run tests using:

```bash
dotnet test
```

---

## 📊 Observability Setup

To set up observability with Prometheus and Grafana:

1. **Configure OpenTelemetry** in `appsettings.json` for trace and metric exports.  
2. Run Prometheus and Grafana using Docker Compose:  
   ```bash
   docker-compose -f docker-compose.observability.yml up -d
   ```
3. Access Grafana at `http://localhost:3000` and configure dashboards for Glotto metrics.

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository.  
2. Create a feature branch (`git checkout -b feature/your-feature`).  
3. Commit your changes (`git commit -m "Add your feature"`).  
4. Push to the branch (`git push origin feature/your-feature`).  
5. Open a pull request with a clear description of your changes.

Please ensure your code follows the project's coding standards and includes tests where applicable.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 📬 Contact

For questions or feedback, reach out to the maintainer:  
- **GitHub:** [AlrzAmini](https://github.com/AlrzAmini)  
- **Email:** mranotmillion@gmail.com
