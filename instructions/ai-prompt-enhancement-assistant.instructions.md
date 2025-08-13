# AI Prompt Enhancement & Engineering Assistant

Modern AI-powered prompt engineering platform with comprehensive enhancement capabilities, built with Next.js 14, TypeScript, and advanced prompt optimization techniques.

## Project Context

- **Tech Stack**: Next.js 14 (App Router), TypeScript, MongoDB, NextAuth.js, OpenAI API, Tailwind CSS, Framer Motion
- **Architecture**: Server-side rendering with API routes, MongoDB for data persistence, Google OAuth authentication
- **Core Features**: 
  - Multi-type prompt enhancement (ENHANCE, ANALYZE, DEBUG, OPTIMIZE, DOCUMENT, TEST)
  - Real-time AI-powered prompt optimization
  - Token quota management and usage tracking
  - Premium/free tier model support
  - Responsive modern UI with animations

---

## Development Standards

### TypeScript & Type Safety
- Use strict TypeScript configuration with proper type definitions
- Define interfaces for all data structures, API responses, and component props
- Use branded types for enhanced type safety (e.g., `UserId`, `ModelId`)
- Implement proper error types and result types with discriminated unions
- Use `zod` for runtime validation and type inference
- Create type-safe API route handlers with proper request/response typing

### Next.js App Router Architecture
- Use App Router exclusively (`app/` directory) for new features
- Implement proper Server Components vs Client Components separation
- Use Server Actions for form submissions and mutations
- Implement proper loading.tsx, error.tsx, and not-found.tsx pages
- Use route groups and parallel routes for complex layouts
- Optimize with proper streaming and Suspense boundaries

### Authentication & Security
- Implement NextAuth.js with Google OAuth provider and MongoDB adapter
- Use JWT strategy with proper session management
- Implement proper authorization checks in API routes and Server Components
- Sanitize all user inputs to prevent XSS and injection attacks
- Use environment variables for sensitive configuration
- Implement proper CORS and security headers

### Database Design & Operations
- Use MongoDB with proper connection pooling and error handling
- Implement efficient collection schemas for users, usage tracking, and sessions
- Use proper indexing for query optimization
- Implement atomic operations for token consumption and quota management
- Handle connection failures gracefully with retry logic
- Use transactions for critical operations

### API Design & Integration
- Implement RESTful API routes with proper HTTP methods and status codes
- Use OpenAI API with proper error handling and retry logic
- Implement streaming responses for real-time AI interactions
- Use proper request validation with `zod` schemas
- Implement rate limiting and quota enforcement
- Handle API failures with fallback mechanisms

### Prompt Engineering System
- Implement modular prompt templates with parameter substitution
- Use systematic prompt enhancement techniques (Chain-of-Thought, Few-Shot Learning)
- Support multiple programming languages and use cases
- Implement prompt validation and optimization
- Create reusable prompt building blocks and patterns
- Support custom prompt templates and user personalization

### State Management & Data Flow
- Use React Server Components for server-side data fetching
- Implement proper client-side state with React hooks
- Use React Context for global state (authentication, theme)
- Implement optimistic updates for better UX
- Use proper loading states and error boundaries
- Implement real-time features with streaming APIs

### UI/UX Design Patterns
- Use Tailwind CSS with consistent design system and color palette
- Implement responsive design with mobile-first approach
- Use Framer Motion for smooth animations and transitions
- Create accessible components with proper ARIA attributes
- Implement proper focus management and keyboard navigation
- Use semantic HTML and proper heading hierarchy

### Performance Optimization
- Implement code splitting with dynamic imports and Next.js optimization
- Use proper image optimization with next/image
- Implement proper caching strategies (API routes, static assets)
- Optimize bundle size with tree shaking and dependency analysis
- Use React.memo and useMemo for expensive computations
- Implement proper loading patterns and skeleton screens

### Error Handling & Monitoring
- Implement comprehensive error boundaries and fallback UI
- Use proper error logging and monitoring
- Implement user-friendly error messages with actionable guidance
- Handle API errors with proper retry mechanisms
- Implement proper validation error display
- Use proper debugging tools and development aids

### Testing Strategy
- Write unit tests for utility functions and hooks
- Implement integration tests for API routes
- Use React Testing Library for component testing
- Test error scenarios and edge cases
- Implement E2E tests for critical user flows
- Use proper mocking for external dependencies

---

## Code Organization

### File Structure
```
app/
├── (auth)/              # Authentication-related routes
├── api/                 # API route handlers
│   ├── auth/           # Authentication endpoints
│   ├── generate/       # Prompt generation
│   └── models/         # Model management
├── globals.css         # Global styles
├── layout.tsx          # Root layout
└── page.tsx            # Home page

components/
├── AuthProvider.tsx    # Authentication context
├── GoogleSignInButton.tsx
├── PromptPlayground.tsx
└── PromptPlaygroundModern.tsx

lib/
├── auth.ts             # NextAuth configuration
├── models.ts           # AI model definitions
├── mongodb.ts          # Database connection
├── openai.ts           # OpenAI client
├── prompt-core.ts      # Core prompt engine
├── quota.ts            # Usage tracking
└── useStreamingApi.ts  # Streaming API hook
```

### Component Architecture
- Create reusable, composable components with clear interfaces
- Separate business logic from presentation components
- Use proper component composition patterns
- Implement proper prop drilling alternatives
- Create custom hooks for reusable logic
- Use proper component naming conventions

### API Route Patterns
```typescript
// Proper API route structure
export async function POST(request: NextRequest) {
  try {
    const session = await getServerSession(authOptions)
    if (!session) {
      return NextResponse.json({ error: 'Unauthorized' }, { status: 401 })
    }

    const body = await request.json()
    const validatedData = schema.parse(body)
    
    // Business logic here
    
    return NextResponse.json({ data: result })
  } catch (error) {
    console.error('API Error:', error)
    return NextResponse.json(
      { error: 'Internal server error' }, 
      { status: 500 }
    )
  }
}
```

---

## Prompt Engineering Patterns

### Template Structure
- Use systematic template patterns with clear sections (INSTRUCTION, CONTEXT, EXAMPLES)
- Implement parameter substitution with validation
- Create reusable prompt building blocks
- Use proper prompt versioning and testing
- Implement prompt performance metrics

### Enhancement Techniques
- Apply Chain-of-Thought reasoning for complex tasks
- Use Few-Shot Learning with relevant examples
- Implement proper context setting and role definition
- Use clear output formatting specifications
- Apply systematic debugging and optimization approaches

### Model Integration
- Support multiple AI models with different capabilities
- Implement proper model selection logic
- Handle model-specific limitations and requirements
- Use appropriate system prompts for different models
- Implement fallback mechanisms for model failures

---

## Security & Compliance

### Data Protection
- Implement proper data encryption and secure storage
- Use secure session management and token handling
- Implement proper data retention and deletion policies
- Handle sensitive user data with appropriate protections
- Use proper access controls and authorization

### API Security
- Implement proper rate limiting and quota enforcement
- Use secure API key management and rotation
- Implement proper input validation and sanitization
- Use HTTPS for all communications
- Implement proper CORS and security headers

---

## Deployment & Operations

### Environment Configuration
- Use proper environment variable management
- Implement different configurations for development/staging/production
- Use secure credential storage and management
- Implement proper logging and monitoring
- Use proper backup and disaster recovery procedures

### Performance Monitoring
- Implement proper application performance monitoring
- Track user engagement and usage metrics
- Monitor AI model performance and costs
- Implement proper alerting for critical issues
- Use proper analytics and reporting

---

## Best Practices

### Code Quality
- Follow consistent coding standards and conventions
- Use proper linting and formatting tools
- Implement comprehensive testing coverage
- Use proper code review processes
- Maintain clean, self-documenting code

### User Experience
- Implement intuitive and responsive user interfaces
- Provide clear feedback and loading states
- Use proper error messaging and recovery
- Implement accessibility best practices
- Optimize for different devices and screen sizes

### Maintenance & Scalability
- Design for horizontal scalability and growth
- Implement proper caching and optimization strategies
- Use proper dependency management and updates
- Implement proper database optimization and indexing
- Plan for feature expansion and technical debt management

---

## Implementation Guidelines

### Feature Development Process
1. **Analysis**: Understand user requirements and technical constraints
2. **Design**: Create proper system architecture and data models
3. **Implementation**: Build with proper testing and validation
4. **Integration**: Ensure proper integration with existing systems
5. **Testing**: Comprehensive testing including edge cases
6. **Deployment**: Proper staging and production deployment
7. **Monitoring**: Ongoing performance and usage monitoring

### Code Review Checklist
- Type safety and proper TypeScript usage
- Security considerations and input validation
- Performance implications and optimization
- Accessibility and user experience
- Error handling and edge cases
- Test coverage and documentation
- Code style and consistency

---

applyTo: '**/*.ts, **/*.tsx, **/*.js, **/*.jsx, **/*.md'
description: 'AI-powered prompt enhancement platform with Next.js, TypeScript, and advanced prompt engineering capabilities'
---

# AI Prompt Enhancement & Engineering Assistant

Instructions for developing and maintaining a modern AI-powered prompt engineering platform with comprehensive enhancement capabilities, real-time optimization, and enterprise-grade security and scalability.