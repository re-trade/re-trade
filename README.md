# Re-Trade Monorepo

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Java](https://img.shields.io/badge/Java-24-orange.svg)](https://www.oracle.com/java/)
[![Node.js](https://img.shields.io/badge/Node.js-20+-green.svg)](https://nodejs.org/)
[![Next.js](https://img.shields.io/badge/Next.js-15-black.svg)](https://nextjs.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-brightgreen.svg)](https://spring.io/projects/spring-boot)

## 🌟 Overview

Re-Trade is a comprehensive monorepo project that provides a complete e-commerce and trading platform ecosystem. The project consists of multiple microservices and client applications designed to handle various aspects of online trading, user management, and business operations.

## 🏗️ Architecture

This monorepo contains three main components:

### 🖥️ Frontend Applications (`rt-client`)
- **Admin Panel**: Management dashboard for administrators
- **Customer App**: Customer-facing e-commerce application
- **Seller App**: Seller dashboard and management tools

### ☕ Backend Services (`rt-coffee-service`)
Java-based microservices architecture with Spring Boot:
- **Account Service**: User authentication and authorization
- **Main Service**: Core business logic and APIs
- **Gateway Service**: API gateway and routing
- **Storage Service**: File and data storage management
- **Voucher Service**: Discount and promotion management
- **Feedback & Notification Service**: User feedback and notification system

### 🚀 Node.js Service (`rt-node-service`)
GraphQL-based mobile backend service providing:
- Mobile API endpoints
- Real-time data synchronization
- Integration with main backend services

## 🛠️ Technology Stack

### Frontend
- **Framework**: Next.js 15 with TypeScript
- **Styling**: Tailwind CSS
- **Build Tool**: Turbo (Monorepo management)
- **Charts**: Highcharts
- **Package Manager**: Yarn

### Backend (Java)
- **Framework**: Spring Boot 3.4.5
- **Java Version**: 24
- **Build Tool**: Maven
- **Communication**: gRPC
- **Service Discovery**: Consul
- **Databases**: MongoDB, PostgreSQL

### Backend (Node.js)
- **Runtime**: Node.js 20+
- **Framework**: Express.js
- **API**: GraphQL with Apollo Server
- **Communication**: gRPC
- **Language**: TypeScript

## 🚀 Quick Start

### Prerequisites

Ensure you have the following installed:
- **Java JDK 17-24** (for backend services)
- **Node.js 20+** (for frontend and Node.js service)
- **Docker & Docker Compose** (for infrastructure)
- **Maven** (for Java services)
- **Yarn** (for frontend applications)

### Infrastructure Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/re-trade/re-trade.git
   cd re-trade
   ```

2. **Start infrastructure services**
   ```bash
   # Navigate to coffee service for infrastructure setup
   cd rt-coffee-service

   # Copy environment template
   cp .env.example .env
   # Edit .env with your configuration

   # Start infrastructure (Consul, MongoDB, PostgreSQL)
   docker compose -f ./docker/compose.local.yaml -p retrade-services --env-file .env up -d
   ```

### Backend Services

1. **Start Java services**
   ```bash
   cd rt-coffee-service
   mvn clean install
   # Configure environment variables as per .env.examples
   # Run individual services or use your IDE
   ```

2. **Start Node.js service**
   ```bash
   cd rt-node-service
   yarn install
   yarn dev
   ```

### Frontend Applications

```bash
cd rt-client
yarn install
yarn dev
```

Access the applications:
- **Admin Panel**: http://localhost:3001
- **Customer App**: http://localhost:3000
- **Seller App**: http://localhost:3002

## 📁 Project Structure

```
re-trade/
├── rt-client/                 # Frontend applications
│   ├── apps/
│   │   ├── admin/            # Admin dashboard
│   │   ├── customer/         # Customer application
│   │   └── seller/           # Seller application
│   └── packages/             # Shared packages
├── rt-coffee-service/        # Java backend services
│   ├── services/
│   │   ├── account/          # User management
│   │   ├── main/             # Core business logic
│   │   ├── gateway/          # API gateway
│   │   ├── storage/          # File storage
│   │   ├── voucher/          # Promotions
│   │   └── feedback-notification/
│   └── packages/             # Shared Java packages
└── rt-node-service/          # Node.js GraphQL service
    └── src/                  # Source code
```

## 🔧 Development

### Git Workflow

We follow a structured branching strategy:

**Branch Naming Convention:**
```
<type>/<short-description>
```

**Types:**
- `feature/` - New features
- `bugfix/` - Bug fixes
- `hotfix/` - Urgent production fixes
- `release/` - Release preparation
- `chore/` - Maintenance tasks
- `docs/` - Documentation updates
- `test/` - Test updates

**Rules:**
- Create branches from `develop`, not `main`
- Add reviewers for all merge requests
- No force pushing
- Keep branches up to date with develop
- Ensure code is runnable before pushing

### Code Standards

- Remove unused imports
- Follow language-specific conventions
- Write meaningful commit messages
- Add tests for new features
- Document complex logic

## 🧪 Testing

Each service includes its own testing setup:

```bash
# Frontend tests
cd rt-client
yarn test

# Java service tests
cd rt-coffee-service
mvn test

# Node.js service tests
cd rt-node-service
yarn test
```

## 🚢 Deployment

Each service includes Docker configuration for containerized deployment:

- Frontend apps: Individual Dockerfiles in each app directory
- Java services: Dockerfiles in each service directory
- Node.js service: Dockerfile in root directory

## 👥 Contributors

- [@AnataAria](https://github.com/AnataAria)
- [@haiha0402](https://github.com/haiha0402)
- [@tohka-vo-tri](https://github.com/tohka-vo-tri)
- [@Shuichiiv](https://github.com/Shuichiiv)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

If you encounter any issues or need help:

1. Check the individual service READMEs for specific setup instructions
2. Review the troubleshooting sections in service documentation
3. Contact the development team for assistance

## 🔗 Related Documentation

- [Frontend Documentation](./rt-client/README.md)
- [Java Backend Documentation](./rt-coffee-service/README.md)
- [Node.js Service Documentation](./rt-node-service/README.md)