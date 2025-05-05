# NammaLakes: Distributed Lake Monitoring, the Smarter Way

 **NammaLakes**, an IoT-powered distributed system designed to monitor the health and status of urban lakes. As urbanization grows, many freshwater bodies suffer from pollution, mismanagement, and neglect. NammaLakes takes a step toward smarter, data-driven lake conservation and management.

## See It in Action

[Explore the live system](https://nammalakes.github.io)  

## What’s This Project All About?

At its core, this system leverages a network of IoT devices and intelligent software to monitor lake parameters in real-time — from water quality to sensor-driven alerts. This allows stakeholders and authorities to take timely action, backed by accurate data and reliable insights.

The system provides: 
- Real-time Monitoring: Continuous collection of water quality parameters
- Intelligent Analytics: ML-powered anomaly detection (Isolation Forest algorithm)
- Interactive Dashboard: User-friendly visualization of complex environmental data
- Automated Alerts: Instant notifications when parameters exceed safe thresholds
- Scalable Architecture: Built to monitor multiple water bodies simultaneously

## The Problems We Are Solving

Traditional approaches to lake monitoring have significant limitations:

- Delayed Response: Manual sampling causes critical delays in detecting contamination events
- Limited Data: Infrequent collection makes it impossible to identify subtle trends
- Low Visibility: Lack of centralized visualization prevents effective decision-making
- No Early Warning: Absence of automated alerts means pollution events often go unnoticed

## Architecture Overview

The NammaLakes system consists of three primary layers:

### 1. Edge Layer (IoT Devices)
- Hardware: ESP32 microcontrollers and Raspberry Pi devices
- Sensors: pH, turbidity, temperature, dissolved oxygen, conductivity
- Edge Processing: Initial data filtering and preprocessing
- Communication: MQTT protocol for efficient, lightweight data transmission
### 2. Cloud & Processing Layer
- Backend APIs: FastAPI (Python) for robust, high-performance data handling
- Databases:
- PostgreSQL for structured data (sensor metadata, users, alerts)
- SQLite for development/testing
- Message Broker: RabbitMQ for reliable communication between components
- Analytics: Machine learning models for identifying abnormal readings
### 3. Application & Visualization Layer
- Frontend: React-based responsive dashboard
- Data Visualization: Interactive charts for parameter tracking
- Geospatial Interface: Map-based sensor location overview
- Documentation: Comprehensive guides with Docusaurus

## Technology Stack
<table style="border-collapse: collapse; border: 2px solid #666;">
<tr>
   <th style="border: 2px solid #666; padding: 8px;">Component</th>
   <th style="border: 2px solid #666; padding: 8px;">Technologies</th>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Frontend</td>
   <td style="border: 2px solid #666; padding: 8px;">ReactJS, TypeScript, Tailwind CSS</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Backend</td>
   <td style="border: 2px solid #666; padding: 8px;">FastAPI (Python)</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Database</td>
   <td style="border: 2px solid #666; padding: 8px;">PostgreSQL</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">IoT Communication</td>
   <td style="border: 2px solid #666; padding: 8px;">MQTT (Mosquitto broker)</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Message Queue</td>
   <td style="border: 2px solid #666; padding: 8px;">RabbitMQ</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Containerization</td>
   <td style="border: 2px solid #666; padding: 8px;">Docker</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Deployment</td>
   <td style="border: 2px solid #666; padding: 8px;">AWS</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Package Management</td>
   <td style="border: 2px solid #666; padding: 8px;">Poetry</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Logging</td>
   <td style="border: 2px solid #666; padding: 8px;">Loguru</td>
</tr>
<tr>
   <td style="border: 2px solid #666; padding: 8px;">Documentation</td>
   <td style="border: 2px solid #666; padding: 8px;">Docusaurus</td>
</tr>
</table>

## Intelligence Under the Hood

This isn’t just a data dashboard. The system also uses **trained machine learning models**, such as the **Isolation Forest**, to detect anomalies in lake behavior — spotting irregular patterns in temperature, turbidity, or sensor activity.

Microservices are provided to allow alert messages to be sent via **E-Mails, Whatsapp and Telegram** to users

---
## The Bigger Picture: Why We’re Doing This

At a time when sustainability matters more than ever, NammaLakes aims to bridge the gap between smart city tech and environmental conservation. By creating a scalable, open system for lake monitoring, we hope to empower local communities, researchers, and administrators to keep our lakes healthy and thriving.

This is more than a tech stack — it’s a collective step toward ecological responsibility, one data point at a time.

---
## Ready to Explore?

Whether you’re a developer, environmentalist, or curious citizen, we welcome contributions, feedback, and ideas. Dive into the code, check out the docs, or spin up your own deployment. There’s a lot to build — and a lot more to protect.

---

## Getting Started

Prerequisites
- Python 3.9+
- Node.js 16+
- Docker and Docker Compose
- Poetry (Python dependency management)

To get started locally:

```bash
git clone https://github.com/NammaLakes/nammalakes.git
cd nammalakes
```

Install Python packages:

```bash
cd backend
poetry install
```

Spin up containers (RabbitMQ, DB, API):

```bash
sudo docker compose up --build
```

For the dashboard:

```bash
cd dashboard
npm install
npm run dev
```

And for documentation:

```bash
cd docs
npm install
npm run start
```

## Folder Structure

The project is organized into the following core folders:

```bash
NammaLakes/
├── backend/               # FastAPI backend service
│   ├── data/              # Data storage and logs
│   ├── lakewatch/         # Core application code
│   │   ├── db/            # Database models and DAOs
│   │   ├── services/      # External service integrations
│   │   └── web/           # API endpoints and server config
│   ├── tests/             # Backend test suite
│   └── deploy/            # Deployment configurations
├── dashboard/             # React frontend application
│   ├── src/               # Source code
│   │   ├── components/    # Reusable UI components
│   │   ├── hooks/         # Custom React hooks
│   │   ├── lib/           # Utilities
│   │   └── pages/         # Page components
├── docs/                  # Documentation site
│   └── docs/              # Markdown documentation files
├── node/                  # IoT sensor node service
│   ├── node/              # Node application code
│   │   ├── read/          # GPIO sensor reading functionality
│   │   ├── transmit/      # RabbitMQ transmission logic
│   │   └── logger/        # Logging configuration
│   └── tests/             # Node test suite
└── .github/               # GitHub configuration files
    └── profile/           # Organization profile
```

## Contributing

We welcome contributions from developers, researchers, and curious minds alike.

To contribute:

1. Fork this repository.
2. Create a new branch:
   ```bash
   git checkout -b your-feature-branch
   ```
3. Make your changes and commit:
   ```bash
   git commit -m "Add your message here"
   ```
4. Push to your fork and open a Pull Request:
   ```bash
   git push origin your-feature-branch
   ```

We review PRs regularly and are happy to collaborate.

---

## Contact

For questions, collaboration, or demo access, reach out at:  
`contact@nammalakes.org`  
Or open an issue on this repository.
