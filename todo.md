# Roadside Enforcement Tool - TODO Checklist
 
## Prompt 1: User Authentication & Role Management
- [ ] Create User entity/model with fields: username, hashed password, role (Officer/Admin)
- [ ] Create database migration/seed to add at least one Admin user
- [ ] Implement secure password hashing
- [ ] Implement login API endpoint with credential validation
- [ ] Implement logout API endpoint to end user session
- [ ] Implement role-based access control (RBAC) middleware/guards
- [ ] Implement audit logging for login and logout actions (user ID + timestamp, immutable)
- [ ] Write unit tests for:
  - Successful login
  - Failed login (wrong credentials)
  - Logout
  - RBAC enforcement
- [ ] Write integration tests for login/logout flows
- [ ] Wire all components into minimal runnable server example
 
## Prompt 2: Manual Data Entry UI & Validation
- [ ] Design React form with two inputs: Driver ID and Vehicle Registration Number
- [ ] Implement frontend validation:
  - Only one field must be filled
  - Validate correct format for each field
  - No empty submission
- [ ] Implement backend API endpoint to receive and validate input
- [ ] Show validation errors clearly on frontend
- [ ] Write frontend unit tests covering validation rules
- [ ] Write backend tests for input validation
- [ ] Integrate frontend form submission with backend API
- [ ] Test end-to-end form submission and validation
 
## Prompt 3: WoA/Notice Lookup Backend & Frontend
- [ ] Design backend API to query WoA/Notice data by driver ID or vehicle registration
- [ ] Define data model with fields:
  - Reference number
  - Offense type
  - Offense description
  - Date issued
  - Amount due
  - Status (Outstanding, Paid, Executed)
  - Linkage (Driver or Vehicle)
  - Location of offence
  - Court date (if applicable)
  - Issuing authority
- [ ] Implement mock data store/service for WoA/Notice entries
- [ ] Implement backend query logic with tests
- [ ] Create frontend results list component displaying all fields and linkage tags
- [ ] Write frontend tests for correct rendering of results
- [ ] Integrate lookup form (Prompt 2) with results display component
- [ ] Test full lookup flow end-to-end
 
## Prompt 4: Enforcement Actions Interface
- [ ] Implement UI to select WoA/Notice entry for action
- [ ] Provide options to mark as Executed or Paid
- [ ] Add reason dropdown with predefined options (e.g., "Paid on the spot", "Arrest executed")
- [ ] Implement optional file upload for supporting evidence (photos, PDFs)
- [ ] Implement backend endpoints to update status and store evidence securely
- [ ] Enforce validation:
  - Officer must confirm displayed details
  - Must select reason before submission
- [ ] Implement audit logging for all enforcement actions (timestamp, user ID, details)
- [ ] Write UI and backend tests covering validation, updates, file upload, and logging
- [ ] Integrate frontend and backend for enforcement actions
 
## Prompt 5: Receipt and Warrant PDF Generation
- [ ] Implement PDF generation service for executed/paid entries
- [ ] PDF must include:
  - User information
  - Timestamp
  - Reference number
  - Action type (Paid, Executed)
- [ ] Implement in-browser PDF viewer
- [ ] Add option to download generated PDFs
- [ ] Write tests to validate PDF content and correctness
- [ ] Integrate PDF generation triggered after enforcement action completion
 
## Prompt 6: TRAFMAN Daily XML Export
- [ ] Implement backend job or manual trigger for daily transaction aggregation
- [ ] Generate XML file with fields:
  - Transaction type (Payment or Execution)
  - Timestamp
  - User ID
  - Entry details (notice ID, vehicle reg, driver ID)
- [ ] Create admin UI to trigger XML export and download file
- [ ] Write tests to validate XML format and export functionality
 
## Prompt 7: Admin Reconciliation Module
- [ ] Build admin UI to view:
  - Logs of all payments
  - Logs of executed WoAs
- [ ] Implement upload interface for TRAFMAN reconciliation XML files
- [ ] Implement backend parsing of uploaded XML files
- [ ] Implement logic to detect mismatches between uploaded XML and internal logs
- [ ] Display mismatches with filtering and search options
- [ ] Enable tagging mismatches as resolved with user comments
- [ ] Log all resolution actions (timestamp, user ID, comment)
- [ ] Write tests for upload parsing, mismatch detection, UI functionality, and resolution tagging
 
## Prompt 8: Officer Session History
- [ ] Implement backend storage of session-based recent lookups and actions per officer
- [ ] Limit history to current shift/session
- [ ] Create frontend UI to display recent entries including:
  - Lookup input (Driver ID or Vehicle Reg)
  - Timestamp of action
  - Status (Viewed, Paid, Executed)
- [ ] Enable quick access or re-processing of entries within session
- [ ] Write tests for backend session management and frontend UI rendering
- [ ] Integrate session history with lookup and enforcement features
 
## Cross-Cutting & Non-Functional Requirements
- [ ] Enforce HTTPS-only communication
- [ ] Ensure encrypted storage and transmission of sensitive data
- [ ] Comply with OWASP Top 10 security guidelines
- [ ] Maintain immutable audit logs for all transactions and edits
- [ ] Ensure system performs responsively under roadside conditions
- [ ] Plan for no offline mode support in MVP
