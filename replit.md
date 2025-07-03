# Wesh Dating App

## Overview

Wesh is a modern Tinder-style dating app with swiping functionality, animated heart logo, and real-time matching features. The application is built as a full-stack web application with a React frontend and Node.js/Express backend, targeting adults 18+ of all genders worldwide. The app provides core dating features including user profiles, swipe & match system, chat functionality, notifications, subscription plans, and multilingual support (Arabic and English).

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for development and production builds
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: TanStack Query for server state, React hooks for local state
- **Routing**: Wouter for client-side routing
- **UI Components**: Radix UI primitives with custom styling
- **Internationalization**: Custom i18n implementation with Arabic (RTL) and English (LTR) support

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL via Neon serverless with Drizzle ORM
- **Authentication**: Replit Auth with session management
- **Session Storage**: PostgreSQL-backed sessions via connect-pg-simple

### Database Design
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Schema**: Includes users, profiles, matches, messages, subscriptions, and sessions tables
- **Relationships**: Proper foreign key constraints and cascading deletes
- **Migrations**: Drizzle-kit for schema management

## Key Components

### Authentication System
- **Provider**: Replit Auth with OpenID Connect
- **Session Management**: Server-side sessions stored in PostgreSQL
- **User Management**: Automatic user creation and profile linking
- **Security**: HTTP-only cookies with secure flags in production

### Profile Management
- **User Profiles**: Detailed profiles with photos, bio, interests, and preferences
- **Photo Upload**: Support for multiple profile photos
- **Interest System**: Tag-based interests for matching
- **Location Services**: Location-based discovery

### Discovery & Matching
- **Swipe System**: Like/pass functionality with match detection
- **Discovery Algorithm**: Profile-based discovery with filtering
- **Match Management**: Mutual like detection and match creation
- **Super Likes**: Premium feature for enhanced matching

### Chat System
- **Real-time Messaging**: Match-based chat functionality
- **Message Threading**: Conversation management per match
- **Read Receipts**: Message read status tracking
- **Chat UI**: Mobile-first chat interface

### Subscription System
- **Tiered Plans**: Free, Premium ($19.99/month), and Gold ($39.99/month) subscription tiers
- **Feature Gating**: Premium features like unlimited swipes and super likes
- **Payment Integration**: Full PayPal integration with order creation, capture, and subscription management
- **Transaction Tracking**: Complete payment transaction logging and status management

### Internationalization
- **Multi-language**: English and Arabic support
- **RTL Support**: Right-to-left layout for Arabic
- **Language Switching**: Dynamic language switching
- **Cultural Adaptation**: Localized UI patterns

## Data Flow

1. **User Authentication**: Users authenticate via Replit Auth, creating a session
2. **Profile Creation**: New users complete profile setup with photos and preferences
3. **Discovery**: Users browse potential matches based on location and preferences
4. **Matching**: Mutual likes create matches, enabling chat functionality
5. **Communication**: Matched users can exchange messages in real-time
6. **Subscription & Payment**: Users can upgrade to premium plans via PayPal integration

### Payment Flow
1. **Plan Selection**: User selects Premium ($19.99) or Gold ($39.99) subscription
2. **Order Creation**: Backend creates PayPal order and transaction record
3. **PayPal Redirect**: User redirected to PayPal for secure payment processing
4. **Payment Capture**: Backend captures successful payment and activates subscription
5. **Subscription Activation**: User gains access to premium features immediately

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connection
- **drizzle-orm**: Database ORM and query builder
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: UI component primitives
- **express**: Web framework
- **passport**: Authentication middleware

### Development Tools
- **Vite**: Build tool and development server
- **TypeScript**: Type safety and development experience
- **Tailwind CSS**: Utility-first CSS framework
- **ESLint/Prettier**: Code quality and formatting

### External Services
- **Neon Database**: Serverless PostgreSQL hosting
- **Replit Auth**: Authentication service
- **Font Awesome**: Icon library
- **Google Fonts**: Typography (Inter font family)

## Deployment Strategy

### Development Environment
- **Replit Integration**: Built-in Replit development environment
- **Hot Reload**: Vite HMR for frontend development
- **Database**: Neon serverless PostgreSQL
- **Environment Variables**: DATABASE_URL, SESSION_SECRET, REPLIT_DOMAINS

### Production Build
- **Frontend**: Vite production build with optimization
- **Backend**: ESBuild bundling for Node.js deployment
- **Static Assets**: Served from dist/public directory
- **Session Management**: Production-ready session configuration

### Scalability Considerations
- **Database**: Serverless PostgreSQL for automatic scaling
- **Session Storage**: Database-backed sessions for horizontal scaling
- **Static Assets**: Prepared for CDN integration
- **API Design**: RESTful endpoints ready for load balancing

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Enhancements

### Advanced Features Added (July 01, 2025)
- **Location-Based Filtering**: Added geolocation support with distance filters (1-100km)
- **Advanced Discovery Filters**: Age range, interests, verification status, and activity filters
- **Enhanced Match Notifications**: Animated match celebration with confetti effects and detailed profile preview
- **Real-time Notification System**: Push notifications for matches, messages, and profile interactions
- **Improved User Experience**: Enhanced navigation with filter indicators and notification badges
- **Extended Multilingual Support**: Added support for 45+ languages including Asian, European, Middle Eastern, and African languages
- **Advanced Language Selector**: Modern language selection interface with regional categorization and search functionality
- **Comprehensive Logging System**: Detailed application logging for authentication, payments, matches, and performance monitoring

### Technical Improvements
- **Location Schema**: Added latitude, longitude, and maxDistance fields to profiles table
- **Interactive Components**: Custom slider component for distance and age range selection
- **Notification Management**: Complete notification system with read/unread states and permission handling
- **Filter Persistence**: Advanced filtering with visual indicators and state management
- **Internationalization Enhancement**: Extended from 2 languages (Arabic/English) to 45+ languages with RTL support
- **Logging Infrastructure**: Comprehensive logging system with file output, log levels, and structured metadata
- **Modern Landing Page**: Professional landing page showcasing multilingual capabilities and app features

## Changelog

Changelog:
- July 01, 2025. Initial setup and complete MVP implementation
- July 01, 2025. Added PayPal payment integration for subscriptions
- July 01, 2025. Enhanced user experience with location filtering, advanced notifications, and improved match system