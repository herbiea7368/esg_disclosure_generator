# ESG Disclosure Generator for SMEs

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/%3C%2F%3E-TypeScript-%230074c1.svg)](https://www.typescriptlang.org/)
[![Next.js](https://img.shields.io/badge/Next.js-13+-black)](https://nextjs.org/)
[![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com)

A comprehensive SaaS platform that guides Small and Medium Enterprises (SMEs) through ESG data collection and generates jurisdiction-compliant disclosure reports. Built with modern web technologies and designed for scalability, security, and user experience.

## 🚀 Features

### Core Functionality
- **Multi-Jurisdiction Support**: EU (CSRD/ESRS), UK (TCFD), US (SEC/California), Canada (ISSB), MENA, Asia-Pacific
- **Smart Rules Engine**: Automatic compliance requirement detection based on company profile
- **Progressive Data Collection**: Guided wizard with smart defaults and real-time validation
- **Professional Report Generation**: PDF, Word, JSON, and XBRL export formats
- **Real-Time Preview**: Live document preview during data entry
- **Industry Benchmarking**: Compare performance against sector peers

### Business Features  
- **Freemium Model**: Free ESG readiness assessment with paid tier upgrades
- **Multi-Tenancy**: Organization-based access control with role management
- **API Integration**: RESTful API for third-party integrations
- **White-Label Options**: Customizable branding for enterprise clients
- **Compliance Tracking**: Automated deadline management and progress monitoring

### Technical Features
- **GDPR Compliant**: EU hosting with comprehensive data protection
- **Real-Time Collaboration**: Multi-user editing with conflict resolution
- **Audit Trail**: Complete activity logging for compliance requirements
- **Performance Optimized**: Sub-2 second load times, scalable architecture
- **Mobile Responsive**: Optimized experience across all devices

## 🛠 Tech Stack

### Frontend
- **Framework**: Next.js 14 with App Router
- **Styling**: TailwindCSS with custom design system
- **Language**: TypeScript for type safety
- **Forms**: React Hook Form with Zod validation
- **State Management**: Zustand + React Query
- **PDF Generation**: @react-pdf/renderer

### Backend
- **Database**: PostgreSQL with Supabase
- **Authentication**: Supabase Auth with Row Level Security
- **API**: Supabase Edge Functions (TypeScript)
- **Real-time**: Supabase Realtime for live updates
- **File Storage**: Supabase Storage for document assets

### Infrastructure
- **Hosting**: Supabase (EU regions for GDPR compliance)
- **CDN**: Global edge network for optimal performance
- **Monitoring**: Built-in analytics and error tracking
- **Backup**: Automated daily backups with point-in-time recovery

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Node.js 18+ 
- npm or yarn package manager
- Git for version control

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/vidler-co/esg-disclosure-generator.git
cd esg-disclosure-generator
```

### 2. Install Dependencies
```bash
npm install
# or
yarn install
```

### 3. Environment Setup
Create a `.env.local` file in the root directory:
```bash
# Supabase Configuration
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

# Stripe Configuration (for billing)
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

# Application Configuration
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_nextauth_secret
NODE_ENV=development
```

### 4. Database Setup
Run the database migrations and seed data:
```bash
npm run db:setup
```

### 5. Start Development Server
```bash
npm run dev
```

Visit `http://localhost:3000` to see the application running.

## 📁 Project Structure

```
esg-disclosure-generator/
├── src/
│   ├── app/                    # Next.js 14 App Router
│   │   ├── (auth)/            # Authentication routes
│   │   ├── dashboard/         # Main application dashboard
│   │   ├── api/              # API route handlers
│   │   └── globals.css       # Global styles
│   ├── components/           # Reusable UI components
│   │   ├── ui/              # Basic UI components
│   │   ├── forms/           # Form components
│   │   ├── charts/          # Data visualization
│   │   └── layout/          # Layout components
│   ├── lib/                 # Utility functions and configurations
│   │   ├── supabase/       # Supabase client and utilities
│   │   ├── validations/    # Zod schemas
│   │   ├── rules-engine/   # ESG compliance rules
│   │   └── pdf/           # Document generation
│   ├── types/              # TypeScript type definitions
│   └── hooks/             # Custom React hooks
├── supabase/              # Database migrations and functions
│   ├── migrations/       # SQL migration files
│   ├── functions/       # Edge functions
│   └── seed.sql        # Initial data
├── public/              # Static assets
├── docs/               # Documentation
└── tests/             # Test files
```

## 🏗 Development

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint
- `npm run type-check` - Run TypeScript checks
- `npm run test` - Run test suite
- `npm run db:reset` - Reset local database
- `npm run db:seed` - Seed database with sample data

### Code Quality
This project uses several tools to maintain code quality:
- **ESLint**: JavaScript/TypeScript linting
- **Prettier**: Code formatting
- **Husky**: Git hooks for pre-commit checks
- **TypeScript**: Static type checking
- **Jest**: Unit and integration testing

### Contributing Guidelines

1. **Fork the repository** and create a feature branch
2. **Follow the coding standards** established in the project
3. **Write tests** for new functionality
4. **Update documentation** as needed
5. **Submit a pull request** with a clear description

## 🧪 Testing

### Running Tests
```bash
# Run all tests
npm run test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage

# Run E2E tests
npm run test:e2e
```

### Test Structure
- **Unit Tests**: Component and utility function testing
- **Integration Tests**: API endpoint and database interaction testing
- **E2E Tests**: Full user workflow testing with Playwright

## 📚 API Documentation

### Authentication
All API requests require authentication via Supabase Auth. Include the JWT token in the Authorization header:
```
Authorization: Bearer <jwt_token>
```

### Core Endpoints

#### Assessments
```bash
# Create new assessment
POST /api/v1/assessments

# Get assessment by ID
GET /api/v1/assessments/{id}

# Update assessment
PUT /api/v1/assessments/{id}

# Delete assessment
DELETE /api/v1/assessments/{id}
```

#### Reports
```bash
# Generate report
POST /api/v1/reports/generate

# Export report in various formats
GET /api/v1/reports/{id}/export?format=pdf|json|xbrl

# Get report status
GET /api/v1/reports/{id}/status
```

#### Organizations
```bash
# Get organization profile
GET /api/v1/organizations/profile

# Update organization
PUT /api/v1/organizations/profile

# Get team members
GET /api/v1/organizations/members
```

For detailed API documentation, visit `/api/docs` when running the development server.

## 🏢 Deployment

### Production Deployment

#### Supabase Setup
1. Create a new Supabase project in EU region
2. Configure authentication providers
3. Set up Row Level Security policies
4. Deploy edge functions

#### Vercel Deployment
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy to production
vercel --prod
```

#### Environment Variables
Set the following environment variables in your deployment platform:
- `NEXT_PUBLIC_SUPABASE_URL`
- `NEXT_PUBLIC_SUPABASE_ANON_KEY`  
- `SUPABASE_SERVICE_ROLE_KEY`
- `NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY`
- `STRIPE_SECRET_KEY`
- `NEXTAUTH_SECRET`

### Monitoring and Maintenance
- **Error Tracking**: Integrated with Supabase Analytics
- **Performance Monitoring**: Built-in Next.js analytics  
- **Uptime Monitoring**: External service recommended
- **Database Backups**: Automated daily backups
- **Security Updates**: Dependabot for dependency updates

## 🔒 Security

### Data Protection
- **Encryption**: All data encrypted at rest and in transit
- **Access Control**: Role-based permissions with RLS
- **Audit Logging**: Comprehensive activity tracking
- **GDPR Compliance**: EU hosting with data protection controls

### Security Best Practices
- Regular security audits and penetration testing
- Dependency vulnerability scanning
- Secure coding practices and code review process
- Incident response procedures

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🤝 Support

### Getting Help
- **Documentation**: Check the `/docs` folder for detailed guides
- **Issues**: Report bugs and request features via GitHub Issues
- **Discussions**: Join community discussions in GitHub Discussions
- **Email**: For sensitive issues, contact support@vidler.co

### Enterprise Support
For enterprise customers, we offer:
- Priority support with guaranteed response times
- Custom feature development
- On-site training and implementation
- Dedicated success manager

## 🗺 Roadmap

### Q4 2025
- ✅ MVP launch (EU/UK compliance)
- ✅ Freemium model implementation
- 🔄 Beta customer onboarding

### Q1 2026  
- 📋 US and Canada jurisdiction support
- 📋 Advanced benchmarking features
- 📋 API integrations (banks, ERP systems)
- 📋 Mobile application

### Q2 2026
- 📋 MENA and Asia-Pacific expansion  
- 📋 White-label solutions
- 📋 Assurance workflow integration
- 📋 Carbon offset marketplace

### Q3 2026
- 📋 AI-powered ESG insights
- 📋 Supply chain ESG tracking
- 📋 Real-time regulatory updates
- 📋 Advanced analytics dashboard

## 👥 Team

**Vidler & Co Development Team**
- Lead Developer: [Your Name]
- Product Manager: [PM Name]  
- UX Designer: [Designer Name]
- DevOps Engineer: [DevOps Name]

## 🙏 Acknowledgments

- **Supabase** for providing the backend infrastructure
- **Vercel** for hosting and deployment
- **Next.js** team for the excellent framework
- **TailwindCSS** for the utility-first CSS framework
- **ESG Standards Organizations** for guidance on compliance requirements

---

**Built with ❤️ by Vidler & Co**

For more information about our company and services, visit [vidler.co](https://vidler.co)
