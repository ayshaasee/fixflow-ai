
# FixFlow AI - Database Design

## Database
PostgreSQL

## Design Principles

- Use UUID primary keys.
- Use foreign keys for relationships.
- Use created_at and updated_at timestamps.
- Use appropriate unique constraints and indexes.
- Store timestamps in UTC.
- Use explicit status values.
- Enforce business-level data isolation.
- Never rely only on frontend checks for permissions.

## 1. Identity

### users
- id
- full_name
- email
- password_hash
- phone
- account_status
- created_at
- updated_at

### businesses
- id
- business_name
- description
- country_code
- currency_code
- timezone
- address
- created_at
- updated_at

### business_memberships
- id
- business_id
- user_id
- role
- membership_status
- created_at

### customer_profiles
- id
- user_id
- additional_contact_information
- created_at

### technician_profiles
- id
- user_id
- skills
- availability_status
- verification_status
- created_at

## 2. Service Management

### service_categories
- id
- name
- description

### services
- id
- business_id
- category_id
- service_name
- description
- estimated_price
- active
- created_at

### work_orders
- id
- business_id
- customer_user_id
- service_id
- assigned_technician_user_id
- title
- description
- priority
- status
- requested_at
- created_at
- updated_at

### appointments
- id
- business_id
- work_order_id
- scheduled_start
- scheduled_end
- appointment_status
- created_at

### work_order_events
- id
- business_id
- work_order_id
- changed_by_user_id
- previous_status
- new_status
- notes
- created_at

## 3. FixFlow Her

### customer_preferences
- id
- user_id
- female_technician_preferred
- communication_preferences
- created_at
- updated_at

### trusted_contacts
- id
- customer_user_id
- contact_name
- contact_phone
- consent_status
- created_at

### technician_verifications
- id
- technician_user_id
- verification_type
- verification_status
- verified_at
- expires_at

Never store unnecessary identity documents or sensitive
personal information. Keep verification evidence secure.

## 4. AI Knowledge System

### business_documents
- id
- business_id
- uploaded_by_user_id
- file_name
- storage_key
- processing_status
- created_at

### document_chunks
- id
- business_id
- document_id
- chunk_text
- embedding
- chunk_metadata
- created_at

Use pgvector for embedding storage and similarity search.

## 5. AI Agent System

### agent_runs
- id
- business_id
- initiated_by_user_id
- agent_type
- status
- input_summary
- output_summary
- started_at
- completed_at

### tool_execution_logs
- id
- agent_run_id
- tool_name
- input_data
- output_data
- execution_status
- created_at

### approval_requests
- id
- agent_run_id
- requested_by_user_id
- action_type
- proposed_action
- approval_status
- reviewed_by_user_id
- reviewed_at
- created_at

## 6. Important Relationships

- A business can have multiple members.
- A user can belong to multiple businesses.
- A business can offer multiple services.
- A customer can create multiple work orders.
- A work order belongs to one business.
- A work order can have multiple appointments.
- A technician can be assigned multiple work orders.
- A business can upload multiple documents.
- An agent run can execute multiple tools.

## 7. Security Requirements

- Business-owned data must always be scoped by business_id.
- Validate user membership before business operations.
- Customers can only access their own records.
- Technicians can only access authorised assignments.
- Business owners can only manage their own business.
- Agent tools must use the same permission checks as normal APIs.
- Sensitive agent actions require human approval.
- Never store raw passwords or API keys.
