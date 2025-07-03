# goCDB - Group Travel Management Platform

A comprehensive cross-platform solution for managing group travel, expenses, and communication.

## Overview

goCDB streamlines group travel management by consolidating financial tracking, communication coordination, and logistics management into a single, purpose-built solution.

### Components

- **Mobile App**: React Native + Expo (iOS & Android)
- **Admin Panel**: Next.js web dashboard
- **Backend API**: Node.js + TypeScript + Express
- **Database**: PostgreSQL + Redis

## Quick Start

### Prerequisites

- Node.js (>=18.0.0)
- npm (>=8.0.0)
- Docker Desktop
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/JefBronze/goCDB.git
cd goCDB

# Install dependencies
npm install

# Start development environment
npm run docker:up
npm run dev
```

### Access Points

- **Admin Panel**: http://localhost:3000
- **API Documentation**: http://localhost:4000/docs
- **Database Admin**: http://localhost:5050
- **Redis Admin**: http://localhost:8001

## Project Structure

```
goCDB/
├── backend/          # Node.js + TypeScript API
├── admin/           # Next.js admin panel
├── mobile/          # React Native + Expo app
├── shared/          # Shared types and utilities
├── database/        # Database schema and migrations
├── docker-compose.yml
└── package.json     # Root package.json for workspaces
```

## Development

### Available Scripts

```bash
# Development
npm run dev              # Start backend + admin
npm run dev:backend      # Backend only
npm run dev:admin        # Admin panel only
npm run dev:mobile       # Mobile app only

# Building
npm run build            # Build all
npm run build:backend    # Build backend
npm run build:admin      # Build admin panel

# Testing
npm run test             # Run all tests
npm run test:backend     # Backend tests
npm run test:admin       # Admin tests

# Linting
npm run lint             # Lint all
npm run lint:backend     # Lint backend
npm run lint:admin       # Lint admin

# Docker
npm run docker:up        # Start all services
npm run docker:down      # Stop all services
npm run docker:logs      # View logs
```

## Features

- 💰 Smart expense splitting and settlement
- 💬 Real-time group communication
- 📅 Multi-destination trip planning
- 🌐 Multi-currency support
- 🔔 Push notifications and reminders
- 🗺️ Interactive maps and location sharing
- 📄 Secure document storage
- 📊 Financial analytics and reporting
- 💳 In-app payment integration
- 🔒 Biometric authentication
- 📱 Offline-first mobile experience

## Documentation

- [Development Roadmap](./ROADMAP.md)
- [Technical Instructions](./gocdb-instructions.md)
- [Claude Code Guidelines](./CLAUDE.md)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new features
5. Ensure all tests pass
6. Submit a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

- **GitHub**: [JefBronze](https://github.com/JefBronze)
- **Email**: jefersonbronze@gmail.com