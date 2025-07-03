# goCDB - Group Travel Management Platform
## Complete Development Instructions & Implementation Guide

## Table of Contents
1. [Project Overview](#project-overview)
2. [Getting Started](#getting-started)
3. [Project Structure](#project-structure)
4. [Development Phases](#development-phases)
5. [Technical Implementation](#technical-implementation)
6. [Testing Strategy](#testing-strategy)
7. [Deployment Guide](#deployment-guide)
8. [Best Practices](#best-practices)
9. [Troubleshooting](#troubleshooting)

---

## Project Overview

**goCDB** is a cross-platform mobile application designed to streamline group travel management and organizing trips together. The platform consolidates financial tracking, communication coordination and logistics management into a single, purpose-built solution.

### Core Components
- **Mobile App**: React Native + Expo (iOS & Android)
- **Admin Panel**: Next.js web dashboard
- **Backend API**: Node.js + TypeScript + Express
- **Database**: PostgreSQL + Redis
- **Real-time**: Socket.io for live updates

### Key Features
- 💰 **Smart Expense Splitting & Settlement**  
  Split costs evenly or customize shares, track who owes whom, and settle balances in-app.

- 💬 **Real-Time Group Communication**  
  Built-in chat with threaded topics (e.g. “Day 2 lunch”), plus optional WhatsApp integration.

- 📅 **Trip Planning & Management**  
  Multi-destination itineraries, drag-and-drop day-by-day schedules, and shared to-do lists with task assignments.

- 🌐 **Multi-Currency Support**  
  Auto-convert expenses across exchange rates and settle in any currency.

- 🔔 **Push Notifications & Reminders**  
  Instant alerts for new expenses, upcoming deadlines, vote results, and itinerary changes.

- 🗺️ **Interactive Map & Location Sharing**  
  Drop pins for meeting points or attractions, share live locations, and get turn-by-turn directions.

- 📄 **Secure Document Storage**  
  Store and access PDFs, tickets, visas, and confirmations in one encrypted hub.

- 📊 **Financial Analytics & Reporting**  
  View per-person and overall spend breakdowns, generate CSV/PDF summaries, and track budget vs. actual.

- 💳 **In-App Payment Integration**  
  Connect credit cards, PayPal, Venmo, or local e-wallets to settle group bills instantly.

- ❤️ **Personal Health & Emergency Info**  
  Store blood type, allergies, emergency contacts, and medical notes accessible offline for peace of mind.

- 🔒 **User Roles & Permissions**  
  Manage admins, editors, and viewers through the web panel with granular access controls.

- 📥 **Offline Mode & Seamless Sync**  
  Add expenses or view itineraries without connectivity—everything syncs automatically when you’re back online.

- 🏄 **Surf Condition & Weather Tracking**  
  Check live surf reports, tides, and local weather forecasts for your beach-side adventures.

- 🖼️ **Shared Photo Album & Memory Board**  
  Upload trip photos, comment on memories, and create a collaborative scrapbook.

- 🏷️ **Custom Tags & Filters**  
  Organize expenses, tasks, and documents by category, date, or person for quick access.

- 🔗 **Third-Party API Integrations**  
  Plug into Stripe, Google Calendar, Dropbox, and other services to automate workflows.

---

## Getting Started

### Prerequisites
```bash
# Required software
Node.js
npm
Git
Docker Desktop
Cursor
- AI agent should help me with identify any other tool needed.

# Mobile development
Expo CLI
Expo Go
Xcode
Android Studio
- AI agent should help me with identify any other tool needed.
```

### Initial Setup

1. **Create a new repository**

Since the repository does not exist yet, you need to create it first:
- On GitHub, create a new repository named `gocdb` under your organization or user account.

2. **Continue with the setup**

- AI agent should help me with this.

### Environment Configuration

- AI agent should help me with this.

---

## Project Structure

The goCDB project follows a monorepo structure with clear separation of concerns:

```
goCDB/
├── backend/                    # Node.js + TypeScript API Server
│   ├── src/
│   │   ├── controllers/       # HTTP request handlers
│   │   ├── services/          # Business logic
│   │   ├── repositories/      # Database operations
│   │   ├── middleware/        # Auth, validation, error handling
│   │   ├── models/            # Data models and types
│   │   ├── routes/            # API route definitions
│   │   ├── utils/             # Helper functions
│   │   └── websocket/         # Real-time communication
│   ├── tests/                 # Backend tests
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
│
├── admin/                      # Next.js Admin Panel
│   ├── src/
│   │   ├── components/        # Reusable UI components
│   │   ├── pages/             # Next.js pages
│   │   ├── hooks/             # Custom React hooks
│   │   ├── utils/             # Helper functions
│   │   ├── styles/            # Global styles (Tailwind)
│   │   └── lib/               # API clients and utilities
│   ├── public/                # Static assets
│   ├── tests/                 # Admin panel tests
│   ├── package.json
│   ├── tsconfig.json
│   ├── tailwind.config.js
│   └── next.config.js
│
├── mobile/                     # React Native + Expo App
│   ├── src/
│   │   ├── components/        # Reusable mobile components
│   │   ├── screens/           # App screens
│   │   ├── navigation/        # Navigation configuration
│   │   ├── hooks/             # Custom React hooks
│   │   ├── utils/             # Helper functions
│   │   ├── store/             # State management
│   │   └── services/          # API services
│   ├── assets/                # Images, fonts, etc.
│   ├── tests/                 # Mobile app tests
│   ├── package.json
│   ├── tsconfig.json
│   ├── app.json
│   └── expo.json
│
├── shared/                     # Shared TypeScript Types & Utilities
│   ├── src/
│   │   ├── types/             # Shared TypeScript interfaces
│   │   ├── utils/             # Shared utility functions
│   │   └── constants/         # Shared constants
│   ├── package.json
│   └── tsconfig.json
│
├── database/                   # Database Schema & Migrations
│   ├── migrations/            # Database migration files
│   ├── seeds/                 # Database seed data
│   ├── schema.sql             # Database schema
│   └── prisma/                # Prisma ORM configuration
│       ├── schema.prisma
│       └── migrations/
│
├── docker-compose.yml          # Development environment
├── .github/                    # GitHub Actions CI/CD
│   └── workflows/
├── docs/                       # Additional documentation
├── package.json                # Root package.json (workspace config)
├── .gitignore                  # Git ignore rules
├── README.md                   # Project overview
├── ROADMAP.md                  # Development roadmap
├── CLAUDE.md                   # Claude Code guidelines
└── gocdb-instructions.md       # This file
```

### Key Design Decisions

1. **Monorepo Architecture**: All components in one repository for easier development and shared code
2. **TypeScript Everywhere**: Type safety across backend, admin, and mobile
3. **Shared Package**: Common types and utilities prevent code duplication
4. **Clear Separation**: Each component has its own package.json and configuration
5. **Development Scripts**: Root package.json provides convenient scripts for all components
6. **Docker Integration**: Complete development environment with one command

---

## Development Phases

- AI agent should help me with this.

### Admin Panel Features (Parallel Development)

> **AI Assistant Role**  
> The AI agent will help me develop an admin panel in parallel with the main app, providing a centralized overview of all platform activities, data, and configurations. It will automate routine admin tasks, surface key insights, and enable real-time control over users, trips, expenses, and system settings.

### Suggested Admin Panel Features
- 📊 **Central Dashboard**  
  Overview of active trips, total spend, unsettled balances, and recent activity logs at a glance.

- 👥 **User & Group Management**  
  - Invite, approve, or deactivate users  
  - Assign roles (admin, moderator, viewer)  
  - View health/emergency info (blood type, allergies) with privacy controls

- 🗺️ **Trip & Itinerary Oversight**  
  - Create, edit, or cancel trips  
  - Monitor per-trip budgets, headcounts, and status  
  - Drill down into day-by-day schedules and task assignments

- 💰 **Expense & Payment Control**  
  - View all logged expenses in a consolidated table  
  - Flag disputes or override smart splits  
  - Trigger in-app settlements or refunds

- 📈 **Analytics & Reporting**  
  - Generate CSV/PDF reports for spend by user, trip, or category  
  - Visualize trends (e.g., monthly group spend, top cost categories)  
  - Export data for accounting or audit

- 🔔 **Notification & Alerts Configuration**  
  - Define thresholds (e.g., budget overruns) that trigger push/email alerts  
  - Manage announcement channels and poll schedules

- 🔒 **Permissions & Security Settings**  
  - Configure two-factor authentication and session timeouts  
  - Audit log of admin actions (who changed what, when)  
  - IP or role-based access restrictions

- ⚙️ **System & Integration Settings**  
  - Connect or revoke third-party APIs (Stripe, Google Calendar, WhatsApp)  
  - Customize multi-currency exchange rates and rounding rules  
  - White-label branding (logos, color schemes, URLs)

- 📄 **Document & Media Repository**  
  - Approve or remove uploaded documents (tickets, visas)  
  - Manage shared photo albums and memory boards

- 🩺 **Health & Emergency Toolkit**  
  - View and update group members’ emergency contacts and medical notes  
  - Export emergency summary for offline use

- 🌐 **Global Configuration**  
  - Set default languages, time zones, and units (currency, distance)  
  - Manage feature flags (enable/disable beta tools)

### Phase 7: Testing Implementation (Throughout)

#### Mobile Testing

- AI agent should help me with this.

#### E2E Testing

- AI agent should help me with this.

### Phase 8: Deployment Setup (Week 16)

#### CI/CD Pipeline

- AI agent should help me with this.

---

## Technical Implementation

### Offline-First Architecture

- AI agent should help me with this.

### Push Notification Implementation

- AI agent should help me with this.

### Security Implementation

   - AI agent advice me if this is good enough based on industy best practices based on OWASP Mobile Security, NIST Standards, ISO Standards and Platform Guidelines like Apple's iOS Security Guide, Android Security Best Practices and Google Play Protect Requirements.

---

## Testing Strategy

### Unit Testing
- AI agent should help me with this.

### E2E Testing for Mobile
- AI agent should help me with this.

### TDD
- AI agent should help me with this only if it thinks it fits to the ocasion.

---

## Deployment Guide

### Backend Deployment (AWS ECS)

1. **Build Docker image**
- AI agent should help me with this.

2. **Deploy to ECS**
- AI agent should help me with this.

### Mobile App Deployment

1. **iOS (App Store)**
- AI agent should help me with this.

2. **Android (Google Play)**
- AI agent should help me with this.

### Admin Panel Deployment

- AI agent should help me with this.

---

## Best Practices

### Code Style & Standards

1. **TypeScript Strict Mode**
- AI agent should help me with this.


2. **ESLint Configuration**
- AI agent should help me with this.

3. **Git Commit Convention**
- AI agent should help me with this.

### Performance Optimization

1. **Mobile Performance**
   - Use React.memo for expensive components
   - Implement FlashList for large lists
   - Optimize images with react-native-fast-image
   - Enable Hermes for Android
   - Use ProGuard for production builds
   - AI agent should help me with this.

2. **API Performance**
   - Implement pagination for all list endpoints
   - Use database indexes for frequently queried fields
   - Enable response compression
   - Implement caching with Redis
   - Use connection pooling for database
   - AI agent should help me with this.

3. **Bundle Size Optimization**
   - Tree-shake unused code
   - Lazy load screens and features
   - Use dynamic imports for large libraries
   - Optimize asset sizes
   - AI agent should help me with this.

### Security Best Practices

1. **Authentication**
   - Use short-lived access tokens (15 min)
   - Implement refresh token rotation
   - Store tokens securely (Keychain/Keystore)
   - Enable biometric authentication
   - AI agent advice me if this is good enough based on industy best practices based on OWASP Mobile Security, NIST Standards, ISO Standards and Platform Guidelines like Apple's iOS Security Guide, Android Security Best Practices and Google Play Protect Requirements.

2. **API Security**
   - Validate all inputs
   - Sanitize user-generated content
   - Implement CORS properly
   - Use HTTPS everywhere
   - Rate limit all endpoints
   - AI agent advice me if this is good enough based on industy best practices based on OWASP Mobile Security, NIST Standards, ISO Standards and Platform Guidelines like Apple's iOS Security Guide, Android Security Best Practices and Google Play Protect Requirements.

3. **Data Protection**
   - Encrypt sensitive data at rest
   - Use secure communication channels
   - Implement proper access controls
   - Regular security audits
   - AI agent advice me if this is good enough based on industy best practices based on OWASP Mobile Security, NIST Standards, ISO Standards and Platform Guidelines like Apple's iOS Security Guide, Android Security Best Practices and Google Play Protect Requirements.

---

## Troubleshooting

### Common Issues

1. **Build Failures**
- AI agent should help me with this.

2. **Metro Bundler Issues**
- AI agent should help me with this.

3. **Database Migration Issues**
- AI agent should help me with this.

4. **Type Errors**
- AI agent should help me with this.


### Debug Tools

1. **React Native Debugger**
- AI agent should help me with this.

2. **Flipper**
- AI agent should help me with this.

3. **Redux DevTools**
- AI agent should help me with this.

4. **Other Debug Tools**
- AI agent should help me identify if this project needs any other debug tools.

### Performance Profiling

- AI agent should help me with this.

---

## Support & Resources

### Documentation
- AI agent should create the documentation for every implementation as we go.

### Helpful Links
- [React Native Documentation](https://reactnative.dev/docs/getting-started)
- [Expo Documentation](https://docs.expo.dev/)
- [Prisma Documentation](https://www.prisma.io/docs/)
- [Next.js Documentation](https://nextjs.org/docs)

### Contact
- GitHub: JefBronze
- Email: jefersonbronze@gmail.com

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.