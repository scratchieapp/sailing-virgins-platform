# sailing-virgins-platform
# Sailing Virgins Platform

A modern, integrated platform for managing sailing courses, bookings, and community engagement. Built with Supabase, Next.js, and React Native.

## 🚀 Project Overview

This platform replaces fragmented Google Sheets and third-party tools with a unified system that handles:
- Course scheduling and management
- Online bookings with payment processing
- Instructor operations and expense tracking
- Community features and sailing logbooks
- AI-powered course recommendations

## 📁 Project Structure

```
sailing-virgins-platform/
├── apps/                      # Application packages
│   ├── admin-portal/         # Next.js admin dashboard
│   ├── booking-web/          # Public booking website
│   ├── instructor-app/       # Instructor web app
│   └── mobile/              # React Native app
│
├── packages/                 # Shared packages
│   ├── database/            # Supabase migrations & schemas
│   │   ├── migrations/      # SQL migration files
│   │   ├── seeds/          # Seed data for development
│   │   └── types/          # Generated TypeScript types
│   │
│   ├── shared/              # Shared utilities
│   │   ├── utils/          # Helper functions
│   │   ├── types/          # Shared TypeScript types
│   │   └── constants/      # Shared constants
│   │
│   └── ui/                  # Shared UI components
│       ├── components/      # React components
│       └── styles/         # Shared styles
│
├── docs/                    # Documentation
│   ├── api/                # API documentation
│   ├── deployment/         # Deployment guides
│   └── user-guides/        # User documentation
│
├── scripts/                 # Utility scripts
│   ├── migration/          # Data migration scripts
│   └── backup/             # Backup scripts
│
└── config/                  # Configuration files
    ├── env/                # Environment templates
    └── docker/             # Docker configurations
```

## 🛠️ Tech Stack

### Backend
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth
- **Real-time**: Supabase Realtime
- **File Storage**: Supabase Storage
- **Edge Functions**: Supabase Edge Functions

### Frontend
- **Admin Portal**: Next.js 14, TypeScript, Tailwind CSS
- **Booking Site**: Next.js 14, TypeScript, Tailwind CSS
- **Mobile Apps**: React Native, Expo
- **UI Components**: Radix UI, shadcn/ui

### Infrastructure
- **Hosting**: Vercel (web apps), Supabase (backend)
- **Payments**: Stripe
- **Email**: Resend/SendGrid via Supabase
- **Monitoring**: Vercel Analytics, Supabase Dashboard

### Integrations
- **Booking Channels**: Rezdy (via RezdyConnect API)
- **CRM**: HubSpot
- **Project Management**: Asana
- **Automation**: n8n
- **AI/LLM**: OpenAI GPT-4

## 🚦 Getting Started

### Prerequisites
- Node.js 18+ and npm/yarn
- Supabase CLI
- Git
- A Supabase account
- A Stripe account (for payments)

### Initial Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/sailing-virgins/sailing-virgins-platform.git
   cd sailing-virgins-platform
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up Supabase**
   ```bash
   # Install Supabase CLI globally
   npm install -g supabase

   # Login to Supabase
   supabase login

   # Link to your project
   supabase link --project-ref <your-project-id>
   ```

4. **Configure environment variables**
   ```bash
   # Copy environment templates
   cp config/env/.env.example apps/admin-portal/.env.local
   cp config/env/.env.example apps/booking-web/.env.local
   ```

5. **Run database migrations**
   ```bash
   cd packages/database
   supabase db push
   ```

6. **Start development servers**
   ```bash
   # From project root
   npm run dev:admin    # Start admin portal
   npm run dev:booking  # Start booking site
   ```

## 📝 Development Workflow

### Database Changes
1. Create a new migration: `supabase migration new <migration_name>`
2. Write SQL in the generated file
3. Apply locally: `supabase db reset`
4. Push to production: `supabase db push`

### Adding Features
1. Create feature branch: `git checkout -b feature/your-feature`
2. Implement changes
3. Write tests
4. Submit PR with description

### Code Standards
- TypeScript for all new code
- ESLint + Prettier for formatting
- Conventional commits
- Mobile-first responsive design
- Accessibility (WCAG 2.1 AA)

## 🧪 Testing

```bash
# Run all tests
npm test

# Run specific app tests
npm run test:admin
npm run test:booking

# E2E tests
npm run test:e2e
```

## 📦 Deployment

### Staging
- Automatic deployment on `develop` branch push
- Preview deployments for all PRs

### Production
1. Merge to `main` branch
2. Automatic deployment via GitHub Actions
3. Database migrations run automatically

## 📊 Project Phases

### ✅ Phase 1: Core Backend & Admin (Months 0-2)
- Database setup with Supabase
- Admin portal for course management
- Basic booking management
- Data migration from Google Sheets

### 🚧 Phase 2: Booking Frontend (Months 2-3)
- Public course listings
- Online booking flow
- Stripe payment integration
- User accounts

### 📱 Phase 3: Instructor Portal (Months 3-4)
- Instructor dashboard
- Expense management
- Trip tools

### 🌊 Phase 4: Community Features (Months 4-5)
- Sailing logbooks
- Photo sharing
- Social features

### 📲 Phase 5: Mobile Apps (Months 5-6+)
- React Native apps
- GPS tracking
- Offline support

## 🔧 Useful Commands

```bash
# Database
supabase db reset          # Reset local database
supabase db push          # Push migrations to remote
supabase db dump -f dump.sql  # Create backup

# Development
npm run dev               # Start all dev servers
npm run build            # Build all apps
npm run lint             # Run linting
npm run format           # Format code

# Deployment
npm run deploy:staging   # Deploy to staging
npm run deploy:prod     # Deploy to production
```

## 📚 Documentation

- [Database Schema](./docs/database-schema.md)
- [API Documentation](./docs/api/README.md)
- [Deployment Guide](./docs/deployment/README.md)
- [Contributing Guide](./CONTRIBUTING.md)

## 🤝 Contributing

1. Check existing issues or create new one
2. Fork the repository
3. Create feature branch
4. Make changes with tests
5. Submit PR with clear description

## 📄 License

Copyright © 2025 Sailing Virgins. All rights reserved.

---

For questions or support, contact: tech@sailingvirgins.com
