# Hermes Fullstack

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

A comprehensive cybersecurity training and vulnerability demonstration platform. Hermes combines multiple components for web security assessment, vulnerability scanning, and education based on the OWASP Application Security Verification Standard (ASVS) Level 1 framework.

## 🚨 Security Warning

Parts of this application intentionally contain security vulnerabilities for educational purposes. **DO NOT** deploy these components in a production environment or on a public-facing server. The platform should only be run in controlled, isolated environments for learning and training.

## 🌟 Project Components

### 1. Web Scanner
A Python-based security scanner that automatically checks websites for common vulnerabilities and security issues based on OWASP ASVS Level 1 requirements.

### 2. Weak Website
A deliberately vulnerable web application demonstrating common security vulnerabilities from the OWASP ASVS Level 1 checklist, including:
- Authentication vulnerabilities
- Session management flaws
- Access control weaknesses
- Input validation issues
- Cryptographic failures

### 3. GUI
An Ionic/React-based dashboard that provides an interface for scanning websites, viewing vulnerability reports, and learning about web security concepts.

## 🏗️ Architecture

- **Web Scanner**: Python application with asynchronous scanning capabilities
- **Weak Website Client**: React application with TypeScript and ShadCN UI components
- **Weak Website Server**: NestJS backend with TypeScript and TypeORM
- **GUI**: Ionic/React application with TypeScript
- **Containerization**: Docker and Docker Compose for deployment

## 🚀 Getting Started

### Prerequisites

- [Docker](https://www.docker.com/get-started) and Docker Compose
  - Docker Engine: ≥ 20.10.0 for reliable host.docker.internal usage on Linux
  - Docker Desktop: Any recent stable version on macOS/Windows supports host.docker.internal
  - Docker Compose: ≥ 1.28.0 if using the extra_hosts: ["host.docker.internal:host-gateway"] syntax
- [Node.js](https://nodejs.org/) (v18 or higher) for local development
- [Python](https://www.python.org/) 3.9+ for web scanner development
- [Git](https://git-scm.com/) with support for submodules

### Quick Start

1. Clone the repository with submodules:
   ```bash
   git clone --recurse-submodules https://github.com/yourusername/hermes-fullstack.git
   cd hermes-fullstack
   ```

   If you've already cloned the repository without submodules:
   ```bash
   git submodule update --init --recursive
   ```

2. Start the complete platform:
   ```bash
   docker compose up --build -d
   ```

3. Access the components:
   - GUI Dashboard: http://localhost:5173
   - Weak Website: http://localhost:8081
   - Web Scanner API: http://localhost:5000

4. Stop the platform:
   ```bash
   docker compose down
   ```

## 💻 Local Development

### Web Scanner

```bash
cd web-scanner
pip install -r requirements.txt
python src/main.py <url>
```

### Weak Website Client

```bash
cd weak-website/client
npm install
npm run dev
```

### Weak Website Server

```bash
cd weak-website/server
npm install
npm run start:dev
```

### GUI

```bash
cd gui
npm install
npm run dev
```

## 📚 OWASP ASVS Framework

This project is built around the [OWASP Application Security Verification Standard (ASVS) Level 1](https://owasp.org/www-project-application-security-verification-standard/) requirements, covering:

- V1: Architecture, Design and Threat Modeling
- V2: Authentication
- V3: Session Management
- V4: Access Control
- V5: Validation, Sanitization and Encoding
- V6: Stored Cryptography
- V7: Error Handling and Logging
- V8: Data Protection
- V9: Communications
- V10: Malicious Code
- V11: Business Logic
- V12: Files and Resources
- V13: API and Web Service
- V14: Configuration

## 🛠️ Technology Stack

- **Web Scanner**: Python, aiohttp, beautifulsoup4, pyppeteer
- **Weak Website Frontend**: React, TypeScript, ShadCN UI, TailwindCSS, Vite
- **Weak Website Backend**: NestJS, TypeScript, TypeORM, MySQL
- **GUI**: Ionic, React, TypeScript, TailwindCSS
- **Containerization**: Docker, Docker Compose

## 🤝 Contributing

Contributions are welcome! Please read the documentation for each component before submitting pull requests or issues.

## 📑 Project Structure

```
hermes-fullstack/
├── docker-compose.yml        # Main Docker Compose configuration
├── web-scanner/              # Python-based vulnerability scanner (git submodule)
├── weak-website/             # Deliberately vulnerable web application (git submodule)
│   ├── client/               # React frontend
│   └── server/               # NestJS backend
└── gui/                      # Ionic/React dashboard
```

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This application includes intentionally vulnerable components designed for educational and training purposes only. The maintainers are not responsible for any misuse of the vulnerabilities demonstrated in this project.