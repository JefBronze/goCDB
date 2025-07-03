# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

goCDB is a Group Travel Management Platform consisting of three main components:
- **Mobile App**: React Native + Expo (iOS & Android)
- **Admin Panel**: Next.js web dashboard
- **Backend API**: Node.js + TypeScript + Express

## Important Instructions

### Documentation Updates
**CRITICAL**: Whenever you see the phrase "AI agent should help me with this" in `gocdb-instructions.md`, you MUST:
1. Replace that phrase with the actual implementation details as you complete each section
2. Update the documentation in real-time as you work on relevant features
3. Keep the instructions current with any modifications or improvements made during development

For example:
- When creating the project structure → Update the "Project Structure" section
- When setting up environment configuration → Update the "Environment Configuration" section
- When implementing testing → Update the relevant testing sections
- And so on for every section marked with "AI agent should help me with this"

## Common Development Commands

### Backend
```bash
# Development
cd backend && npm run dev

# Build
cd backend && npm run build

# Run tests
cd backend && npm test
cd backend && npm run test:watch  # Watch mode
cd backend && npm run test:coverage  # With coverage

# Linting and formatting
cd backend && npm run lint
cd backend && npm run lint:fix
cd backend && npm run format

# Database
cd backend && npm run db:migrate
cd backend && npm run db:seed
cd backend && npm run db:reset
```

### Mobile App
```bash
# Development
cd mobile && npm start
cd mobile && npm run ios  # iOS simulator
cd mobile && npm run android  # Android emulator

# Build
cd mobile && expo build:ios
cd mobile && expo build:android

# Testing
cd mobile && npm test
cd mobile && npm run test:watch

# Linting
cd mobile && npm run lint
cd mobile && npm run lint:fix
```

### Admin Panel
```bash
# Development
cd admin && npm run dev

# Build and production
cd admin && npm run build
cd admin && npm start  # Production server

# Testing
cd admin && npm test
cd admin && npm run test:e2e

# Linting
cd admin && npm run lint
```

## High-Level Architecture

### Backend Structure
The backend follows a layered architecture:
- **Controllers**: Handle HTTP requests and responses
- **Services**: Business logic implementation
- **Repositories**: Database operations using Prisma ORM
- **Middleware**: Authentication, validation, error handling
- **WebSocket**: Real-time communication layer

Key architectural decisions:
- JWT-based authentication with refresh tokens
- Redis for caching and session management
- Queue system for background jobs (notifications, exports)
- Microservices-ready design for future scaling

### Mobile App Architecture
- **Navigation**: React Navigation with bottom tabs and stack navigators
- **State Management**: Global state with Redux/Zustand
- **Offline Support**: SQLite for local storage, sync queue for API calls
- **UI Components**: Shared component library with React Native Paper

### Admin Panel Architecture
- **SSR/SSG**: Next.js for optimized performance
- **API Routes**: Backend for frontend pattern
- **Authentication**: Session-based with NextAuth
- **UI**: Tailwind CSS with responsive design

### Database Schema
Primary entities:
- **Users**: Authentication and profiles
- **Groups**: Travel groups with members
- **Trips**: Multi-destination itineraries
- **Expenses**: Financial tracking with splits
- **Messages**: Chat functionality
- **Documents**: Shared files and media

### Security Considerations
- All sensitive data encrypted at rest
- API rate limiting implemented
- Input validation on all endpoints
- Biometric authentication on mobile
- Regular security audits scheduled

### Testing Strategy
- Unit tests for all business logic
- Integration tests for API endpoints
- E2E tests for critical user flows
- Minimum 80% code coverage target

## Development Workflow

1. Feature branches from `develop`
2. Pull requests require code review
3. CI/CD pipeline runs tests and linting
4. Automated deployment to staging
5. Manual promotion to production

## Key Technical Decisions

- **Monorepo Structure**: Shared types and utilities between projects
- **TypeScript Everywhere**: Type safety across all codebases
- **API-First Design**: Backend developed ahead of frontends
- **Offline-First Mobile**: Local database with sync capabilities
- **Real-time Updates**: WebSocket connections for live features
- **Multi-currency Support**: Exchange rate API integration
- **File Storage**: S3-compatible object storage for documents