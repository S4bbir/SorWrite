# Sorwrite System Architecture

## Overview

Sorwrite is a full-stack AI-powered SaaS platform for researchers, built with a modern technology stack. The system follows a client-server architecture with a React-based frontend and a Node.js/Express backend, communicating through a RESTful API.

## High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                            Client Layer                             │
├─────────────────────────────────────────────────────────────────────┤
│                        Web Browser (React)                          │
├─────────────────────────────────────────────────────────────────────┤
│                          API Layer                                  │
├─────────────────────────────────────────────────────────────────────┤
│  Authentication  │  Queries  │  Tools  │  Library  │  Subscription   │
│  Payment         │  Teams    │  Diagrams │  Citation Map            │
├─────────────────────────────────────────────────────────────────────┤
│                         Service Layer                               │
├─────────────────────────────────────────────────────────────────────┤
│    Auth Service    │   AI Service    │   Payment Service   │  ...   │
├─────────────────────────────────────────────────────────────────────┤
│                        Data Layer                                   │
├─────────────────────────────────────────────────────────────────────┤
│         MongoDB         │   Pinecone    │    AWS S3    │   Stripe    │
└─────────────────────────────────────────────────────────────────────┘
```

## Technology Stack

### Frontend
- **Framework**: Next.js (React)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Shadcn/UI
- **State Management**: React Context API
- **Build Tool**: Webpack (via Next.js)
- **Deployment**: Vercel

### Backend
- **Framework**: Express.js
- **Language**: Node.js (JavaScript)
- **API**: RESTful API
- **Authentication**: JWT
- **Database**: MongoDB with Mongoose
- **AI Integration**: OpenAI API, LangChain
- **Vector Database**: Pinecone (optional)
- **File Storage**: AWS S3
- **Payments**: Stripe
- **Logging**: Winston
- **Testing**: Jest
- **Deployment**: Render/AWS

### Infrastructure
- **Containerization**: Docker
- **Orchestration**: Docker Compose
- **Database**: MongoDB Atlas
- **File Storage**: AWS S3
- **CI/CD**: GitHub Actions
- **Monitoring**: (Future implementation)

## System Components

### 1. Frontend (Next.js)

The frontend is a single-page application built with Next.js, providing a responsive and interactive user interface for researchers.

**Key Features:**
- Dashboard with research tools
- Query management interface
- Library organization
- Team collaboration
- Subscription management
- Responsive design for all devices

**Folder Structure:**
```
/frontend
├── /components     # Reusable UI components
├── /layouts        # Page layouts
├── /pages          # Next.js pages
├── /styles         # CSS and Tailwind config
├── /utils          # Helper functions
├── /hooks          # Custom React hooks
├── /context        # React context providers
└── /public         # Static assets
```

### 2. Backend (Express.js)

The backend is a RESTful API server built with Express.js, handling business logic, data processing, and external service integrations.

**Key Features:**
- User authentication and authorization
- Research query processing
- AI service integration
- Library and team management
- Subscription and payment handling
- Data validation and error handling

**Folder Structure:**
```
/backend
├── /api            # API route handlers
├── /controllers    # Business logic
├── /models         # Database models
├── /middlewares    # Express middleware
├── /services       # External service integrations
├── /utils          # Helper functions
└── server.js       # Entry point
```

### 3. Database (MongoDB)

MongoDB serves as the primary database for storing user data, research queries, libraries, and other application data.

**Collections:**
- **Users**: User accounts and profiles
- **Queries**: Research questions and AI responses
- **Libraries**: Organized collections of queries
- **Tools**: Available AI tools
- **Teams**: Research team collaboration
- **Subscriptions**: User subscription information

### 4. AI Services

The AI layer integrates with OpenAI and other AI services to provide intelligent research assistance.

**Services:**
- **Research Assistant**: Answer research questions
- **AI Writer**: Generate research papers
- **Paraphraser**: Rewrite text while maintaining meaning
- **Citation Generator**: Create formatted citations
- **Research Gap Finder**: Identify research opportunities
- **Diagram Generator**: Create visual representations
- **Citation Mapper**: Visualize citation networks

### 5. File Storage (AWS S3)

AWS S3 is used for storing research documents, papers, and other file assets.

### 6. Vector Database (Pinecone)

Pinecone is used for semantic search and similarity matching of research content (optional).

### 7. Payment Processing (Stripe)

Stripe handles subscription payments and billing management.

## Data Flow

1. **User Authentication**
   - User registers/logs in through the frontend
   - Credentials sent to backend auth API
   - JWT token generated and returned
   - Token stored in browser for subsequent requests

2. **Research Query Processing**
   - User submits a research question
   - Frontend sends query to backend
   - Backend validates and processes query
   - AI service generates response
   - Response stored in database
   - Results sent back to frontend

3. **Library Management**
   - User creates/organizes libraries
   - Queries associated with libraries
   - Libraries shared with team members
   - Access controlled through permissions

4. **Subscription Management**
   - User selects subscription plan
   - Payment processed through Stripe
   - Subscription record created/updated
   - User access level adjusted

5. **Team Collaboration**
   - User creates/joins teams
   - Team members share libraries
   - Access controlled through roles
   - Real-time updates (future feature)

6. **Diagram Generation**
   - User requests diagram generation
   - Backend processes request
   - AI service generates diagram data
   - Data sent back to frontend for visualization

7. **Citation Mapping**
   - User requests citation map
   - Backend processes request
   - Citation data retrieved/processed
   - Data sent back to frontend for visualization

## Security Considerations

- **Authentication**: JWT-based authentication with secure tokens
- **Authorization**: Role-based access control (RBAC)
- **Data Encryption**: HTTPS for all communications
- **Password Security**: bcrypt hashing for password storage
- **Input Validation**: Server-side validation for all inputs
- **Rate Limiting**: API rate limiting to prevent abuse
- **CORS**: Cross-origin resource sharing controls

## Scalability Considerations

- **Horizontal Scaling**: Stateless backend services
- **Database Sharding**: MongoDB sharding for large datasets
- **Caching**: Redis caching for frequently accessed data
- **Load Balancing**: Reverse proxy for distributing traffic
- **Microservices**: Potential migration to microservices architecture

## Deployment Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend       │    │   Database      │
│   (Vercel)      │◄──►│   (Render/AWS)  │◄──►│   (MongoDB)     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   File Storage  │    │   AI Services   │    │   Payments      │
│   (AWS S3)      │    │   (OpenAI)      │    │   (Stripe)      │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## Future Enhancements

1. **Real-time Collaboration**: WebSocket integration for real-time team collaboration
2. **Mobile App**: React Native mobile application
3. **Advanced Analytics**: Research analytics and insights
4. **Integration Platform**: API for third-party integrations
5. **Advanced AI Models**: Integration with more specialized AI models
6. **Offline Support**: Progressive Web App (PWA) features