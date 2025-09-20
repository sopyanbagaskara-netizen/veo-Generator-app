# Overview

A modern video generation application that leverages Google's Gemini AI (VEO models) to create videos from text prompts and optional reference images. The application features a React TypeScript frontend with shadcn/ui components, an Express.js backend, and PostgreSQL database integration using Drizzle ORM. The UI supports dark mode theming and provides comprehensive video generation options including aspect ratios, resolutions, sound settings, and person generation controls.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **UI Library**: shadcn/ui components built on top of Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Routing**: Wouter for client-side routing
- **State Management**: React hooks with TanStack Query for server state
- **Form Handling**: React Hook Form with Zod validation

## Backend Architecture
- **Framework**: Express.js with TypeScript
- **API Structure**: RESTful API with `/api` prefix routing
- **Development Setup**: Hot reload with Vite integration in development
- **Error Handling**: Centralized error middleware with status code mapping
- **Storage Interface**: Abstracted storage layer supporting both in-memory and database implementations

## Data Storage Solutions
- **Database**: PostgreSQL with Neon serverless integration
- **ORM**: Drizzle ORM for type-safe database operations
- **Schema Management**: Drizzle migrations with shared schema definitions
- **Development Storage**: In-memory storage implementation for development/testing

## Authentication and Authorization
- **Session Management**: PostgreSQL session storage using connect-pg-simple
- **User Schema**: Basic user model with username/password fields
- **Security**: UUID-based user IDs with database-generated defaults

## External Dependencies
- **Video Generation**: Google Gemini AI (VEO models) via dynamic import from CDN
- **AI Service**: @google/genai package for video generation API calls
- **Models Supported**: VEO 3.0 Preview, VEO 3.0 Fast, and VEO 2.0
- **File Processing**: Client-side file handling for image uploads and video downloads
- **Database**: Neon PostgreSQL serverless database
- **Deployment**: Replit-optimized build configuration with runtime error handling

## Key Features
- **Video Generation Options**: Multiple aspect ratios (16:9, 9:16), resolutions (1080p, 720p), sound control
- **Person Generation Controls**: Configurable adult content and general person generation settings  
- **Image Reference Support**: Optional image upload for enhanced video generation context
- **Progress Tracking**: Real-time loading indicators with rotating status messages
- **Responsive Design**: Mobile-first approach with comprehensive component library
- **Dark Mode**: Built-in dark theme with CSS custom properties