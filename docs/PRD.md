
# FixFlow AI - Product Requirements Document

Version: 1.0
Development target: 60 days
Product type: AI-powered SaaS platform
Initial markets: India and UAE

---

# 1. Product Vision

FixFlow AI is an intelligent service operations platform
that connects customers, service businesses and technicians.

It uses AI to simplify service requests, automate business
workflows, provide operational insights and improve
transparency and trust in home-service experiences.

# 2. Problem Statement

Small service businesses often manage customer requests,
appointments, technicians and follow-ups through
disconnected tools such as calls, WhatsApp and spreadsheets.

This creates:
- Missed customer requests.
- Scheduling conflicts.
- Poor communication.
- Difficulty tracking work.
- Limited business insights.
- Lack of transparency for customers.

FixFlow AI aims to solve these problems through one
centralised platform.

# 3. Target Users

## Customer
A person who needs a home or appliance service.

## Business Owner
A person managing a repair or maintenance business.

## Technician
A professional who receives and completes service jobs.

# 4. Core Product Modules

## 4.1 Customer Portal

- Customer registration and login.
- Browse available services.
- Submit service requests.
- Upload supporting photos.
- Select appointment preferences.
- Track job status.
- View service history.
- Submit feedback.

## 4.2 Business Dashboard

- Business registration and profile.
- Manage service categories.
- Manage customers.
- Manage technicians.
- Create and manage work orders.
- Assign technicians.
- Schedule appointments.
- Track job completion.
- View operational analytics.

## 4.3 Technician Portal

- Technician login.
- View assigned jobs.
- View approved job details.
- Update job status.
- Upload work photographs.
- Submit completion notes.
- View work history.

# 5. AI Capabilities

## 5.1 AI Request Processor

Convert natural-language customer requests into
structured service request data.

Extract:
- Service category.
- Equipment or appliance.
- Reported issue.
- Customer requirements.
- Preferred appointment.
- Missing information.

Validate the output before creating a work order.

## 5.2 AI Business Copilot

Allow business owners to ask questions about
their own business data.

Examples:
- Show pending work orders.
- Which technician has the most assignments?
- Summarise completed jobs this week.
- Identify overdue appointments.

Answers must be based on authorised business data.

## 5.3 AI Agent System

Create an agent capable of:
- Understanding business requests.
- Selecting approved tools.
- Retrieving relevant information.
- Executing permitted workflow steps.
- Handling tool failures.
- Requesting human approval when necessary.

Initial tools:
- Search work orders.
- Check technician availability.
- Retrieve service information.
- Prepare customer messages.
- Suggest technician assignments.

Sensitive actions require approval.

## 5.4 RAG Knowledge Assistant

- Upload service manuals and business documents.
- Extract and split document text.
- Generate embeddings.
- Store vectors using PostgreSQL and pgvector.
- Retrieve relevant information.
- Generate source-grounded answers.

## 5.5 AI Job Summary

Convert technician notes into structured
job completion reports.

# 6. FixFlow Her

A women-centred service experience integrated
into the customer portal.

Features:
- Female technician preference.
- Transparent technician profiles.
- Display verification status accurately.
- Appointment tracking.
- Trusted contact sharing with consent.
- Visit updates.
- Privacy preferences.
- Customer reporting and feedback.

Safety must never be guaranteed by an AI system.
Verification status must reflect actual checks.

# 7. AI Agent Safety

- No unrestricted database access.
- Tools must enforce user permissions.
- Validate all AI-generated arguments.
- Require approval for sensitive actions.
- Maintain an audit history.
- Handle incorrect outputs and API failures.
- Never expose another business's data.

# 8. Technical Architecture

Frontend:
React, TypeScript, Vite and Tailwind CSS.

Main Backend:
Java 21, Spring Boot and Spring Security.

AI Service:
Python, FastAPI and LLM APIs.

Database:
PostgreSQL and pgvector.

Infrastructure:
Docker and GitHub.

# 9. User Roles and Permissions

CUSTOMER:
Can manage their own requests and view their appointments.

BUSINESS_OWNER:
Can manage their business, technicians,
customers and work orders.

TECHNICIAN:
Can view and update assigned jobs within
their authorised permissions.

# 10. MVP Acceptance Criteria

The MVP is considered functional when:

1. Users can register and authenticate.
2. Business owners can manage service requests.
3. Customers can submit requests.
4. Technicians can receive assignments.
5. Work orders can progress through their lifecycle.
6. AI can extract structured request information.
7. Business owners can use the AI Copilot.
8. The knowledge assistant can answer from uploaded documents.
9. FixFlow Her preferences and appointment features work.
10. Business data is isolated and protected.
11. Important features have automated tests.
12. The application is deployed and demonstrable.

# 11. Development Constraints

- Solo developer.
- 60-day MVP target.
- Free-first development tools.
- Avoid unnecessary infrastructure.
- Prioritise working features over excessive complexity.
- Advanced features can be added after MVP launch.
