# Sorwrite - AI Research Assistant SaaS

An AI-powered SaaS platform for researchers to enhance their research workflow with AI tools.

> **Note**: This implementation is complete in terms of code structure and components. However, to run the application, Node.js and npm need to be installed on your system.

## Features

- AI Research Assistant
- AI Writer for structured research papers
- Library for storing and organizing research
- Academic paper search
- Citation mapping
- Diagram generation
- Various AI tools (Naturalizer, Essay Writer, Research Gap Finder, Paraphraser)
- Pro subscription with advanced features

## Implementation Status

✅ **Complete**: All UI components, pages, and functionality have been implemented according to the requirements.

⚠️ **Environment Setup Required**: To run the application, Node.js and npm need to be installed on your system.

📝 **Documentation**: Comprehensive documentation has been added for context providers, custom hooks, and utility functions.

## Tech Stack

### Frontend
- Next.js 14 (App Router)
- React 18
- TailwindCSS
- Shadcn/UI
- TypeScript

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- OpenAI API
- LangChain
- Pinecone (optional)
- AWS S3
- Stripe for payments

### Deployment
- Vercel (Frontend)
- Render/AWS (Backend)

## Documentation

Detailed documentation is available in the [docs](docs/) directory:

- [API Documentation](docs/api-docs.md)
- [Architecture](docs/architecture.md)
- [Context Providers](docs/context-providers.md)
- [Custom Hooks](docs/custom-hooks.md)
- [Utilities](docs/utilities.md)
- [Implementation Summary](docs/implementation-summary.md)

## Project Structure

```
/sorwrite
│── /frontend
│   │── /components         # Reusable UI components
│   │── /layouts            # Layout components
│   │── /pages              # Next.js pages
│   │── /styles             # Global CSS / Tailwind config
│   │── /utils              # Frontend helpers
│   │── /hooks              # Custom React hooks
│   │── /context            # React context providers
│   │── /public             # Static assets
│   │── next.config.js      # Next.js config
│   │── tailwind.config.js  # Tailwind config
│   │── package.json

│── /backend
│   │── /api                # Route handlers
│   │── /controllers        # Business logic
│   │── /models             # MongoDB schemas
│   │── /middlewares        # Auth & error handling
│   │── /services           # AI integrations
│   │── /utils              # Helper functions
│   │── server.js           # Express server entry
│   │── package.json

│── /config
│   │── db.js               # Database connection
│   │── env.js              # Environment variables
│   │── logger.js           # Logging utility

│── /scripts                # Deployment scripts

│── /tests
│   │── /frontend           # Frontend tests
│   │── /backend            # Backend tests
│   │── jest.config.js

│── /docs
│   │── api-docs.md         # API documentation
│   │── architecture.md     # System design notes

│── .env                    # Environment variables
│── .gitignore
│── docker-compose.yml      # Container setup
│── package.json
```

## Getting Started

### Prerequisites
- Node.js >= 18.x (required for running the application)
- MongoDB instance (local or cloud)
- OpenAI API key
- AWS account for S3 (optional)
- Stripe account for payments (optional)

> **Note**: The application code is fully implemented but requires Node.js to be installed to run.

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd sorwrite
```

2. Install dependencies for both frontend and backend:
```bash
npm install
cd frontend && npm install
cd ../backend && npm install
```

Or use the root script:
```bash
npm run install:all
```

### Environment Variables

Create `.env` files in both frontend and backend directories:

**Frontend (.env.local)**:
```env
NEXT_PUBLIC_API_URL=http://localhost:5000
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_...
```

**Backend (.env)**:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/sorwrite
OPENAI_API_KEY=sk-...
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...
STRIPE_SECRET_KEY=sk_test_...
JWT_SECRET=your-jwt-secret
```

### Running the Application

1. Start the development servers:
```bash
# Run both frontend and backend
npm run dev

# Or run separately
npm run frontend
npm run backend
```

2. Visit the application:
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

## Deployment

### Frontend
Deploy to Vercel with environment variables configured.

### Backend
Deploy to Render or AWS with environment variables configured.

## Testing

Run tests for both frontend and backend:
```bash
npm run test
```

## Contributing

We welcome contributions to Sorwrite! Here's how you can help:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

### Development Guidelines

- Follow the existing code style
- Write tests for new functionality
- Update documentation as needed
- Keep pull requests focused on a single feature or bug fix

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For support or inquiries, please contact the Sorwrite team.