# Replit.md - La Lampara Beach Club Application

## Overview

This is a full-stack beach club management application built with React frontend and Express backend. The application manages a beach club (La Lampara) located in Fiumefreddo Bruzio, Cosenza, offering umbrella reservations, food/drink orders, and admin management capabilities. It uses a modern tech stack with TypeScript, Tailwind CSS, shadcn/ui components, PostgreSQL database, and Drizzle ORM for database operations.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **Styling**: Tailwind CSS with custom beach-themed color palette
- **UI Components**: shadcn/ui component library with Radix UI primitives
- **State Management**: React Context API for cart and authentication
- **Data Fetching**: TanStack Query (React Query) for server state management
- **Build Tool**: Vite with custom configuration for development and production

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Design**: RESTful API with JSON responses
- **Middleware**: Custom logging, JSON parsing, error handling
- **Development**: Hot reload with Vite integration in development mode

### Database Architecture
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Database**: PostgreSQL (Replit Neon Database)
- **Schema**: Shared schema definitions between frontend and backend
- **Migrations**: Drizzle Kit for schema migrations
- **Storage**: DatabaseStorage implementation with full CRUD operations

## Key Components

### Core Entities
1. **Products**: Menu items (cocktails, panini, gelati) with pricing and categories
2. **Umbrellas**: Beach umbrellas with positioning (front/back row) and pricing
3. **Orders**: Customer food/drink orders with status tracking
4. **Reservations**: Umbrella bookings by date with customer information
5. **Admins**: Administrative users for management dashboard

### Frontend Features
- **Public Interface**: Home page with hero section, menu browsing, umbrella reservation system
- **Shopping Cart**: Persistent cart with localStorage, quantity management
- **Admin Dashboard**: Management interface for products, umbrellas, orders, and reservations
- **Authentication**: Simple admin login system with localStorage persistence
- **Responsive Design**: Mobile-first approach with Tailwind breakpoints

### Backend Features
- **Product Management**: CRUD operations for menu items
- **Umbrella Management**: Availability checking and reservation system
- **Order Processing**: Order creation and status updates
- **Admin Authentication**: Basic username/password authentication
- **Statistics**: Dashboard analytics for admin interface

## Data Flow

1. **Customer Flow**:
   - Browse menu items from `/api/products`
   - Add items to cart (localStorage)
   - Place orders via `/api/orders`
   - Reserve umbrellas via `/api/reservations`

2. **Admin Flow**:
   - Login via `/api/admin/login`
   - Manage products, umbrellas, orders through respective endpoints
   - View dashboard statistics via `/api/admin/stats`

3. **Data Persistence**:
   - Database operations through Drizzle ORM
   - Cart state in localStorage
   - Admin session in localStorage

## External Dependencies

### Frontend Dependencies
- **UI Framework**: React with wouter for routing
- **Styling**: Tailwind CSS, shadcn/ui components, Radix UI primitives
- **State Management**: TanStack Query for server state, React Context for client state
- **Forms**: React Hook Form with zod validation
- **Utilities**: date-fns for date handling, clsx for conditional classes

### Backend Dependencies
- **Database**: @neondatabase/serverless for PostgreSQL connection
- **ORM**: drizzle-orm with drizzle-zod for validation
- **Server**: Express.js with standard middleware
- **Development**: tsx for TypeScript execution, esbuild for production builds

### Development Tools
- **Build**: Vite with React plugin and runtime error overlay
- **Database**: Drizzle Kit for migrations and schema management
- **Replit Integration**: Custom plugins for development environment

## Deployment Strategy

### Development Environment
- **Frontend**: Vite dev server with HMR
- **Backend**: tsx with file watching for auto-restart
- **Database**: PostgreSQL connection via environment variable
- **Integration**: Vite middleware for backend integration in development

### Production Build
- **Frontend**: Vite build to `dist/public` directory
- **Backend**: esbuild bundle to `dist/index.js`
- **Static Files**: Express serves built frontend files
- **Database**: Production PostgreSQL via DATABASE_URL environment variable

### Configuration Requirements
- **DATABASE_URL**: PostgreSQL connection string for Neon Database
- **Environment**: NODE_ENV for development/production switching
- **Build Process**: Separate frontend and backend build steps with single entry point

The application follows a monorepo structure with shared TypeScript definitions, enabling type safety across the full stack while maintaining clear separation between client and server concerns.