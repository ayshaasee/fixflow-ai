
# FixFlow AI - Project Instructions

## 1. Product Overview

FixFlow AI is an AI-powered service operations SaaS platform.

It connects customers, service businesses and technicians through one platform.

Its goals are:
- Simplify service request management.
- Automate repetitive business operations using AI.
- Provide intelligent business insights.
- Improve transparency, privacy and service experiences for women.

## 2. Technology Stack

### Frontend
- React
- TypeScript
- Vite
- Tailwind CSS

### Main Backend
- Java 21
- Spring Boot
- Spring Security
- REST APIs

### AI Service
- Python
- FastAPI
- LLM APIs
- Structured outputs
- AI tool calling
- RAG and embeddings

### Database and Infrastructure
- PostgreSQL
- pgvector
- Redis when needed
- Docker
- Git and GitHub

## 3. Project Structure

- frontend/: React application
- backend/: Spring Boot application
- ai-service/: Python AI service
- docs/: Product and technical documentation

## 4. Architecture Rules

- Keep business logic in the Spring Boot backend.
- Use FastAPI for AI-specific processing.
- Communicate between services through documented APIs.
- Keep the architecture modular and maintainable.
- Avoid unnecessary microservices.
- Use PostgreSQL as the primary database.
- Enforce business-level data isolation.

## 5. AI Engineering Requirements

- Use structured LLM outputs wherever possible.
- Validate all AI-generated data before processing.
- Implement tool calling with explicit permissions.
- Never allow unrestricted AI access to the database.
- Require human approval for sensitive business actions.
- Handle API failures, invalid responses and timeouts.
- Record agent actions and important decisions.
- Evaluate AI accuracy and failure cases.
- Implement RAG with source-grounded answers.

## 6. Security Requirements

- Use secure authentication.
- Implement role-based access control.
- Protect customer and business information.
- Never hardcode API keys or credentials.
- Use environment variables for secrets.
- Validate all user input.
- Enforce tenant isolation in every relevant query.
- Do not expose private customer information unnecessarily.

## 7. Coding Standards

- Write readable, maintainable code.
- Use meaningful names.
- Avoid unnecessary duplication.
- Follow established project conventions.
- Add error handling.
- Write tests for important functionality.
- Do not introduce dependencies without a reason.

## 8. Development Rules

Before implementing a feature:
1. Inspect the existing code.
2. Explain the implementation plan.
3. Identify affected files.
4. Check security implications.
5. Implement only the requested feature.
6. Run relevant tests.
7. Summarise changes and remaining issues.

Never rewrite working application code unnecessarily.

Do not claim that a feature is implemented unless it has been implemented and verified.

## 9. Current Development Goal

Build a secure, functional, AI-powered MVP within 60 days.

Prioritise:
- Working functionality.
- Security.
- AI integration.
- Testability.
- Documentation.
- Deployment readiness.
